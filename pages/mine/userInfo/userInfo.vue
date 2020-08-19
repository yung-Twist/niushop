<template>
	<view class="userInfo">
		<view class="cu-list menu sm-border" style="margin-top: 30upx;">
			<view class="cu-item arrow">
				<view class="content">
					<text class="text-black text-bold">头像</text>
				</view>
				<view class="action">
					<view class="cu-avatar round" style="background-image:url(https://ossweb-img.qq.com/images/lol/web201310/skin/big10001.jpg)"></view>
				</view>
			</view>
			<view class="cu-item">
				<view class="content">
					<text class="text-black text-bold">账号</text>
				</view>
				<view class="action">
					<text class="text-grey text-sm">zz123456</text>
				</view>
			</view>
			<view class="cu-item arrow">
				<view class="content">
					<text class="text-black text-bold">昵称</text>
				</view>
				<view class="action">
					<text class="text-grey text-sm">张三李四</text>
				</view>
			</view>
			<view class="cu-item arrow">
				<view class="content">
					<text class="text-black text-bold">密码</text>
				</view>
			</view>
			<view class="cu-item arrow">
				<view class="content">
					<text class="text-black text-bold">支付密码</text>
				</view>
			</view>
		</view>
		<view class="cu-list menu sm-border" style="margin-top: 30upx;">
			<view class="cu-item arrow">
				<view class="content">
					<text class="text-black text-bold">绑定手机</text>
				</view>
				<view class="action">
					<text class="text-grey text-sm">13878787878</text>
				</view>
			</view>
			<view class="cu-item arrow">
				<view class="content">
					<text class="text-black text-bold">绑定邮箱</text>
				</view>
				<view class="action">
					<text class="text-grey text-sm">13878787878@163.com</text>
				</view>
			</view>
		</view>
		<view class="userInfo-btn">
			<button class="cu-btn round btnstyle ">退出登录</button>
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
.userInfo{
	.userInfo-btn{
		margin-top: 170upx;
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
