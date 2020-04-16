<template>
	<view>
		<!-- 导航栏 -->
		<swiper-tab-head
		 :tabIndex='tabIndex'
		 @tabtap='tabtap'
		 :navList='navList'
		 ></swiper-tab-head>
		<!-- 图文列表 -->
		<view class="uni-tab-bar">
			<swiper 
			class="swiper-box" 
			:current="current"
			:style="{height:swiperheight+'px'}"
			@change="tabChange"
			>
				<swiper-item v-for="items in 7" :key='items'>
					<scroll-view class="list" scroll-y>
						<block class="list-box" v-for="item in 9" :key='item'>
							<index-list></index-list>
						</block>
					</scroll-view>
				</swiper-item>
			</swiper>
		</view>
	</view>
</template>

<script>
	import swiperTabHead from '@/components/common/swiper-tab-head.vue'
	import indexList from '@/components/index/index-list.vue'
	export default {
		components: {
			swiperTabHead,
			indexList
		},
		data() {
			return {
				current: 0, // 	swiper所在的index
				swiperheight: 500,
				scrollInto: "",
				tabIndex: 0,
				navList: ['关注', '推荐', '体育', '热点', '财经', '娱乐']
			}
		},
		onLoad() {
			uni.getSystemInfo({
				success: (res)=> {
					console.log(res.windowHeight);
					let height=res.windowHeight-uni.upx2px(100)
					this.swiperheight=height;
				}
			})
		},
		// 监听原生标题栏搜索输入框点击事件
		onNavigationBarSearchInputClicked() {
			uni.navigateTo({
				url: '../search/search'
			})
		},
		// 监听原生标题栏按钮点击事件 (取消按钮)
		onNavigationBarButtonTap(val){
			console.log(val)
			if(val.index == 1) {
				uni.navigateTo({
					url: '../send-msg/send-msg'
				})
			}
		},
		methods: {
			// 点解导航栏切换
			tabtap(index) {
				this.tabIndex = index
				this.current = index
			},
			// 左右滑动页面
			tabChange(e) {
				console.log(e.detail)
				this.tabIndex = e.detail.current
			}
		}
	}
</script>

<style lang="scss" scoped>
	
	
</style>
