<template>
	<view class="home">
		
		<!-- 搜索 -->
		<view class="home-search">
			<view class="searchInput">
				<image src="http://daiwu668.dianaikeji.com/bgimg/search.png"></image>
				<input class="uni-input" confirm-type="search" v-model="searchWord" @confirm="search" placeholder-class="placeholderStyle" placeholder="请输入你想要的内容"/>
			</view>
		</view>
		
		<!-- 轮播图 -->
		<view class="home-banner">
			<swiper class="swiper" :autoplay="true" :interval="3000" :circular="true">
				<swiper-item v-for="(item, index) in bannerList" :key="index">
					<image :src="item.imagePath" mode="" class="bannerImg"></image>
				</swiper-item>
			</swiper>
		</view>
		
		<!-- 秒杀 砍价 -->
		<view class="home-buyType">
			<view class="buytype-item" v-for="(item, index) in buyTypeList" :key="index" @click="toItemPath(item)">
				<image :src="item.icon" mode="" class="type-icon"></image>
				<text class="type-title">{{item.title}}</text>
			</view>
		</view>
		
		<!-- 推荐商品 -->
		<view class="home-recommend">
			<ModuleTitle2 title="推荐商品"/>
			<view class="recommend-product">
				<view class="recommend-product-Item" v-for="(item, index) in productList" :key="index" @click="toGoodsDetail(item)">
					<image :src="item.imagePath" mode="" class="product-image"></image>
					<view class="product-name">{{item.name}}</view>
					<view class="product-info">
						<text class="product-info-item">产地：{{item.origin}}</text>
						<text class="product-info-item">材质：{{item.material}}</text>
						<text class="product-info-item">功能：{{item.features}}</text>
					</view>
				</view>
			</view>
		</view>
		
		<Tarbar :route="route"/>
	</view>
</template>

<script>
	import Tarbar from '@/components/Tarbar'
	import ModuleTitle2 from '@/components/ModuleTitle2.vue'
	export default {
		data() {
			return {
				route:null,
				searchWord:'',
				bannerList:[
					{
						imagePath:'https://cube.elemecdn.com/6/94/4d3ea53c084bad6931a56d5158a48jpeg.jpeg',
						route:''
					},
					{
						imagePath:'https://img.yzcdn.cn/vant/apple-2.jpg',
						route:''
					},
					{
						imagePath:'https://img.yzcdn.cn/vant/apple-1.jpg',
						route:''
					},
					{
						imagePath:'https://img.yzcdn.cn/vant/apple-2.jpg',
						route:''
					}
				],
				buyTypeList:[
					{
						title:'秒杀',
						route:'/pages/index/second/second',
						icon:'http://daiwu668.dianaikeji.com/bgimg/second.png'
					},
					{
						title:'砍价',
						route:'/pages/index/bargain/bargain',
						icon:'http://daiwu668.dianaikeji.com/bgimg/bargain.png'
					},
					{
						title:'拼团',
						route:'/pages/index/group/group',
						icon:'http://daiwu668.dianaikeji.com/bgimg/group.png'
					},
					{
						title:'积分商城',
						route:'/pages/index/integralstore/integralstore',
						icon:'http://daiwu668.dianaikeji.com/bgimg/integral.png'
					}
				],
				productList:[
					{
						imagePath:'http://www.canpro.cn/uploads/products-img/img_5a21182569c69.png',
						name:'CANPRO -黑武士',
						origin:'厦门',
						material:' 高密度陶瓷+PP抗菌',
						features:'全自动翻盖、一体式挂壁智能马桶'
					},
					{
						imagePath:'http://www.canpro.cn/uploads/products-img/img_5a24b92034743.png',
						name:'CANPRO -黑武士',
						origin:'厦门',
						material:' 高密度陶瓷+PP抗菌',
						features:'全自动翻盖、一体式挂壁智能马桶'
					},
					{
						imagePath:'http://www.canpro.cn/uploads/products-img/img_5a21182569c69.png',
						name:'CANPRO -黑武士',
						origin:'厦门',
						material:' 高密度陶瓷+PP抗菌',
						features:'全自动翻盖、一体式挂壁智能马桶'
					}
				]
			}
		},
		onLoad() {
			let routes = getCurrentPages();
			this.route = routes[routes.length - 1].route
		},
		components:{
			Tarbar,
			ModuleTitle2
		},
		methods: {
			search(){
			},
			// 秒杀,拼团...
			toItemPath(item){
				uni.navigateTo({
					url:item.route
				})
			},
			// 前往商品详情
			toGoodsDetail(item){
				uni.navigateTo({
					url:'/pages/goodsDetail/goodsDetail'
				})
			}
		}
	}
</script>

<style lang="scss">
page{
	background-color: #FFFFFF;
}
.home{
	display: flex;
	flex-direction: column;
	align-items: center;
	box-sizing: border-box;
	.home-search{
		.searchInput{
			width: 690upx;
			height: 70upx;
			background-color: #f2f2f2;
			border-radius: 35upx;
			display: flex;
			flex-direction: row;
			align-items: center;
			padding: 0 2vw;
			.placeholderStyle{
				color: #c2c2c2;
				font-size: 28upx;
			}
			image{
				width: 30upx;
				height: 30upx;
				margin: 2vw;
			}
		}
	}
	.home-banner{
		width: 690upx;
		margin-top: 30upx;
		border-radius: 20upx;
		overflow: hidden;
		.bannerImg{
			width: 100%;
			height: 320upx;
			border-radius: 20upx;
		}
	}
	.home-buyType{
		width: 690upx;
		height: 204upx;
		border-radius: 20upx;
		margin-top: 30upx;
		background:rgba(255,255,255,1);
		box-shadow:6px 9px 20px 0px rgba(39,71,98,0.2);
		display: flex;
		flex-direction: row;
		justify-content: space-between;
		padding: 30upx;
		.buytype-item{
			display: flex;
			flex-direction: column;
			align-items: center;
			justify-content: space-between;
			.type-icon{
				width: 100upx;
				height: 100upx;
				margin-bottom: 2upx;
			}
			.type-title{
				font-size:24upx;
				
				font-weight:400;
				color:rgba(52,52,52,1);
				line-height:25upx;
			}
		}
	}
	.home-recommend{
		width:690upx;
		margin-top: 30upx;
		.recommend-product{
			.recommend-product-Item{
				margin-top: 30upx;
				width:690upx;
				padding: 67upx 80upx 30upx 67upx;
				background:rgba(255,255,255,1);
				box-shadow:6upx 9upx 20upx 0upx rgba(39,71,98,0.2);
				border-radius:20upx;
				.product-image{
					width:530upx;
					height:480upx;
				}
				.product-name{
					margin-top: 47upx;
					font-size:34upx;
					font-weight:bold;
					color:rgba(52,52,52,1);
				}
				.product-info{
					margin-top: 71upx;
					display: flex;
					flex-direction: column;
					.product-info-item{
						margin-bottom: 27upx;
						font-size:28upx;
						
						font-weight:400;
						color:rgba(154,154,154,1);
					}
				}
			}
		}
	}
}
</style>
