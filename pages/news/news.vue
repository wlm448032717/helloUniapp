<template>
	<view class="content">
		<!-- <image class="logo" src="/static/logo.png"></image> -->
		<view class="">
			<view class="view-box 
				animated" 
				hover-stay-time="800"
				hover-class="view-box-hover rubberBand">第一个view</view>
		</view>
		<view class="">
			第一个view文本第一个view文本第一个view文本
			第一个view文本第一个view文本第一个view文本
			第一个view文本第一个view文本第一个view文本
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				title: 'news'
			}
		},
		onLoad() {

		},
		methods: {

		}
	}
</script>

<style scoped>
	.content {
		padding: 25upx;
	}
	.view-box {
		width: 200upx;
		height: 200upx;
		background-color: #0077AA;
	}
	.view-box-hover {
		background-color: #18BC37;
	}
</style>
