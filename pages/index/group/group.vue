<template>
	<view class="group">
		<image src="http://daiwu668.dianaikeji.com/bgimg/groupbg.png" mode="" class="groupbg"></image>
		<view class="group-goods-list">
			<!-- 拼团说明 -->
			<view class="group-instructions">
				<view class="group-instruct-text">拼团说明</view>
				<view class="group-instruct-wrap">
					<view class="group-instruct-item">
						<image src="http://daiwu668.dianaikeji.com/bgimg/opengroup.png" mode=""></image>
						<view class="group-instruct-item-text">
							开团/参团
						</view>
					</view>
					<view class="group-instruct-item">
						<image src="http://daiwu668.dianaikeji.com/bgimg/order.png" mode=""></image>
						<view class="group-instruct-item-text">
							填写订单付款
						</view>
					</view><view class="group-instruct-item">
						<image src="http://daiwu668.dianaikeji.com/bgimg/groupfill.png" mode=""></image>
						<view class="group-instruct-item-text">
							人满成团
						</view>
					</view>
				</view>
			</view>
			<view class="group-goods-item" v-for="(item, index) in groupList" :key="index">
				<view class="group-countdown">
					<!-- <CountDown :date="item.endTime"/> -->
					秒杀团
				</view>
				<view class="group-goods-image">
					<image :src="item.imagePath" mode=""></image>
				</view>
				<view class="group-goods-info">
					<view class="group-goods-name">{{item.name}}</view>
					<view class="group-goods-tag">
						<view class='cu-tag round light bg-blue sm'>已抢3件</view>
						<view class='cu-tag round light line-blue sm'>5人团</view>
						<view class='cu-tag round light line-blue sm'>包邮</view>
					</view>
					<view class="group-price-buy">
						<view class="group-goods-price">
							<text class="group-price-text">砍后价：</text>
							<text class="group-price">¥{{item.price}}</text>
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
				groupList:[
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
.group{
	position: relative;
	.groupbg{
		width: 100vw;
		height: 520upx;
	}
	.group-goods-list{
		position: absolute;
		top: 490upx;
		z-index: 999;
		left: 30upx;
		.group-instructions{
			width:690upx;
			height:214upx;
			background:rgba(191,211,244,1);
			box-shadow:5upx 9upx 20upx 0upx rgba(38,71,98,0.2);
			border-radius:20upx;
			margin-bottom: 40upx;
			padding: 40upx 30upx;
			.group-instruct-text{
				font-size:30upx;
				color:rgba(51,51,51,1);
				text-align: center;
				margin-bottom: 20upx;
			}
			.group-instruct-wrap{
				display: flex;
				flex-direction: row;
				justify-content: space-between;
				align-items: center;
				.group-instruct-item{
					display: flex;
					flex-direction: row;
					align-items: center;
					image{
						width: 40upx;
						height: 40upx;
					}
					.group-instruct-item-text{
						font-size:26upx;
						color:rgba(52,52,52,1);
						line-height:38px;
					}
				}
			}
		}
		.group-goods-item{
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
			.group-countdown{
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
			.group-goods-image{
				width: 282upx;
				height: 176upx;
				padding: 0 26upx;
				box-sizing: border-box;
				image{
					width: 100%;
					height: 100%;
				}
			}
			.group-goods-info{
				border-left: 1px solid rgba(190,190,190,1);
				padding: 0 26upx;
				flex: 1;
				.group-goods-name{
				font-size:26upx;
				font-weight:400;
				color:rgba(51,51,51,1);
				line-height:36upx;		
				margin-bottom: 30upx;
				}
				.group-price-buy{
					display: flex;
					flex-direction: row;
					align-items: center;
					justify-content: space-between;
					margin-top: 28upx;
					.group-goods-price{
						display: flex;
						flex-direction: row;
						align-items: center;
						.group-price-text{
							font-size:24upx;
							color:rgba(255,28,0,1);
							line-height:34upx;
						}
						.group-price{
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
