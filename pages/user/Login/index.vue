<template>
 <view class="loginPage">
    <view class="login">
     	 <view class="login_title">快速登陆注册</view>
		 <view class="login_input">
		 	 <view class="login_input_phone acea-row-between">
		 	 	  <input type="text"   placeholder="请输入手机号" placeholder-style="color:#B7B7B7;font-size: 36rpx;"/>
		 	      <view class="sendCode">发送验证码</view>  
			 </view>
		 	 <view class="login_input_code">
		 	 	  <input type="text"   placeholder="请输入验证码" placeholder-style="color:#B7B7B7;font-size: 36rpx;"/>
		 	 </view>			 
		 </view>
		 <view class="login_check acea-line-height">
		 	 <view class="login_check_img">
		 	 	 <image src="../../../static/icon/chenckF.png" mode=""></image>
		 	     <!-- <image src="../../../static/icon/chenckT.png" mode=""></image> -->
			 </view>
		 	 <view class="login_check_text">
		 	 	<text>已阅读并同意</text><text>《用户服务手册》</text><text>的相关规则</text>
		 	 </view>			 
		 </view>
		 <view class="login_button">快速登录</view>
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

		}
	}
</script>

<style lang="less"  scoped>
 image{ width: 100%;height: 100%;}
.loginPage{
	width: 100%;
	.login{
		width: 610rpx;
		margin:0 auto;
	    // background-color: pink;
		.login_title{
			font-size: 48rpx;
			font-family: PingFangSC-Semibold, PingFang SC;
			font-weight: 600;
			color: #131313;
		}
		.login_input{
			.login_input_phone{
				width: 100%;
				height: 85rpx;
				margin-top: 105rpx;
				border-bottom: 1rpx solid #E0E0E0;	
			    input{
					height: 100%;
					// background-color: hotpink;
				}
				.sendCode{
					width: 200rpx;
					height: 60rpx;
					text-align: center;
					line-height: 60rpx;
		        	letter-spacing: 2rpx;					
					background: linear-gradient(142deg, #5E8FEC 0%, #4465D8 100%);
					box-shadow: 0rpx 4rpx 10rpx 0rpx rgba(68, 101, 216, 0.5);
					border-radius: 55rpx;
					font-size: 28rpx;
					font-family: PingFangSC-Regular, PingFang SC;
					font-weight: 400;
					color: #FFFFFF;					
				}	
			}
			.login_input_code{
				width: 100%;
				height: 85rpx;
				margin-top: 50rpx;
				border-bottom: 1rpx solid #E0E0E0;	
			    input{
					height: 100%;
					// background-color: hotpink;
				}								
			}
		}
		.login_check{
			margin-top: 38rpx;
			.login_check_img{
				width: 31rpx;
				height: 31rpx;	
				border-radius: 50%;
				image{border-radius: 50%; vertical-align: top}
			}
			.login_check_text{
				height: 31rpx;	
				line-height: 30rpx;
				margin-left: 13rpx;
				font-size: 28rpx;
				font-family: PingFangSC-Regular, PingFang SC;
				font-weight: 400;
				color: #B7B7B7;
				text:nth-of-type(2){color:#4465D8;margin-left: 3rpx;margin-right: 3rpx;}
			}		
		}
		.login_button{
			width: 610rpx;
			height: 110rpx;
			line-height: 110rpx;
			text-align: center;
			letter-spacing: 4rpx;
			background: linear-gradient(142deg, #5E8FEC 0%, #4465D8 100%);
			box-shadow: 0rpx 4rpx 10rpx 0rpx rgba(68, 101, 216, 0.5);
			border-radius: 55rpx;
			margin-top: 65rpx;
			font-size: 34rpx;
			font-family: PingFangSC-Medium, PingFang SC;
			font-weight: 500;
			color: #FFFFFF;
		}
	}
	
}
</style>
