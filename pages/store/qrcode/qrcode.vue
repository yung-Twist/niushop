<template>
	<view class="qrcode">
		<view class="qrcode-wrap">
			<view class="qrcode-header">
				<canvas canvas-id="qrcode" style="width: 285px;height: 285px;" />
			</view>
			<view class="qrcode-store-info">
				<image src="https://img-cdn-qiniu.dcloud.net.cn/uploads/avatar/000/09/75/97_avatar_max.jpg" mode=""></image>
				<view class="qrcode-store-name">九牧卫浴的店铺</view>
			</view>
		</view>
		
	</view>
</template>

<script>
	import uQRCode  from '@/utils/uqrcode.js'
	export default {
		data() {
			return {
				
			};
		},
		onShow() {
			this.make()
		},
		methods: {
		    make() {
		      uQRCode.make({
		        canvasId: 'qrcode',
		        componentInstance: this,
		        text: 'http://www.baidu.com',
		        size: 285,
		        margin: 10,
		        backgroundColor: '#ffffff',
		        foregroundColor: '#000000',
		        correctLevel: uQRCode.errorCorrectLevel.H,
		        success: res => {
		          console.log(res)
		        }
		      })
		    }
		}
	}
</script>

<style lang="scss">
	page{
		background:#8EAFE7;
	}
	.qrcode{
		.qrcode-wrap{
			width: 628upx;
			height: 880upx;
			margin: 40upx auto;
			background-color: #FFFFFF;
			position: relative;
			&::before{
				content: '';
				width: 40upx;
				height: 40upx;
				border-radius: 50%;
				position: absolute;
				background-color: #8EAFE7;
				top: 650upx;
				left: -20upx;
			}
			&::after{
				content: '';
				width: 40upx;
				height: 40upx;
				border-radius: 50%;
				position: absolute;
				background-color: #8EAFE7;
				top: 650upx;
				right: -20upx;
			}
			.qrcode-header{
				width: 100%;
				height: 670upx;
				border-bottom: 2upx dotted #F2F2F2;
				display: flex;
				justify-content: center;
				align-items: center;
			}
			.qrcode-store-info{
				width: 100%;
				height: 210upx;
				display: flex;
				flex-direction: column;
				align-items: center;
				justify-content: center;
				image{
					width: 90upx;
					height: 90upx;
					border:2upx solid rgba(42,108,220,1);
					border-radius: 50%;
				}
				.qrcode-store-name{
					font-size:30upx;
					color:#343434;
					margin-top: 25upx;
				}
			}
		}
	}

</style>
