<template>
 <view class="user">
	 <!-- 头部 -->
    <view class="head acea-row-between">
	     <view class="head_left acea-line-height">
				 <view class="head_left_img"><image src="../../../static/heading.png" mode=""></image></view>	
				 <view class="head_left_center">
					 <view class="head_center_name">LUCKY</view>
					 <view class="head_center_introduce">我是…,希望能为大家带来力所……</view>			 
				 </view>	
         </view>					 
         <view class="head_right">
         	 <image src="../../../static/icon/arrow_right.png" mode=""></image>
         </view>		  
    </view>
	<!-- 我的健康档案 -->
	<view class=" health_files acea-row-between" @click="goHealthRecords()">
		 <view class="health_files_left acea-line-height">
		 	  <view><image src="../../../static/icon/file.png" mode=""></image></view>
		 	  <view>我的健康档案</view>			  
		 </view>
		 <view class="health_files_right">
		  	<image src="../../../static/icon/arrow_right.png" mode=""></image>
		 </view>
	</view>
	<!-- 我的服务 -->
	<view class="service">
		<view class="service_title">我的服务</view>
		<view class="service_list acea-row-center">
			<view class="service_item">
				<view class="service_item_img">
					<image src="../../../static/icon/HD.png" mode=""></image>
				</view>
				<view class="service_item_txt">我的活动</view>			
			</view>
			<view class="service_item">
				<view class="service_item_img">
					<image src="../../../static/icon/CP.png" mode=""></image>
				</view>
				<view class="service_item_txt">我的测评</view>			
			</view>
			<view class="service_item"  @click="goLogin()">
				<view class="service_item_img">
					<image src="../../../static/icon/SC.png" mode=""></image>
				</view>
				<view class="service_item_txt">我的收藏</view>			
			</view>			
		</view>		
	</view>
 </view>
</template>

<script>
	export default {
		data() {
			return {
			
			}
		},
		onLoad() {

		},
		methods: {
		  goHealthRecords(){
			   uni.navigateTo({
			      url: '/pages/user/HealthRecords/index',
			   });				
		  },
          goLogin(){
			   uni.navigateTo({
			      url: '/pages/user/Login/index',
			   });
		  }
		}
	}
</script>

<style lang="less"  scoped>
 image{ width: 100%;height: 100%;}
.user {
    height: 100%;
	width: 690rpx;
	margin:0 auto;
	.head{
		height: 126.83rpx;
		width: 100%;
		// background-color: pink;
		.head_left{
			.head_left_img{
				height: 126.83rpx;
				width: 126.83rpx;
				border-radius: 50%;
				image{border-radius: 50%;}		
			}
			.head_left_center{
				margin-left: 32rpx;			
				// background-color: hotpink;	
				 .head_center_name{
					font-size: 48rpx;
					font-family: PingFangSC-Semibold, PingFang SC;
					font-weight: 600;
					color: #131313; 
					margin-top: -7rpx;
				 }
				 .head_center_introduce{
					font-size: 24rpx;
					font-family: PingFangSC-Regular, PingFang SC;
					font-weight: 400;
					color: #858892;
				 }			 
			}			
		}
		.head_right{
			height: 34rpx;
			width: 20rpx;
			margin-right: 8rpx;
		}
	}
	// 健康档案
	.health_files{
		width: 100%;
		height: 130rpx;
		background: #FFFFFF;
		box-shadow: 0rpx 4rpx 24rpx 0rpx rgba(0, 0, 0, 0.08);
		border-radius: 20rpx;
		margin-top: 41rpx;
		.health_files_left{
			 view:nth-of-type(1){
				height: 62rpx;
				width: 56rpx; 
				margin-left: 34rpx;			
			 }
			 view:nth-of-type(2){
				font-size: 34rpx;
				font-family: PingFangSC-Semibold, PingFang SC;
				font-weight: 600;
				color: #131313;
				margin-top: -9rpx;
				margin-left: 34rpx;		
				// background-color: pink;
			 }			 
		}
		.health_files_right{
			height: 34rpx;
			width: 20rpx;
			margin-right: 42rpx;
		}		
	}
	// 我的服务
	.service{
		width: 100%;
		height: 281rpx;	
		background: #FFFFFF;
		box-shadow: 0rpx 4rpx 24rpx 0rpx rgba(0, 0, 0, 0.08);
		border-radius: 20rpx;
		margin-top: 20rpx;	
		.service_title{
			font-size: 34rpx;
			font-family: PingFangSC-Semibold, PingFang SC;
			font-weight: 600;
			color: #131313;	
			margin-left: 34rpx;
			padding-top:27rpx;
			box-sizing: border-box;
		}
		.service_list{
			margin-top: 45rpx;			
			.service_item{
				&:nth-of-type(2){
					margin-left:110rpx;
					margin-right:110rpx;
				}
				.service_item_img{
					height: 66rpx;
					width: 65rpx; 
					margin: 0 auto;
					display: flex;
					align-items: center;
	                justify-content:center;
					image{
						&:nth-of-type(1){
							height: 56rpx;
							width: 51rpx;  
						}
						&:nth-of-type(2){
							height: 48rpx;
							width: 56rpx;  
						}
						&:nth-of-type(3){
							height: 59rpx;
							width: 63rpx;  
						}												
					}
				}
				.service_item_txt{
					font-size: 28rpx;
					font-family: PingFangSC-Regular, PingFang SC;
					font-weight: 400;
					color: #131313;
					// margin-top: 8rpx;		
				}			
			}				
		}
	}
		
}
</style>
