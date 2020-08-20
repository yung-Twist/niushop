<template>
	<view class="goodsDetail">
		<view class="goodsDetail-header">
			<view class="goodsDetail-iamge-big-wrap">
				<image class="goodsDetail-iamge-big" :src="goodsInfo.imageList[imageIndex]" mode=""></image>
			</view>
			<view class="goodsDetail-image-sm-wrap">
				<view class="goodsDetail-image-sm-item" v-for="(item, index) in goodsInfo.imageList" :key="index" @click="changeImage(index)">
					<image class="goodsDetail-iamge-sm" :src="item" mode=""></image>
				</view>
			</view>
		</view>
		<view class="goodsDetail-content">
			<!-- 商品信息 -->
			<view class="goodsDetail-info">
				<view class="goodsDetail-name">商品商品商品商品商品商品商品商品商品商品商品商品商品商品</view>
				<view class="goodsDetail-Postage">快递免邮</view>
				<view class="goodsDetail-price-share">
					<view class="goodsDetail-price">
						<view class="goodsDetail-nowPrice">￥9999</view>
						<view class="goodsDetail-originPrice">￥12000</view>
					</view>
					<view class="goodsDetail-share">
						<text class="margin-right cuIcon-share"></text>
						分享
					</view>
				</view>
			</view>
			<!-- 优惠券 -->
			<view class="goodsDetail-coupon">
				<view class="coupon-info-get">
					<view class="coupon-info">
						<view class="coupon-title-text">优惠券：</view>
						<view class="coupon-title">店铺无门槛十元优惠券</view>
					</view>
					<view class="coupon-get">
						<button class="cu-btn round sm coupon-get-btn text-white">领券</button>
					</view>
				</view>
				<view class="coupon-info-get" style="margin-top: 40upx;">
					<view class="coupon-info">
						<view class="coupon-title-text">满减：</view>
						<view class="coupon-title">满500 减50</view>
					</view>
					<view class="coupon-detail">
						查看
						<text class="margin-left cuIcon-right"></text>
					</view>
				</view>
			</view>
			<!-- 商品店铺 -->
			<view class="goodsDetail-store">
				<view class="goodsDetail-store-left">
					<view class="store-avatar">
						<image src="https://ossweb-img.qq.com/images/lol/web201310/skin/big10001.jpg" mode=""></image>
					</view>
					<view class="store-name-follow">
						<view class="store-name">张三李四的店</view>
						<view class="store-follow">已关注</view>
					</view>
				</view>
				<image class="store-more" src="http://daiwu668.dianaikeji.com/bgimg/right.png"></image>
			</view>
			<!-- 评价 -->
			<view class="goodsDetail-evaluation">
				<view class="evaluation-header">
					<view class="evaluation-text-num">
						<view class="evaluation-text">用户评价</view>
						<view class="evaluation-num">(15)</view>
					</view>
					<view class="evaluation-more">
						查看更多
						<text class="cuIcon-right"></text>
					</view>
				</view>
				<view class="evaluation-content">
					<view class="evaluation-content-header">
						<image class="evaluation-user-avatar" src="https://img-cdn-qiniu.dcloud.net.cn/uploads/avatar/000/09/75/97_avatar_max.jpg"
						 mode=""></image>
						<view class="user-nickname-date">
							<view class="user-nickname">李四王五</view>
							<view class="user-date">2020-05-20 12:26:30</view>
						</view>
					</view>
					<view class="evaluation-content-bottom">
						啊哈哈哈哈哈哈哈哈啊哈哈哈哈哈哈哈哈哈哈哈哈哈啊哈哈哈哈哈哈哈哈
					</view>
				</view>
			</view>
			<!-- 商品详情 -->
			<view class="goodsDetail-intro">
				<view class="intro-header">
					<view :class="active == index ? 'intro-type-itemA' : 'intro-type-item'" v-for="(item, index) in detailType" :key="index"
					 @click="changeType(index)">{{item.title}}</view>
				</view>
				<view class="goodsDetail-intro-content">
					<!-- 商品详情富文本 -->
					<!-- <view v-html=""></view> -->
					商品详情
				</view>
			</view>
		</view>
		<!-- 底部按钮 -->
		<view class="goodsDetail-bottom-btn">
			<view class="cu-bar bg-white tabbar border shop">
				<view class="action">
					<view class="cuIcon-upload">
					</view>
					上架
				</view>
				<view class="action">
					<view class="cuIcon-share">
					</view>
					分享
				</view>
				<view class="add-cart-btn submit text-white">加入购物车</view>
				<view class="buyNow-btn submit text-white">立即订购</view>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				imageIndex: 0,
				goodsInfo: {
					imageList: [
						'http://www.canpro.cn/uploads/products-img/img_5a24b92034743.png',
						'http://www.canpro.cn/uploads/products-img/img_5a21182569c69.png',
						'http://www.canpro.cn/uploads/products-img/img_5a24b92034743.png'
					],
					goodsName: '商品描述商品描述商品描述商品描述商品描述商品描述商品描述商品描述商品描述...',
					Postage: 0, // 邮费
					price: 9999,
					originPrice: 12000,
					store: '张三李四的店'
				},
				detailType: [{
						title: '商品详情'
					},
					{
						title: '售后保障'
					}
				],
				active: '0'
			};
		},
		methods: {
			changeImage(index) {
				this.imageIndex = index
			},
			changeType(index) {
				this.active = index
			}
		}
	}
</script>

<style lang="scss">
	.goodsDetail {
		position: relative;

		.goodsDetail-header {
			width: 100vw;
			height: 770upx;
			background-color: #C0D4F4;

			.goodsDetail-iamge-big-wrap {
				width: 480upx;
				height: 480upx;
				margin: auto;

				.goodsDetail-iamge-big {
					width: 100%;
					height: 100%;
				}
			}

			.goodsDetail-image-sm-wrap {
				width: 480upx;
				display: flex;
				flex-direction: row;
				flex-wrap: nowrap;
				overflow: scroll;
				margin: 50upx auto;

				.goodsDetail-image-sm-item {
					width: 140upx;
					height: 140upx;
					box-sizing: border-box;
					border: 2upx solid #FFFFFF;
					margin-right: 30upx;
					flex-shrink: 0;
					border-radius: 10upx;

					.goodsDetail-iamge-sm {
						width: 100%;
						height: 100%;
					}
				}
			}
		}

		.goodsDetail-content {
			width: 690upx;
			position: absolute;
			top: 700upx;
			left: 30upx;
			padding-bottom: 130upx;

			.goodsDetail-info {
				width: 100%;
				background: #FFFFFF;
				box-shadow: 6upx 9upx 20upx 0upx rgba(39, 71, 98, 0.2);
				border-radius: 20upx;

				.goodsDetail-name {
					padding: 30upx;
					font-size: 30upx;
					font-weight: bold;
				}

				.goodsDetail-Postage {
					padding-left: 30upx;
					font-size: 26upx;
					color: #BEBEBE;
				}

				.goodsDetail-price-share {
					display: flex;
					flex-direction: row;
					align-items: center;
					padding: 30upx 0 30upx 30upx;
					justify-content: space-between;

					.goodsDetail-price {
						display: flex;
						flex-direction: row;
						align-items: center;

						.goodsDetail-nowPrice {
							font-size: 40upx;
							color: #FC3820;
						}

						.goodsDetail-originPrice {
							font-size: 26upx;
							text-decoration: line-through;
							color: #BEBEBE;
							margin-left: 22upx;
						}
					}

					.goodsDetail-share {
						width: 138upx;
						height: 45upx;
						background: $main-color;
						border-radius: 23upx 0upx 0upx 23upx;
						font-size: 22upx;
						color: #FFFFFF;
						line-height: 45upx;
						padding-left: 18upx;

					}
				}
			}

			.goodsDetail-coupon {
				width: 100%;
				background: #FFFFFF;
				box-shadow: 6upx 9upx 20upx 0upx rgba(39, 71, 98, 0.2);
				border-radius: 20upx;
				padding: 30upx;
				margin-top: 30upx;

				.coupon-info-get {
					display: flex;
					justify-content: space-between;
					align-items: center;

					.coupon-info {
						display: flex;
						justify-content: space-between;
						align-items: center;

						.coupon-title-text {
							color: #343434;
							font-size: 26upx;
							font-weight: bold;
						}

						.coupon-title {
							color: $main-color;
							font-size: 26upx;
						}
					}

					.coupon-get {
						.coupon-get-btn {
							background-color: $main-color;
						}
					}

					.coupon-detail {
						font-size: 24upx;
						color: #9A9A9A;
					}
				}
			}

			.goodsDetail-store {
				width: 690upx;
				height: 140upx;
				background: $main-color;
				box-shadow: 6upx 9upx 20upx 0upx rgba(39, 71, 98, 0.2);
				border-radius: 20upx;
				padding: 30upx;
				margin-top: 30upx;
				display: flex;
				flex-direction: row;
				justify-content: space-between;
				align-items: center;

				.goodsDetail-store-left {
					display: flex;
					flex-direction: row;

					.store-avatar {
						width: 100upx;
						height: 100upx;
						border-radius: 50%;
						border: 2upx solid #FFFFFF;
						overflow: hidden;

						image {
							width: 100%;
							height: 100%;
						}
					}

					.store-name-follow {
						margin-left: 22upx;
						display: flex;
						flex-direction: column;
						justify-content: space-between;

						.store-name {
							font-size: 32upx;
							color: #FFFFFF;
						}

						.store-follow {
							width: 94upx;
							height: 34upx;
							background: #FFFFFF;
							border: 2upx solid #FFFFFF;
							border-radius: 17upx;
							font-size: 20upx;
							color: $main-color;
							text-align: center;
							line-height: 34upx;
						}
					}
				}

				.store-more {
					width: 40upx;
					height: 40upx;
				}
			}

			.goodsDetail-evaluation {
				width: 100%;
				background: #FFFFFF;
				box-shadow: 6upx 9upx 20upx 0 rgba(39, 71, 98, 0.2);
				border-radius: 20upx;
				margin-top: 30upx;

				.evaluation-header {
					display: flex;
					flex-direction: row;
					justify-content: space-between;
					align-items: center;
					padding: 35upx 30upx;
					border-bottom: 2upx solid #EEEEEE;

					.evaluation-text-num {
						font-size: 30upx;
						font-weight: bold;
						display: flex;
						align-items: center;

						.evaluation-text {}

						.evaluation-num {
							margin-left: 1em;
						}
					}

					.evaluation-more {
						font-size: 26upx;
						color: #9A9A9A;
					}
				}

				.evaluation-content {
					padding: 30upx;

					.evaluation-content-header {
						display: flex;
						flex-direction: row;
						align-items: center;

						.evaluation-user-avatar {
							width: 70upx;
							height: 70upx;
							border-radius: 50%;
						}

						.user-nickname-date {
							display: flex;
							flex-direction: column;
							margin-left: 24upx;
							justify-content: space-between;

							.user-nickname {
								font-size: 28upx;
								font-family: PingFang;
								font-weight: 500;
							}

							.user-date {
								font-size: 24upx;
								font-family: PingFang;
								font-weight: 500;
								color: #9A9A9A;
							}
						}
					}

					.evaluation-content-bottom {
						margin-top: 30upx;
						font-size: 30upx;
						font-family: PingFang;
					}
				}
			}

			.goodsDetail-intro {
				width: 100%;
				background: #FFFFFF;
				box-shadow: 6upx 9upx 20upx 0 rgba(39, 71, 98, 0.2);
				border-radius: 20upx;
				margin-top: 30upx;

				.intro-header {
					border-bottom: 4upx solid #EEEEEE;
					padding: 22upx 0;
					display: flex;
					flex-direction: row;
					align-items: center;
					justify-content: space-around;

					.intro-type-item {
						font-size: 32upx;
						color: #9A9A9A;
						padding-bottom: 20upx;
						border-bottom: 4upx solid #FFFFFF;
					}

					.intro-type-itemA {
						font-size: 32upx;
						color: $main-color;
						padding-bottom: 20upx;
						border-bottom: 4upx solid $main-color;
					}
				}
			}
		}
		.goodsDetail-bottom-btn{
			width: 100vw;
			position: fixed;
			bottom: 0;
			left: 0;
			.add-cart-btn{
				background:rgba(42,108,220,.5);
			}
			.buyNow-btn{
				background:$main-color;
			}
		}
	}
</style>
