<template>
 <view class="healthRecords">
	 <!-- ----------------------- -->
     <view class="file">
     	 <view class="file_title acea-row-between">
     	 	 <view class="file_title_name">
     	 	 	   <view>姓名</view><view>LUCKY</view>
     	 	 </view>
     	 	 <view class="file_title_sex">
     	 	 	   <view>性别</view><view>女</view>
     	 	 </view>
     	 	 <view class="file_title_age">
     	 	 	   <view>年龄</view><view>36</view>
     	 	 </view>						 
     	 </view>
		 <view class="file_list">
			 <!-- 诊断 -->
		 	  <view class="file_list_item  acea-row-between">
		 	  	  <view class="file_list_item_name">诊断</view>
				  <view class="file_list_item_right acea-line-height">
					  <view>DM、乳腺癌D</view>
					  <view class="file_list_item_right_img">
						  <image src="../../../static/icon/arrow_right.png" mode=""></image>
					  </view>
				  </view>
		 	  </view>
			  <!-- 治疗 -->
		 	  <view class="file_list_item  acea-row-between">
		 	  	  <view class="file_list_item_name">治疗</view>
				  <view class="file_list_item_right acea-line-height">
					  <view>化疗、手术</view>
					  <view class="file_list_item_right_img">
						  <image src="../../../static/icon/arrow_right.png" mode=""></image>
					  </view>
				  </view>
		 	  </view>
			  <!-- 家族史 -->
		 	  <view class="file_list_item  acea-row-between">
		 	  	  <view class="file_list_item_name">家族史</view>
				  <view class="file_list_item_right acea-line-height">
					  <view>高血压</view>
					  <view class="file_list_item_right_img">
						  <image src="../../../static/icon/arrow_right.png" mode=""></image>
					  </view>
				  </view>
		 	  </view>
			  <!-- 过敏史 -->
		 	  <view class="file_list_item  acea-row-between">
		 	  	  <view class="file_list_item_name">过敏史</view>
				  <view class="file_list_item_right acea-line-height">
					  <view>青霉素</view>
					  <view class="file_list_item_right_img">
						  <image src="../../../static/icon/arrow_right.png" mode=""></image>
					  </view>
				  </view>
		 	  </view>
			  <!-- 日常生活史 -->
		 	  <view class="file_list_item  acea-row-between">
		 	  	  <view class="file_list_item_name">日常生活史</view>
				  <view class="file_list_item_right acea-line-height">
					  <view>饮酒</view>
					  <view class="file_list_item_right_img">
						  <image src="../../../static/icon/arrow_right.png" mode=""></image>
					  </view>
				  </view>
		 	  </view>	
		 </view>
		 <!-- 监测指标 -->
		 <view class="index">
		 	 <view class="index_title">监测指标</view>
			 <view class="index_tab">
				<view class="index_tab_title acea-row-center">
				　　<view @tap="change(0)" :class="{btna:btnnum == 0}">膳食<i v-if='btnnum == 0'></i> </view>
				  　<view @tap="change(1)" :class="{btna:btnnum == 1}">运动<i v-if='btnnum == 1'></i></view>
				</view>
				<!-- 膳食内容 -->
				<view class="end-cont" v-if="btnnum == 0">
				 　　<view class="end-cont_time   acea-row-between">
							<view class="shijian">时间</view>
							<view class="end-cont_right acea-line-height">
								<view>2020.01.01-2020.01.07</view>
								<view class="end-cont_right_img">
									<image src="../../../static/icon/arrow_right.png" mode=""></image>
								</view>
							</view> 
				     </view>
					 <!-- 监测指标 -->
					 <view class="end-cont_index">
					 	    <view class="end-cont_index_title">监测指标</view>
							<!-- 图表 -->
					 		<view class="end-cont_chart">

					 		</view>
					 </view> 
					 <!-- 膳食日记 --> 
					 <view class="dietDiary">
					 	  <view class="dietDiary_title">膳食日记</view>
						  <view class="dietDiary_list">
							  <view class="dietDiary_list_item acea-row-between"  @tap="goDiet()">
								    <view>2020年1月1日</view>
								    <view class="dietDiary_list_item_right  acea-line-height">
								    	 <view>详情</view>
										 <view>
											<image src="../../../static/icon/arrow_right.png" mode=""></image>
										 </view>
								    </view>									
							  </view>
							  <view class="dietDiary_list_item acea-row-between">
							  								    <view>2020年1月1日</view>
							  								    <view class="dietDiary_list_item_right  acea-line-height">
							  								    	 <view>详情</view>
							  										 <view>
							  											<image src="../../../static/icon/arrow_right.png" mode=""></image>
							  										 </view>
							  								    </view>									
							  </view>
							  <view class="dietDiary_list_item acea-row-between">
							  								    <view>2020年1月1日</view>
							  								    <view class="dietDiary_list_item_right  acea-line-height">
							  								    	 <view>详情</view>
							  										 <view>
							  											<image src="../../../static/icon/arrow_right.png" mode=""></image>
							  										 </view>
							  								    </view>									
							  </view>
							  <view class="dietDiary_list_item acea-row-between">
							  								    <view>2020年1月1日</view>
							  								    <view class="dietDiary_list_item_right  acea-line-height">
							  								    	 <view>详情</view>
							  										 <view>
							  											<image src="../../../static/icon/arrow_right.png" mode=""></image>
							  										 </view>
							  								    </view>									
							  </view>
						  </view>
					 </view>
				</view>	
				<view class="end-cont"  v-if="btnnum == 1">
<view class="end-cont_time   acea-row-between">
							<view class="shijian">时间</view>
							<view class="end-cont_right acea-line-height">
								<view>2020.01.01-2020.01.07</view>
								<view class="end-cont_right_img">
									<image src="../../../static/icon/arrow_right.png" mode=""></image>
								</view>
							</view> 
				     </view>
					 <!-- 监测指标 -->
					 <view class="end-cont_index">
					 	    <view class="end-cont_index_title">监测指标</view>
							<!-- 图表 -->
					 		<view class="end-cont_chart">

					 		</view>
					 </view> 
					 <!-- 运动记录 --> 
					 <view class="dietDiary">
					 	  <view class="dietDiary_title">运动记录</view>
						  <view class="dietDiary_list">
							  <view class="dietDiary_list_item acea-row-between" @tap="goSport">
								    <view>2020年1月1日</view>
								    <view class="dietDiary_list_item_right  acea-line-height">
								    	 <view>详情</view>
										 <view>
											<image src="../../../static/icon/arrow_right.png" mode=""></image>
										 </view>
								    </view>									
							  </view>
							  <view class="dietDiary_list_item acea-row-between">
							  								    <view>2020年1月1日</view>
							  								    <view class="dietDiary_list_item_right  acea-line-height">
							  								    	 <view>详情</view>
							  										 <view>
							  											<image src="../../../static/icon/arrow_right.png" mode=""></image>
							  										 </view>
							  								    </view>									
							  </view>
							  <view class="dietDiary_list_item acea-row-between">
							  								    <view>2020年1月1日</view>
							  								    <view class="dietDiary_list_item_right  acea-line-height">
							  								    	 <view>详情</view>
							  										 <view>
							  											<image src="../../../static/icon/arrow_right.png" mode=""></image>
							  										 </view>
							  								    </view>									
							  </view>
							  <view class="dietDiary_list_item acea-row-between">
							  								    <view>2020年1月1日</view>
							  								    <view class="dietDiary_list_item_right  acea-line-height">
							  								    	 <view>详情</view>
							  										 <view>
							  											<image src="../../../static/icon/arrow_right.png" mode=""></image>
							  										 </view>
							  								    </view>									
							  </view>
						  </view>
					 </view>
				</view>						 
				</view> 	
			 </view>
		 </view>
     </view>
 </view>
</template>

<script>
	export default {
		data() {
			return {
		    	btnnum: 0,
			}
		},
		onLoad() {

		},
		methods: {
		   change(e) {
			  this.btnnum = e
			  console.log(this.btnnum)
		  },
		  goDiet(){
			  uni.navigateTo({
			     url: '/pages/user/Diet/index'
			  });	
		  },
		  goSport(){
		  			  uni.navigateTo({
		  			     url: '/pages/user/sport/index'
		  			  });				  
		  }
		}
	}
</script>

<style lang="less"  scoped>
 image{ width: 100%;height: 100%;vertical-align: top}
 .healthRecords{
	width: 100%;	
	.file{
		width: 100%;
        background: #FFFFFF;
        background: pink;		
        border-radius: 50rpx 50rpx 0rpx 0rpx;
		.file_title{
			.file_title_name,
			.file_title_sex,
			.file_title_age
			{
				margin-top:34rpx;
				width: 150rpx;
				text-align: center;
				 view:nth-of-type(1){
			       font-size: 30rpx;
			       font-family: PingFangSC-Semibold, PingFang SC;
			       font-weight: 600;
			       color: #9F9F9F;	
				 }
				 view:nth-of-type(2){
					font-size: 34rpx;
					font-family: PingFangSC-Semibold, PingFang SC;
					font-weight: 600;
					color: #131313; 
					margin-top:15rpx;
				 }				 
			}
			.file_title_name{
				margin-left: 85rpx;
			}		
			.file_title_age{
				margin-right: 85rpx;
			}					
		}
		.file_list{
			width: 690rpx;
			margin:0 auto;
           .file_list_item{
				width: 100%;
				height: 110rpx;
				background: #FFFFFF;
				box-shadow: 0rpx 4rpx 24rpx 0rpx rgba(0, 0, 0, 0.08);
				border-radius: 20rpx;
				margin-top:20rpx;
				&:nth-of-type(1){margin-top:60rpx;}
				.file_list_item_name{
					font-size: 34rpx;
					font-family: PingFangSC-Semibold, PingFang SC;
					font-weight: 600;
					color: #131313;
					margin-left:36rpx;
				}
				.file_list_item_right{
					line-height: 110rpx;
					font-size: 34rpx;
					font-family: PingFangSC-Regular, PingFang SC;
					font-weight: 400;
					color: #797979;	
					.file_list_item_right_img{
							width: 19rpx;
							height: 33rpx;
							margin-left: 38rpx;
							margin-right: 32rpx;
					}
				}
				
		   }	   
		}
		// 监测指标
		.index{
			.index_title{
				height: 89rpx;
				line-height: 89rpx;
				font-size: 34rpx;
				font-family: PingFangSC-Semibold, PingFang SC;
				font-weight: 600;
				color: #131313;	
				margin-left: 48rpx;
			}
			.index_tab{
				width: 690rpx;
				margin:0 auto;
				margin-bottom: 169rpx;
				background: #FFFFFF;
				box-shadow: 0rpx 4rpx 24rpx 0rpx rgba(0, 0, 0, 0.08);
				border-radius: 20rpx;
				    .index_tab_title{
						height: 141rpx;
						width: 100%;
						font-size: 34rpx;
						font-family: PingFangSC-Semibold, PingFang SC;
						font-weight: 600;
						color: #131313;
						view{
							width: 88rpx;
							text-align: center;
							i{
								width: 46rpx;
								height: 8rpx;
								background: #fff;
								margin: 0 auto;
								margin-top: 8rpx;		
                                background: linear-gradient(149deg, #809CFF 0%, #BFCEFF 100%);
							}
						}	
						view:nth-of-type(2){
							margin-left: 60rpx;
						}			
					}
					/* 将两个内容view的display设置为none */
				    .end-cont{
				        // display: none;
				        .end-cont_time{
							width: 644rpx;
							height:109rpx;
							border-top: 1rpx solid #E3E3E3;
							border-bottom: 1rpx solid #E3E3E3;	
							margin-left:46rpx;
								.shijian{
									font-size: 34rpx;
									font-family: PingFangSC-Semibold, PingFang SC;
									font-weight: 600;
									color: #131313;
									margin-left: 2rpx;
								}
								.end-cont_right{
										font-size: 30rpx;
										font-family: PingFangSC-Regular, PingFang SC;
										font-weight: 400;
										color: #131313;
										.end-cont_right_img{
											width: 19rpx;
											height:33rpx;
											margin-right: 31rpx;
											margin-left:33rpx;
										}								
							    }						
						}
						.end-cont_index{
							width:100%;
							.end-cont_index_title{
								font-size: 34rpx;
								font-family: PingFangSC-Semibold, PingFang SC;
								font-weight: 600;
								color: #131313;
								margin-top: 22rpx;
								margin-left: 42rpx;
							}	
				            .end-cont_chart{
								width: 540rpx;
								height: 396rpx;
								margin:0 auto;
								margin-top: 23rpx;
								background-color:#FF9797;
							}								
						}
						.dietDiary{
							width: 644rpx;
							margin-left: 46rpx;
							.dietDiary_title{
								font-size: 34rpx;
								font-family: PingFangSC-Semibold, PingFang SC;
								font-weight: 600;
								color: #131313;
								margin-top:60rpx;
							}
							.dietDiary_list{
								margin-top: 26rpx;
								.dietDiary_list_item{
									 width: 100%;
									 height: 109rpx;
									 border-top:1rpx solid #E3E3E3;
									 font-size: 30rpx;
									 font-family: PingFangSC-Regular, PingFang SC;
									 font-weight: 400;
									 color: #131313; 
									 .dietDiary_list_item_right{
										   view:nth-of-type(2){
											   width: 19rpx;
											   height: 33rpx;
											   margin-left: 33rpx;
											   margin-right: 31rpx;
										   }
									 }									 
								}
							}							
						}
				    }
				    .btna{
						font-size: 44rpx;
						font-family: PingFangSC-Semibold, PingFang SC;
						font-weight: 600;
						color: #4C72DE;
						// border-bottom:8rpx solid #809CFF;
				    }
				    .dis{
				        display: block;
				    } 
			}			
		}		
	}
 }
</style>
