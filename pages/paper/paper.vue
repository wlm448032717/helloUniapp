<template>
	<view>
		<uni-list>
			<uni-list-item 
				v-for="(item,index) in Data" 
				:title="item.name" 
				:note="item.content"
				showArrow
				@click="onClick(item)"
				link
				thumb="https://vkceyugu.cdn.bspapp.com/VKCEYUGU-dc-site/460d46d0-4fcc-11eb-8ff1-d5dcf8779628.png"
			>
				</uni-list-item>
		</uni-list>
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
						content:'我吹过你催的风，哪算不算很穷，我吹过你催的风，哪算不算很穷我吹过你催的风，哪算不算很穷',
						list:[
							{
								name: '一夜风1',
								content:'我吹过你催的风，哪算不算很穷，我吹过你催的风，哪算不算很穷我吹过你催的风，哪算不算很穷'
							},
							{
								name: '一夜风2',
								content:'我吹过你催的风，哪算不算很穷，我吹过你催的风，哪算不算很穷我吹过你催的风，哪算不算很穷'
							},
							{
								name: '一夜风3',
								content:'我吹过你催的风，哪算不算很穷，我吹过你催的风，哪算不算很穷我吹过你催的风，哪算不算很穷'
							}
						]
					},
					{
						name: '星空',
						content:'，一闪杨斯涵，我都很生气额誒覅一闪杨斯涵，我都很生气额誒覅一闪杨斯涵，我都很生气额誒覅一闪杨斯涵，我都很生气额誒',
						list:[
							{
								name: '星空1',
								content:'我吹过你催的风，哪算不算很穷，我吹过你催的风，哪算不算很穷我吹过你催的风，哪算不算很穷'
							},
							{
								name: '星空2',
								content:'我吹过你催的风，哪算不算很穷，我吹过你催的风，哪算不算很穷我吹过你催的风，哪算不算很穷'
							},
							{
								name: '星空3',
								content:'我吹过你催的风，哪算不算很穷，我吹过你催的风，哪算不算很穷我吹过你催的风，哪算不算很穷'
							},
						]
					},
					{
						name: '大笨蛋',
						content:'有人傻哈哈额二姐附近的的纷纷嗯嗯，有人傻哈哈额二姐附近的的纷纷嗯嗯是有人傻哈哈额二姐附近的的纷纷嗯嗯是是',
						list:[
							{
								name: '大笨蛋1',
								content:'我吹过你催的风，哪算不算很穷，我吹过你催的风，哪算不算很穷我吹过你催的风，哪算不算很穷'
							},
							{
								name: '大笨蛋2',
								content:'我吹过你催的风，哪算不算很穷，我吹过你催的风，哪算不算很穷我吹过你催的风，哪算不算很穷'
							},
							{
								name: '大笨蛋3',
								content:'我吹过你催的风，哪算不算很穷，我吹过你催的风，哪算不算很穷我吹过你催的风，哪算不算很穷'
							},
						]
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
			onClick(e) { 
				var navData = JSON.stringify(e)
				uni.navigateTo({
					url:"./detail?row="+navData
				})
			}
		}
	}
</script>

<style>
	.content {
		padding: 15upx;
	}
	.other-login {
		
	}
</style>



