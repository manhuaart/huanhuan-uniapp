<template>
<view>	
  <!-- 推荐列表 -->
  <view class="recommendList">
    <view class="recommend_item acea-row-between">
		<view class="recommend_item_left">
			<view class="item_title">心肌梗死（myocardial infarction）概述</view>
			<view class="item_down acea-row-between">
				<view class="img"><image src="../static/images/zding@2x.png" mode=""></image></view>
			   	<text>1122阅读</text>
			</view>
		</view>  
		<view class="recommend_item_right">
			<image src="../static/images/items2.png" mode=""></image>
		</view> 		
	</view>
    <view class="recommend_item acea-row-between">
		<view class="recommend_item_left">
			<view class="item_title">什么是心脏病?并发症都有哪些?</view>
			<view class="item_down acea-row-between">
				<view class="img"><image src="../static/images/zding@2x.png" mode=""></image></view>
			   	<text>1122阅读</text>
			</view>
		</view>  
		<view class="recommend_item_right">
			<image src="../static/images/items.png" mode=""></image>
		</view> 		
	</view>
    <view class="recommend_item acea-row-between">
		<view class="recommend_item_left">
			<view class="item_title">
				心肌梗死（myocardial infarction）概述
			</view>
			<view class="item_down acea-row-between">
				<view class="img"><image src="../static/images/zding@2x.png" mode=""></image></view>
			   	<text>1122阅读</text>
			</view>
		</view>  
		<view class="recommend_item_right">
			<image src="../static/images/items2.png" mode=""></image>
		</view> 		
	</view>
    <view class="recommend_item acea-row-between">
		<view class="recommend_item_left">
			<view class="item_title">
				心肌梗死（myocardial infarction）概述
			</view>
			<view class="item_down acea-row-between">
				<view class="img"><image src="../static/images/zding@2x.png" mode=""></image></view>
			   	<text>1122阅读</text>
			</view>
		</view>  
		<view class="recommend_item_right">
			<image src="../static/images/items.png" mode=""></image>
		</view> 		
	</view>
  </view>
  <!-- 轮播图 -->
  <view class="slider-banner">
			<swiper indicatorDots="true" indicator-active-color='#fff' indicator-color='rgba(255,255,255,0.5)' 
		      current='0' interval='4000' duration='800' v-if="banner.length > 0" autoplay circular>
				<block v-for="(item, bannerIndex) in banner" :key="bannerIndex">
					<swiper-item>
						<view @click="goRoll(item)" class="swiper-item">
							<image :src="item.pic"/>
						</view>
					</swiper-item>
				</block>
			</swiper>
  </view>
  <!-- 医学资询 -->
  <view class="information">
	   <view class="information_title">医学咨询</view>
  	   <view class="information_img  acea-row-between">
  	   	   <image src="../static/images/zixun.png" mode=""></image>
  	       <image src="../static/images/doctor.png" mode=""></image>
	   </view> 
  </view>
  <!-- 趣味测试 -->
  <view class="test">
	   <view class="test_title">趣味测试</view>
	   <view class="test_list">
		   <!-- 1 -->
		   <view class="test_list_item">
			   <view class="test_list_item_title">匹兹堡睡眠质量指数</view>
			   <view class="test_list_item_img">
			   	   <image src="../static/images/sleep.png" mode=""></image>
			   </view>
		   </view>	 
		   <!-- 2 -->
		   <view class="test_list_item">
			   <view class="test_list_item_title">EQ情商测试</view>
			   <view class="test_list_item_img">
			   	   <image src="../static/images/EQ.png" mode=""></image>
			   </view>			  
		   </view>
		   <!-- 3 -->
		   <view class="test_list_item">
			   <view class="test_list_item_title">职业性格测试</view>
			   <view class="test_list_item_img">
			   	   <image src="../static/images/disposition.png" mode=""></image>
			   </view>			  
		   </view>											
	   </view>
  </view>  
</view>
</template>
<script>
export default {
  name: "RecommendList",
  props: {
    recommendList: {
      type: Array,
      default: () => []
    },
    isSort: {
      type: Boolean,
      default: true
    }
  },
  data: function() {
    return {
		banner: [
			{pic:'../static/images/banner2.png'},
			{pic:'../static/images/banner1.png'},
			{pic:'../static/images/banner2.png'}			
		],
	};
  },
  methods:{

  }
};
</script>
<style lang="less"  scoped>
  image{width: 100%;height:100%;}
  .recommendList{
	.recommend_item{
		height:200rpx;
		margin-left: 32rpx;
		border-bottom: 1rpx solid #CDCDCD;
		.recommend_item_left{
			height:141rpx;
			width: 393rpx;
			// background-color: pink;
			margin-left:2rpx;
			.item_title{
				font-size: 34rpx;
				font-family: PingFangSC-Semibold, PingFang SC;
				font-weight: 600;
				color: #131313;
			}
			.item_down{
				margin-top: 12rpx;
				.img{
					width: 80rpx;
					height:39rpx;
				}
				text{
					font-size: 24rpx;
					font-family: PingFangSC-Regular, PingFang SC;
					font-weight: 400;
					color: #131313;
					line-height: 44rpx;	
					margin-right: 19rpx;
				}
			}
		}
		.recommend_item_right{
			width: 261rpx;
			height:140rpx;
			// background-color: pink;
			margin-left:30rpx;			
			margin-right:30rpx;
		}		
	}
  }

/* 轮播图 */
  .slider-banner{
    width: 687.14rpx;
	margin: 0 auto;
    height: 270rpx;
	// background-color: pink;
    background-size: 100%;
    margin-top: 31rpx;
	swiper{
		height: 270rpx;
	    border-radius: 20rpx;
	}
    image {
		width: 687.14rpx;
		height: 270rpx;
		border-radius: 18rpx;
    }	
  }
  // 医学咨询
  .information{
	width: 690rpx;
	margin:0 auto;	
	// background-color: pink;  
	margin-top: 30rpx; 
	.information_title{
		font-size: 34rpx;
		font-family: PingFangSC-Semibold, PingFang SC;
		font-weight: 600;
		color: #1F1F1F;
		margin-left:1rpx;	
	} 	 
	.information_img{
	    margin-top: 30rpx; 	
		image{
          width: 335rpx; 
          height: 181rpx; 			
		}	
	}
  }
  // 趣味测试
  .test{
	width: 690rpx;
	margin:0 auto;	  
	margin-top: 30rpx; 
	.test_title{
		font-size: 34rpx;
		font-family: PingFangSC-Semibold, PingFang SC;
		font-weight: 600;
		color: #1F1F1F;
		margin-left:1rpx;
	} 	 
	.test_list{
		margin-bottom: 78rpx;
    	.test_list_item{
			width: 100%;
			height: 200rpx;
			border-radius: 20rpx;
			margin-top: 64rpx; 
			position: relative;
			&:nth-of-type(1){
				background-color:#E1EBFF;
				margin-top: 57rpx; 
			}
			&:nth-of-type(2){
				background-color:#FFEEE3;
			}
			&:nth-of-type(3){
				background-color:#DFF0FF;
			}
			.test_list_item_title{
				line-height:200rpx;
				font-size: 34rpx;
				font-family: PingFangSC-Semibold, PingFang SC;
				font-weight: 600;
				color: #131313;
		    	margin-left:51rpx;	
			}
			.test_list_item_img{
				width: 196rpx;
				height: 219rpx;
				// z-index: 100;
				position: absolute;right: 47rpx;bottom:23rpx;
			}
	
		}
	}

  }
</style>
