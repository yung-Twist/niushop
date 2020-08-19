<template>
	<view class="moduleTitle">
		<image class="module-title-bg" :style="{width:width+'rpx',height:height+'rpx'}" :src="imagePath"></image>
		<view class="module-title-text">
			<view class="title-line"></view>
			<view class="title-point"></view>
			<view class="title-text">{{title}}</view>
			<view class="title-point"></view>
			<view class="title-line"></view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
			};
		},
		props:{
			title:String,
			imagePath:String,
			width:{
				type:Number,
				default:659
			},
			height:{
				type:Number,
				default:74
			}
		}
	}
</script>

<style lang="scss">
	.moduleTitle {
		width:100%;
		height:180upx;
		border-radius:30upx;
		margin: 40upx 0;
		position: relative;
		.module-title-bg {
			position: absolute;
			left: 0;
			right: 0;
			margin: auto;
			top: 73upx;
		}

		.module-title-text {
			position: absolute;
			width: 659upx;
			height: 74upx;
			left: 15upx;
			top: 73upx;
			display: flex;
			flex-direction: row;
			align-items: center;
			justify-content: center;

			.title-line {
				width: 45upx;
				height: 6upx;
				background: $main-color;
				margin: 0 25upx;
			}

			.title-point {
				width: 14upx;
				height: 14upx;
				background: $main-color;
				border-radius: 50%;
			}

			.title-text {
				font-size: 51upx;
				font-weight: bold;
				font-style: italic;
				color: $main-color;
				margin: 0 50upx;
			}
		}
	}
</style>
