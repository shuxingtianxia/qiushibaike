<template>
	<view>
		搜索页面
	</view>
</template>

<script>
	export default {
		data() {
			return {
				
			}
		},
		// 监听原生标题栏按钮点击事件 (取消按钮)
		onNavigationBarButtonTap(val){
			console.log(val)
			if(val.index == 0) {
				uni.navigateBack({
					delta: 1
				})
			}
		},
		methods: {
			
		}
	}
</script>

<style>

</style>
