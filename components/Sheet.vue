<template>
	<view>
		<view class="tui-actionsheet" :class="[show?'tui-actionsheet-show':'']">
			<view class="tui-actionsheet_button acea-row-between">
				 <view :hover-stay-time="150" v-if="isCancel" @tap="handleClickCancel">取消</view>
				 <view :hover-stay-time="150" v-if="isFinsh" @tap="handleClickFinsh">完成</view>		
			</view>			
<!-- 			<view class="tui-tips" :style="{fontSize:size+'rpx',color:color}" v-if="tips">
				{{tips}}
			</view> -->
			<view :class="[isCancel?'tui-operate-box':'']">
				<block v-for="(item,index) in itemList" :key="index">
					<view class="tui-actionsheet-btn"   
						:class="{'tui-actionsheet-hovers':clicked==index}"
						hover-class="tui-actionsheet-hover" :hover-stay-time="150" :data-index="index"
						 @tap="handleClickItem">{{item.text}}</view>
				</block>
			</view>
		</view>
		<view class="tui-actionsheet-mask" :class="[show?'tui-mask-show':'']" @tap="handleClickMask"></view>
	</view>
</template>
 
<script>
	export default {
		name: "tuiActionsheet",
		data(){
			return{
				clicked:undefined,	
			}
		},
		props: {
			//点击遮罩 是否可关闭
			maskClosable: {
				type: Boolean,
				default: true
			},
			//显示操作菜单
			show: {
				type: Boolean,
				default: false
			},
			//菜单按钮数组，自定义文本颜色，红色参考色：#e53a37
			itemList: {
				type: Array,
				default: function() {
					return [{
						text: "测试",
						// color: "#929292"
					}]
				}
			},
			//提示文字
			// tips: {
			// 	type: String,
			// 	default: ""
			// },
			//提示文字颜色
			// color: {
			// 	type: String,
			// 	default: "#9a9a9a"
			// },
			//提示文字大小 rpx
			// size: {
			// 	type: Number,
			// 	default: 26
			// },
			//是否需要取消按钮
			isCancel: {
				type: Boolean,
				default: true
			},
			//是否需要完成按钮
			isFinsh:{
				type: Boolean,
				default: true
			},
		},
		methods: {
			handleClickMask() {
				if (!this.maskClosable)  return;
				this.handleClickCancel();
			},
			handleClickItem(e) {
				if (!this.show) return;
				const dataset = e.currentTarget.dataset;
				 this.clicked = dataset.index;
				 console.log(this.clicked)
				this.$emit('chooseItem', {
					index: dataset.index
				});
			},
			handleClickCancel() {
				this.$emit('chooseCancel');
				this.clicked = -1;
			},
			handleClickFinsh(){
				this.$emit('chooseFinsh');
			}
		}
	}
</script>
 
<style lang="less">
.tui-actionsheet {
		width: 100%;
		position: fixed;
		left: 0;
		right: 0;
		bottom: 0;
		z-index: 9999;
		visibility: hidden;
		transform: translate3d(0, 100%, 0);
		transform-origin: center;
		transition: all 0.3s ease-in-out;
		background: #FFFFFF;
		min-height: 100rpx;
		
		.tui-actionsheet_button{
			width: 100%;
			height: 103rpx;
			background-color: #FFFFFF;
			border-bottom: 1rpx solid #DFDFDF;
			font-size: 34rpx;
			font-family: PingFangSC-Regular, PingFang SC;
			font-weight: 400;
			color: #959595;
			padding-left:60rpx;
			padding-right:60rpx;
			box-sizing: border-box;
			view:nth-of-type(2){
				color: #4466B9;
			}
		}
}
	.tui-actionsheet-show {
		transform: translate3d(0, 0, 0);
		visibility: visible;
	}
	.tui-operate-box {
		padding-bottom: 60rpx;
	}
	// .tui-tips {
	// 	width: 100%;
	// 	padding: 30rpx 60rpx;
	// 	box-sizing: border-box;
	// 	text-align: center;
	// 	background: #fff;
	// 	display: flex;
	// 	align-items: center;
	// 	justify-content: center;
	// }

	.tui-actionsheet-btn {
		width: 100%;
		height: 100rpx;
		display: flex;
		align-items: center;
		justify-content: center;
		text-align: center;
		font-family: PingFangSC-Semibold, PingFang SC;
		font-weight: 600;
		font-size: 36rpx;
        color: #929292;
	}

	.tui-btn-last {
		background-color: plum;
		padding-bottom: env(safe-area-inset-bottom);
	}
	.tui-actionsheet-hover,.tui-actionsheet-hovers{
		color:#1A1A1A;
        font-size: 40rpx;
		background-color: #F2F2F2;
	}
	.tui-actionsheet-mask {
		position: fixed;
		top: 0;
		left: 0;
		right: 0;
		bottom: 0;
		background: rgba(0, 0, 0, 0.6);
		z-index: 8888;
		transition: all 0.3s ease-in-out;
		opacity: 0;
		visibility: hidden;
	}
 
	.tui-mask-show {
		opacity: 1;
		visibility: visible;
	}
</style>