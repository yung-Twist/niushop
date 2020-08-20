<template>
	<view class="poster">
		<view class="poster-wrap">
			<view class="poster-title">智能豪华木头安装视频</view>
			<view class="poster-date">
				<text class="cuIcon-time margin-right-sm lg text-lg"></text>
				2020-10-01 22:30:36
			</view>
			<view class="poster-vedio">
				<image src="http://daiwu668.dianaikeji.com/bgimg/postimg.png" mode=""></image>
			</view>
			<view class="poster-intro">
				内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容
			</view>
			<view class="poster-qrcode">
				<QRcode :width="97" :height="97" text="http://www.baidu.com"/>
			</view>
		</view>
	</view>
</template>

<script>
	import QRcode from '@/components/uQRcode.vue'
	export default {
		data() {
			return {
				
			};
		},
		components:{
			QRcode
		}
	}
</script>

<style lang="scss">
page{
	background-color: #B6CAEB;
}
.poster{
	.poster-wrap{
		width:690upx;
		background:#FFFFFF;
		box-shadow:6upx 9upx 20upx 0upx rgba(39,71,98,0.2);
		border-radius:30upx;
		margin: 30upx;
		padding:50upx 30upx;
		.poster-title{
			font-size:36upx;
			text-align: center;
		}
		.poster-date{
			font-size:24upx;
			color:#9a9a9a;
			margin-top: 40upx;
		}
		.poster-vedio{
			width: 630upx;
			height: 470upx;
			margin: 30upx 0;
			image{
				width: 100%;
				height: 100%;
			}
		}
		.poster-intro{
			text-indent: 2em;
			font-size:28upx;
			color:#9A9A9A;
			line-height:48upx;
		}
		.poster-qrcode{
			width: 240upx;
			height: 240upx;
			background:rgba(182,202,235,1);
			border-radius:30upx;
			margin: 48upx auto;
			display: flex;
			justify-content: center;
			align-items: center;
		}
	}
}
</style>
