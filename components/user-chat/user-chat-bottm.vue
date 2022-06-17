<template>
	<view>
		<!-- 发送输入框 -->
		<view class="user-chat-bottom u-f-ac">
			<input type="text" v-model="text" placeholder="文明发言" />
			<view class="icon iconfont icon-zhifeiji" @tap="submit"></view>
		</view>
	</view>
</template>

<script>
	export default {
		name:"user-chat",
		props:{},
		data() {
			return {
				text: ''
			};
		},
		methods:{
			submit() { 
				this.$emit('submit',this.text)
				this.text = "";
			}
		}
	}
</script>

<style scoped>
.user-chat-bottom {
		position: fixed;
		bottom: 0;
		left: 0;
		right: 0;
		height: 120upx;
		padding:0 20upx;
		background: #FFFFFF;
		border-top: 1px solid #EEEEEE;
	}
	.user-chat-bottom >input {
		
		flex: 1;
		margin-right: 8upx;
		padding: 20upx 10upx;
		border-radius: 10upx;
		background: #F7F7F7;
		font-size: 35upx;
		text-indent: 8upx;
		/* border: 1upx solid #EEEEEE; */
	}
	.user-chat-bottom >uni-view{
		width: 60upx;
		font-size: 60upx;
	}
</style>
