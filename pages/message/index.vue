<template>
<view class="html">
		<view class="order-item" v-for="(item, index) in dataList"   :key="index">
			<view class="left"  :data-index="index"   @touchstart="drawStart" 
			      @touchmove="drawMove" @touchend="drawEnd" 
				  :style="{ left: item.left + 'rpx' }">{{ item.content }}
		    </view>
			<view class="you">
				 <view class="remove" @click="delItem">删除</view>
			</view>
		</view>	
</view>
</template>

<script>
	export default {
		data() {
			return {
                delBtnWidth: 160,
                dataList: [
                    { content: '1', left: 0 },
                    { content: '2', left: 0 },
                    { content: '3', left: 0 },
                    { content: '4', left: 0 },
                    { content: '5', left: 0 },
                    { content: '6', left: 0 },
                    { content: '7', left: 0 },
                ],
				startX: '',
			}
		},
		onLoad: function() {

		},
		methods: {
			// 当手指触摸屏幕时候触发
                drawStart: function(e) {
                    var touch = e.touches[0];
                    for (var index in this.dataList) {
                        this.dataList[index].left = 0;
                    }
                    this.startX = touch.clientX;
                },
				// 当手指在屏幕上滑动的时候连续地触发
                drawMove: function(e) {
                    var touch = e.touches[0];
                    var item = this.dataList[e.currentTarget.dataset.index];
                    var disX = this.startX - touch.clientX;
                    if (disX >= 20) {
                        if (disX > this.delBtnWidth) {
                            disX = -this.delBtnWidth;
                        }
                        item.left = -disX;
                    }
					// if (disX < 0) { 
					// 	 // console.log(disX)
					// 	//如果移动距离小于等于0，说明向右滑动，文本层位置不变
					// 	item.left = 0;
					// }
					 else {
                            item.left = 160;
                    }		

                },
				// 当手指从屏幕上离开的时候触发
                drawEnd: function(e) {
                    var item = this.dataList[e.currentTarget.dataset.index];
						  console.log(item.left)
                          if (item.left <= this.delBtnWidth / 2) {
                              item.left = -this.delBtnWidth;
                          } else {
                              item.left = 0;
                          }  
                },
                delItem() { console.log('点击删除按钮') }
		}
	}
</script>

<style lang="less" scoped>
	.order-item {
		height: 84rpx;
		width: 587rpx;
		margin: 0 auto;
		margin-bottom: 10rpx;
		display: flex;
		align-items: center;
		justify-content: space-between;
		position: relative;
	}
	.left{
		height: 100%;
		width: 100%;
		position: absolute;
		left:0;
		background-color: #F1F1F1;
		z-index: 999;
	}
    .you{
		background-color: hotpink;
	}
	.remove {
		width: 160rpx;
		height: 100%;
		background-color: #E75454;
		color: white;
		position: absolute;
		top: 0;right: 0;
		display: flex;
		justify-content: center;
		align-items: center;
		z-index: 1;
	}
</style>
