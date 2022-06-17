<template>
	<view>
		<block v-for="(item, index) in list" :key="index">
			<index-list :item="item" :index="index"/>
		</block>
	</view>
</template>

<script>
import indexList from '../../components/index-List.vue';
	export default {
		components: { indexList },
		data() {
			return {
				list: [
					{
						userpic:"../../static/assset/3.jpg",
						username:"昵称",
						isguanzhu: false,
						title:'我是标题我是我是标题我是',
						type: "video",//video, img
						titlepic:"../../static/assset/xue.jpg",
						playnum:'20W',
						long:' 2:47',
						inofnum: {
							index: 1, //1踩2顶0
							num: 11,
							dingnum: 11,
							cainum: 11,
							commentnum: 1,
							sharenum: 10
						}
					},
					{
						userpic:"../../static/assset/3.jpg",
						username:"小修奥",
						isguanzhu: true,
						title:'我是无敌五的小可爱',
						type: "img",//video, img
						titlepic:"../../static/assset/xue.jpg",
						playnum:'20W',
						long:' 2:47',
						inofnum: {
							index: 0, //1踩2顶0
							num: 11,
							dingnum: 11,
							cainum: 11,
							commentnum: 1,
							sharenum: 10
						}
					}
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
			}
		}
	}
</script>


