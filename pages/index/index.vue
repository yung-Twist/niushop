<template>
	<view>
		<Tarbar :route="route"/>
	</view>
</template>

<script>
	import Tarbar from '@/components/Tarbar'
	export default {
		data() {
			return {
				route:null
			}
		},
		onLoad(e){
			uni.hideTabBar()
		},
		onShow() {
			let routes = getCurrentPages();
			this.route = routes[routes.length - 1].route
		},
		components:{
			Tarbar
		},
		methods: {

		}
	}
</script>

<style>

</style>
