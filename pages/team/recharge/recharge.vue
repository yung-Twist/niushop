<template>
	<view class="recharge">
		<view class="recharge-header">
			<view class="recharge-commission-item">
				<view class="recharge-text">可提现佣金金额</view>
				<view class="recharge-money">￥500.00</view>
			</view>
			<view class="recharge-commission-item">
				<view class="recharge-text">佣金总金额</view>
				<view class="recharge-money">￥500.00</view>
			</view>
		</view>
		<view class="recharge-content">
			<view class="recharge-type">
				<view class="recharge-type-left">
					<view class="recharge-type-text">提款方式：</view>
					<view class="recharge-type-select">提现到余额</view>
				</view>
				<image class="recharge-right" src="http://daiwu668.dianaikeji.com/bgimg/moduleright.png"></image>
			</view>
			<view class="recharge-type">
				<view class="recharge-type-left">
					<view class="recharge-type-text">提现金额：</view>
					<view class="recharge-type-select">
						<input type="number" placeholder="请输入提现金额" />
					</view>
				</view>
				<image class="recharge-right" src="http://daiwu668.dianaikeji.com/bgimg/moduleright.png"></image>
			</view>
		</view>
		<view class="text-red margin-top text-center">最低提现金额为0.01元，必须为1的整倍数</view>
		<view class="text-gray text-center">注：可提现金额为交易成功后7天且未体现的金额</view>
		<view class="recharge-btn">
			<button class="cu-btn round btnstyle ">立即提现</button>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				
			};
		}
	}
</script>

<style lang="scss">
.recharge{
	.recharge-header{
		width:100vw;
		height:250upx;
		background:$main-color;
		padding: 84upx 110upx;
		display: flex;
		flex-direction: row;
		justify-content: space-between;
		align-items: center;
		.recharge-commission-item{
			height: 100%;
			display: flex;
			flex-direction: column;
			justify-content: space-between;
			align-items: center;
			.recharge-text{
				font-size:24upx;
				color:#FFFFFF;
			}
			.recharge-money{
				font-size:40upx;
				color:#FFFFFF;
			}
		}
	}
	.recharge-content{
		width:690upx;
		height:180upx;
		background:#FFFFFF;
		border-radius:30upx;
		margin: 30upx;
		padding: 0 30upx;
		.recharge-type{
			&:nth-child(1){
				border-bottom: 2upx solid #EEEEEE;
			}
			display: flex;
			flex-direction: row;
			justify-content: space-between;
			align-items: center;
			padding: 20upx 0;
			.recharge-type-left{
				display: flex;
				flex-direction: row;
				align-items: center;
				font-size:28upx;
				.recharge-type-text{
					
				}
				.recharge-type-select{
					margin-left: 2em;
				}
			}
			.recharge-right{
				width: 34upx;
				height: 34upx;
			}
		}
	}
	.recharge-btn{
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
</style>
