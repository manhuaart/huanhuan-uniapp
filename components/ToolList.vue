<template>
<view>	
<!-- 工具列表 -->

  <!-- 膳食运动 -->
  <view class="tool acea-row-center">
      <view class="tool_item">
      	 <view class="tool_item_left">
			 <view>膳食</view><view>指数偏高</view><view><text>2486</text><text>kcal</text></view>
		 </view>
      	 <view class="tool_item_right">
      	 	 <image src="../static/images/meal.png" mode=""></image>
      	 </view>		 
      </view>
      <view class="tool_item">
      	 <view class="tool_item_left">
			 <view>运动</view><view>运动量偏少</view><view><text>2389</text><text>kcal</text></view>
		 </view>
      	 <view class="tool_item_right">
      	 	 <image src="../static/images/sport.png" mode=""></image>
      	 </view>      	
      </view>	  
  </view>
  <!-- 身体评估 -->
  <view class="physical">
	 <view class="physical_title">身体评估</view>
	 <!-- 滑动轮播图 -->
	 <view class="physical_scroll">
		  <scroll-view  scroll-x='true'  @scroll="scroll"  scroll-left="50" refresher-enabled="true"  refresher-background="black">
			<view class="tang">
		  		<image src="../static/images/physical1.png"></image>
		  	</view>
            <view class="tang">
	 	 	   <image src="../static/images/physical2.png"></image>
	 	    </view>
            <view class="tang">
	 	 	  <image src="../static/images/physical3.png"></image>
	    	</view>
            <view class="tang">
	 	 	   <image src="../static/images/physical4.png"></image>
	 	    </view>		
		  </scroll-view>				  
	 </view>
  </view>
  <!-- 趣味测试 -->
  <view class="test">
	   <view class="test_title">趣味测试</view>
	   <view class="test_list">
		   <!-- 1 -->
		   <view class="test_list_item">
			   <view class="test_list_item_title">安全感测试</view>
			   <view class="test_list_item_img">
			   	   <image src="../static/images/safe.png" mode=""></image>
			   </view>
		   </view>	 
		   <!-- 2 -->
		   <view class="test_list_item">
			   <view class="test_list_item_title">吸烟指数</view>
			   <view class="test_list_item_img">
			   	   <image src="../static/images/smock.png" mode=""></image>
			   </view>			  
		   </view>
		   <!-- 3 -->
		   <view class="test_list_item">
			   <view class="test_list_item_title">职业性格测试</view>
			   <view class="test_list_item_img">
			   	   <image src="../static/images/disposition.png" mode=""></image>
			   </view>			  
		   </view>	
		   <!-- 4 -->
		   <view class="test_list_item">
			   <view class="test_list_item_title">酒精依赖度测试</view>
			   <view class="test_list_item_img">
			   	   <image src="../static/images/alcohol.png" mode=""></image>
			   </view>			  
		   </view>
	       <!-- 5 -->
	       <view class="test_list_item">
				   <view class="test_list_item_title">尼古丁依赖度测试</view>
				   <view class="test_list_item_img">
				   	   <image src="../static/images/nicotine.png" mode=""></image>
				   </view>			  
	       </view>														  
	       <!-- 6 -->
	       <view class="test_list_item">
				   <view class="test_list_item_title">中医九种体质辨识</view>
				   <view class="test_list_item_img">
				   	   <image src="../static/images/medicine.png" mode=""></image>
				   </view>			  
	       </view>														  
	       <!-- 7 -->
	       <view class="test_list_item">
				   <view class="test_list_item_title">趣味性格测试</view>
				   <view class="test_list_item_img">
				   	   <image src="../static/images/interest.png" mode=""></image>
				   </view>			  
	       </view>														  
	       <!-- 8 -->
	       <view class="test_list_item">
				   <view class="test_list_item_title">EQ情商测试</view>
				   <view class="test_list_item_img">
				   	   <image src="../static/images/EQ.png" mode=""></image>
				   </view>			  
	       </view>															  
	       <!-- 9 -->
	       <view class="test_list_item">
				   <view class="test_list_item_title">DISC性格测试</view>
				   <view class="test_list_item_img">
				   	   <image src="../static/images/disc.png" mode=""></image>
				   </view>			  
	       </view>															  
	       <!-- 10 -->
	       <view class="test_list_item">
				   <view class="test_list_item_title">匹兹堡睡眠质量指数</view>
				   <view class="test_list_item_img">
				   	   <image src="../static/images/sleep.png" mode=""></image>
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
            scrollTop: 0,
            old: {
                scrollTop: 0
            },
		banner: [
			{pic:'../static/images/banner2.png'},
			{pic:'../static/images/banner1.png'},
			{pic:'../static/images/banner2.png'}			
		],
	};
  },
  methods:{
        scroll: function(e) {
            console.log(e)
            this.old.scrollTop = e.detail.scrollTop
        },
  }
};
</script>
<style lang="less"  scoped>
  image{width: 100%;height:100%;}
  .tool{
	  margin-top:36rpx;
     .tool_item{
		 width: 335rpx;
		 height: 220rpx;
		 border-radius: 20rpx;
		 display: flex;
		 justify-content: space-between;
		 &:nth-of-type(1){
			background: linear-gradient(149deg, #C6CFFD 0%, #F8F9FF 100%); 
		 }		 
		 &:nth-of-type(2){
		    background: linear-gradient(143deg, #DFDFFF 0%, #FAFAFF 100%);
			margin-left: 20rpx;
		 }
		 .tool_item_left{
			 // background-color: pink;
			 margin-left: 25rpx;
			 view:nth-of-type(1){
				 font-size: 34rpx;
				 font-family: PingFangSC-Semibold, PingFang SC;
				 font-weight: 600;
				 color: #3F3F3F;
				 margin-top: 32rpx;
			 }
			 view:nth-of-type(2){
				font-size: 24rpx;
				font-family: PingFangSC-Semibold, PingFang SC;
				font-weight: 600;
				color: #8C9AEA;
				margin-top: 3rpx;
			 }	
			 view:nth-of-type(3){
				margin-top: 26rpx;
				font-family: DINAlternate-Bold, DINAlternate;
				 text:nth-of-type(1){
					font-size: 40rpx;
					font-weight: bold;
					color: #131313;	 
				 }
				 text:nth-of-type(2){
					font-size: 24rpx;
					font-weight: bold;
					color: #131313;
					margin-left: 11rpx;
				 }				 
			 }					  
		 }
		 .tool_item_right{
			 width: 60rpx;
			 height: 60rpx;
			 margin-right: 60rpx;
			 margin-top: 36rpx;
		 }		 
	 }
  }
  // 身体测评
  .physical{
	width: 690rpx;
	margin:0 auto;	  
	margin-top: 55rpx; 
	.physical_title{
		font-size: 34rpx;
		font-family: PingFangSC-Semibold, PingFang SC;
		font-weight: 600;
		color: #1F1F1F;
		margin-left:1rpx;
	} 	
	.physical_scroll{
		 height: 161rpx;
		 width: 100%;
	     margin-top: 25rpx; 
        scroll-view{
	        width: 690rpx;
			height: 300rpx;
			white-space: nowrap;
			.tang{
				width:260rpx;
				height: 161rpx;	
				margin-left: 20rpx;
				&:nth-of-type(1){margin-left: 0}
				display: inline-block;
			}			
	   }		
		
	}
  }
  //--------------------------------
   .container {
      width: 690rpx;
	  height: 161rpx;
	  overflow-x:  scroll;
      padding-bottom: 20rpx;
      background: #FD9494;
  }
  
  .content {
	  width:260rpx;
	  height: 161rpx;	
      background: #ddd;
      border-radius: 16rpx;
      font-size: 34rpx;
      text-align: center;
  }
// -----------------------------------------------------
  // 趣味测试
  .test{
	width: 690rpx;
	margin:0 auto;	  
	margin-top: 51rpx; 
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
				background-color:#EDFFF7;
				margin-top: 57rpx; 
			}
			&:nth-of-type(2){
				background-color:#F0F0FF;
			}
			&:nth-of-type(3){
				background-color:#DFF0FF;
			}
			&:nth-of-type(4){
				background-color:#FFF0F0;
			}
			&:nth-of-type(5){
				background-color:#EDFCFF;
			}	
			&:nth-of-type(6){
				background-color:#EEF3FF;
			}
			&:nth-of-type(7){
				background-color:#FFFCCF;
			}
			&:nth-of-type(8){
				background-color:#FFEEE3;
			}
			&:nth-of-type(9){
				background-color:#FFF0F0;
			}
			&:nth-of-type(10){
				background-color:#E1EBFF;
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
