<template>
<!-- 膳食 -->
<view class="diet">
	<view class="diet_center">
		 <view class="diet_center_head acea-row-between">
		 	  <view class="diet_center_head_headimg">
				  <image src="../../../static/heading.png" mode=""></image>
			  </view>
			  <view class="diet_center_head_right acea-line-height">
				<view>个人基础信息</view>
				<view><image src="../../../static/icon/arrow_right.png" mode=""></image></view>
			  </view>
		 </view>
		 <view class="diet_center_serch acea-row-between">
		 	 <view class="diet_center_serch_input">
		 	 	<input type="text" value="" />
		 	 </view>
		 	 <view class="diet_center_serch_button">搜索</view>			 
		 </view>
		 <!-- 三大产能比 -->
		 <view class="diet_center_capacity">
		     <view class="diet_center_capacity_chart">
		     	 <view>三大产能比</view>
		     	 <view class="chart_than">
					 
				 </view>				 
		     </view>
			 <view class="line"></view>
		     <view class="diet_center_capacity_num">
		     	  <view>推荐摄入量</view>
		     	  <view>1800kcal</view>				  
		     </view>
		 </view>
		 <!-- 营养参考价值 -->
		 <view class="diet_center_value">
		     <view class="diet_center_value_head acea-line-height">
		     	 <view>营养素</view><view>参考值</view><view>实际摄入</view><view>达标情况</view>			 
		     </view>
			 <!-- 未达标 -->
			 <view class="diet_center_value_noStandard">
			 	<view class="diet_center_value_noStandard_head">未达标</view>
			 	<view class="diet_center_value_noStandard_list">
					 <view class="diet_center_value_noStandard_list_item acea-line-height">
						 <view class="item_nutrient">维生素A</view>
						 <view class="item_value">150mg</view>
						 <view class="item_intake">120mg</view>
						 <view class="percentage"></view>			 
					 </view>
					 <view class="diet_center_value_noStandard_list_item acea-line-height">
						 <view class="item_nutrient">维生素C</view>
						 <view class="item_value">1000mg</view>
						 <view class="item_intake">48mg</view>
						 <view class="percentage"></view>			 
					 </view>
					 <view class="diet_center_value_noStandard_list_item acea-line-height">
						 <view class="item_nutrient">钙</view>
						 <view class="item_value">150mg</view>
						 <view class="item_intake">600mg</view>
						 <view class="percentage"></view>			 
					 </view>
					 <view class="diet_center_value_noStandard_list_item acea-line-height">
						 <view class="item_nutrient">叶酸</view>
						 <view class="item_value">200ug</view>
						 <view class="item_intake">60mg</view>
						 <view class="percentage"></view>			 
					 </view>
					 <view class="diet_center_value_noStandard_list_item acea-line-height">
						 <view class="item_nutrient">维生素D</view>
						 <view class="item_value">600IU</view>
						 <view class="item_intake">390mg</view>
						 <view class="percentage"></view>			 
					 </view>
					 <view class="diet_center_value_noStandard_list_item acea-line-height">
						 <view class="item_nutrient">铁</view>
						 <view class="item_value">8mg</view>
						 <view class="item_intake">7.2mg</view>
						 <view class="percentage"></view>			 
					 </view>										  
				</view>				
			 </view>
			 <!-- 超标 -->
			 <view class="diet_center_value_noStandard">
			 	<view class="diet_center_value_noStandard_head">超标</view>
			 	<view class="diet_center_value_noStandard_list">
					 <view class="diet_center_value_noStandard_list_item acea-line-height">
						 <view class="item_nutrient">维生素A</view>
						 <view class="item_value">150mg</view>
						 <view class="item_intake">120mg</view>
						 <view class="percentage"></view>			 
					 </view>
					 <view class="diet_center_value_noStandard_list_item acea-line-height">
						 <view class="item_nutrient">维生素C</view>
						 <view class="item_value">1000mg</view>
						 <view class="item_intake">48mg</view>
						 <view class="percentage"></view>			 
					 </view>
					 <view class="diet_center_value_noStandard_list_item acea-line-height">
						 <view class="item_nutrient">钙</view>
						 <view class="item_value">150mg</view>
						 <view class="item_intake">600mg</view>
						 <view class="percentage"></view>			 
					 </view>
					 <view class="diet_center_value_noStandard_list_item acea-line-height">
						 <view class="item_nutrient">叶酸</view>
						 <view class="item_value">200ug</view>
						 <view class="item_intake">60mg</view>
						 <view class="percentage"></view>			 
					 </view>
					 <view class="diet_center_value_noStandard_list_item acea-line-height">
						 <view class="item_nutrient">维生素D</view>
						 <view class="item_value">600IU</view>
						 <view class="item_intake">390mg</view>
						 <view class="percentage"></view>			 
					 </view>
					 <view class="diet_center_value_noStandard_list_item acea-line-height">
						 <view class="item_nutrient">铁</view>
						 <view class="item_value">8mg</view>
						 <view class="item_intake">7.2mg</view>
						 <view class="percentage"></view>			 
					 </view>										  
				</view>				 	
			 </view>
		 </view>				  
	</view>
	<!-- 底部按钮 -->
	<view class="bottom  acea-row-center">
		<view class="bottom_button" @tap="goViewLog">查看日志</view>
	</view>
</view>
</template>

<script>
// import showActionSheet from '../../../components/Sheet.vue'
	export default {
		// components: {
		// 	showActionSheet
		// },
		data() {
			return {
				
			}
		},
		onLoad() {

		},
		methods: {
			goViewLog(){
				uni.navigateTo({
				   url: '/pages/user/viewLog/index'
				});	
			}
		}
	}
</script>
<style>
	page {
		background-color:#FFFFFF;
	}
</style>
<style lang="less" scoped>
image {
  width: 100%;
  height: 100%;
  vertical-align: top
}	
.diet{
	width: 100%;
	background: #FFFFFF;
	.diet_center{
		width: 690rpx;
		margin:0 auto;
		.diet_center_head{
			width: 100%;
			height: 120rpx;
			background: #FFFFFF;
			box-shadow: 0rpx 4rpx 24rpx 0rpx rgba(0, 0, 0, 0.08);
			border-radius: 20rpx;
			.diet_center_head_headimg{
				width: 78rpx;height: 78rpx;
				background-color:green;
				border-radius: 50%;
				margin-left: 43rpx;	
				image{ border-radius: 50%;}
			}
			.diet_center_head_right{
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
		.diet_center_serch{
			margin-top: 40rpx;
			.diet_center_serch_input{
				width: 525rpx;
				height: 60rpx;
				background: #F1F0F0;
				border-radius: 35rpx;
				input{
					width: 93%;
					height: 100%;
					border-radius: 17rpx;
					margin-left:5%;
				}
			}
			.diet_center_serch_button{
				width: 143rpx;
				height: 60rpx;
				line-height: 60rpx;
				letter-spacing: 5rpx;
				text-align: center;
				background: linear-gradient(112deg, #5E87EC 0%, #445ED8 100%);
				border-radius: 30rpx;
				font-size: 30rpx;
				font-family: PingFangSC-Regular, PingFang SC;
				font-weight: 400;
				color: #FFFFFF;
			}
		}
		.diet_center_capacity{
			width: 100%;
			height: 359rpx;
			margin-top:46rpx;
			background: #FFFFFF;
			box-shadow: 0rpx 4rpx 24rpx 0rpx rgba(0, 0, 0, 0.08);
			border-radius: 20rpx;
			font-family: PingFangSC-Semibold, PingFang SC;
			font-weight: 600;
			display: flex;
		    .diet_center_capacity_chart{
				width: 211rpx;
				margin-left:73rpx;
				text-align: center;
				font-size: 24rpx;
				color: #4B67CD;
				view:nth-of-type(1){margin-top: 43rpx;}				
				view:nth-of-type(2){
					height: 211rpx;
					width: 211rpx;
					margin-top: 15rpx;
					border-radius: 50%;
					background: #57C6DF;
				}		 
			}
			.line{
				width: 1rpx;
				height: 196rpx;
				margin-left:62rpx;
				margin-top: 98rpx;
				background: linear-gradient(180deg, #EAEDF8 0%, #BECCED 48%, #EAEEF8 100%);	
			}
		    .diet_center_capacity_num{
				margin-left:57rpx;
				view:nth-of-type(1){
					margin-top: 139rpx;
					font-size: 24rpx;
					color: #95AAF8;	
				}
				view:nth-of-type(2){
					margin-top: 7rpx;
					font-size: 44rpx;
					color: #4B67CD;
				}				
			}						
		}
		.diet_center_value{
			width: 100%;
			box-shadow: 0rpx 4rpx 24rpx 0rpx rgba(0, 0, 0, 0.08);
			border-radius: 10rpx;
			background: #FFFFFF;		
			margin-top:42rpx;
			margin-bottom: 236rpx;
			font-family: PingFangSC-Regular, PingFang SC;
			.diet_center_value_head{
				height: 86rpx;
				font-size: 30rpx;
				font-weight: 400;
				color: #4C72DE;
				padding-left:43rpx;
				padding-right:38rpx;	
				box-sizing:border-box;
				view{
					&:nth-of-type(2){ margin-left:109rpx; }
					&:nth-of-type(3),&:nth-of-type(4){ margin-left:40rpx; }
				}
			}
			.diet_center_value_noStandard{
				width:100%;		
				.diet_center_value_noStandard_head{
					height: 60rpx;
					line-height: 60rpx;
					background: #596EE4;
					font-size: 28rpx;
					font-weight: 400;
					color: #FFFFFF;
					padding-left:43rpx;
				}
			    &:last-child .diet_center_value_noStandard_head{
					 background: #F2BCB7;
				}
				.diet_center_value_noStandard_list{
					font-size: 30rpx;
					font-family: PingFangSC-Regular, PingFang SC;
					font-weight: 400;
					color: #4C72DE;
					margin-left:43rpx;
					margin-right:38rpx;	
					.diet_center_value_noStandard_list_item{
						margin-top:10rpx;
						height: 120rpx;
						&:nth-of-type(1){
							margin-top:0rpx;
						}
                        .item_nutrient{
						    width: 129rpx;
							// background: plum;
					    }
                        .item_value{
						    width: 124rpx;
							margin-left:36rpx;
							text-align: right;
							color: #7D98F9; 
							// background: pink;
					    }	
                        .item_intake{
						    width: 116rpx;
							margin-left:44rpx;
							text-align: right;
							// background: hotpink;
					    }	
                        .percentage{
							width: 77rpx;
							height: 77rpx;
							margin-left:83rpx;
							background: #4167F0;
							border-radius: 50%;
					    }																		
					}
				}
				&:last-child .diet_center_value_noStandard_list .diet_center_value_noStandard_list_item  .percentage{
					background: #F2BCB7;
				}	
			}
			
		}
	}
	// 底部按钮
	.bottom {
		width: 100%;
		height: 168rpx;
		background: #FFFFFF;
		box-shadow: 0px 29px 39px 0px rgba(0, 0, 0, 1.08);
		position: fixed;
		bottom: 0;
		z-index: 6666;
		.bottom_button {
			width: 692rpx;
			height: 110rpx;
			line-height: 110rpx;
			text-align: center;
			background: linear-gradient(112deg, #5E87EC 0%, #445ED8 100%);
			border-radius: 59rpx;
			margin: 0 auto;
			font-size: 34rpx;
			font-family: PingFangSC-Regular, PingFang SC;
			font-weight: 400;
			color: #FFFFFF;
		}
	}
}
</style>
