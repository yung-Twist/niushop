<template>
	<view>
		<view class="category">
			<!-- 昨边分类 -->
			<view class="category-left">
				<view :class="active == item.id ? 'category-itemA' : 'category-item'" v-for="(item, index) in categoryList" :key="index" @click="changeCategory(item)">
					<text>{{item.title}}</text>
				</view>
			</view>
			<!-- 右边商品 -->
			<view class="category-right">
				<view class="category-product-item" v-for="(item, index) in categoryProductList" :key="index">
					<view class="item-header" :style="{'background-color':item.bgcolor}">
						<text class="product-title">{{item.title}}</text>
						<text class="product-name">{{item.name}}</text>
						<image :src="item.imagePath" mode="" class="product-image"></image>
					</view>
					<view class="product-introduction">{{item.introduction}}</view>
					<view class="item-footer">
						<view class="product-price"><text>￥</text>{{item.price}}</view>
						<view class="moreBtn">了解详情</view>
					</view>
				</view>
			</view>
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
				active:1,
				categoryList:[
					{
						id:1,
						title:'热门推荐'
					},
					{
						id:2,
						title:'新品首发'
					},
					{
						id:3,
						title:'促销单品'
					},
					{
						id:4,
						title:'拼团专区'
					}
				],
				categoryProductList:[
					{
						imagePath:require('@/static/images/product.png'),
						title:'CANPRO -黑武士',
						name:'全自动垃圾处理器',
						introduction:'产品描述产品描述产品描述产品描述产品描述产品描述产品描述',
						price:6666,
						bgcolor:'#D4E2F8'
					},
					{
						imagePath:require('@/static/images/product.png'),
						title:'CANPRO -黑武士',
						name:'全自动垃圾处理器',
						introduction:'产品描述产品描述产品描述产品描述产品描述产品描述产品描述',
						price:6666,
						bgcolor:'#F5E6E3'
					},
					{
						imagePath:require('@/static/images/product.png'),
						title:'CANPRO -黑武士',
						name:'全自动垃圾处理器',
						introduction:'产品描述产品描述产品描述产品描述产品描述产品描述产品描述',
						price:6666,
						bgcolor:'#D6D6F0'
					}
				]
			};
		},
		methods:{
			changeCategory(item){
				this.active = item.id
			}
		},
		onLoad() {
			let routes = getCurrentPages();
			this.route = routes[routes.length - 1].route
		},
		components:{
			Tarbar
		},
	}
</script>

<style lang="scss">
	page{
		background-color: #FFFFFF;
	}
.category{
	.category-left{
		width: 198upx;
		height: 100vh;
		position: fixed;
		left: 0;
		overflow-y: scroll;
		padding-bottom: calc(var(--window-bottom) + 126upx);
		background-color: rgba(220,220,220,.2);
		.category-item{
			width: 100%;
			display: flex;
			flex-direction: column;
			height: 88upx;
			text-align: center;
			line-height: 88upx;
			color: #343434;
			font-size:28upx;
			font-weight:400;
			color:rgba(52,52,52,1);
		}
		.category-itemA{
			width: 100%;
			display: flex;
			flex-direction: column;
			height: 88upx;
			text-align: center;
			line-height: 88upx;
			background-color: #FFFFFF;
			font-size:28upx;
			font-weight:400;
			color:rgba(42,108,220,1);
			position: relative;
			&::after {
			    content: "";
			    width: 6upx;
			    height: 60upx;
			    position: absolute;
			    background-color: rgba(42,108,220,1);
			    top: 0;
			    left: 0upx;
			    bottom: 0;
			    margin: auto;
			  }
		}
	}
	.category-right{
		width: 552upx;
		position: fixed;
		right: 0;
		padding: 0 31upx;
		height: 100vh;
		overflow-y: scroll;
		padding-bottom: calc(var(--window-bottom) + 126upx);
		.category-product-item{
			width: 491upx;
			background:rgba(255,255,255,1);
			box-shadow:6upx 9upx 20upx 0upx rgba(39,71,98,0.2);
			border-radius:20upx;
			margin-top: 86upx;
			.item-header{
				position: relative;
				display: flex;
				flex-direction: column;
				padding: 38upx 29upx;
				border-radius:20upx;
				.product-title{
					font-size:30upx;
					font-weight:bold;
					color:rgba(52,52,52,1);
				}
				.product-name{
					font-size:26upx;
					font-weight:400;
					color:rgba(52,52,52,1);
				}
				.product-image{
					width: 151upx;
					height: 205upx;
					position: absolute;
					right: 37upx;
					top: -56upx;
				}
			}
			.product-introduction{
				margin-top: 30upx;
				font-size:24upx;
				font-weight:400;
				color:rgba(102,102,102,1);
				line-height:36upx;
				padding: 0 29upx;
			}
			.item-footer{
				display: flex;
				flex-direction: row;
				align-items: center;
				justify-content: space-between;
				margin-top: 40upx;
				padding: 0 29upx 38upx;
				.product-price{
					font-size:24upx;
					font-weight:400;
					color:rgba(255,0,0,1);
				}
				.moreBtn{
					width: 140upx;
					height: 40upx;
					background-color: #94B6ED;
					box-shadow:6upx 9upx 20upx 0upx rgba(39,71,98,0.2);
					border-radius:20upx;
					font-size:24upx;
					font-weight:400;
					color:rgba(255,255,255,1);
					text-align: center;
					line-height: 40upx;
				}
			}
		}
	}
}
</style>
