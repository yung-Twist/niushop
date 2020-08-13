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
			};
		},
		onShow() {
			let routes = getCurrentPages();
			this.route = routes[routes.length - 1].route
		},
		components:{
			Tarbar
		},
	}
</script>

<style lang="less">

</style>
