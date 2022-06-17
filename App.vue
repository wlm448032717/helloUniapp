<script>
	export default {
		onLaunch: function() {
			console.log('App Launch')
		},
		onShow: function() {
			console.log('App Show')
		},
		onHide: function() {
			console.log('App Hide')
		}
	}
</script>
<style>
	/*每个页面公共css */
	@import url("./common/common.css");
	@import url("./common/uni.scss");
	/* @import url("~@/static/assset/fonts/iconfont.scss"); */
	/* @import url("./static/assset/fonts/iconfont.scss"); */
	 @import url("http://at.alicdn.com/t/font_3057863_w6kbd2cd9mk.css");
	
	::-webkit-scrollbar{
		display: none;
	}
</style>

