<template>
	<view class="content">
		<uni-group title="分组1" top="20">
				<view>分组1 的内容</view>
				<view>分组1 的内容</view>
		</uni-group>
		
		<uni-group title="分组2">
				<view>分组2 的内容</view>
				<view>分组2 的内容</view>
		</uni-group>
	</view>
</template>

<script>
	export default {
		components:{ },
		data() {
			return {
				Data: [
					{
						name: '一夜风',
						content:'我吹过你催的风，哪算不算很穷'
					},
					{
						name: '星空',
						content:'一闪杨斯涵，我都很生气额誒覅'
					},
					{
						name: '大笨蛋',
						content:'有人傻哈哈额二附近的的纷纷嗯嗯是'
					},
				]
			}
		},
		onLoad() {

		},
		methods: {
			onNavigationBarButtonTap(e) {
				if(e.index === 0) {
					console.log("跳转设置页面")
				}
			},
			onClick(e) { console.log(1111)}
		}
	}
</script>

<style scoped>
	.content {
		padding: 15upx;
	}
	.other-login {
		
	}
</style>

