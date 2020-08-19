<template>
	<view class="CountDown">
		<view  v-if="!isTimeout">
			<text v-if="second != ''">{{title}}</text>
			<text v-if="day > 0">{{day}}天</text>
			<text v-if="hour != ''">{{hour}}小时</text>
			<text v-if="min != ''">{{min}}分</text>
			<text v-if="second != ''">{{second}}秒</text>
		</view>
		<text v-else>已结束</text>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				time:'',
				day:'',
				hour:'',
				min:'',
				second:'',
				isTimeout:false
			};
		},
		props:{
			date:String,//2020-07-08
			title:String
		},
		computed:{
		},
		methods:{
			timeDown(){
				let that = this
				let timer = setInterval(()=>{
					let nowtime = new Date(); //当前时间
					let lefttime = parseInt((Date.parse(new Date(that.date.replace(/-/g,'/'))) - Date.parse(new Date())) / 1000);
					this.day = parseInt(lefttime / 3600 / 24);
					this.hour = parseInt((lefttime / 3600) % 24) > 9 ? parseInt((lefttime / 3600) % 24) : "0" + parseInt((lefttime / 3600) % 24);
					this.min = parseInt((lefttime / 60) % 60) > 9 ? parseInt((lefttime / 60) % 60) : "0" + parseInt((lefttime / 60) % 60);
					this.second = parseInt(lefttime % 60) > 9 ? parseInt(lefttime % 60) : "0" + parseInt(lefttime % 60);
					if(lefttime <= 0){
						clearInterval(timer)
						this.isTimeout = true
					}
				},1000)
			}
			
		},
		onShow() {
			
		},
		onReady() {
			this.timeDown()
			// console.log(this.date)
		}
	}
</script>

<style lang="scss">
.CountDown{
	text{
		// color: #E4003C;
	}
}
</style>