<template>
	<view class="myTeam">
		<view class="myTeam-header">
			<view :class="active == index ? 'myTeam-type-itemA' : 'myTeam-type-item'" v-for="(item, index) in detailType" :key="index"
			 @click="changeType(index)">{{item.title}}</view>
		</view>
		<view class="myTeam-wrap">
			<view class="myTeam-item" v-for="(item, index) in dataList" :key="index">
				<image class="myTeam-avatar" :src="item.avatar"></image>
				<view class="myTeam-right">
					<view class="myTeam-phone">{{item.phone}}<view class='cu-tag round sm line-blue margin-left'>推广员</view></view>
					<view class="myTeam-people">团队人数：{{item.person}}人</view>
					<view class="myTeam-phone">注册时间：{{item.date}}</view>
				</view>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				detailType: [{
						title: '推广员'
					},
					{
						title: '会员'
					}
				],
				active:'0',
				dataList:[
					{
						avatar:'https://img-cdn-qiniu.dcloud.net.cn/uploads/avatar/000/09/75/97_avatar_max.jpg',
						phone:13878789879,
						person:88,
						date:'2020-02-02 22:22:12'
					},
					{
						avatar:'https://img-cdn-qiniu.dcloud.net.cn/uploads/avatar/000/09/75/97_avatar_max.jpg',
						phone:13878789879,
						person:88,
						date:'2020-02-02 22:22:12'
					},
					{
						avatar:'https://img-cdn-qiniu.dcloud.net.cn/uploads/avatar/000/09/75/97_avatar_max.jpg',
						phone:13878789879,
						person:88,
						date:'2020-02-02 22:22:12'
					}
				]
			};
		},
		methods:{
			changeType(index) {
				this.active = index
			}
		}
	}
</script>

<style lang="scss">
.myTeam{
	.myTeam-header {
		border-bottom: 4upx solid #EEEEEE;
		padding: 22upx 0;
		display: flex;
		flex-direction: row;
		align-items: center;
		background-color: #FFFFFF;
		justify-content: space-around;
	
		.myTeam-type-item {
			font-size: 24upx;
			color: #9A9A9A;
			padding-bottom: 20upx;
			border-bottom: 4upx solid #FFFFFF;
		}
	
		.myTeam-type-itemA {
			font-size: 28upx;
			color: $main-color;
			padding-bottom: 20upx;
			border-bottom: 4upx solid $main-color;
		}
	}
	.myTeam-wrap{
		.myTeam-item{
			margin-top: 30upx;
			background-color: #FFFFFF;
			padding: 30upx;
			display: flex;
			align-items: center;
			.myTeam-avatar{
				width: 120upx;
				height: 120upx;
			}
			.myTeam-right{
				height: 120upx;
				font-size:32upx;
				display: flex;
				flex-direction: column;
				justify-content: space-between;
				margin-left: 30upx;
			}
		}
	}
}
</style>
