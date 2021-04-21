<template>
	<!-- 查看日志 -->
	<view class="viewlog">
		<!-- 时间-日期 -->
		<view class="viewlog_head">

		</view>
		<!-- 中心内容 -->
		<view class="viewlog_content">
			<!-- item -->
			<view class="viewlog_content_item"  v-for="items in morning" :key="morning.id">
				<view class="viewlog_content_item_left">
					<image src="../../../static/icon/morning.png" mode=""></image>
				</view>
				<view class="viewlog_content_item_right">
					<view class="viewlog_content_item_right_head  acea-row-between">
						<view>{{items.title}}</view>
						<view class="add" @tap="chooseFood"></view>
					</view>
					<view class="viewlog_content_item_right_list">
						<!-- ------------item 左滑 ---------- -->
						<view class="viewlog_content_item_right_list_item" v-for="(item, index) in items.morningList" :key="index">
							<view class="left   acea-row-between" :data-index="index" @touchstart="drawStart" @touchmove="drawMove"
							 @touchend="drawEnd" :style="{ left: item.left + 'rpx' }">
								<view>{{item.content}}</view>
								<view class="arrow_right acea-line-height">
									<view>{{item.less}}</view>
									<view>
										<image src="../../../static/icon/arrow_right.png" mode=""></image>
									</view>
								</view>
							</view>
							<view class="remove" @tap.stop="delItem()">删除</view>
						</view>
						<!-- --------------------end-------------------- -->
					</view>
				</view>
			</view>
			<!-- end -->
			<!-- item -->
			<view class="viewlog_content_item">
				<view class="viewlog_content_item_left">
					<image src="../../../static/icon/morningjia.png" mode=""></image>
				</view>
				<view class="viewlog_content_item_right">
					<view class="viewlog_content_item_right_head  acea-row-between">
						<view>上午加餐</view>
						<view class="add"></view>
					</view>
					<view class="viewlog_content_item_right_list">
						<!-- ------------item 左滑 ---------- -->
						<view class="viewlog_content_item_right_list_item" v-for="(item, index) in morningjiaList" :key="index">
							<view class="left   acea-row-between" :data-index="index" @touchstart="drawStart" @touchmove="drawMove"
							 @touchend="drawEnd" :style="{ left: item.left + 'rpx' }">
								<view>{{item.content}}</view>
								<view class="arrow_right acea-line-height">
									<view>{{item.less}}</view>
									<view>
										<image src="../../../static/icon/arrow_right.png" mode=""></image>
									</view>
								</view>
							</view>
							<view class="remove" @tap.stop="delItem()">删除</view>
						</view>
						<!-- --------------------end-------------------- -->
					</view>
				</view>
			</view>
			<!-- end -->
			<!-- item -->
			<view class="viewlog_content_item">
				<view class="viewlog_content_item_left">
					<image src="../../../static/icon/noon.png" mode=""></image>
				</view>
				<view class="viewlog_content_item_right">
					<view class="viewlog_content_item_right_head  acea-row-between">
						<view>午餐</view>
						<view class="add"></view>
					</view>
					<view class="viewlog_content_item_right_list">
						<!-- ------------item 左滑 ---------- -->
						<view class="viewlog_content_item_right_list_item" v-for="(item, index) in noonList" :key="index">
							<view class="left   acea-row-between" :data-index="index" @touchstart="drawStart" @touchmove="drawMove"
							 @touchend="drawEnd" :style="{ left: item.left + 'rpx' }">
								<view>{{item.content}}</view>
								<view class="arrow_right acea-line-height">
									<view>{{item.less}}</view>
									<view>
										<image src="../../../static/icon/arrow_right.png" mode=""></image>
									</view>
								</view>
							</view>
							<view class="remove" @tap.stop="delItem()">删除</view>
						</view>
						<!-- --------------------end-------------------- -->
					</view>
				</view>
			</view>
			<!-- end -->
			<!-- item -->
			<view class="viewlog_content_item">
				<view class="viewlog_content_item_left">
					<image src="../../../static/icon/noonjia.png" mode=""></image>
				</view>
				<view class="viewlog_content_item_right">
					<view class="viewlog_content_item_right_head  acea-row-between">
						<view>下午加餐</view>
						<view class="add"></view>
					</view>
					<view class="viewlog_content_item_right_list">
						<!-- ------------item 左滑 ---------- -->
						<view class="viewlog_content_item_right_list_item" v-for="(item, index) in noonjiaList" :key="index">
							<view class="left   acea-row-between" :data-index="index" @touchstart="drawStart" @touchmove="drawMove"
							 @touchend="drawEnd" :style="{ left: item.left + 'rpx' }">
								<view>{{item.content}}</view>
								<view class="arrow_right acea-line-height">
									<view>{{item.less}}</view>
									<view>
										<image src="../../../static/icon/arrow_right.png" mode=""></image>
									</view>
								</view>
							</view>
							<view class="remove" @tap.stop="delItem()">删除</view>
						</view>
						<!-- --------------------end-------------------- -->
					</view>
				</view>
			</view>
			<!-- end -->
			<!-- item -->
			<view class="viewlog_content_item">
				<view class="viewlog_content_item_left">
					<image src="../../../static/icon/night.png" mode=""></image>
				</view>
				<view class="viewlog_content_item_right">
					<view class="viewlog_content_item_right_head  acea-row-between">
						<view>晚餐</view>
						<view class="add"></view>
					</view>
					<view class="viewlog_content_item_right_list">
						<!-- ------------item 左滑 ---------- -->
						<view class="viewlog_content_item_right_list_item" v-for="(item, index) in nightList" :key="index">
							<view class="left   acea-row-between" :data-index="index" @touchstart="drawStart" @touchmove="drawMove"
							 @touchend="drawEnd" :style="{ left: item.left + 'rpx' }">
								<view>{{item.content}}</view>
								<view class="arrow_right acea-line-height">
									<view>{{item.less}}</view>
									<view>
										<image src="../../../static/icon/arrow_right.png" mode=""></image>
									</view>
								</view>
							</view>
							<view class="remove" @tap.stop="delItem()">删除</view>
						</view>
						<!-- --------------------end-------------------- -->
					</view>
				</view>
			</view>
			<!-- end -->
			<!-- item -->
			<view class="viewlog_content_item">
				<view class="viewlog_content_item_left">
					<image src="../../../static/icon/nightjia.png" mode=""></image>
				</view>
				<view class="viewlog_content_item_right">
					<view class="viewlog_content_item_right_head  acea-row-between">
						<view>晚上加餐</view>
						<view class="add"></view>
					</view>
					<view class="viewlog_content_item_right_list">
						<!-- ------------item 左滑 ---------- -->
						<view class="viewlog_content_item_right_list_item" 
						v-for="(item, index) in nightjiaList" :key="index">
							<view class="left   acea-row-between" :data-index="index" @touchstart="drawStart" @touchmove="drawMove"
							 @touchend="drawEnd" :style="{ left: item.left + 'rpx' }">
								<view>{{item.content}}</view>
								<view class="arrow_right acea-line-height">
									<view>{{item.less}}</view>
									<view>
										<image src="../../../static/icon/arrow_right.png" mode=""></image>
									</view>
								</view>
							</view>
							<view class="remove" @tap.stop="delItem()">删除</view>
						</view>
						<!-- --------------------end-------------------- -->
					</view>
				</view>
			</view>
			<!-- end -->
		</view>
        <!-- 餐次 模态框 -->
		<view class="mask" v-if='mkfalse' @tap="clickBackmask">
			<view class="boxView"  @tap.stop="stop">
				<view class="boxView_title">添加记录</view>
				<view class="boxView_content acea-row-between"  @tap="chooseMeals">
					<view>餐次</view>
					<view class="acea-line-height">
						<text>{{shuju}}</text>
						<view>
							<image src="../../../static/icon/arrow_right.png" mode=""></image>
						</view>
					</view>
				</view>
				<view class="boxView_button" @tap="addMeals">添加</view>
			</view>
		</view>
        <!-- 食物 模态框 -->
		<view class="masks" v-if='foodfalse' @tap="clickBackmasks">
			<view class="boxView" @tap.stop="stop">
				<view class="boxView_title">添加食物</view>
				<view class="boxView_content acea-row-between">
					<view>食物/饮品</view>
					<view class="acea-line-height">
						<input type="text" v-model="foodname"   placeholder="请输入食品/饮品名称" style="text-align:right"/>
					</view>
				</view>
				<view class="boxView_content acea-row-between">
					<view>摄入量</view>
					<view class="acea-line-height">
						<input type="text"  v-model="intake"  placeholder="请输入摄入量" style="text-align:right"/>
					</view>
				</view>
				<view class="boxView_button" @tap="addFood">添加</view>
			</view>
		</view>
		<!-- 底部按钮 -->
		<view class="bottom acea-row-center">
			<view class="bottom_button" @tap="modalTap">记录日志</view>
		</view>
		<show-action-sheet :tips="showActionSheet.tips" :itemList="showActionSheet.itemList" :show="showActionSheet.show" :maskClosable="showActionSheet.maskClosable"  :isCancel="showActionSheet.isCancel"  :isFinsh="showActionSheet.isFinsh"     @chooseCancel="chooseCancel" @chooseFinsh="chooseFinsh"  @chooseItem="chooseItem()"></show-action-sheet>
	</view>
</template>

<script>
import showActionSheet from '../../../components/Sheet.vue'
	export default {
		components: {
			showActionSheet
		},
		data() {
			return {
                showActionSheet: {
					show: false,
					maskClosable: true,
					// tips: "请选择申请节点身份，不同的节点消耗福卡不同",
					itemList: [
						{ text: "早餐"},
					    {text: "上午加餐"},
					    {text: "午餐"},
					    {text: "下午加餐"},
					    {text: "晚餐"},						
					    {text: "晚上加餐"},
					],
					color: "#9a9a9a",
					size: 26,
					isCancel: true,
					isFinsh: true,
				},
				// ----------------------------
				shuju:"请选择",
				food:"请输入食品/饮品名称",
				intake:"请输入摄入量",
				foodname:undefined, //食物名称
				intake:undefined, //摄入量
				mkfalse: false,
				foodfalse: false,
				delBtnWidth: 100,
					// 早餐
				morning:[
					{
						id:0,
						title:"早餐",
						morningList:[						
							{
								content: '鸡蛋',
								less: '1个',
								left: 0
							},					
						]						
					}
				],
// ---------------------------------------------------------------
				morningjiaList: [{
						content: '咖啡',
						less: '500ml',
						left: 0
					},
					{
						content: '蛋糕',
						less: '150g',
						left: 0
					},
				],
				noonList: [{
						content: '西红柿',
						less: '200g',
						left: 0
					},
					{
						content: '鸡蛋',
						less: '50g',
						left: 0
					},
					{
						content: '米饭',
						less: '200g',
						left: 0
					},
				],
				noonjiaList: [{
						content: '蛋挞',
						less: '1个',
						left: 0
					},
					{
						content: '百事可乐',
						less: '340ml',
						left: 0
					},
				],
				nightList: [{
						content: '牛肉',
						less: '50g',
						left: 0
					},
					{
						content: '拉面',
						less: '200g',
						left: 0
					},
					{
						content: '西芹',
						less: '100g',
						left: 0
					},
					{
						content: '花生豆',
						less: '50g',
						left: 0
					},
				],
				nightjiaList: [
					{
						content: '玉米',
						less: '1个',
						left: 0
					},
					{
						content: '银耳',
						less: '200g',
						left: 0
					},
				],
				startX: '',
			}
		},
		onLoad() {

		},
		methods: {
			stop(){
				console.log("阻止事件冒泡")
			},
			// 点击 记录日志
			   modalTap() {this.mkfalse = !this.mkfalse;},
			// 点击 选择餐次
			   chooseMeals(){ this.showActionSheet.show = true;},
			// 点击 添加 餐次
			   addMeals() { 
				   console.log(this.shuju)
				   this.morning.push({
					   id:1,
					   title:this.shuju,
				   })
				   this.shuju = "请选择"
				   this.mkfalse = !this.mkfalse; 
			   },
			// 点击+ 进入 显示食物模态框
			   chooseFood() { 
				    this.foodfalse = !this.foodfalse; 
				   console.log("添加食物")
			   },
			// 点击 添加 食物
			   addFood() { 
				   if(this.foodname && this.intake){
					   this.morning[0].morningList.push({
							content: this.foodname,
							left: 0,
							less: this.intake
					   })  
					   this.foodfalse = !this.foodfalse; 
					   this.foodname = '';
					   this.intake = '';					   
				   }
			   },
			   // 点击 添加餐次模态框的 背景遮罩层
			   clickBackmask(){ this.mkfalse = !this.mkfalse; },
			   // 点击 添加食物模态框的 背景遮罩层
			   clickBackmasks(){ this.foodfalse = !this.foodfalse; },
			//底部弹窗 选择item
				chooseItem(index){
					var I = index.index
					var items=this.showActionSheet.itemList[I].text
					console.log(items)
					this.shuju = items
				},
			// 底部弹窗 关闭
				chooseFinsh() {
					console.log("点击 完成")
					this.showActionSheet.show = false;
				},
			// 底部弹窗 关闭
				chooseCancel() {
					console.log("点击 取消")
					this.shuju = "请选择"
					this.showActionSheet.show = false;
				},
			// 当手指触摸屏幕时候触发
				drawStart: function(e) {
					var touch = e.touches[0];
					for (var index in this.morningjiaList) {
						this.morningjiaList[index].left = 0;
					}
					this.startX = touch.clientX;
				},
			// 当手指在屏幕上滑动的时候连续地触发
				drawMove: function(e) {
					var touch = e.touches[0];
					var item = this.morningjiaList[e.currentTarget.dataset.index];
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
						item.left = 100;
					}

				},
			// 当手指从屏幕上离开的时候触发
				drawEnd: function(e) {
					var item = this.morningjiaList[e.currentTarget.dataset.index];
					console.log(item.left)
					if (item.left <= this.delBtnWidth / 2) {
						item.left = -this.delBtnWidth;
					} else {
						item.left = 0;
					}
				},
				delItem() {
					console.log('点击删除按钮')
				}
		}
	}
</script>
<style>
	page {
		background-color: #F3F3F3;
	}
</style>
<style lang="less" scoped>
	image {
		width: 100%;
		height: 100%;
		vertical-align: top
	}

	.viewlog {
		width: 100%;
		background: #F3F3F3;

		.viewlog_head {
			height: 100px;
			background: #FFFFFF;
		}

		.viewlog_content {
			width: 690rpx;
			margin: 0 auto;
			margin-top: 28rpx;
			margin-bottom: 330rpx;

			.viewlog_content_item {
				width: 100%;
				margin-top: 21rpx;
				background: #FFFFFF;
				box-shadow: 0rpx 4rpx 24rpx 0rpx rgba(0, 0, 0, 0.08);
				border-radius: 20rpx;
				position: relative;

				.viewlog_content_item_left {
					width: 85rpx;
					height: 100%;
					border-radius: 20rpx;
					border-top-right-radius: 0rpx;
					border-bottom-left-radius: 0rpx;
					background-color: #596EE4;
					background: linear-gradient(180deg, #3A60C3 0%, #596EE4 120%);
					text-align: center;
					position: absolute;
					left: 0;
					top: 0;
					z-index: 1000;

					image {
						width: 36rpx;
						height: 35rpx;
						margin-top: 32rpx;
					}
				}

				&:nth-child(2n) .viewlog_content_item_left {
					background: linear-gradient(180deg, #EBA79F 0%, #F7D1CB 120%);
				}

				.viewlog_content_item_right {
					width: 587rpx;
					height: 100%;
					margin-left: 104rpx;

					.viewlog_content_item_right_head {
						height: 98rpx;
						line-height: 98rpx;
						padding-left: 22rpx;
						box-sizing: border-box;

						view:nth-of-type(1) {
							font-size: 34rpx;
							font-family: PingFangSC-Semibold, PingFang SC;
							font-weight: 600;
							color: #131313;
						}

						.add {
							width: 30rpx;
							height: 30rpx;
							margin-right: 47rpx;
							color: #B1B1B1;
							transition: color .25s;
							position: relative;

							&::before {
								content: '';
								position: absolute;
								left: 0rpx;
								right: 0rpx;
								margin: 0 auto;
								top: 47%;
								width: 30rpx;
								border-top: 3rpx solid;
							}

							&::after {
								content: '';
								position: absolute;
								left: 47%;
								top: 0rpx;
								buttom: 0rpx;
								height: 30rpx;
								border-left: 3rpx solid;
							}
						}

					}

					.viewlog_content_item_right_list {
						margin-top: 18rpx;

						.viewlog_content_item_right_list_item {
							width: 100%;
							height: 84rpx;
							border-bottom: 1rpx solid #DFDFDF;
							font-size: 30rpx;
							font-family: PingFangSC-Regular, PingFang SC;
							font-weight: 400;
							color: #131313;
							position: relative;

							// -------------------------
							.left {
								height: 100%;
								width: 100%;
								position: absolute;
								left: 22rpx;
								background-color: #FFFFFF;
								z-index: 888;
								padding-left: 22rpx;
								box-sizing: border-box;

								.arrow_right {
									color: #797979;

									view:nth-of-type(2) {
										width: 16rpx;
										height: 28rpx;
										margin-left: 38rpx;
										margin-right: 47rpx;
									}
								}
							}

							.remove {
								width: 100rpx;
								height: 84rpx;
								line-height: 84rpx;
								background: #E75454;
								font-size: 28rpx;
								font-family: PingFangSC-Regular, PingFang SC;
								font-weight: 400;
								color: #FFFFFF;
								text-align: center;
								letter-spacing: 1rpx;
								position: absolute;
								top: 0;
								right: 0;
								display: flex;
								justify-content: center;
								align-items: center;
								z-index: 1;
							}

							// ---------------------------------------------
							&:last-child {
								border-bottom: none;
							}

							&:last-child>.remove {
								border-radius: 0rpx 0rpx 20rpx 0rpx;
							}
						}
					}

				}
			}

			.viewlog_content_item:nth-of-type(1) {
				margin-top: 0rpx;
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

		// 弹出框
		.mask,.masks{
			width: 100%;
			height: 100%;
			background: rgba(0, 0, 0, 0.4);
			position: fixed;
			left: 0;
			top: 0;
			z-index: 7777;
			display: flex;
			justify-content: center;

			.boxView {
				width: 586rpx;
				height: 440rpx;
				margin-top: 200rpx;
				background: #FFFFFF;
				border-radius: 20rpx;
				position: relative;

				.boxView_title {
					width: 100%;
					margin-top: 55rpx;
					text-align: center;
					font-size: 34rpx;
					font-family: PingFangSC-Semibold, PingFang SC;
					font-weight: 600;
					color: #1A1A1A;
				}

				.boxView_content {
					width: 520rpx;
					height: 110rpx;
					margin: 0 auto;
					background: #F7F7F7;
					border-radius: 10rpx;
					margin-top: 45rpx;
					font-family: PingFangSC-Regular, PingFang SC;
					color: #131313;

					view:nth-of-type(1) {
						font-size: 34rpx;
						font-weight: 600;
						margin-left: 29rpx;
					}

					view:nth-of-type(2) {
						font-size: 30rpx;
						font-weight: 400;
						view {
							width: 16rpx;
							height: 28rpx;
							margin-left:33rpx;
							margin-right: 32rpx;
						}
					}

				}

				.boxView_button {
					width: 335rpx;
					height: 90rpx;
					letter-spacing: 4rpx;
					text-align: center;
					line-height: 90rpx;
					font-size: 34rpx;
					font-family: PingFangSC-Regular, PingFang SC;
					font-weight: 400;
					color: #FFFFFF;
					position: absolute;
					left: 0;
					right: 0;
					margin: 0 auto;
					bottom: 42rpx;
					background: linear-gradient(112deg, #5E87EC 0%, #445ED8 100%);
					border-radius: 59rpx;
				}
			}
		}
		.masks .boxView{
			height: 557rpx;	
            color: #B1B1B1;
			.boxView_content  view:nth-of-type(2){
				 width: 56%;
				 height:100%;		 
                 color: #131313;
				 margin-right: 24rpx;
				 input::-webkit-input-placeholder { color: #B1B1B1;}
				 input::-moz-input-placeholder { color: #B1B1B1; }
				 input::-ms-input-placeholder { color: #B1B1B1; } 
			}
			.boxView_content:nth-of-type(3){
				margin-top:20rpx;
				// background-color: plum;
			}
			.boxView_button { bottom: 46rpx;}			
			
		}
	}
</style>
