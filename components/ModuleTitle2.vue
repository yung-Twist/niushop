<template>
	<view class="module2-tag">
		<image src="http://daiwu668.dianaikeji.com/bgimg/tagImg.png" mode="" class="modu2-imagebg"></image>
		<text class="module2-goods">{{title}}</text>
	</view>
</template>

<script>
	export default {
		data() {
			return {

			};
		},
		props:{
			title:String
		}
	}
</script>

<style lang="scss">
	.module2-tag {
		border-radius: 43upx;
		background: rgba(42, 108, 220, .2);
		position: relative;
		height: 86upx;

		.modu2-imagebg {
			position: absolute;
			width: 336upx;
			height: 20upx;
			left: 177upx;
			top: 34upx;
		}

		.module2-goods {
			position: absolute;
			left: 280upx;
			top: 23upx;
			font-size: 33upx;
			font-weight: bold;
			color: rgba(42, 108, 220, 1);
		}
	}
</style>
