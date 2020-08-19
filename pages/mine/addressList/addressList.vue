<template>
	<view class="address">
		<view class="address-wrap">
			<view class="address-item"  v-for="(item, index) in addressList" :key="index">
				<view class="address-name-phone">
					<view class="address-name">{{item.name}}</view>
					<view class="address-name">{{item.phone}}</view>
				</view>
				<view class="address-detail">
					{{item.province}} - {{item.city}} - {{item.county}} - {{item.addressDetail}}
				</view>
				<view class="address-default-edit">
					<view class="address-default">
						<checkbox class='round blue' :checked="item.default == 1" style="zoom:50%;"></checkbox>
						<view class="address-default-text">默认地址</view>
					</view>
					<view class="address-edit-delete">
						<view class="address-edit">
							<text class="cuIcon-edit"></text>
							编辑
						</view>
						<view class="address-delete">
							<text class="cuIcon-delete"></text>
							删除
						</view>
					</view>
				</view>
			</view>
		</view>
		<view class="address-btn">
			<button class="cu-btn round btnstyle ">新增地址</button>
		</view>
		<view class="address-btn">
			<button class="cu-btn round btnstyle " style="background-color: #8EAFE7;">一键获取地址</button>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				addressList:[
					{
						name:'张三',
						phone:13787878787,
						province:'福建省',
						city:'厦门市',
						county:'集美区',
						addressDetail:'软件园三期B02栋604室',
						default:1
					},
					{
						name:'张三',
						phone:13787878787,
						province:'福建省',
						city:'厦门市',
						county:'集美区',
						addressDetail:'软件园三期B02栋604室',
						default:2
					}
				]
			};
		}
	}
</script>

<style lang="scss">
.address{
	.address-wrap{
		.address-item{
			background-color: #FFFFFF;
			padding: 30upx;
			margin-top: 30upx;
			.address-name-phone{
				display: flex;
				flex-direction: row;
				align-items: center;
				justify-content: space-between;
				font-size:32upx;
				font-weight:bold;
				color:#0C0C0C;
			}
			.address-detail{
				font-size:28upx;
				color:#999999;
				padding: 34upx 0;
				border-bottom: 2upx solid #EEEEEE;
			}
			.address-default-edit{
				display: flex;
				flex-direction: row;
				align-items: center;
				justify-content: space-between;
				padding-top:10upx;
				.address-default{
					display: flex;
					flex-direction: row;
					align-items: center;
					.address-default-text{
						font-size:26upx;
						color:#999999;
						margin-left: 10upx;
					}
				}
				.address-edit-delete{
					display: flex;
					flex-direction: row;
					align-items: center;
					font-size:26upx;
					color:#999999;
					.address-edit{
						margin-right: 30upx;
					}
				}
			}
		}
	}
	.address-btn{
		margin-top: 30upx;
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
