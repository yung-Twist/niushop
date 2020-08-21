<template>
	<view class="offerShare">
		<view class="offerShare-content">
			<view class="offerShare-user-name">
				<view class="user-name-text">客户名称</view>
				<view class="user-name">张先生</view>
			</view>
			<view class="offerShare-user-name">
				<view class="user-name-text">手机账号</view>
				<view class="user-name">13898989898</view>
			</view>
			<view class="offerShare-images" >
				<view class="images-upload" @click="uploadImage">+</view>
				<image class="offerShare-image-item" :src="item" mode="" v-for="(item, index) in shareImageList" :key="index"></image>
			</view>
			<view class="offerShare-user-name">
				<view class="user-name-text">商品总价</view>
				<view class="user-name-text">￥8888.00</view>
			</view>
			<view class="offerShare-user-name">
				<view class="user-name-text">成本总价</view>
				<view class="user-name-text">￥8888.00</view>
			</view>
			<view class="offerShare-user-name">
				<view class="user-name-text">总价折扣</view>
				<view class="discount-right">
					<button class="cu-btn line-blue" style="margin-right: 1em;">85</button>
					折
				</view>
			</view>
			<view class="offerShare-user-name">
				<view class="user-name-text">最终价格</view>
				<view class="user-name-text">￥8888.00</view>
			</view>
			<view class="offerShare-user-name">
				<view class="user-name-text">获得佣金</view>
				<view class="user-name-text">￥8888.00</view>
			</view>
		</view>
		<view class="offerShare-tips">
			<text class="text-blue">提示：</text>修改折扣会影响您最终成交获得的佣金，最终价格最低不得超过成本总价
		</view>
		<view class="offerShare-btn">
			<button class="cu-btn round btnstyle ">生成报价图</button>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				shareImageList:[]
			};
		},
		methods:{
			uploadImage(){
				let that = this
				uni.chooseImage({
				    success: (chooseImageRes) => {
				        const tempFilePaths = chooseImageRes.tempFilePaths;// 图片数组
						that.shareImageList = [...that.shareImageList, ...tempFilePaths]
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
.offerShare{
	.offerShare-content{
		background-color: #FFFFFF;
		.offerShare-user-name{
			height: 100upx;
			border-bottom: 2upx solid #EEEEEE;
			display: flex;
			padding: 0 30upx;
			flex-direction: row;
			justify-content: space-between;
			align-items: center;
			.user-name-text{
				font-size:30upx;
			}
			.user-name{
				font-size:30upx;
				color:$main-color;
			}
		}
		.offerShare-images{
			padding: 30upx;
			display: flex;
			flex-direction: row;
			align-items: center;
			overflow-x: scroll;
			border-bottom: 2upx solid #EEEEEE;
			.images-upload{
				width: 100upx;
				height: 100upx;
				line-height: 100upx;
				text-align: center;
				border:2upx solid #DCDCDC;
				border-radius:2upx;
				font-size: 40upx;
				color: #DCDCDC;
				margin-right:30upx;
				flex-shrink: 0;
			}
			.offerShare-image-item{
				width: 100upx;
				height: 100upx;
				margin-right:30upx;
				flex-shrink: 0;
			}
		}
	}
	.offerShare-tips{
		font-size:24upx;
		padding: 30upx;
		color: #999999;
		line-height: 40upx;
	}
	.offerShare-btn{
		margin-top: 60upx;
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
