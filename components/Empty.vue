<template>
	<view class="empty">
		<image src="../static/images/empty.png" mode=""></image>
		<view class="emptyText">
			{{text}}
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				
			};
		},
		props:{
			text:{
				type:String,
				default:'暂无数据'
			}
		}
	}
</script>

<style lang="scss">
.empty{
	display: flex;
	flex-direction: column;
	justify-content: center;
	align-items: center;
	image{
		// width: ;
	}
	.emptyText{
		font-size: 60upx;
		color: #969799;
	}
}
</style>
