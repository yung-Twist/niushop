<template>
	<view class="integralstore">
		<image src="../../../static/images/integralbg.png" mode="" class="integralbg"></image>
		<view class="integral-content">
			<view class="integral-userInfo">
				<view class="userInfo-detail">
					<view class="userInfo-avatar">
						<open-data type="userAvatarUrl"></open-data>
					</view>
					<view class="userInfo-nickname">
						<open-data type="userNickName"></open-data>
						<text>我的积分：6868</text>
					</view>
				</view>
				<view class="integral-desc">
					积分说明
				</view>
			</view>
			<view class="integral-tag">
				<image src="../../../static/images/tagImg.png" mode=""></image>
				<text class="integral-goods">积分兑换</text>
			</view>
			<!-- 积分商品 -->
			<view class="integral-goods-list">
				<view class="integral-goods-item" v-for="(item, index) in productList" :key="index" :style="{background:item.color}">
					<view :class="['intergral-goods-intro',index % 2 == 0 ? 'positionLeft' : 'positionRight']">
						<view class="intergral-goods-name">{{item.name}}</view>
						<view class="goods-info">
							<text class="goods-info-item">产地：{{item.origin}}</text>
							<text class="goods-info-item">材质：{{item.material}}</text>
							<text class="goods-info-item">功能：{{item.features}}</text>
						</view>
						<view class="intergral-price" :style="{color:index % 2 == 0 ? '#2A6CDC' : '#FF0000'}">{{item.price}}积分</view>
					</view>
					<view :class="['intergral-goods-image',index % 2 == 0 ? 'positionRight' : 'positionLeft']">
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
		}
	}
</script>

<style lang="scss">
.integralstore{
	position: relative;
	.integralbg{
		width: 100vw;
		height: 332upx;
	}
	.integral-content{
		width: 690upx;
		position: absolute;
		left: 30upx;
		top: 300upx;
		.integral-userInfo{
			display: flex;
			flex-direction: row;
			align-items: center;
			justify-content: space-between;
			padding: 25upx 0;
			background:rgba(255,255,255,1);
			box-shadow:0upx 3upx 4upx 0upx rgba(40,95,240,0.15);
			border-radius:20upx;
			padding-left: 30upx;
			.userInfo-detail{
				display: flex;
				flex-direction: row;
				align-items: center;
				.userInfo-avatar{
					width: 100upx;
					height: 100upx;
					border-radius: 50%;
					overflow: hidden;
					border: 2upx solid #2A6CDC;
				}
				.userInfo-nickname{
					display: flex;
					flex-direction: column;
					justify-content: center;
					font-size:32upx;
					margin-left: 20upx;
					text{
						font-size:24upx;
						color:rgba(153,153,153,1);
						margin-top: 18upx;
					}
				}
			}
			.integral-desc{
				width:138upx;
				height:45upx;
				background:#2A6CDC;
				border-radius:23upx 0upx 0upx 23upx;
				font-size:22upx;
				color:rgba(255,255,255,1);
				line-height:45upx;
				text-align: center;
			}
		}
		.integral-tag{
			border-radius:43upx;
			background:rgba(42,108,220,.2);
			position: relative;
			height: 86upx;
			margin-top: 30upx;
			image{
				position: absolute;
				width: 336upx;
				height: 20upx;
				left: 177upx;
				top: 34upx;
			}
			.integral-goods{
				position: absolute;
				left: 280upx;
				top: 23upx;
				font-size:33upx;
				font-weight:bold;
				color:rgba(42,108,220,1);
			}
		}
		.integral-goods-list{
			.integral-goods-item{
				height: 340upx;
				display: flex;
				flex-direction: row;
				align-items: center;
				box-shadow:5upx 9upx 20upx 0upx rgba(38,71,98,0.2);
				border-radius:30upx;
				margin-top: 50upx;
				position: relative;
				.intergral-goods-intro{
					width: 380upx;
					display: flex;
					flex-direction: column;
					position: absolute;
					top: 30upx;
					.intergral-goods-name{
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
					.intergral-price{
						font-size:36upx;
						margin-top: 20upx;
					}
				}
				.intergral-goods-image{
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
