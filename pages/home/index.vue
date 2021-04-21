<template>
	<view class="home">
		<view class="wrapperBox">
			<view class="nav acea-row-center" :class="scrollTop > 30?'fiedc' : ''">
				<article @click='slect1' :class="{col: !bol1}">推荐<span v-if='!bol1'></span></article>
				<article @click='slect2' :class="{col: bol2}" >百科<span v-if='bol2'></span></article>
				<article @click='slect3' :class="{col: bol3}">工具<span v-if='bol3'></span></article>
			</view>
			<!-- 1 -->
			<view class="wrapper" v-if="likeInfo > 0 && !bol1">
			  <view class="listpox">
				   <Recommend-list :recommend-list="likeInfo" :is-sort="false"></Recommend-list>
			  </view>
			</view>
			<!-- 2 -->
			<view class="wrapper" v-if="likeInfo> 0 && bol2">
			  <view class="listpox">
				   <Baike-list></Baike-list>
			  </view>
			</view>
			<!-- 3 -->
			<view class="wrapper" v-if="likeInfo > 0 && bol3">
			  <view class="listpox">
				   <Tool-list/>
			  </view>
			</view>
			<!-- 3 -->
		</view>
	</view>
</template>
<script>
	import RecommendList from "@/components/RecommendList";
	import BaikeList from "@/components/BaikeList";		
	import ToolList from "@/components/ToolList";	
	export default {
		components: {
			RecommendList,
			ToolList,
			BaikeList
		},
		data() {
			return {
			    bol1: false,
			    bol2: false,
			    bol3: false,
				likeInfo:3,
				scrollTop: 0,
			}
		},
		onPageScroll(e){
		      let _this = this;
		      this.scrollTop =e.scrollTop;
		},
		onLoad() {

		},
		methods: {
			slect1(){
			  this.bol1 = false
			  this.bol2 = false
			  this.bol3 = false
			},
			slect2(){
			  this.bol1 = true
			  this.bol2 = true
			  this.bol3 = false
			},
			slect3(){
			  this.bol1 = true
			  this.bol2 = false
			  this.bol3 = true
			},
		}
	}
</script>

<style scoped lang="less">
	.wrapperBox{
	  width: 100%;
		.nav{
			height: 76rpx;
			width:100%;
			background-color: #496DDC;
			color: #C9D4FF;
			font-size: 28rpx;
			font-family: PingFangSC-Regular, PingFang SC;
			article:nth-of-type(2){
				margin-left: 120rpx;
				margin-right: 120rpx;
			}
			article span{
			  width: 20px;
			  height: 3px;
			  background: #DE1B05;
			  border-radius: 20px;
			  margin-top: 2px;
			  box-shadow: 0 2px 6px #ddd;
			}
			.col{
			  color:#FFFFFF!important;
			}	
						
		}	
		.wrapper{
			.title{
				color: #F26C6C;
				background-color: yellow;
			}
			.listpox{
				// background-color: pink;
			}
		}  
	}	
</style>
