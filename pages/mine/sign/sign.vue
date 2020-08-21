<template>
	<view class="sign">
		<view class="sign-header">
			<view class="sign-btn-wrap">
				<view class="sign-btn-item">签到</view>
			</view>
			<view class="sign-calendar">
				<uni-calendar :showMonth="false" :selected="signData"/>
			</view>
		</view>
	</view>
</template>

<script>
	import uniCalendar from '@/components/uni-calendar/uni-calendar.vue'
	export default {
		data() {
			return {
				signData:[
					{
						date: '2020-08-17', 
						info: '已签到',
					},
					{
						date: '2020-08-27', 
						info: '签到',
					},
				]
			};
		},
		components: {
			uniCalendar
		},
		methods: {
			change(e) {
				console.log(e);
			}
		}
	}
</script>

<style lang="scss">
.sign{
	.sign-header{
		width:750upx;
		height:520upx;
		background:$main-color;
		padding-top: 106upx;
		position: relative;
		.sign-btn-wrap{
			width:218upx;
			height:218upx;
			background:rgba(255,255,255,.5);
			border-radius:50%;
			padding: 13upx;
			margin: auto;
			.sign-btn-item{
				width:192upx;
				height:192upx;
				background:#FFFFFF;
				border-radius:50%;
				font-size:40upx;
				color:$main-color;
				text-align: center;
				line-height: 192upx;
			}
		}
		.sign-calendar{
			width:690upx;
			// height:696upx;
			background:#FFFFFF;
			box-shadow:0 10upx 20upx 0 rgba(42,108,220,0.15);
			border-radius:20upx;
			position: absolute;
			left: 30upx;
			top: 440upx;
			padding: 30upx 0;
			&::after{
				content: '';
				width: 620upx;
				position: absolute;
				top: -10upx;
				left: 35upx;
				border-top: 20upx dotted #FFFFFF;
			}
		}
		
	}
}
</style>
