<template>
	<view class="second">
		<image src="../../../static/images/secondbg.png" mode="" class="secondbg"></image>
		<view class="second-goods-list">
			<view class="second-goods-item" v-for="(item, index) in secondList" :key="index">
				<view class="second-countdown">
					<CountDown :date="item.endTime"/>
				</view>
				<view class="second-goods-image">
					<image :src="item.imagePath" mode=""></image>
				</view>
				<view class="second-goods-info">
					<view class="second-goods-name">{{item.name}}</view>
					<view class="cu-progress round">
						<view class="bg-blue" :style="[{ width:(item.sale/item.total) * 100 + '%'}]">{{(item.sale/item.total) * 100 + '%'}}</view>
					</view>
					<view class="second-price-buy">
						<view class="second-goods-price">
							<text class="second-price-text">秒杀价：</text>
							<text class="second-price">¥{{item.price}}</text>
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
				secondList:[
					{
						imagePath:'http://www.canpro.cn/uploads/products-img/img_5a21182569c69.png',
						name:'CANPRO -黑武士',
						total:100,
						sale:60,
						price:99,
						endTime:'2020-08-28'
					},
					{
						imagePath:'http://www.canpro.cn/uploads/products-img/img_5a21182569c69.png',
						name:'CANPRO -黑武士',
						total:100,
						sale:60,
						price:99,
						endTime:'2020-08-28'
					},
					{
						imagePath:'http://www.canpro.cn/uploads/products-img/img_5a21182569c69.png',
						name:'CANPRO -黑武士',
						total:100,
						sale:60,
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

<style lang="less">
.second{
	position: relative;
	.secondbg{
		width: 100vw;
		height: 382upx;
	}
	.second-goods-list{
		position: absolute;
		top: 340upx;
		z-index: 999;
		left: 30upx;
		.second-goods-item{
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
			.second-countdown{
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
			.second-goods-image{
				width: 282upx;
				height: 176upx;
				padding: 0 26upx;
				box-sizing: border-box;
				image{
					width: 100%;
					height: 100%;
				}
			}
			.second-goods-info{
				border-left: 1px solid rgba(190,190,190,1);
				padding: 0 26upx;
				flex: 1;
				.second-goods-name{
				font-size:26upx;
				font-weight:400;
				color:rgba(51,51,51,1);
				line-height:36upx;		
				margin-bottom: 30upx;
				}
				.second-price-buy{
					display: flex;
					flex-direction: row;
					align-items: center;
					justify-content: space-between;
					margin-top: 28upx;
					.second-goods-price{
						display: flex;
						flex-direction: row;
						align-items: center;
						.second-price-text{
							font-size:24upx;
							color:rgba(255,28,0,1);
							line-height:34upx;
						}
						.second-price{
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
