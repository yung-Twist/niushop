<template>
	<view>
		<view class="cart-store">
			<checkbox-group class="block" @change="CheckboxStoreChange">
				<view class="cart-store-item" v-for="(item, index) in cartList" :key="index">
					<view class="cart-store-header">
						<view class="cart-store-left">
							<checkbox class='round blue' :value="index" style="zoom:80%;"></checkbox>
							<image src="../../static/tarabr/storeA.png" mode="" class="store-icon"></image>
							<text class="store-name">{{item.storeName}}</text>
						</view>
						<view class="store-edit">编辑</view>
					</view>
					<view class="cart-store-goods">
						<checkbox-group class="block" @change="CheckboxGoodsChange">
							<view class="cart-store-goods-item" v-for="(item2, idnex2) in item.cartList" :key="index2">
								<checkbox class='round blue' :value="item2.id" style="zoom:80%;"></checkbox>
								<view class="cart-goods-info">
									<image :src="item2.imagePath" mode="" class="cart-goods-image"></image>
									<view class="cart-goods-detail">
										<view class="cart-goods-name">{{item2.name}}</view>
										<view class="cart-goods-spec">{{item2.spec}}</view>
										<view class="cart-goods-price-num">
											<view class="cart-goods-price">￥{{item2.price}}</view>
											<view class="cart-goods-step-num">
												<button class="cu-btn bg-gray margin-tb-sm sm">-</button>
												 <input v-model="item2.num" class="cart-goods-num-input"></input>
												<button class="cu-btn bg-gray margin-tb-sm sm">+</button>
											</view>
										</view>
									</view>
								</view>
							</view>
						</checkbox-group>
					</view>
				</view>
			</checkbox-group>
		</view>
		<Tarbar :route="route"/>
	</view>
</template>

<script>
	import Tarbar from '@/components/Tarbar'
	export default {
		data() {
			return {
				route:null,
				cartList:[
					{
						storeName:'张三李四的店',
						cartList:[
							{
								imagePath:'https://img.yzcdn.cn/vant/apple-2.jpg',
								name:'商品描述商品描述商品描述商品描述商品描述商品描述...',
								spec:'颜色:白色',
								price:6666,
								num:1,
								id:1
							},
							{
								imagePath:'https://cube.elemecdn.com/6/94/4d3ea53c084bad6931a56d5158a48jpeg.jpeg',
								name:'商品描述商品描述商品描述商品描述商品描述商品描述...',
								spec:'颜色:白色',
								price:6666,
								num:2,
								id:2
							}
						]
					},
					{
						storeName:'赵五周六的店',
						cartList:[
							{
								imagePath:'https://img.yzcdn.cn/vant/apple-2.jpg',
								name:'商品描述商品描述商品描述商品描述商品描述商品描述...',
								spec:'颜色:白色',
								price:6666,
								num:1,
								id:3
							},
							{
								imagePath:'https://cube.elemecdn.com/6/94/4d3ea53c084bad6931a56d5158a48jpeg.jpeg',
								name:'商品描述商品描述商品描述商品描述商品描述商品描述...',
								spec:'颜色:白色',
								price:6666,
								num:2,
								id:4
							}
						]
					}
				]
			};
		},
		onShow() {
			let routes = getCurrentPages();
			this.route = routes[routes.length - 1].route
		},
		components:{
			Tarbar
		},
		methods:{
			CheckboxStoreChange(e){
				console.log(e.detail.value)
			},
			CheckboxGoodsChange(e){
				console.log(e.detail.value)
			}
		}
	}
</script>

<style lang="less">
.cart-store{
	padding: 30upx;
	.cart-store-item{
		width:690upx;
		background:rgba(255,255,255,1);
		border-radius:20upx;
		margin-top: 30upx;
		.cart-store-header{
			padding: 20upx;
			display: flex;
			flex-direction: row;
			justify-content: space-between;
			align-items: center;
			border-bottom: 2upx solid #EEEEEE;
			.cart-store-left{
				display: flex;
				flex-direction: row;
				align-items: center;
				.store-icon{
					width: 40upx;
					height: 40upx;
					margin: 0 4upx 0 20upx;
				}
				.store-name{
					font-size:30upx;
					font-weight:400;
					color:rgba(52,52,52,1);
				}
			}
			.store-edit{
				font-size:28upx;
				color:rgba(42,108,220,1);
			}
		}
		.cart-store-goods{
			.cart-store-goods-item{
				padding: 20upx;
				display: flex;
				flex-direction: row;
				align-items: center;
				border-bottom: 2upx solid #EEEEEE;
				.cart-goods-info{
					display: flex;
					flex-direction: row;
					align-items: center;
					.cart-goods-image{
						width: 204upx;
						height: 108upx;
						border-radius:10upx;
						margin:0 20upx;
					}
					.cart-goods-detail{
						.cart-goods-name{
							font-size:26upx;
							line-height:40upx;
						}
						.cart-goods-spec{
							font-size:24upx;
							font-family:PingFang;
							color:rgba(158,158,158,1);
							line-height:42upx
						}
						.cart-goods-price-num{
							display: flex;
							flex-direction: row;
							align-items: center;
							justify-content: space-between;
							.cart-goods-price{
								font-size:24upx;
								color:rgba(255,0,1,1);
								line-height:42upx;
							}
							.cart-goods-step-num{
								display: flex;
								flex-direction: row;
								align-items: center;
								.cart-goods-num-input{
									width: 68upx;
									text-align: center;
								}
							}
						}
					}
				}
			}
		}
	}
}
</style>
