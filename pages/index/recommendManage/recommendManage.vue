<template>
	<view class="recommendManage">
		<!-- 搜索 -->
		<view class="home-search">
			<view class="searchInput">
				<image src="http://daiwu668.dianaikeji.com/bgimg/search.png"></image>
				<input class="uni-input" confirm-type="search" v-model="searchWord" @confirm="search" placeholder-class="placeholderStyle" placeholder="请输入你想要的内容"/>
			</view>
		</view>
		<!-- 分类排序 -->
		<view class="recommendManage-categoryOrder">
			<view class="recommendManage-category">
				分类<text class="lg text-lg text-gray cuIcon-triangledownfill"></text>
			</view>
			<view class="recommendManage-category">
				排序<text class="lg text-lg text-gray cuIcon-triangledownfill"></text>
			</view>
		</view>
		<!-- 商品列表 -->
		<view class="recommend-goodsList">
			<checkbox-group class="block" @change="CheckboxChange">
				<view class="goodsList-item" v-for="(item, index) in dataList" :key="index">
					<view class="goodsList-item-checkbox">
						<checkbox class='round blue' :value="item.id" style="zoom: 80%;"></checkbox>
					</view>
					<view class="goodsList-item-goodsInfo">
						<image class="goodsInfo-image" :src="item.imagePath"></image>
						<view class="goodsInfo-detail">
							<view class="goodsInfo-name">{{item.name}}</view>
							<view class="goodsInfo-sale">
								<view class='cu-tag sm round line-blue'>包邮</view>
								<text class="text-gray margin-left">销量：</text>
								{{item.sale}}
							</view>
							<view class="goodsInfo-price">
								<text class="text-gray">零售价：</text>
								<text class="text-red">{{item.price}}</text>
							</view>
							<view class="goodsInfo-commission">
								<text class="text-gray">佣金：</text>
								<text class="text-red">{{item.commission}}</text>
								
							</view>
						</view>
					</view>
					<view class="goodsInfo-editBtn">
						<button class="cu-btn round bg-blue sm" @click="editPrice(item)">编辑价格</button>
					</view>
				</view>
			</checkbox-group>
		</view>
		<!-- 编辑弹窗 -->
		<view class="cu-modal" :class="showEdit ? 'show':''">
			<view class="cu-dialog">
				<view class="cu-bar bg-white justify-end">
				  <view class="content">店铺二维码</view>
				  <view class="action" @click="showEdit = false">
						<text class="cuIcon-close text-red"></text>
				  </view>
				</view>
				<view class="padding-xl">
				  123
				</view>
		  </view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				showEdit:false,
				dataList:[
					{
						id:1,
						imagePath:'https://ss3.bdstatic.com/70cFv8Sh_Q1YnxGkpoWK1HF6hhy/it/u=3978824836,2427222933&fm=26&gp=0.jpg',
						name:'商品描述商品描述',
						sale:999,
						price:200.00,
						commission:10.35,
						
					},
					{
						id:2,
						imagePath:'https://ss3.bdstatic.com/70cFv8Sh_Q1YnxGkpoWK1HF6hhy/it/u=3978824836,2427222933&fm=26&gp=0.jpg',
						name:'商品描述商品描述',
						sale:999,
						price:200.00,
						commission:10.35,
						
					}
				]
			};
		},
		methods:{
			search(){},
			CheckboxChange(){},
			editPrice(item){
				this.showEdit = true
			}
		}
	}
</script>

<style lang="scss">
.recommendManage{
	.home-search{
		background-color: #FFFFFF;
		padding: 30upx;
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
	.recommendManage-categoryOrder{
		background-color: #FFFFFF;
		display: flex;
		justify-content: space-around;
		align-items: center;
		padding: 30upx;
		font-size: 24upx;
		color: #9A9A9A;
	}
	.recommend-goodsList{
		width: 690upx;
		margin-left: 30upx;
		background-color: #FFFFFF;
		margin-top: 30upx;
		border-radius: 20upx;
		.goodsList-item{
			display: flex;
			flex-direction: row;
			align-items: center;
			padding: 30upx;
			border-bottom: 2upx solid #EEEEEE;
			position: relative;
			.goodsList-item-checkbox{
				
			}
			.goodsList-item-goodsInfo{
				display: flex;
				flex-direction: row;
				align-items: center;
				.goodsInfo-image{
					width: 204upx;
					height: 180upx;
					margin: 0 20upx;
				}
				.goodsInfo-detail{
					.goodsInfo-name{
						font-size: 26upx;
						color: #343434;
					}
					.goodsInfo-sale{
						display: flex;
						flex-direction: row;
						align-items: center;
					}
				}
			}
			.goodsInfo-editBtn{
				position: absolute;
				right: 30upx;
				bottom: 40upx;
			}
		}
	}
}
</style>
