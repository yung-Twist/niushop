<template>
	<view class="bargain">
		<image src="../../../static/images/bargainbg.png" mode="" class="bargainbg"></image>
		<view class="bargain-goods-list">
			<!-- 砍价说明 -->
			<view class="bargain-instructions">
				<view class="bargain-instruct-text">砍价说明</view>
				<view class="bargain-instruct-wrap">
					<view class="bargain-instruct-item">
						<view class="instruct-item-num">1</view>
						<view class="instruct-item-num-text">
							<view>选择商品</view>
							<view>发起砍价</view>
						</view>
					</view>
					<view class="bargain-instruct-item">
						<view class="instruct-item-num">2</view>
						<view class="instruct-item-num-text">
							<view>邀请好友</view>
							<view>帮忙砍价</view>
						</view>
					</view><view class="bargain-instruct-item">
						<view class="instruct-item-num">3</view>
						<view class="instruct-item-num-text">
							<view>立即出手</view>
							<view>下单购买</view>
						</view>
					</view>
				</view>
			</view>
			<view class="bargain-goods-item" v-for="(item, index) in bargainList" :key="index">
				<view class="bargain-countdown">
					<CountDown :date="item.endTime"/>
				</view>
				<view class="bargain-goods-image">
					<image :src="item.imagePath" mode=""></image>
				</view>
				<view class="bargain-goods-info">
					<view class="bargain-goods-name">{{item.name}}</view>
					<view class="cu-progress round">
						<view class="bg-blue" :style="[{ width:(item.sale/item.total) * 100 + '%'}]">{{(item.sale/item.total) * 100 + '%'}}</view>
					</view>
					<view class="bargain-origin-price">
						原价：¥{{item.originPrice}}
					</view>
					<view class="bargain-price-buy">
						<view class="bargain-goods-price">
							<text class="bargain-price-text">砍后价：</text>
							<text class="bargain-price">¥{{item.price}}</text>
						</view>
						<button class="cu-btn round bg-blue sm">马上抢</button>
					</view>
				</view>
			</view>
		</view>
	</view>
</template>

<script>
	import CountDown from '@/components/CountDown'
	export default {
		data() {
			return {
				bargainList:[
					{
						imagePath:'http://www.canpro.cn/uploads/products-img/img_5a21182569c69.png',
						name:'CANPRO -黑武士',
						total:100,
						sale:60,
						originPrice:388,
						price:99,
						endTime:'2020-08-28'
					},
					{
						imagePath:'http://www.canpro.cn/uploads/products-img/img_5a21182569c69.png',
						name:'CANPRO -黑武士',
						total:100,
						sale:60,
						originPrice:388,
						price:99,
						endTime:'2020-08-28'
					},
					{
						imagePath:'http://www.canpro.cn/uploads/products-img/img_5a21182569c69.png',
						name:'CANPRO -黑武士',
						total:100,
						sale:60,
						originPrice:388,
						price:99,
						endTime:'2020-08-28'
					}
				]
			};
		},
		components:{
			CountDown
		}
	}
</script>

<style lang="scss">
.bargain{
	position: relative;
	.bargainbg{
		width: 100vw;
		height: 520upx;
	}
	.bargain-goods-list{
		position: absolute;
		top: 490upx;
		z-index: 999;
		left: 30upx;
		.bargain-instructions{
			width:690upx;
			height:214upx;
			background:rgba(191,211,244,1);
			box-shadow:5upx 9upx 20upx 0upx rgba(38,71,98,0.2);
			border-radius:20upx;
			margin-bottom: 40upx;
			padding: 40upx 30upx;
			.bargain-instruct-text{
				font-size:30upx;
				color:rgba(51,51,51,1);
				text-align: center;
				margin-bottom: 40upx;
			}
			.bargain-instruct-wrap{
				display: flex;
				flex-direction: row;
				justify-content: space-between;
				align-items: center;
				.bargain-instruct-item{
					display: flex;
					flex-direction: row;
					align-items: center;
					.instruct-item-num{
						font-size:66upx;
						font-weight:bold;
						font-style:italic;
						color:rgba(42,108,220,1);
						line-height:80upx;
					}
					.instruct-item-num-text{
						display: flex;
						flex-direction: column;
						margin-left: 24upx;
						font-size: 26upx;
					}
				}
			}
		}
		.bargain-goods-item{
			width:690upx;
			height:250upx;
			background:rgba(255,255,255,1);
			box-shadow:5upx 9upx 20upx 0upx rgba(38,71,98,0.2);
			border-radius:20upx;
			display: flex;
			flex-direction: row;
			align-items: center;
			margin-bottom: 40upx;
			position: relative;
			.bargain-countdown{
				position: absolute;
				left: 0;
				top: 0;
				height: 40upx;
				text-align: center;
				background-color: #FF1C00;
				font-size:22upx;
				color:rgba(255,255,255,1);
				line-height:40upx;
				border-radius:20upx 0 ;
				padding: 0 20upx;
			}
			.bargain-goods-image{
				width: 282upx;
				height: 176upx;
				padding: 0 26upx;
				box-sizing: border-box;
				image{
					width: 100%;
					height: 100%;
				}
			}
			.bargain-goods-info{
				border-left: 1px solid rgba(190,190,190,1);
				padding: 0 26upx;
				flex: 1;
				.bargain-goods-name{
				font-size:26upx;
				font-weight:400;
				color:rgba(51,51,51,1);
				line-height:36upx;		
				margin-bottom: 30upx;
				}
				.bargain-origin-price{
					font-size:24upx;
					color:rgba(190,190,190,1);
					margin-top: 20upx;
				}
				.bargain-price-buy{
					display: flex;
					flex-direction: row;
					align-items: center;
					justify-content: space-between;
					// margin-top: 28upx;
					.bargain-goods-price{
						display: flex;
						flex-direction: row;
						align-items: center;
						.bargain-price-text{
							font-size:24upx;
							color:rgba(255,28,0,1);
							line-height:34upx;
						}
						.bargain-price{
							font-size:36upx;
							color:rgba(252,55,31,1);
							line-height:34upx;
						}
					}
				}
			}
		}
	}
}
</style>
