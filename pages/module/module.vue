<template>
	<view class="module">
		<view class="module-wrap">
			<view class="module-item" v-for="(item, index) in dataList" :key="index">
				<view class="module-item-left">
					<image :src="item.imagePaht" class="module-item-image" mode=""></image>
					<view class="module-image-title">{{item.title}}</view>
				</view>
				<image class="module-item-right" src="http://daiwu668.dianaikeji.com/bgimg/moduleright.png" mode=""></image>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				dataList:[
					{
						title:'产品 · 分享',
						imagePaht:'http://daiwu668.dianaikeji.com/bgimg/shareProduct.png'
					},
					{
						title:'素材 · 百科',
						imagePaht:'http://daiwu668.dianaikeji.com/bgimg/sucaibaike.png'
					},
					{
						title:'店铺 · 管理',
						imagePaht:'http://daiwu668.dianaikeji.com/bgimg/stroremanage.png'
					},
					{
						title:'个人 · 团队',
						imagePaht:'http://daiwu668.dianaikeji.com/bgimg/personalteam.png'
					}
				]
			};
		}
	}
</script>

<style lang="scss">
	page{
		background: url('http://daiwu668.dianaikeji.com/bgimg/modulebg.png') no-repeat;
		background-size: 100% 100%;
	}
.module{
	position: relative;
	.module-wrap{
		position: absolute;
		top: 440upx;
		left: 30upx;
		.module-item{
			width:690upx;
			height:150upx;
			background:#FFFFFF;
			box-shadow:0upx 2upx 10upx 0upx rgba(71,73,78,0.2);
			border-radius:30upx;
			display: flex;
			flex-direction: row;
			align-items: center;
			justify-content: space-between;
			padding: 30upx;
			margin-top: 30upx;
			.module-item-left{
				display: flex;
				flex-direction: row;
				align-items: center;
				.module-item-image{
					width: 97upx;
					height: 97upx;
				}
				.module-image-title{
					font-size:30upx;
					color:#333333;
					margin-left: 30upx;
				}
			}
			.module-item-right{
				width: 40upx;
				height: 40upx;
			}
		}
	}
}
</style>
