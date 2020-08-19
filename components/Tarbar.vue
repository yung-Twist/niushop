<template>
	<view class="customize-tarbar">
		<view class="cu-bar tabbar bg-white">
			<view :class="['action',route == 'pages/index/index' ? 'text-blue' : 'text-gray']" @click="switchPath('/pages/index/index')">
				<view>
					<image v-if="route == 'pages/index/index'" :src="tarbarIcon.homeA" mode="" style="width: 50rpx;height: 50rpx;"></image>
					<image v-else :src="tarbarIcon.home" mode="" style="width: 50rpx;height: 50rpx;"></image>
				</view>
				<text>首页</text>
			</view>
			<view :class="['action',route == 'pages/category/category' ? 'text-blue' : 'text-gray']" @click="switchPath('/pages/category/category')">
				<view>
					<image v-if="route == 'pages/category/category'" :src="tarbarIcon.productA" mode="" style="width: 50rpx;height: 50rpx;"></image>
					<image v-else :src="tarbarIcon.product" mode="" style="width: 50rpx;height: 50rpx;"></image>
				</view>
				<text>分类</text>
			</view>
			<view class="action text-gray add-action" @click="switchPath('/pages/team/team')">
				<button class="cu-btn cuIcon-group_fill bg-blue shadow"></button>
			</view>
			<view :class="['action',route == 'pages/shopCart/shopCart' ? 'text-blue' : 'text-gray']" @click="switchPath('/pages/shopCart/shopCart')">
				<view>
					<image v-if="route == 'pages/shopCart/shopCart'" :src="tarbarIcon.cartA" mode="" style="width: 50rpx;height: 50rpx;"></image>
					<image v-else :src="tarbarIcon.cart" mode="" style="width: 50rpx;height: 50rpx;"></image>
				</view>
				<text>购物车</text>
			</view>
			<view :class="['action',route == 'pages/mine/mine' ? 'text-blue' : 'text-gray']" @click="switchPath('/pages/mine/mine')">
				<view>
					<image v-if="route == 'pages/mine/mine'" :src="tarbarIcon.mineA" mode="" style="width: 50rpx;height: 50rpx;"></image>
					<image v-else :src="tarbarIcon.mine" mode="" style="width: 50rpx;height: 50rpx;"></image>
				</view>
				<text>我的</text>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				tarbarIcon:{
					home:require('@/static/tarbar/home.png'),
					homeA:require('@/static/tarbar/homeA.png'),
					product:require('@/static/tarbar/product.png'),
					productA:require('@/static/tarbar/productA.png'),
					cart:require('@/static/tarbar/cart.png'),
					cartA:require('@/static/tarbar/cartA.png'),
					mine:require('@/static/tarbar/mine.png'),
					mineA:require('@/static/tarbar/mineA.png'),
				}
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

<style lang="scss">
.customize-tarbar{
	position: fixed;
	width: 100vw;
	bottom: 0;
	left: 0;
	z-index: 999;
}
</style>
