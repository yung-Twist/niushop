<template>
	<view class="customize-tarbar">
		<view class="customize-tarbar-wrap">
			<view class="customize-tarbar-item" @click="switchPath('/pages/index/index')">
				<image v-if="route == 'pages/index/index'" src="../static/tarbar/homeA.png" mode="" class="customize-tarbar-icon"></image>
				<image v-else src="../static/tarbar/home.png" mode="" class="customize-tarbar-icon"></image>
				<text :class="route == 'pages/index/index' ? 'textColorA':'textColor'">首页</text>
			</view>
			<view class="customize-tarbar-item" @click="switchPath('/pages/category/category')">
				<image v-if="route == 'pages/category/category'" src="../static/tarbar/productA.png" mode="" class="customize-tarbar-icon"></image>
				<image v-else src="../static/tarbar/product.png" mode="" class="customize-tarbar-icon"></image>
				<text :class="route == 'pages/category/category' ? 'textColorA':'textColor'">分类</text>
			</view>
			<view class="customize-tarbar-item-center">
				<view class="customize-tarbar-icon-image">
					<image src="../static/tarbar/group.png" mode="" class="customize-tarbar-icon-center"></image>
				</view>
			</view>
			<view class="customize-tarbar-item" @click="switchPath('/pages/shopCart/shopCart')">
				<image v-if="route == 'pages/shopCart/shopCart'" src="../static/tarbar/cartA.png" mode="" class="customize-tarbar-icon"></image>
				<image v-else src="../static/tarbar/cart.png" mode="" class="customize-tarbar-icon"></image>
				<text :class="route == 'pages/shopCart/shopCart' ? 'textColorA':'textColor'">购物车</text>
			</view>
			<view class="customize-tarbar-item" @click="switchPath('/pages/mine/mine')">
				<image v-if="route == 'pages/mine/mine'" src="../static/tarbar/mineA.png" mode="" class="customize-tarbar-icon"></image>
				<image v-else src="../static/tarbar/mine.png" mode="" class="customize-tarbar-icon"></image>
				<text :class="route == 'pages/mine/mine' ? 'textColorA':'textColor'">我的</text>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				// pic:require('@/static/tarbar/home.png')
			};
		},
		props:{
			route:{
				type:String,
				default:'pages/index/index'
			}
		},
		methods:{
			switchPath(path){
				uni.switchTab({
					url:path
				})
			},
			navigatePath(path){
				uni.navigateTo({
					url:path,
					animationType:'fade-in'
				})
			}
		}
		
	}
</script>

<style lang="less">
.customize-tarbar{
	position: fixed;
	width: 100vw;
	bottom: 0;
	left: 0;
	.customize-tarbar-wrap{
		display: flex;
		flex-direction: row;
		justify-content: space-around;
		align-items: center;
		background-color: #FFFFFF;
		.customize-tarbar-item-center{
			width: 126upx;
			height: 100upx;
			position: relative;
			.customize-tarbar-icon-image{
				position: absolute;
				height: 126upx;
				width: 126upx;
				bottom: 12upx;
				background-color: #FFFFFF;
				border-radius: 50%;
				display: flex;
				justify-content: center;
				align-items: center;
				.customize-tarbar-icon-center{
					width: 100upx;
					height: 100upx;
				}
			}
		}
		.customize-tarbar-item{
			display: flex;
			flex-direction: column;
			align-items: center;
			height: 100upx;
			padding: 12upx 0;
			.customize-tarbar-icon{
				width: 50rpx;
				height: 50rpx;
			}
			.textColor{
				font-size:20upx;
				font-weight:400;
				color:rgba(153,153,153,1);
			}
			.textColorA{
				font-size:20upx;
				font-weight:400;
				color:rgba(42,108,220,1);
			}
		}
	}
}
</style>
