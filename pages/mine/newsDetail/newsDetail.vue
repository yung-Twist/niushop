<template>
	<view class="newsDetail">
		<view class="newsDetail-header">
			<image src="http://daiwu668.dianaikeji.com/bgimg/newsbg.png" mode=""></image>
		</view>
		<view class="newsDetail-content">
			<view class="newsDetail-Info">
				<view class="newsDetail-title">智能豪华木桶安装视频</view>
				<view class="newsDetail-date">2018/10/20</view>
				<view class="newsDetail-tip">做漂亮而且好用的东西是一个我们的终极使命！</view>
			</view>
			<view class="newsDetail-content-text">
				内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容
			</view>
			<view class="newsDetail-btn">
				<button class="cu-btn round btnstyle "
				@click="createPoster">海报生成</button>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				
			};
		},
		methods:{
			createPoster(){
				uni.navigateTo({
					url:'/pages/store/poster/poster'
				})
			}
		}
	}
</script>

<style lang="scss">
.newsDetail{
	position: relative;
	.newsDetail-header{
		width: 100vw;
		height: 560upx;
		image{
			width: 100%;
			height: 100%;
		}
	}
	.newsDetail-content{
		width: 690upx;
		position: absolute;
		top: 490upx;
		left: 30upx;
		.newsDetail-Info{
			width: 100%;
			height: 222upx;
			background:#B6CAEB;
			box-shadow:6upx 9upx 20upx 0 rgba(39,71,98,0.2);
			border-radius:30upx;
			padding: 40upx 30upx;
			display: flex;
			flex-direction: column;
			justify-content: space-between;
			.newsDetail-title{
				font-size:32upx;
				color:#222222;
			}
			.newsDetail-date{
				font-size:24upx;
				color:#9A9A9A;
			}
			.newsDetail-tip{
				font-size:28upx;
				color:#666666;
			}
		}
		.newsDetail-content-text{
			width:690upx;
			background:#FFFFFF;
			box-shadow:6upx 9upx 20upx 0px rgba(39,71,98,0.2);
			border-radius:30upx;
			margin-top: 30upx;
			padding: 30upx 30upx 78upx 30upx;
			font-size:28upx;
			color:#9A9A9A;
			line-height:48upx;
		}
		.newsDetail-btn{
			text-align: center;
			position: absolute;
			bottom: -45upx;
			left: 0;
			right: 0;
			margin: auto;
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
}

</style>
