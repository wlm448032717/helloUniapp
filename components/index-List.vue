<template>
	<view class="index-list">
		<view class="index-list1 u-f-ac u-f-sb">
			<view class="u-f-ac">
				<image :src="item.userpic" mode="" lazy-load></image>
				{{item.username}}
			</view>
			<view class="u-f-ac" v-show="item.isguanzhu">
				<image class="guanzhuImg" src="../static/assset/push.png" 
					mode="widthFix">
				</image>
				关注
			</view>
		</view>
		<view class="index-list2" v-html="item.title"></view>
		<view class="index-list3 u-f-ajc">
			<image :src="item.titlepic" mode="widthFix" lazy-load></image>
			<template v-if="item.type == 'video'">
				<view class="index-list-play">
					<image src="../static/assset/play.png"
					 mode="widthFix" lazy-load></image>
				</view>
				<view class="index-list-playinfo">
					{{item.playnum}}次播放{{item.long}}
				</view>
			</template>
		</view>
		<view class="index-list4 u-f-ac u-f-sb">
			<view class="u-f-ac ">
				<view class="u-f-ac " :class="{'active':(item.inofnum.index == 1)}">
					<image src="../static/assset/xiaolian.png" mode="widthFix"></image>
					{{item.inofnum.dingnum}}
					</view>
				<view class="u-f-ac " :class="{'active-hover':(item.inofnum.index == 2)}">
					<image src="../static/assset/kulian.png" mode="widthFix"></image>
					{{item.inofnum.cainum}}
				</view>
			</view>
			<view class="u-f-ac ">
				<view class="u-f-ac ">
					<image src="../static/assset/message.png" mode="widthFix"></image>
					{{item.inofnum.commentnum}}
				</view>
				<view class="u-f-ac ">
					<image src="../static/assset/zuanfa.png" mode="widthFix"></image>
					{{item.inofnum.sharenum}}
				</view>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		name:"index-List",
		props:{
			item: Object,
			index: Number
		},
		data() {
			return {
				
			};
		}
	}
</script>

<style scoped>
.index-list {
	padding: 20upx;
	bottom: 1upx solid ;
}
.index-list1 > view:first-child {
	color: #999;
}
.index-list1 > view:last-child {
	color: #353535;
	padding: 5upx 15upx;
	background: #e1e1e1;
	border-radius: 5upx;
}
.index-list1 > view:first-child  image{
	width: 85upx;
	height: 85upx;
	border-radius: 100%;
	margin-right: 10upx;
}
.index-list1 > view:last-child >view{
	height: 40upx;
	font-size: 14upx;
	border-radius: 100%;
	margin-right: 10upx;
}
.index-list1 > view .guanzhuImg{
	width: 24upx !important;
}
.index-list2 {
	padding: 35upx 0 10upx 0;
}
.index-list3 {
	position: relative;
}
.index-list3 image{
	width: 100%;
	border-radius: 20upx;
}
.index-list-play {
	position: absolute;
}
.index-list-play image {
	width: 60upx;
	background-color: #FFFFFF;
}
.index-list-playinfo {
	position: absolute;
	background: rgba(51,51,51,0.72);
	bottom: 8upx;
	right: 8upx;
	color: #FFFFFF;
	font-size: 18upx;
	border-radius: 40upx;
	padding: 8upx 15upx;
}

.index-list4 {
	padding: 15upx 0;
}
.index-list4 > view>view {
	font-size: 12px;
	margin-right: 15upx;
}
.index-list4 > view>view uni-image {
	width: 24upx;
	margin-right: 5upx;
}
.index-list4 >view >.active{
	color: #c5f61c;
}
.index-list4 >view >.active uni-image  {
	border-radius: 50%;
	background: #c5f61c;
	border: 1px solid #c5f61c;
}
</style>
