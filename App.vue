<script>
	export default {
		globalData: {  
		},
		onLaunch: function() {
			uni.hideTabBar()
		},
		onShow: function() {
			// console.log('App Show')
		},
		onHide: function() {
			// console.log('App Hide')
		}
	}
</script>

<style lang="scss">
	/*每个页面公共css */
	@import "colorui/main.css";
	@import "colorui/icon.css";
	page{
		background-color: #F2F2F2;
		font-family:Microsoft YaHei;
		font-weight:400;
		color:#343434;
		padding-bottom: calc(var(--window-bottom) + 126upx);
	}
</style>
