<template>
<!-- 今日运动 -->
<view class="sport">
	<!-- 头部 个人基础信息 -->
	<view class="sport_head acea-row-between">
		<view class="sport_head_headimg">
			<image src="../../../static/heading.png" mode=""></image>
		</view>
		<view class="sport_head_right acea-line-height">
			<view>个人基础信息</view>
			<view><image src="../../../static/icon/arrow_right.png" mode=""></image></view>
		</view>
	</view>
	<view class="sport_kcal">
		<view class="sport_kcal_num acea-row-center">
			<view>1725</view><view>kcal</view>   
		</view>
		<view class="sport_kcal_button acea-row-center" @tap="record">
			<view class="sport_kcal_button_jia"><image src="../../../static/icon/jia.png" mode=""></image></view>
		    <view>记录</view>
		</view>		
	</view>
	<!-- 运动列表 -->
	<view class="sport_list">
		<!-- item -->
		<view class="sport_list_item">
			<view class="sport_list_item_left">
				 <view class="sport_list_item_left_time">09:26</view>
				 <view class="sport_list_item_left_line"></view>				 
			</view>
			<view class="sport_list_item_right">
				 <view>慢跑运动</view>
				 <view>40mins</view>
			</view>							
		</view>	
		<!-- end -->
		<!-- item -->
		<view class="sport_list_item">
			<view class="sport_list_item_left">
				 <view class="sport_list_item_left_time">09:26</view>
				 <view class="sport_list_item_left_line"></view>				 
			</view>
			<view class="sport_list_item_right">
				 <view>轻松瑜伽</view>
				 <view>40mins</view>
			</view>							
		</view>	
		<!-- end -->
		<!-- item -->
		<view class="sport_list_item">
			<view class="sport_list_item_left">
				 <view class="sport_list_item_left_time">09:26</view>
				 <view class="sport_list_item_left_line"></view>				 
			</view>
			<view class="sport_list_item_right">
				 <view>轻松瑜伽</view>
				 <view>40mins</view>
			</view>							
		</view>	
		<!-- end -->
		<!-- item -->
		<view class="sport_list_item">
			<view class="sport_list_item_left">
				 <view class="sport_list_item_left_time">09:26</view>
				 <view class="sport_list_item_left_line"></view>				 
			</view>
			<view class="sport_list_item_right">
				 <view>轻松瑜伽</view>
				 <view>40mins</view>
			</view>							
		</view>	
		<!-- end -->
		<!-- item -->
		<view class="sport_list_item">
			<view class="sport_list_item_left">
				 <view class="sport_list_item_left_time">09:26</view>
				 <view class="sport_list_item_left_line"></view>				 
			</view>
			<view class="sport_list_item_right">
				 <view>慢跑运动</view>
				 <view>40mins</view>
			</view>							
		</view>	
		<!-- end -->
	</view>
	<!-- 添加运动 记录 模态框 -->
	<view class="mask" v-if='mkfalse' @tap="clickBackmask">
		<view class="boxView"  @tap.stop="stop">
			<view class="boxView_title">添加记录</view>
			<!-- 时间 -->
			<view class="boxView_content acea-row-between"  @tap="chooseMeals">
				<view>时间</view>
				<view class="acea-line-height">
					<text>{{recordTime}}</text>
					<view>
						<image src="../../../static/icon/arrow_right.png" mode=""></image>
					</view>
				</view>
			</view>
			<!-- 运动方式 -->
			<view class="boxView_content acea-row-between"  @tap="chooseMeals">
				<view>运动</view>
				<view class="acea-line-height">
					<text>{{recordSport}}</text>
					<view>
						<image src="../../../static/icon/arrow_right.png" mode=""></image>
					</view>
				</view>
			</view>			
			<view class="boxView_button" @tap="addSport">添加</view>
		</view>
	</view> 
</view>
</template>

<script>
// import showActionSheet from '../../../components/Sheet.vue'
	export default {
		components: {
			// showActionSheet
		},
		data() {
			return {
                mkfalse: false,
				recordTime:"请选择",
				recordSport:"请选择",
			}
		},
		onLoad() {

		},
		methods: {
			// 点击 显示弹出框
			record(){
				this.mkfalse = !this.mkfalse;
			},
			//点击 模态框的背景遮罩层
			clickBackmask(){ this.mkfalse = !this.mkfalse; },
		    // 点击 模态框中的 添加按钮
		    addSport() { 
				console.log("确认添加时间 和 运动方式")
			   // this.mkfalse = !this.mkfalse; 
		    },
			stop(){ console.log("阻止事件冒泡")},
		}
	}
</script>
<style>
	page{ background-color: #FFFFFF; }
</style>
<style lang="less" scoped>
	image {
		width: 100%;
		height: 100%;
		vertical-align: top
	}
	.sport {
		width: 690rpx;
		margin:0 auto;
		.sport_head{
			width: 100%;
			height: 120rpx;
			background: #FFFFFF;
			box-shadow: 0rpx 4rpx 24rpx 0rpx rgba(0, 0, 0, 0.08);
			border-radius: 20rpx;
			.sport_head_headimg{
				width: 78rpx;height: 78rpx;
				background-color:green;
				border-radius: 50%;
				margin-left: 43rpx;	
				image{ border-radius: 50%;}
			}
			.sport_head_right{
				font-size: 30rpx;
				font-family: PingFangSC-Regular, PingFang SC;
				font-weight: 400;
				color: #131313;
				margin-right: 47rpx;
				view:nth-of-type(2){
					width: 16rpx;
					height: 28rpx;
					margin-left: 34rpx;
				}
				
			}			
		}
		.sport_kcal{
			margin-top: 48rpx;
			.sport_kcal_num{
				width: 350rpx;
				height: 350rpx;
				border-radius: 50%;
				margin:0 auto;
				background: linear-gradient(180deg, #F3F6FF 0%, #DCE3FF 100%);
				box-shadow: 0rpx 39rpx 28rpx 0rpx rgba(77, 109, 227, 0.03);
			    view{
					font-size: 80rpx;
					font-family: Futura-Bold, Futura;
					font-weight: bold;
					color: #4D6CE3;
					&:nth-of-type(2){
						font-size: 34rpx;
						margin-top: 33rpx;
					}
				} 
			}
			.sport_kcal_button{
				width: 400rpx;
				height: 70rpx;
				margin:0 auto;
				margin-top: 50rpx;
				background: #FFFFFF;
				border-radius: 35rpx;
				border: 3rpx solid  #5A6EE5;
				font-size: 30rpx;
				font-family: PingFangSC-Semibold, PingFang SC;
				font-weight: 600;
				color: #5A6EE5;
				.sport_kcal_button_jia{
					width: 30rpx;
					height: 30rpx;
					margin-right: 22rpx;
				}
			}
		}
		.sport_list{
			width:100%;
			margin-top: 61rpx;
			margin-bottom: 72rpx;
			.sport_list_item{
				width:100%;
				margin-bottom: 15rpx;
				display: flex;
				justify-content: space-between;
                .sport_list_item_left{
					width:79rpx;
					margin-left: 2rpx;
				    .sport_list_item_left_time{
						width:100%;
						text-align: center;
				     	font-size: 34rpx;
				     	font-family: Impact;
				     	color: #202020;
				    }	
				    .sport_list_item_left_line{
				     	width: 1rpx;
				     	height: 132rpx;
						margin: auto;
						margin-top:16rpx;
						background-color: #979797;
				    }					 
				}
				&:last-child .sport_list_item_left  .sport_list_item_left_line{
					display: none; 
				}
                .sport_list_item_right{
				   width: 583rpx;
				   height: 163rpx;
				   margin-top: 7rpx;
				   margin-right: 1rpx;
				   background: linear-gradient(310deg, rgba(240, 192, 192, 0.23) 0%, #E3ADAD 100%);
				   box-shadow: 0rpx 4rpx 24rpx 0rpx rgba(0, 0, 0, 0.08);
				   border-radius: 20rpx 20rpx 20rpx 0rpx;	
				   padding-top:38rpx;
				   box-sizing: border-box;
                   view{
					letter-spacing:3rpx;
					font-size: 34rpx;
					font-family: SourceHanSansCN-Heavy, SourceHanSansCN;
					font-weight: 800;
					color: #FFFFFF;  
					margin-left: 80rpx;
				   }  
				}				
			}		
		}
		
		
		// 弹出框
		.mask{
			width: 100%;
			height: 100%;
			background: rgba(0, 0, 0, 0.4);
			position: fixed;
			left: 0;
			top: 0;
			z-index: 7777;
			display: flex;
			justify-content: center;
		
			.boxView {
				width: 586rpx;
				height: 557rpx;	
				margin-top: 200rpx;
				background: #FFFFFF;
				border-radius: 20rpx;
				position: relative;
				.boxView_title {
					width: 100%;
					margin-top: 55rpx;
					text-align: center;
					font-size: 34rpx;
					font-family: PingFangSC-Semibold, PingFang SC;
					font-weight: 600;
					color: #1A1A1A;
				}
				.boxView_content {
					width: 520rpx;
					height: 110rpx;
					margin: 0 auto;
					background: #F7F7F7;
					border-radius: 10rpx;
					margin-top: 45rpx;
					font-family: PingFangSC-Regular, PingFang SC;
					color: #131313;
					&:nth-of-type(3){
						margin-top:20rpx;
					}
					view:nth-of-type(1) {
						font-size: 34rpx;
						font-weight: 600;
						margin-left: 29rpx;
					}
		
					view:nth-of-type(2) {
						font-size: 30rpx;
						font-weight: 400;
						view {
							width: 16rpx;
							height: 28rpx;
							margin-left:33rpx;
							margin-right: 32rpx;
						}
					}
		
				}
		
				.boxView_button {
					width: 335rpx;
					height: 90rpx;
					letter-spacing: 4rpx;
					text-align: center;
					line-height: 90rpx;
					font-size: 34rpx;
					font-family: PingFangSC-Regular, PingFang SC;
					font-weight: 400;
					color: #FFFFFF;
					position: absolute;
					left: 0;
					right: 0;
					margin: 0 auto;
					bottom: 46rpx;
					background: linear-gradient(112deg, #5E87EC 0%, #445ED8 100%);
					border-radius: 59rpx;
				}
			}
		}
	}
</style>
