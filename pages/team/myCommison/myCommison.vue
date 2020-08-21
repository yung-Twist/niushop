<template>
	<view class="commissioning">
		<view class="commission-header">
			<view class="commission-detail">明细</view>
			<view style="font-size: 24upx;color: #FFFFFF;text-align: center;">可提现佣金金额</view>
			<view class="commission-money">￥500.00</view>
			<view class="commission-type">
				<view class="commission-type-item">
					<view class="commission-type-name">累计佣金</view>
					<view class="commission-type-count">600</view>
				</view>
				<view class="commission-type-item">
					<view class="commission-type-name">待审核佣金</view>
					<view class="commission-type-count">600</view>
				</view>
				<view class="commission-type-item">
					<view class="commission-type-name">已提现佣金</view>
					<view class="commission-type-count">600</view>
				</view>
			</view>
			<view class="commission-promote">
				<view class="commission-promote-title">推广商</view>
				<view class="commission-promote-money">
					<view class="promote-money-text">推广佣金</view>
					<view class="promote-money-num">￥0.00<text class="text-gray cuIcon-right" style="margin-left: 1em;"></text></view>
				</view>
			</view>
			<view class="commission-btn">
				<button class="cu-btn round btnstyle " @click="toRecharge">申请提现</button>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				
			};
		},
		methods:{
			toRecharge(){
				uni.navigateTo({
					url:'/pages/team/recharge/recharge'
				})
			}
		}
	}
</script>

<style lang="scss">
.commissioning{
	.commission-header{
		width:750upx;
		height:320upx;
		background:$main-color;
		.commission-detail{
			padding: 30upx 30upx 12upx;
			text-align: right;
			font-size:28upx;
			color:#FFFFFF;
		}
		.commission-money{
			font-size:60upx;
			color:#FFFFFF;
			text-align: center;
			margin-top: 30upx;
		}
		.commission-type{
			width:690upx;
			height:150upx;
			margin-left: 30upx;
			background:#FFFFFF;
			border-radius:30upx;
			display: flex;
			flex-direction: row;
			align-items: center;
			justify-content: space-around;
			margin-top: 30upx;
			.commission-type-item{
				height: 100%;
				display: flex;
				flex-direction: column;
				align-items: center;
				justify-content: center;
				.commission-type-name{
					font-size:26upx;
					color:#333333;
				}
				.commission-type-count{
					font-size:36upx;
					color:$main-color;
					margin-top: 21upx;
				}
				&:nth-child(2){
					position: relative;
					&::after{
						content: '';
						position: absolute;
						width:4upx;
						height:70upx;
						background:#DCDCDC;
						border-radius:1px;
						left: -49upx;
						top: 0;
						bottom: 0;
						margin: auto;
					}
					&::before{
						content: '';
						position: absolute;
						width:4upx;
						height:70upx;
						background:#DCDCDC;
						border-radius:1px;
						right: -49upx;
						top: 0;
						bottom: 0;
						margin: auto;
					}
				}
			}
		}
		.commission-promote{
			width:690upx;
			// height:180upx;
			margin: 30upx;
			padding: 30upx;
			background:#FFFFFF;
			border-radius:30upx;
			.commission-promote-title{
				font-size:30upx;
				color:#333333;
				padding-bottom: 28upx;
				border-bottom: 2upx solid #EEEEEE;
			}
			.commission-promote-money{
				font-size:28upx;
				color:#333333;
				display: flex;
				justify-content: space-between;
				padding-top: 28upx;
			}
		}
		.commission-btn{
			margin-top: 300upx;
			text-align: center;
			.btnstyle{
				width: 500upx;
				height: 90upx;
				background-color: $main-color;
				font-size:30upx;
				color:#FFFFFF;
				box-shadow:1upx 10upx 20upx 0 rgba(42,108,220,0.3);
			}
		}
	}
}
</style>
