<template>
	<view class="favorites">
		<view class="favorite-type-wrap">
			<view :class="active == item.id ? 'favorite-type-itemA':'favorite-type-item'" v-for="(item, index) in favoriteTypeList" :key="index" @click="changeTabs(item)">
				{{item.title}}
			</view>
		</view>
		<view class="favorite-goods-wrap">
			<view class="favorite-goods-item" v-for="(item, index) in goodsList" :key="index">
				<view class="favorite-goods-store">
					<image src="../../../static/tarbar/storeA.png" mode=""></image>
					<view class="store-name">
						{{item.storeName}}
					</view>
				</view>
				<view class="favorite-goods-info">
					<image :src="item.imagePath" mode=""></image>
					<view class="favorite-goods-name-price">
						<view class="goods-name">{{item.name}}</view>
						<view class="goods-price">¥{{item.price}}</view>
					</view>
				</view>
			</view>
		</view>
		<Empty v-if="favoriteTypeList.length == 0"/>
	</view>
</template>

<script>
	import Empty from '@/components/Empty.vue'
	export default {
		data() {
			return {
				active:'1',
				favoriteTypeList:[
					{
						title:'宝贝',
						id:1
					},
					{
						title:'店铺',
						id:2
					}
				],
				goodsList:[
					{
						imagePath:'http://www.canpro.cn/uploads/products-img/img_5a21182569c69.png',
						name:'商品描述商品描述商品描述商品描述商品描述商品描述...',
						storeName:'张三李四的店',
						price:6666
					},
					{
						imagePath:'http://www.canpro.cn/uploads/products-img/img_5a21182569c69.png',
						name:'商品描述商品描述商品描述商品描述商品描述商品描述...',
						storeName:'张三李四的店',
						price:6666
					},
					{
						imagePath:'http://www.canpro.cn/uploads/products-img/img_5a21182569c69.png',
						name:'商品描述商品描述商品描述商品描述商品描述商品描述...',
						storeName:'张三李四的店',
						price:6666
					}
				]
			};
		},
		components:{
			Empty
		},
		methods:{
			changeTabs(item){
				this.active = item.id
			}
		}
	}
</script>

<style lang="scss">
.favorites{
	.favorite-type-wrap{
		display: flex;
		flex-direction: row;
		align-items: center;
		width: 100%;
		overflow-x: scroll;
		padding: 46upx 30upx;
		background-color: #FFFFFF;
		.favorite-type-item{
			font-size:26upx;
			color:#999999;
			line-height:25upx;
			opacity:0.5;
			margin-right: 54upx;
			padding-bottom: 14upx;
			white-space: nowrap;
		}
		.favorite-type-itemA{
			font-size:30upx;
			font-weight:bold;
			color:$main-color;
			line-height: 25upx;
			margin-right: 54upx;
			white-space: nowrap;
			padding-bottom: 16upx;
			border-bottom: 6upx solid $main-color;
		}
	}
	.favorite-goods-wrap{
		padding: 30upx;
		.favorite-goods-item{
			width:690upx;
			height:348upx;
			background:#FFFFFF;
			border-radius:20upx;
			margin-bottom: 30upx;
			.favorite-goods-store{
				padding: 30upx;
				display: flex;
				align-items: center;
				border-bottom: 2upx solid #EEEEEE;
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
			.favorite-goods-info{
				display: flex;
				flex-direction: row;
				align-items: center;
				padding: 30upx;
				padding-bottom: 0;
				image{
					width: 204upx;
					height: 180upx;
				}
				.favorite-goods-name-price{
					flex: 1;
					display: flex;
					flex-direction: column;
					justify-content: space-between;
					height: 180upx;
					padding-left: 30upx;
					.goods-name{
						font-size:26upx;
						color:#333333;
					}
					.goods-price{
						font-size:36upx;
						color:#ff0000;
					}
				}
			}
		}
	}
}
</style>
