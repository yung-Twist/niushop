<template>
	<view class="orderList">
		<view class="order-type-wrap">
			<view :class="active == item.id ? 'order-type-itemA':'order-type-item'" v-for="(item, index) in orderTypeList" :key="index" @click="changeTabs(item)">
				{{item.title}}
			</view>
		</view>
		<view class="order-goods-wrap">
			<view class="order-goods-item" v-for="(item, index) in goodsList" :key="index">
				<view class="order-store-header">
					<view class="order-goods-store">
						<image src="../../../static/tarbar/storeA.png" mode=""></image>
						<view class="store-name">
							{{item.storeName}}
						</view>
					</view>
					<view class="order-status">待支付</view>
				</view>
				<!-- 订单商品 -->
				<view class="order-goods-info" v-for="(item2, index2) in item.goodsList" :key="index2">
					<image :src="item2.imagePath" mode=""></image>
					<view class="order-goods-name-price">
						<view class="goods-name">{{item2.name}}</view>
						<view class="goods-spec">{{item2.spec}}</view>
						<view class="goods-price-num">
							<view class="goods-price">¥{{item2.price}}</view>
							<view class="goods-num">X{{item2.num}}</view>
						</view>
					</view>
				</view>
				<view class="order-item-bottom">
					<button class="cu-btn round line-grey margin-sm">关闭订单</button>
					<button class="cu-btn round bg-blue margin-sm">去支付</button>
				</view>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				active:'0',
				orderTypeList:[
					{
						id:0,
						title:'全部',
					},
					{	id:1,
						title:'待付款',
					},
					{	id:2,
						title:'待发货',
					},
					{	id:3,
						title:'待收货',
					},
					{	id:4,
						title:'已完成'
					},
					{	id:5,
						title:'退款/售后'
					},
					{
						id:6,
						title:'待评价'
					}
				],
				goodsList:[
					{
						storeName:'张三李四的店',
						orderPrice:6666,
						goodsList:[
							{
								imagePath:'http://www.canpro.cn/uploads/products-img/img_5a21182569c69.png',
								name:'商品描述商品描述商品描述商品描述商品描述商品描述...',
								price:6666,
								spec:'颜色：白色',
								num:1,
							},
							{
								imagePath:'http://www.canpro.cn/uploads/products-img/img_5a21182569c69.png',
								name:'商品描述商品描述商品描述商品描述商品描述商品描述...',
								price:6666,
								spec:'颜色：白色',
								num:1,
							}
						]
						
					},
					{
						storeName:'张三李四的店',
						orderPrice:6666,
						goodsList:[
							{
								imagePath:'http://www.canpro.cn/uploads/products-img/img_5a21182569c69.png',
								name:'商品描述商品描述商品描述商品描述商品描述商品描述...',
								price:6666,
								spec:'颜色：白色',
								num:1,
							},
							{
								imagePath:'http://www.canpro.cn/uploads/products-img/img_5a21182569c69.png',
								name:'商品描述商品描述商品描述商品描述商品描述商品描述...',
								price:6666,
								spec:'颜色：白色',
								num:1,
							}
						]
					}
				]
			};
		},
		methods:{
			changeTabs(item){
				this.active = item.id
			}
		}
	}
</script>

<style lang="scss">
.orderList{
	.order-type-wrap{
		display: flex;
		flex-direction: row;
		align-items: center;
		width: 100%;
		overflow-x: scroll;
		padding: 20upx 30upx;
		background-color: #FFFFFF;
		.order-type-item{
			font-size:26upx;
			color:#999999;
			line-height:25upx;
			opacity:0.5;
			margin-right: 54upx;
			padding-bottom: 14upx;
			white-space: nowrap;
		}
		.order-type-itemA{
			font-size:30upx;
			color:$main-color;
			line-height: 25upx;
			margin-right: 54upx;
			white-space: nowrap;
			padding-bottom: 16upx;
			border-bottom: 4upx solid $main-color;
		}
	}
	.order-goods-wrap{
		padding: 30upx;
		.order-goods-item{
			width:690upx;
			background:#FFFFFF;
			border-radius:20upx;
			margin-bottom: 30upx;
			.order-store-header{
				display: flex;
				justify-content: space-between;
				align-items: center;
				border-bottom: 2upx solid #EEEEEE;
				.order-goods-store{
					padding: 30upx;
					display: flex;
					align-items: center;
					image{
						width: 40upx;
						height: 40upx;
					}
					.store-name{
						color: #333333;
						font-size:30upx;
						margin-left: 17upx;
					}
				}
				.order-status{
					font-size:28upx;
					color:$main-color;
					padding-right: 30upx;
				}
			}
			.order-goods-info{
				display: flex;
				flex-direction: row;
				align-items: center;
				padding: 30upx;
				border-bottom: 2upx solid #EEEEEE;
				&::last-child{
					border-bottom: 0;
				}
				image{
					width: 204upx;
					height: 180upx;
				}
				.order-goods-name-price{
					flex: 1;
					display: flex;
					flex-direction: column;
					height: 180upx;
					justify-content: space-between;
					padding-left: 30upx;
					.goods-name{
						font-size:26upx;
						color:#333333;
					}
					.goods-spec{
						font-size:24upx;
						color:#9e9e9e;
					}
					.goods-price-num{
						display: flex;
						flex-direction: row;
						justify-content: space-between;
						align-items: center;
						.goods-price{
							font-size:36upx;
							color:#ff0000;
						}
						.goods-num{
							font-size:26upx;
							color:#9a9a9a;
						}
					}
				}
			}
			.order-item-bottom{
				width: 100%;
				text-align: right;
			}
		}
	}
}
</style>
