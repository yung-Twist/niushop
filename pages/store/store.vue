<template>
	<view class="store">
		<!-- 头部 -->
		<view class="store-header">
			<view class="store-info">
				<view class="store-avatar">
					<image src="https://ss0.bdstatic.com/70cFuHSh_Q1YnxGkpoWK1HF6hhy/it/u=3628123082,3513352290&fm=11&gp=0.jpg" mode=""></image>
				</view>
				<view class="store-name">张三李四的店铺</view>
				<view class="store-member">
					<view class="store-member-count">
						<image src="../../static/images/member.png" mode=""></image>
						<view class="store-num">8888</view>
					</view>
					<view class="store-member-count">
						<image src="../../static/images/thumb.png" mode=""></image>
						<view class="store-num">8888</view>
					</view>
				</view>
			</view>
			<view class="store-operation">
				<view class="operation-item">
					<image src="../../static/images/share.png" mode=""></image>
				</view>
				<view class="operation-item">
					<image src="../../static/images/decoration.png" mode=""></image>
				</view>
				<view class="operation-item">
					<image src="../../static/images/live.png" mode=""></image>
				</view>
			</view>
		</view> 
		<!-- 推荐 -->
		<view class="store-module">
			<view class="store-module-item">
				<ModuleTitle title="推荐商品" imagePath="../static/images/Recommend.png" :width="646" :height="85"/>
				<ModuleItem imagePath="http://www.canpro.cn/uploads/products-img/img_5a21182569c69.png" name="CANPRO -黑武士" origin="厦门" material="高密度陶瓷+PP抗菌" features="全自动翻盖、一体式挂壁智能马桶" @increaseGoods="increaseGoods"/>
			</view>
			<view class="store-module-item">
				<ModuleTitle title="秒杀推荐" imagePath="../static/images/Flashsale.png" :width="493" :height="85"/>
				<ModuleItem imagePath="http://www.canpro.cn/uploads/products-img/img_5a21182569c69.png" name="CANPRO -黑武士" origin="厦门" material="高密度陶瓷+PP抗菌" features="全自动翻盖、一体式挂壁智能马桶" @increaseGoods="increaseGoods"/>
			</view>
			<view class="store-module-item">
				<ModuleTitle title="砍价推荐" imagePath="../static/images/Haggle.png" :width="367" :height="110"/>
				<ModuleItem imagePath="http://www.canpro.cn/uploads/products-img/img_5a21182569c69.png" name="CANPRO -黑武士" origin="厦门" material="高密度陶瓷+PP抗菌" features="全自动翻盖、一体式挂壁智能马桶" @increaseGoods="increaseGoods"/>
			</view>
			<view class="store-module-item">
				<ModuleTitle title="拼团推荐" imagePath="../static/images/Groupbuying.png" :width="709" :height="110"/>
				<ModuleItem imagePath="http://www.canpro.cn/uploads/products-img/img_5a21182569c69.png" name="CANPRO -黑武士" origin="厦门" material="高密度陶瓷+PP抗菌" features="全自动翻盖、一体式挂壁智能马桶" @increaseGoods="increaseGoods"/>
			</view>
		</view>
		<!-- 项目销售报价 -->
		<view class="store-offer">
			<view class="store-offer-text">项目销售报价</view>
			<text class="sm text-sm cuIcon-right"></text>
		</view>
		<!-- 袋客工具 -->
		<view class="store-tools">
			<view class="store-tools-text">
				<ModuleTitle title="袋客工具"/>
			</view>
			<view class="store-tools-wrap">
				<view class="store-tools-item" v-for="(item, index) in storeToolsItem" :key="index">
					<view class="tools-item-icon" :style="{background:index % 2 == 0 ? '#2A6CDC':'#D4E2F8'}">
						<image :src="item.icon" mode=""></image>
					</view>
					<view class="tools-item-name">{{item.title}}</view>
				</view>
			</view>
		</view>
	</view>
</template>

<script>
	import ModuleTitle from '@/components/ModuleTitle.vue'
	import ModuleItem from '@/components/ModuleItem.vue'
	export default {
		data() {
			return {
				storeToolsItem:[
					{
						title:'我的店铺',
						icon:require('@/static/images/store.png'),
						route:''
					},
					{
						title:'店铺设置',
						icon:require('@/static/images/setting.png'),
						route:''
					},
					{
						title:'二维码',
						icon:require('@/static/images/qrcode.png'),
						route:''
					},
					{
						title:'我的订单',
						icon:require('@/static/images/storeorder.png'),
						route:''
					},
					{
						title:'我的团队',
						icon:require('@/static/images/storeteam.png'),
						route:''
					},
					{
						title:'我的佣金',
						icon:require('@/static/images/money.png'),
						route:''
					},
					{
						title:'进行中佣金',
						icon:require('@/static/images/moneying.png'),
						route:''
					},
					{
						title:'佣金提现',
						icon:require('@/static/images/recharge.png'),
						route:''
					},
					{
						title:'投诉建议',
						icon:require('@/static/images/complaint.png'),
						route:''
					},
					{
						title:'专属客服',
						icon:require('@/static/images/service.png'),
						route:''
					},
					{
						title:'合伙人规则',
						icon:require('@/static/images/rule.png'),
						route:''
					},
					{
						title:'素材百科',
						icon:require('@/static/images/encyclopedia.png'),
						route:''
					}
				]
			};
		},
		components:{
			ModuleTitle,
			ModuleItem
		},
		methods:{
			increaseGoods(){
				console.log(123)
			}
		}
		
	}
</script>

<style lang="scss">
page{
	background-color: #94B5ED;
}
.store{
	.store-header{
		padding: 300upx 42upx 0;
		width: 100vw;
		height: 849upx;
		background:#93A4C4;
		position: relative;
		.store-info{
			width:666upx;
			height:414upx;
			background:rgba(255,255,255,.5);
			box-shadow:0 8upx 10upx 0 rgba(42,108,220,0.3);
			border-radius:30upx;
			position: relative;
			.store-avatar{
				width:365upx;
				height:365upx;
				position: absolute;
				left: 151upx;
				top: -175upx;
				background:rgba(65,65,65,1);
				border:8upx solid rgba(255,255,255,1);
				border-radius:50%;
				overflow: hidden;
				image{
					width: 100%;
					height: 100%;
				}
			}
			.store-name{
				width: 100%;
				position: absolute;
				top: 235upx;
				font-size:40upx;
				font-weight:bold;
				line-height:36upx;
				text-align: center;
			}
			.store-member{
				width: 100%;
				position: absolute;
				top: 315upx;
				display: flex;
				flex-direction: row;
				justify-content: space-between;
				padding: 0 114upx;
				.store-member-count{
					display: flex;
					flex-direction: row;
					align-items: center;
					image{
						width: 52upx;
						height: 52upx;
					}
					.store-num{
						font-size:37upx;
						color:$main-color;
						margin-left: 10upx;
					}
				}
			}
		}
		.store-operation{
			width: 100%;
			position: absolute;
			padding: 0  80upx;
			left: 0;
			bottom: -50upx;
			display: flex;
			flex-direction: row;
			justify-content: space-between;
			.operation-item{
				width:99upx;
				height:99upx;
				background:$main-color;
				border-radius:50%;
				display: flex;
				justify-content: center;
				align-items: center;
				image{
					width: 64upx;
					height: 64upx;
				}
			}
		}
	}
	.store-module{
		padding: 42upx;	
	}
	.store-offer{
		width:666upx;
		margin-left: 42upx;
		height:140upx;
		background:$main-color;
		border-radius:30upx;
		color: #FFFFFF;
		font-size:36upx;
		display: flex;
		flex-direction: row;
		justify-content: space-between;
		padding: 50upx 30upx;
	}
	.store-tools{
		width:666upx;
		margin-left: 42upx;
		// height:1130upx;
		background:#FFFFFF;
		border-radius:30px;
		margin: 40upx;
		padding-bottom: 40upx;
		.store-tools-wrap{
			display: grid;
			grid-template-columns: repeat(3,222upx);
			grid-template-rows: repeat(4,222upx);
			.store-tools-item{
				display: flex;
				flex-direction: column;
				align-items: center;
				.tools-item-icon{
					width: 130upx;
					height: 130upx;
					border-radius: 50%;
					overflow: hidden;
					display: flex;
					justify-content: center;
					align-items: center;
					image{
						width: 60upx;
						height: 60upx;
					}
				}
				.tools-item-name{
					font-size:24ux;
					color:#666666;
					margin-top: 26upx;
				}
			}
		}
	}
}
</style>
