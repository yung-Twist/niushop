<template>
	<view class="team">
		<view class="team-header">
			<view class="team-header-left">
				<view class="team-avatar">
					<image src="https://img-cdn-qiniu.dcloud.net.cn/uploads/avatar/000/09/75/97_avatar_max.jpg" mode=""></image>
				</view>
				<view class="team-info">
					<view class="team-name">张三李四的店</view>
					<view class="team-grade">初级袋客</view>
					<view class="team-grade-next">再消费满500元，可升级为中级袋客</view>
				</view>
			</view>
			<view class="team-qrcode">
				<text class="text-white cuIcon-qrcode"></text>
			</view>
			<view class="team-follwer-member">
				<view class="team-follwer-item">
					<view class="team-item-num">666</view>
					<view class="team-item-text">粉丝</view>
				</view>
				<view class="team-follwer-item">
					<view class="team-item-num">888</view>
					<view class="team-item-text">点赞</view>
				</view>
				<view class="team-follwer-item">
					<view class="team-item-num">666</view>
					<view class="team-item-text">关注</view>
				</view>
			</view>
		</view>
		<view class="team-content">
			<ModuleTitle2 title="个人成绩"/>
			<view class="team-grade">
				<view class="grade-item">
					<view class="grade-item-title">待付款</view>
					<view class="grade-item-num">50</view>
				</view>
				<view class="grade-item">
					<view class="grade-item-title">待收货</view>
					<view class="grade-item-num">50</view>
				</view>
				<view class="grade-item">
					<view class="grade-item-title">已成交</view>
					<view class="grade-item-num">150</view>
				</view>
				<view class="grade-item">
					<view class="grade-item-title">已评价</view>
					<view class="grade-item-num">150</view>
				</view>
				<view class="grade-item">
					<view class="grade-item-title">售后/退款</view>
					<view class="grade-item-num">15</view>
				</view>
				<view class="grade-item">
					<view class="grade-item-title">我的团队</view>
					<view class="grade-item-num">50</view>
				</view>
				<view class="grade-item">
					<view class="grade-item-title">可提现佣金</view>
					<view class="grade-item-num">5555</view>
				</view>
				<view class="grade-item">
					<view class="grade-item-title">待审核佣金</view>
					<view class="grade-item-num">1000</view>
				</view>
				<view class="grade-item">
					<view class="grade-item-title">累计佣金</view>
					<view class="grade-item-num">6666</view>
				</view>
				<view class="grade-item">
					<view class="grade-item-title">进行中佣金</view>
					<view class="grade-item-num">2000</view>
				</view>
			</view>
			<ModuleTitle2 title="团队成绩"/>
			<view class="team-grade">
				<view class="grade-item">
					<view class="grade-item-title">待付款</view>
					<view class="grade-item-num">50</view>
				</view>
				<view class="grade-item">
					<view class="grade-item-title">待收货</view>
					<view class="grade-item-num">50</view>
				</view>
				<view class="grade-item">
					<view class="grade-item-title">已成交</view>
					<view class="grade-item-num">150</view>
				</view>
				<view class="grade-item">
					<view class="grade-item-title">已评价</view>
					<view class="grade-item-num">150</view>
				</view>
				<view class="grade-item">
					<view class="grade-item-title">售后/退款</view>
					<view class="grade-item-num">15</view>
				</view>
				<view class="grade-item">
					<view class="grade-item-title">我的团队</view>
					<view class="grade-item-num">50</view>
				</view>
				<view class="grade-item">
					<view class="grade-item-title">可提现佣金</view>
					<view class="grade-item-num">5555</view>
				</view>
				<view class="grade-item">
					<view class="grade-item-title">待审核佣金</view>
					<view class="grade-item-num">1000</view>
				</view>
				<view class="grade-item">
					<view class="grade-item-title">累计佣金</view>
					<view class="grade-item-num">6666</view>
				</view>
				<view class="grade-item">
					<view class="grade-item-title">进行中佣金</view>
					<view class="grade-item-num">2000</view>
				</view>
				<view class="grade-item">
					<view class="grade-item-title">初级袋客</view>
					<view class="grade-item-num">50</view>
				</view>
				<view class="grade-item">
					<view class="grade-item-title">中级袋客</view>
					<view class="grade-item-num">50</view>
				</view>
				<view class="grade-item">
					<view class="grade-item-title">高级袋客</view>
					<view class="grade-item-num">50</view>
				</view>
				<view class="grade-item">
					<view class="grade-item-title">黄金袋客</view>
					<view class="grade-item-num">50</view>
				</view>
				<view class="grade-item">
					<view class="grade-item-title">钻石袋客</view>
					<view class="grade-item-num">50</view>
				</view>
			</view>
			<ModuleTitle2 title="袋客工具"/>
			<view class="tools-list">
				<view class="tools-item" v-for="(item, index) in toolList" :key="index" :style="{background:item.bgColor}">
					<image :src="item.iconPath" mode=""></image>
					<text>{{item.name}}</text>
				</view>
			</view>
		</view>
		<Tarbar :route="route"/>
	</view>
</template>

<script>
	import Tarbar from '@/components/Tarbar.vue'
	import ModuleTitle2 from '@/components/ModuleTitle2.vue'
	export default {
		data() {
			return {
				route:null,
				toolList:[
					{
						id:1,
						name:'我的店铺',
						iconPath:require('@/static/images/store.png'),
						bgColor:'#94B5ED'
					},
					{
						id:2,
						name:'店铺设置',
						iconPath:require('@/static/images/setting.png'),
						bgColor:'#D4E2F8'
					},
					{
						id:3,
						name:'二维码',
						iconPath:require('@/static/images/qrcode.png'),
						bgColor:'#D5D6F0'
					},
					{
						id:4,
						name:'我的订单',
						iconPath:require('@/static/images/storeorder.png'),
						bgColor:'#D4E2F8'
					},
					{
						id:5,
						name:'我的团队',
						iconPath:require('@/static/images/storeteam.png'),
						bgColor:'#94B5ED'
					},
					{
						id:6,
						name:'我的佣金',
						iconPath:require('@/static/images/money.png'),
						bgColor:'#F5E6E3'
					},
					{
						id:7,
						name:'进行中佣金',
						iconPath:require('@/static/images/moneying.png'),
						bgColor:'#D5D6F0'
					},
					{
						id:8,
						name:'佣金提现',
						iconPath:require('@/static/images/recharge.png'),
						bgColor:'#D4E2F8'
					},
					{
						id:9,
						name:'投诉建议',
						iconPath:require('@/static/images/complaint.png'),
						bgColor:'#D5D6F0'
					},
					{
						id:10,
						name:'专属客服',
						iconPath:require('@/static/images/service.png'),
						bgColor:'#D4E2F8'
					},
					{
						id:11,
						name:'合伙人规则',
						iconPath:require('@/static/images/rule.png'),
						bgColor:'#94B5ED'
					},
					{
						id:12,
						name:'素材百科',
						iconPath:require('@/static/images/encyclopedia.png'),
						bgColor:'#D4E2F8'
					}
					
				]
			};
		},
		components:{
			Tarbar,
			ModuleTitle2
		},
		onLoad() {
			let routes = getCurrentPages();
			this.route = routes[routes.length - 1].route
		},
	}
</script>

<style lang="scss">
.team{
	.team-header{
		width: 100vw;
		height:300upx;
		background:$main-color;
		box-shadow:6upx 9upx 20upx 0 rgba(39,71,98,0.2);
		border-radius:0upx 0upx 30upx 30upx;
		display: flex;
		flex-direction: row;
		justify-content: space-between;
		padding: 40upx 30upx;
		position: relative;
		.team-header-left{
			display: flex;
			flex-direction: row;
			.team-avatar{
				border: 2upx solid #FFFFFF;
				width: 100upx;
				height: 100upx;
				border-radius: 50%;
				overflow: hidden;
				image{
					width: 100%;
					height: 100%;
				}
			}
			.team-info{
				display: flex;
				flex-direction: column;
				margin-left: 20upx;
				.team-name{
					font-size:32upx;
					color:#FFFFFF;
					font-weight: bold;
				}
				.team-grade{
					width: 110upx;
					height: 34upx;
					background:rgba(255,255,255,.6);
					border-radius:17upx;
					font-size:20upx;
					color:$main-color;
					text-align: center;
					line-height: 34upx;
					margin: 20upx 0 26upx ;
				}
				.team-grade-next{
					font-size:24upx;
					color:#FFFFFF;
				}
			}
		}
		.team-qrcode{
			font-size: 70upx;
		}
		.team-follwer-member{
			position: absolute;
			width:690upx;
			height:120upx;
			background:#FFFFFF;
			box-shadow:6upx 9upx 20upx 0upx rgba(39,71,98,0.2);
			border-radius:20upx;
			bottom: -54upx;
			left: 30upx;
			display: flex;
			justify-content: space-around;
			align-items: center;
			.team-follwer-item{
				display: flex;
				flex-direction: column;
				align-items: center;
				.team-item-num{
					font-size:34upx;
					color:#343434;
				}
				.team-item-text{
					font-size:22upx;
					color:#9A9A9A;
				}
				&:nth-child(2){
					position: relative;
					&::after{
						content: '';
						position: absolute;
						width:2upx;
						height:44upx;
						background:#DCDCDC;
						border-radius:1px;
						left: -88upx;
						top: 0;
						bottom: 0;
						margin: auto;
					}
					&::before{
						content: '';
						position: absolute;
						width:2upx;
						height:44upx;
						background:#DCDCDC;
						border-radius:1px;
						right: -88upx;
						top: 0;
						bottom: 0;
						margin: auto;
					}
				}
			}
		}
		
	}
	.team-content{
		padding: 0 30upx;
		margin-top: 84upx;
		.team-grade{
			width:690upx;
			background:#FFFFFF;
			box-shadow:6upx 9upx 20upx 0 rgba(39,71,98,0.2);
			border-radius:20upx;
			display: grid;
			grid-template-columns: repeat(5,138upx);
			margin: 30upx 0;
			.grade-item{
				display: flex;
				flex-direction: column;
				justify-content: center;
				align-items: center;
				width: 138upx;
				height: 138upx;
				.grade-item-title{
					font-size:22upx;
					color:#9A9A9A;
				}
				.grade-item-num{
					font-size:30upx;
					color:#FF0000;
					margin-top: 20upx;
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
</style>
