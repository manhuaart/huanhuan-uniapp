<template>
<!-- 我的银行卡 start -->
<view class="box">
				<view class="bxre" v-for="(item,index) in list" :key="index">
					<view :style="item.txtStyle" class="card" @touchstart="touchS" @touchmove="touchM" :data-index="index" @touchend="touchE">
						<view class="top">
							<view class="right">
								<view class="title">{{item.backName}}</view>
								<text>储蓄卡</text>
							</view>
						</view>
					</view>
					<view class="del">
						<view></view>
						<view class="right" @tap="delItem()">删除</view>
					</view>
				</view>
</view>
<!-- 我的银行卡 end -->
</template>

<script>
	export default {
		data() {
			return {
				delBtnWidth: 100, //删除按钮宽度单位（rpx）
				startX: '',
				//新加
				list: [
			        { backName: '中国建设银行1', left: 0 },
			        { backName: '中国建设银行2', left: 0 },
			        { backName: '中国建设银行3', left: 0 },
			        { backName: '中国建设银行4', left: 0 }		
				],
			}
		},
		onLoad() {
			// this.userid = uni.getStorageSync('userid')
			// this.bankList()
		},
		onShow() {
			// this.bankList()
		},
		methods: {
			//获取数据列表
			// bankList() {
			// 	let data = {
			// 		userId: this.userid
			// 	}
			// 	this.$LoadingMsg('获取数据中')
			// 	this.$Request.getToken(this.$api.userBackList, data).then(res => {
			// 		if (res.code == 0) {
			// 			uni.hideLoading()
			// 			this.list = res.data
			// 			for (let i in res.data) {
			// 				res.data[i].txtStyle = 'left:0px'
			// 			}
			// 			this.list = res.data
			// 		}
			// 	})
			// },
			touchS: function(e) {
				// console.log("drawStart");
				var touch = e.touches[0];
				for (var index in this.list) {
				    this.list[index].left = 0;
				}
				this.startX = touch.clientX;
				console.log(this.startX);
				
				// console.log('touchS')
				// if (e.touches.length == 1) {
				// 	//设置触摸起始点水平方向位置
				// 	this.startX = e.touches[0].clientX
				// 	// console.log(this.startX)
				// }
			},
			touchM: function(e) {
				// console.log(e.touches.length)
				if (e.touches.length == 1) {
					//手指移动时水平方向位置
					var moveX = e.touches[0].clientX;
					//手指起始点位置与移动期间的差值
					var disX = this.startX - moveX;
					var delBtnWidth = this.delBtnWidth;
					var txtStyle = "";
					if (disX == 0 || disX < 0) { //如果移动距离小于等于0，说明向右滑动，文本层位置不变
						txtStyle = "left:0px";
					} else if (disX > 0) { //移动距离大于0，文本层left值等于手指移动距离
						txtStyle = "left:-" + disX + "px";
						if (disX >= delBtnWidth) {
							//控制手指移动距离最大值为删除按钮的宽度
							txtStyle = "left:-" + delBtnWidth + "px";
						}
					}
					//获取手指触摸的是哪一项
					var index = e.currentTarget.dataset.index;
					var list = this.list;
					console.log(index)
					list[index].txtStyle = txtStyle;
					// console.log(list[index].txtStyle)
					//更新列表的状态
					this.list = list;
				}
			},
			touchE: function(e) {
				// console.log('touchE')
				if (e.changedTouches.length == 1) {
					//手指移动结束后水平位置
					var endX = e.changedTouches[0].clientX;
					//触摸开始与结束，手指移动的距离
					var disX = this.startX - endX;
					var delBtnWidth = this.delBtnWidth;
					//如果距离小于删除按钮的1/2，不显示删除按钮
					var txtStyle = disX > delBtnWidth / 2 ? "left:-" + delBtnWidth + "px" : "left:0px";
					//获取手指触摸的是哪一项
					var index = e.currentTarget.dataset.index;
					var list = this.list;
					list[index].txtStyle = txtStyle;
					// console.log(list[index].txtStyle)
					//更新列表的状态{
					this.list = list
				}
			},
			//点击删除按钮事件
			delItem() {
				console.log("删除吗？")
			},
		}
	}
</script>

<style lang="scss">
	page {
		background: #F8F8F8;
	}
		.box {
			margin: 0 35rpx;
			margin-bottom: 20rpx;
			.bxre {
				position: relative;
				.card {
					width: 100%;
					height: 150rpx;
					background-image: linear-gradient(90deg,#ff5252 0%,#9a0606 100%);
					border-radius: 20rpx;
					position: relative;
					margin-bottom: 20rpx;
					z-index: 999;
					.top {
						display: flex;
						flex-direction: row;
						align-items: center;
						padding-left: 35rpx;
						padding-top: 28rpx;

						image {
							width: 50rpx;
							height: 50rpx;
						}
						.right {
							margin-left: 20rpx;
							.title {
								font-size: 24rpx;
								line-height: 24rpx;
								color: #FFFFFF;
							}
							text {
								display: block;
								font-size: 20rpx;
								line-height: 20rpx;
								margin-top: 10rpx;
								color: #FFFFFF;
							}
						}
					}
					.bottom-card {
						position: absolute;
						right: 63rpx;
						bottom: 52rpx;
						color: #FFFFFF;
					}
				}

				.del {
					width:150rpx;
					height: 150rpx;
					background-color: #ff4f4f;
					border-radius: 20rpx;
					position: absolute;
					top: 0;
					right: 0;
					z-index: 1;
					text-align: right;
					line-height: 150rpx;
					display: flex;
					flex-direction: row;
					align-items: center;
					justify-content: space-between;

					.right {
						color: #fefefe;
						font-size: 28rpx;
						margin-right: 40rpx;
					}
				}
			}

		}
</style>


