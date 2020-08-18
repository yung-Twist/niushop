<template>
	<view class="mine">
		<view class="mine-header">
			<view class="mine-userInfo">
				<view class="mine-userInfo-left">
					<open-data type="userNickName"></open-data>
					<view class="mine-userInfo-menberType">普通会员</view>
				</view>
				<view class="mine-userInfo-setting">
					<image src="../../static/images/setting.png" mode=""></image>
				</view>
			</view>
			<view class="userInfo-phone">1335856233</view>
			<view class="userInfo-avatar">
				<open-data type="userAvatarUrl"></open-data>
			</view>
			<view class="userInfo-assets">
				<view class="userInfo-assets-item">
					<view class="assets-item-num">200</view>
					<view class="assets-item-text">余额</view>
				</view>
				<view class="userInfo-assets-item">
					<view class="assets-item-num">450</view>
					<view class="assets-item-text">积分</view>
				</view>
				<view class="userInfo-assets-item">
					<view class="assets-item-num">6</view>
					<view class="assets-item-text">优惠券</view>
				</view>
			</view>
		</view>
		<view class="mine-content">
			<!-- 我的订单 -->
			<view class="mine-order">
				<view class="mine-order-title">
					<text>我的订单</text>
					<image src="../../static/images/right.png" mode=""></image>
				</view>
				<view class="mine-order-type-wrap">
					<view class="mine-order-type-item" v-for="(item, index) in orderType" :key="index">
						<view class="order-type-image">
							<image :src="item.iconPath" mode=""></image>
							<view class="order-type-badge" v-if="item.badge > 0">{{item.badge}}</view>
						</view>
						<view class="order-type-text">{{item.title}}</view>
					</view>
				</view>
			</view>
			<!-- 常用工具 -->
			<view class="mine-commontools">
				<view class="commontools-title">
					<image class="commontools-title-bg" src="../../static/images/Common%20tools.png"></image>
					<view class="commontools-title-text">
						<view class="title-line"></view>
						<view class="title-point"></view>
						<view class="title-text">常用工具</view>
						<view class="title-point"></view>
						<view class="title-line"></view>
					</view>
				</view>
				<!-- 常用工具列表 -->
				<view class="tools-list">
					<view class="tools-item" v-for="(item, index) in toolList" :key="index" :style="{background:item.bgColor}">
						<image :src="item.iconPath" mode=""></image>
						<text>{{item.name}}</text>
					</view>
				</view>
			</view>
			<view class="block" style="height: 10vh;"></view>
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
				orderType:[
					{
						title:'待付款',
						iconPath:require('@/static/images/waitpay.png'),
						badge:3
					},
					{
						title:'待发货',
						iconPath:require('@/static/images/waitsend.png'),
						badge:0
					},
					{
						title:'待收货',
						iconPath:require('@/static/images/waitreceipt.png'),
						badge:0
					},
					{
						title:'待评价',
						iconPath:require('@/static/images/waitevaluation.png'),
						badge:0
					},
					{
						title:'退款/售后',
						iconPath:require('@/static/images/refund.png'),
						badge:3
					}
				],
				toolList:[
					{
						id:1,
						name:'签到',
						iconPath:require('@/static/images/sign.png'),
						bgColor:'#94B5ED'
					},
					{
						id:2,
						name:'收藏',
						iconPath:require('@/static/images/star.png'),
						bgColor:'#D4E2F8'
					},
					{
						id:3,
						name:'个人资料',
						iconPath:require('@/static/images/userInfo.png'),
						bgColor:'#D5D6F0'
					},
					{
						id:4,
						name:'收货地址',
						iconPath:require('@/static/images/address.png'),
						bgColor:'#D4E2F8'
					},
					{
						id:5,
						name:'积分商城',
						iconPath:require('@/static/images/integralstore.png'),
						bgColor:'#94B5ED'
					},
					{
						id:6,
						name:'我的拼团',
						iconPath:require('@/static/images/mygroup.png'),
						bgColor:'#F5E6E3'
					},
					{
						id:7,
						name:'我的秒杀',
						iconPath:require('@/static/images/mysecond.png'),
						bgColor:'#D5D6F0'
					},
					{
						id:8,
						name:'我的砍价',
						iconPath:require('@/static/images/mybargain.png'),
						bgColor:'#D4E2F8'
					},
					{
						id:9,
						name:'客服中心',
						iconPath:require('@/static/images/service.png'),
						bgColor:'#D5D6F0'
					},
					{
						id:10,
						name:'百科',
						iconPath:require('@/static/images/baike.png'),
						bgColor:'#D4E2F8'
					},
					{
						bgColor:'#94B5ED'
					},
					{
						bgColor:'#D4E2F8'
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
		}
	}
</script>

<style lang="less">
.mine{
	position: relative;
	.mine-header{
		width: 750upx;
		height: 720upx;
		background:#FFFFFF;
		.mine-userInfo{
			padding: 0 28upx 0 62upx;
			display: flex;
			flex-direction: row;
			align-items: center;
			justify-content: space-between;
			.mine-userInfo-left{
				display: flex;
				flex-direction: row;
				align-items: center;
				font-size:40upx;
				font-weight:bold;
				color:#333333;
				line-height:40upx;
				.mine-userInfo-menberType{
					background:#2A6CDC;
					border-radius:20upx;
					font-size:22upx;
					color:#FFFFFF;
					font-weight:400;
					line-height:44upx;
					padding: 0 20upx;
					margin-left: 24upx;
				}
			}
			.mine-userInfo-setting{
				image{
					width: 40upx;
					height: 40upx;
				}
			}
		}
		.userInfo-phone{
			padding-left: 62upx;
			font-size:28upx;
			font-weight:400;
			color:#666666;
			margin-top: 20upx;
		}
		.userInfo-avatar{
			margin-left: 50upx;
			margin-top: 38upx;
			width: 180upx;
			height: 180upx;
			border-radius: 50%;
			border: 4upx solid #2A6CDC;
			overflow: hidden;
			image{
				width: 100%;
				height: 100%;
			}
		}
		.userInfo-assets{
			padding: 0 80upx;
			display: flex;
			flex-direction: row;
			justify-content: space-between;
			align-items: center;
			margin-top: 50upx;
			.userInfo-assets-item{
				display: flex;
				flex-direction: column;
				align-items: center;
				.assets-item-num{
					font-size:48upx;
					color:#2A6CDC;
				}
				.assets-item-text{
					font-size:24upx;
					color:#333333;
					margin-top: 20upx;
				}
			}
		}
	}
	.mine-content{
		position: absolute;
		top: 520upx;
		width: 100vw;
		padding: 30upx;
		.mine-order{
			width: 100%;
			height:262upx;
			background:#2A6CDC;
			box-shadow:0 10upx 20upx 0upx rgba(42,108,220,0.3);
			border-radius:10upx;
			.mine-order-title{
				display: flex;
				flex-direction: row;
				align-items: center;
				justify-content: space-between;
				text{
					font-size:28upx;
					color: #FFFFFF;
					margin-left: 56upx;
				}
				image{
					width: 40upx;
					height: 40upx;
					margin: 18upx;
				}
			}
			.mine-order-type-wrap{
				display: flex;
				flex-direction: row;
				justify-content: space-around;
				align-items: center;
				padding: 30upx 0;
				margin-top: 30upx;
				.mine-order-type-item{
					display: flex;
					flex-direction: column;
					justify-content: center;
					align-items: center;
					.order-type-image{
						width: 56upx;
						height: 56upx;
						position: relative;
						image{
							width: 100%;
							height: 100%;
						}
						.order-type-badge{
							width: 30upx;
							height: 30upx;
							position: absolute;
							right: -10upx;
							top: -10upx;
							background:#FFFFFF;
							border-radius:50%;
							font-size:20upx;
							color:#2A6CDC;
							line-height:30upx;
							text-align: center;
						}
					}
					.order-type-text{
						font-size:24upx;
						color: #FFFFFF;
						margin-top: 14upx;
					}
				}
			}
		}
		.mine-commontools{
			width: 100%;
			.commontools-title{
				width:690upx;
				height:220upx;
				background:rgba(148,181,237,1);
				box-shadow:0upx 10upx 20upx 0upx rgba(42,108,220,0.3);
				border-radius:30upx;
				margin: 40upx 0;
				position: relative;
				.commontools-title-bg{
					position: absolute;
					width: 659upx;
					height: 74upx;
					left: 15upx;
					top: 73upx;
				}
				.commontools-title-text{
					position: absolute;
					width: 659upx;
					height: 74upx;
					left: 15upx;
					top: 73upx;
					display: flex;
					flex-direction: row;
					align-items: center;
					justify-content: center;
					.title-line{
						width:45upx;
						height:6upx;
						background:#2B6FDD;
						margin: 0 25upx;
					}
					.title-point{
						width:14upx;
						height:14upx;
						background:#2B6FDD;
						border-radius:50%;
					}
					.title-text{
						font-size:51upx;
						font-weight:bold;
						font-style:italic;
						color:#2B6FDD;
						margin: 0 50upx;
					}
				}
			}
			.tools-list{
				width: 690upx;
				display: grid;
				grid-template-columns: repeat(3,230upx);
				grid-template-rows: repeat(4,230upx);
				background:rgba(212,226,248,1);
				box-shadow:1upx 10upx 20upx 0upx rgba(42,108,220,0.3);
				border-radius:30upx;
				overflow: hidden;
				.tools-item{
					display: flex;
					flex-direction: column;
					justify-content: center;
					align-items: center;
					image{
						width: 70upx;
						height: 70upx;
					}
					text{
						font-size:24upx;
						color:rgba(52,52,52,1);
					}
				}
			}
		}
	}
}
</style>
