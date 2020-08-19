<template>
	<view class="storeSetting">
		<view class="store-setting-name">
			<view class="store-name">店铺名称</view>
			<input placeholder="请输入店铺名称" v-model="form.storeName"></input>
		</view>
		<view class="store-setting-image">
			<view class="store-image-bg">店铺背景图</view>
			<view class="store-image-upload" @click="chooseImage">
				<image :src="form.storeImage" mode=""></image>
			</view>
		</view>
		<view class="store-image-btn">
			<button class="cu-btn round btnstyle ">保存信息</button>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				form:{
					storeName:'九牧卫浴旗舰店',
					storeImage:'https://ss1.bdstatic.com/70cFuXSh_Q1YnxGkpoWK1HF6hhy/it/u=2939026885,456927682&fm=26&gp=0.jpg'
				}
			};
		},
		methods:{
			chooseImage(){
				let that = this
				uni.chooseImage({
				    success: (chooseImageRes) => {
				        const tempFilePaths = chooseImageRes.tempFilePaths;
						that.form.storeImage = tempFilePaths[0]
				        // uni.uploadFile({
				        //     url: 'https://www.example.com/upload', //仅为示例，非真实的接口地址
				        //     filePath: tempFilePaths[0],
				        //     name: 'file',
				        //     formData: {
				        //         'user': 'test'
				        //     },
				        //     success: (uploadFileRes) => {
				        //         console.log(uploadFileRes.data);
				        //     }
				        // });
				    }
				})
			}
		}
	}
</script>

<style lang="scss">
	page{
		background-color: #FFFFFF;
	}
.storeSetting{
	padding: 30upx;
	.store-setting-name{
		display: flex;
		flex-direction: row;
		align-items: center;
		justify-content: space-between;
		padding-bottom: 35upx;
		border-bottom: 2upx solid #EEEEEE;
		.store-name{
			font-size:30upx;
			font-weight:bold;
			color:#0D0D0D;
		}
		input{
			text-align: right;
			font-size:30upx;
			color:rgba(52,52,52,1);
		}
	}
	.store-setting-image{
		.store-image-bg{
			font-size:30upx;
			font-weight:bold;
			color:#0D0D0D;
			margin: 35upx 0;
		}
		.store-image-upload{
			image{
				width: 690upx;
				height: 690upx;
				border-radius:30upx;
			}
		}
	}
	.store-image-btn{
		margin-top: 90upx;
		text-align: center;
		.btnstyle{
			width: 500upx;
			height: 90upx;
			background-color: $main-color;
			font-size:30upx;
			color:#FFFFFF;
			box-shadow:1upx 10upx 20upx 0 rgba(42,108,220,0.3);
		}
	}
}
</style>
