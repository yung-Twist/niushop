<template>
	<view class="product">
		<view class="product-header">
			<view class="product-category-wrap">
				<view :class="active == item.id ? 'product-category-itemA':'product-category-item'" v-for="(item, index) in productCategoryList" :key="index" @click="changeTabs(item)">
					{{item.title}}
				</view>
			</view>
		</view>
		<view class="product-content">
			<view class="product-goods-list">
				<view class="product-goods-item" v-for="(item, index) in productList" :key="index" :style="{background:item.color}">
					<view :class="['product-goods-intro',index % 2 == 0 ? 'positionLeft' : 'positionRight']">
						<view class="product-goods-name">{{item.name}}</view>
						<view class="goods-info">
							<text class="goods-info-item">产地：{{item.origin}}</text>
							<text class="goods-info-item">材质：{{item.material}}</text>
							<text class="goods-info-item">功能：{{item.features}}</text>
						</view>
						<view class="product-detail">了解详情</view>
					</view>
					<view :class="['product-goods-image',index % 2 == 0 ? 'positionRight' : 'positionLeft']">
						<image :src="item.imagePath" mode=""></image>
					</view>
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
				productCategoryList:[
					{
						id:0,
						title:'全部'
					},
					{
						id:1,
						title:'马桶盖'
					},
					{
						id:2,
						title:'正装马桶'
					},
					{
						id:3,
						title:'热水器'
					},
					{
						id:4,
						title:'喷头'
					},
					{
						id:5,
						title:'肥皂'
					},
					{
						id:6,
						title:'马桶'
					}
				],
				productList:[
					{
						imagePath:'http://www.canpro.cn/uploads/products-img/img_5a21182569c69.png',
						name:'CANPRO -黑武士',
						origin:'厦门',
						material:' 高密度陶瓷+PP抗菌',
						features:'全自动翻盖、一体式挂壁智能马桶',
						color:'#D4E2F8',
						price:6666
					},
					{
						imagePath:'http://www.canpro.cn/uploads/products-img/img_5a21182569c69.png',
						name:'CANPRO -黑武士',
						origin:'厦门',
						material:' 高密度陶瓷+PP抗菌',
						features:'全自动翻盖、一体式挂壁智能马桶',
						color:'#F5E6E3',
						price:8888
					},
					{
						imagePath:'http://www.canpro.cn/uploads/products-img/img_5a21182569c69.png',
						name:'CANPRO -黑武士',
						origin:'厦门',
						material:' 高密度陶瓷+PP抗菌',
						features:'全自动翻盖、一体式挂壁智能马桶',
						color:'#D5D6F0',
						price:6868
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
.product{
	position: relative;
	.product-header{
		width: 100vw;
		height: 190upx;
		background:$main-color;
		box-shadow:1upx 10upx 20upx 0upx rgba(42,108,220,0.3);
		border-radius:0upx 0upx 30upx 30upx;
		.product-category-wrap{
			display: flex;
			flex-direction: row;
			align-items: center;
			width: 100%;
			overflow-x: scroll;
			padding: 46upx 30upx;
			.product-category-item{
				font-size:26upx;
				color:#FFFFFF;
				line-height:25upx;
				opacity:0.5;
				margin-right: 54upx;
				padding-bottom: 14upx;
				white-space: nowrap;
			}
			.product-category-itemA{
				font-size:30upx;
				color:#FFFFFF;
				font-weight:bold;
				color:#FFFFFF;
				line-height: 25upx;
				margin-right: 54upx;
				white-space: nowrap;
				padding-bottom: 16upx;
				border-bottom: 6upx solid #FFFFFF;
			}
		}
	}
	.product-content{
		width: 690upx;
		position: absolute;
		left: 30upx;
		top: 100upx;
		.product-goods-list{
			.product-goods-item{
				height: 340upx;
				display: flex;
				flex-direction: row;
				align-items: center;
				box-shadow:5upx 9upx 20upx 0upx rgba(38,71,98,0.2);
				border-radius:30upx;
				margin-top: 50upx;
				position: relative;
				.product-goods-intro{
					width: 380upx;
					display: flex;
					flex-direction: column;
					position: absolute;
					top: 30upx;
					.product-goods-name{
						font-size:34upx;
						font-weight:bold;
						color:#333;
					}
					.goods-info{
						margin-top: 30upx;
						display: flex;
						flex-direction: column;
						.product-info-item{
							margin-bottom: 27upx;
							font-size:24upx;
							color:rgba(102,102,102,1);
						}
					}
					.product-detail{
						font-size:24upx;
						width:150upx;
						height:40upx;
						background:rgba(148,182,237,1);
						border-radius:10px;
						color: #FFFFFF;
						text-align: center;
						line-height: 40upx;
						margin-top: 20upx;
					}
				}
				.product-goods-image{
					width: 230upx;
					height: 324upx;
					position: absolute;
					top: -30upx;
					image{
						width: 100%;
						height: 100%;
						
					}
				}
				.positionLeft{
					left: 30upx;
				}
				.positionRight{
					right: 30upx;
				}
			}
		}
	}
}
</style>
