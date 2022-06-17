<template>
	<view>
		<view class="user-chat-time u-f-ajc">{{ item.time|formatDate}}</view>
		<view class="user-chat-list u-f" :class="{ 'user-chat-me': item.isme }">
			<image v-if="!item.isme" :src="item.userpic" mode="widthFix" lazy-load></image>
			<view class="user-chat-list-body">
				<!-- 文字 -->
				<text v-if="item.type === 'text'">{{ item.data }}</text>
				<!-- 图片 -->
				<image v-if="item.type === 'img'" :src="item.data" mode="widthFix" lazy-load></image>
			</view>
			<image v-if="item.isme" :src="item.userpic" mode="widthFix" lazy-load></image>
		</view>
	</view>
</template>

<script>
	export default {
		props:{
			item: Object,
			index: Number
		},
		data() {
			return {
				
			}
		},
		methods: {
			
		},
		//时间戳的处理
		filters: {
			formatDate: function(value) {
				var date = new Date();
				//date.setTime(value);
				var month = date.getMonth() + 1;
				var hours = date.getHours();
				if (hours < 10)
					hours = "0" + hours;
				var minutes = date.getMinutes();
				if (minutes < 10)
					minutes = "0" + minutes;
				var time = date.getFullYear() + "-" + month + "-" + date.getDate() +
					" " + hours + ":" + minutes;
				return time;
			}
		}
	}
</script>

<style scoped>
.user-chat-list {
	padding: 0 20upx;
}
.user-chat-list > image {
	width: 100upx;
	height: 100upx;
	border-radius: 100%;
	flex-shrink: 0;
}
.user-chat-list-body {
	position: relative;
	background: #f4f4f4;
	padding: 25upx;
	margin-left: 20upx;
	margin-right: 100upx;
	border-radius: 20upx;
}

.user-chat-list-body:after {
	position: absolute;
	left: -30upx;
	right: 0;
	top: 20upx;
	content: '';
	width: 0;
	height: 0;
	border: 16upx solid #f4f4f4;
	border-color: transparent #f4f4f4 transparent transparent;
}
.user-chat-me {
	justify-content: flex-end;
}
.user-chat-me .user-chat-list-body {
	margin-right: 20upx;
	margin-left: 100upx;
}
.user-chat-me .user-chat-list-body:after {
	left: auto;
	right: -30upx;
	border-color: transparent transparent transparent #f4f4f4;
}
.user-chat-list-body > image {
	max-width: 150upx;
	max-height: 200upx;
}
.user-chat-time {
	padding: 50upx 0;
	color: #a2a2a2;
	font-size: 24upx;
}
</style>
</style>
