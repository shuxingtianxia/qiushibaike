<template>
	<view class="body">
		<paper-nav></paper-nav>
		<paperList></paperList>
	</view>
</template>

<script>
	import paperNav from '@/components/paper/paper-nav.vue'
	import paperList from '@/components/paper/paper-list.vue'
	export default {
		data() {
			return {
				
			}
		},
		methods: {
			
		},
		components: {
			paperNav,
			paperList
		}
	}
</script>

<style scoped>
.body{
	padding: 0 20upx;
}
</style>
