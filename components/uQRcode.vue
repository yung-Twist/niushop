<template>
	<view class="qrcode">
		<canvas canvas-id="qrcode" :style="{width: width + 'px',height: height + 'px'}" />
	</view>
</template>

<script>
	import uQRCode  from '@/utils/uqrcode.js'
	export default {
		data() {
			return {
				
			};
		},
		props:{
			width:{
				type:Number,
				default:200
			},
			height:{
				type:Number,
				default:200
			},
			text:String
		},
		mounted() {
			this.make()
		},
		methods: {
		    make() {
		      uQRCode.make({
		        canvasId: 'qrcode',
		        componentInstance: this,
		        text: this.text,
		        size: this.width,
		        margin: 10,
		        backgroundColor: '#ffffff',
		        foregroundColor: '#000000',
		        correctLevel: uQRCode.errorCorrectLevel.H,
		        success: res => {
		          console.log(res)
		        }
		      })
		    }
		}
	}
</script>

<style lang="scss">

</style>
