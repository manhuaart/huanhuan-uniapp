<template>
<view>	
  <!-- 百科列表 -->
  <view class="baikeList">
    <view class="baike_item acea-row-between">
		<view class="baike_item_left">
			<view class="item_title">心肌梗死（myocardial infarction）概述</view>
			<view class="item_down acea-row-between">
				<view class="img"><image src="../static/images/zding@2x.png" mode=""></image></view>
			   	<text>1122阅读</text>
			</view>
		</view>  
		<view class="baike_item_right">
			<image src="../static/images/items.png" mode=""></image>
		</view> 		
	</view>
    <view class="baike_item acea-row-between">
		<view class="baike_item_left">
			<view class="item_title">什么是心脏病?并发症都有哪些?</view>
			<view class="item_down acea-row-between">
				<view class="img"><image src="../static/images/zding@2x.png" mode=""></image></view>
			   	<text>1122阅读</text>
			</view>
		</view>  
		<view class="baike_item_right">
			<image src="../static/images/items2.png" mode=""></image>
		</view> 		
	</view>
    <view class="baike_item acea-row-between">
		<view class="baike_item_left">
			<view class="item_title">
				心肌梗死（myocardial infarction）概述
			</view>
			<view class="item_down acea-row-between">
				<view class="img"><image src="../static/images/zding@2x.png" mode=""></image></view>
			   	<text>1122阅读</text>
			</view>
		</view>  
		<view class="baike_item_right">
			<image src="../static/images/items.png" mode=""></image>
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
    <view class="baike_item acea-row-between">
		<view class="baike_item_left">
			<view class="item_title">
				心肌梗死（myocardial infarction）概述
			</view>
			<view class="item_down acea-row-between">
				<!-- <view class="img"><image src="../static/images/zding@2x.png" mode=""></image></view> -->
			   	<view class="item_down_left">
					<text class="name">萌妹纸</text>
					<text class="reader">1122阅读</text>			   		
			   	</view>
				<text>11小时前</text>
			</view>
		</view>  
		<view class="baike_item_right">
			<image src="../static/images/items2.png" mode=""></image>
		</view> 		
	</view>
    <view class="baike_item acea-row-between">
		<view class="baike_item_left">
			<view class="item_title">
				心肌梗死（myocardial infarction）概述
			</view>
			<view class="item_down acea-row-between">
				<!-- <view class="img"><image src="../static/images/zding@2x.png" mode=""></image></view> -->
			   	<view class="item_down_left">
					<text class="name">王氏说法</text>
					<text class="reader">335阅读</text>			   		
			   	</view>
				<text>5小时前</text>
			</view>
		</view>  
		<view class="baike_item_right">
			<image src="../static/images/items2.png" mode=""></image>
		</view> 		
	</view>
    <view class="baike_item acea-row-between">
		<view class="baike_item_left">
			<view class="item_title">什么是心脏病?并发症都有哪些?</view>
			<view class="item_down acea-row-between">
				<view class="img"><image src="../static/images/zding@2x.png" mode=""></image></view>
			   	<text>1122阅读</text>
			</view>
		</view>  
		<view class="baike_item_right">
			<image src="../static/images/items2.png" mode=""></image>
		</view> 		
	</view>
  </view>
</view>
</template>
<script>
export default {
  name: "baikeList",
  props: {
    baikeList: {
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
  .baikeList{
	.baike_item{
		margin-bottom: 40rpx;
		height:200rpx;
		margin-left: 32rpx;
		border-bottom: 1rpx solid #CDCDCD;
		.baike_item_left{
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
				.item_down_left{
					.name{
					    color: #979797;
						margin-right: 0;
					}
					.reader{
					    color: #979797;
						margin-right: 0;
						margin-left: 13rpx;
					}
				}
			}
		}
		.baike_item_right{
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
    height: 220rpx;
	// background-color: pink;
    background-size: 100%;
    margin-top: 31rpx;
	swiper{
		height: 220rpx;
	    border-radius: 20rpx;
	}
    image {
		width: 687.14rpx;
		height: 220rpx;
		border-radius: 18rpx;
    }	
  }
</style>
