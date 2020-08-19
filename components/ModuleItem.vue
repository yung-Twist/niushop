<template>
	<view class="module-product">
		<view class="module-product-Item">
			<image :src="imagePath" mode="" class="product-image"></image>
			<view class="product-name">{{name}}</view>
			<view class="product-info">
				<text class="product-info-item">产地：{{origin}}</text>
				<text class="product-info-item">材质：{{material}}</text>
				<text class="product-info-item">功能：{{features}}</text>
			</view>
			<view class="product-increase" @click="increaseGoods">
				添加商品
				<text class="sm text-sm cuIcon-right"></text>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {};
		},
		props: {
			imagePath: String,
			name: String,
			origin: String,
			material: String,
			features: String,
		},
		methods:{
			increaseGoods(){
				this.$emit('increaseGoods')
			}
		}
	}
</script>

<style lang="scss">
	.module-product {
		.module-product-Item {
			margin-top: 30upx;
			width: 100%;
			padding: 67upx 80upx 30upx 67upx;
			background: rgba(255, 255, 255, 1);
			box-shadow: 6upx 9upx 20upx 0upx rgba(39, 71, 98, 0.2);
			border-radius: 20upx;

			.product-image {
				width: 530upx;
				height: 480upx;
			}

			.product-name {
				margin-top: 47upx;
				font-size: 34upx;
				font-weight: bold;
				color: rgba(52, 52, 52, 1);
			}

			.product-info {
				margin-top: 71upx;
				display: flex;
				flex-direction: column;

				.product-info-item {
					margin-bottom: 27upx;
					font-size: 28upx;

					font-weight: 400;
					color: rgba(154, 154, 154, 1);
				}
			}
			.product-increase{
				width: 100%;
				text-align: right;
				color: $main-color;
				font-size: 30upx;
			}
		}
	}
</style>
