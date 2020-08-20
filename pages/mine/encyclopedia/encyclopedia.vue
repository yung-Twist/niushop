<template>
	<view class="encyclopedia">
		<view class="encyclopedia-header">
			<image src="http://daiwu668.dianaikeji.com/bgimg/encyclopediabg.png" mode="" class="encyclopedia-bg"></image>
			<view class="encyclopedia-search">
				<view class="search-input">
					<input type="text" placeholder="请输入您想要的内容" placeholder-class="placeholderStyle">
				</view>
				<view class="search-btn">
					<image src="http://daiwu668.dianaikeji.com/bgimg/searchA.png" mode=""></image>
				</view>
			</view>
			<view class="encyclopedia-type-wrap">
				<view :class="active == item.id ? 'encyclopedia-type-itemA':'encyclopedia-type-item'" v-for="(item, index) in encyclopediaType" :key="index" @click="changeTabs(item)">
					{{item.title}}
					<image v-if="active == item.id" src="http://daiwu668.dianaikeji.com/bgimg/encyclopediaIcon.png" mode=""></image>
					<view class="image-block" v-else></view>
				</view>
			</view>
			<view class="encyclopedia-content">
				<view class="material-wrap">
					<view class="material-item" v-for="(item, index) in materialList" :key="index" @click="toDetail(item)">
						<view class="material-name">{{item.title}}</view>
						<view class="material-date">{{item.date}}</view>
					</view>
				</view>
				<view class="material-btn">
					<button class="cu-btn round btnstyle ">查看更多</button>
				</view>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				active:0,
				encyclopediaType:[
					{
						id:0,
						title:'产品素材'
					},
					{
						id:1,
						title:'厨卫百科'
					},
					{
						id:2,
						title:'其他帮助'
					}
				],
				materialList:[
					{
						title:'智能豪华木桶安装视频',
						date:'2020-02-27'
					},
					{
						title:'智能豪华木桶安装视频',
						date:'2020-02-27'
					},
					{
						title:'智能豪华木桶安装视频',
						date:'2020-02-27'
					},
					{
						title:'智能豪华木桶安装视频',
						date:'2020-02-27'
					},
					{
						title:'智能豪华木桶安装视频',
						date:'2020-02-27'
					}
				]
			};
		},
		methods:{
			changeTabs(item){
				this.active = item.id
			},
			toDetail(item){
				uni.navigateTo({
					url:'/pages/mine/newsDetail/newsDetail'
				})
			},
		}
	}
</script>

<style lang="scss">
	page{
		background-color: #FFFFFF;
	}
.encyclopedia{
	.encyclopedia-header{
		width: 100vw;
		height: 600upx;
		background-color: $main-color;
		border-radius: 0 0 30upx 30upx;
		box-shadow:6upx 9upx 20upx 0 rgba(39,71,98,0.2);
		position: relative;
		.encyclopedia-bg{
			width: 100%;
			height: 362upx;
		}
		.encyclopedia-search{
			position: absolute;
			top: 313upx;
			width: 100vw;
			display: flex;
			justify-content: space-between;
			padding: 0 30upx;
			.search-input{
				width: 570upx;
				height: 100upx;
				background-color:#ffffff;
				border-radius:30upx 31upx 31upx 30upx;
				display: flex;
				align-items: center;
				padding-left: 2em;
				.placeholderStyle{
					font-size:30upx;
					color:#9a9a9a;
				}
			}
			.search-btn{
				width: 100upx;
				height: 100upx;
				background-color:#ffffff;
				border-radius:30upx 31upx 31upx 30upx;
				padding: 20upx;
				image{
					width: 60upx;
					height: 60upx;
				}
			}
		}
		.encyclopedia-type-wrap{
			display: flex;
			flex-direction: row;
			align-items: center;
			width: 100%;
			overflow-x: scroll;
			padding: 10upx 30upx;
			position: absolute;
			bottom: 0;
			.encyclopedia-type-item{
				font-size:26upx;
				color:#FFFFFF;
				opacity:0.5;
				margin-right: 54upx;
				padding-bottom: 16upx;
				white-space: nowrap;
				display: flex;
				flex-direction: column;
				align-items: center;
				.image-block{
					width: 54upx;
					height: 50upx;
					margin-top:37upx;
				}
			}
			.encyclopedia-type-itemA{
				font-size:32upx;
				color:#FFFFFF;
				font-weight:bold;
				color:#FFFFFF;
				margin-right: 54upx;
				white-space: nowrap;
				padding-bottom: 16upx;
				display: flex;
				flex-direction: column;
				align-items: center;
				image{
					width: 54upx;
					height: 50upx;
					margin-top:37upx;
				}
			}
		}
		.encyclopedia-content{
			width: 690upx;
			position: absolute;
			top: 545upx;
			left: 30upx;
			background-color: #FFFFFF;
			height: 600upx;
			border-radius: 30upx;
			box-shadow:6px 9px 20px 0px rgba(39,71,98,0.2);
			.material-wrap{
				padding: 30upx;
				margin-top: 30upx;
				.material-item{
					display: flex;
					flex-direction: row;
					align-items: center;
					justify-content: space-between;
					margin-bottom: 38upx;
					.material-name{
						font-size:32upx;
						color:#343434;
					}
					.material-date{
						font-size:28upx;
						color:#9a9a9a;
					}
				}
			}
			.material-btn{
				text-align: center;
				position: absolute;
				bottom: -45upx;
				left: 95upx;
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
	}
}
</style>
