<template>
<view class="user-chat-item">
	<scroll-view 
		id="scrollview" 
		scroll-y 
		:scroll-top="scrollTop" 
		scroll-with-animation="true"
		:style="{height: style.contentH+'px'}">
		
		<!-- 聊天列表 -->
		<block v-for="(item,index) in list">
			<user-chat-list :item="item" :index="index"/>
		</block>
	</scroll-view>
	
	<!-- 发送输入框 -->
	<user-chat-bottm @submit="submit" />
</view>
</template>

<script>
import userChatBottm from '../../components/user-chat/user-chat-bottm.vue';
import userChatList from '../../components/user-chat/user-chat-list.vue';
export default {
	components: {
		userChatBottm,
		userChatList
	},
	data() {
		return {
			scrollTop: 0,
			style:{
				contentH: 0,
				itemH: 0
			},
			list: [
				{
					userpic: '../../static/assset/newsa.png',
					isme: false,
					type: 'text',
					data: '新年快乐',
					time: '1554970014'
				},
				{
					userpic: '../../static/assset/newsa.png',
					isme: true,
					type: 'text',
					data: '新年快乐，恭喜发财',
					time: '10:31'
				},
				{
					userpic: '../../static/assset/kulian.png',
					isme: false,
					type: 'img',
					data: '../../static/assset/kulian.png',
					time: '10:34'
				},
				{
					userpic: '../../static/assset/newsa.png',
					isme: true,
					type: 'text',
					data: '你怎么了，不开心吗？',
					time: '10:31'
				},
			]
		};
	},
	onLoad() {
		this.initData()
	},
	onReady() {
		this.pageToBottom()
	},
	methods: {
		initData() { 
			try {
				const res = uni.getSystemInfoSync()
				this.style.contentH =  res.windowHeight- uni.upx2px(120)
			}catch(e) {}
		},
		pageToBottom(){
			const q = uni.createSelectorQuery()
			q.select('#scrollview').boundingClientRect()
			q.select('.user-chat-item').boundingClientRect()
			q.exec((res)=>{
				// console.log(JSON.stringify(res))
				res.forEach((ret)=> {
					this.style.itemH += ret.height
				})
				if(this.style.itemH > this.style.contentH) {
					this.scrollTop =  this.style.itemH
				}
			})
		},
		submit(data) {
			if(data === '')return
			// 构建聊天数据
			let now =  new Date().getTime()
			let obj = {
				userpic: '../../static/assset/newsa.png',
				isme: true,
				type: 'text',
				data: data,
				time: now
			}
			this.list.push(obj)
			this.pageToBottom()
		}
	},
	
};
</script>

<style>
</style>
