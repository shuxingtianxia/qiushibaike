<template>
	<view>
		<!-- 导航 -->
		<swiper-tab-head
			:tabIndex='tabIndex'
			@tabtap='tabtap'
			:navList='navList'
		></swiper-tab-head>
		<view class='content'>
			<swiper
			class="swiper-box" 
			:current="current"
			:style="{height:swiperheight+'px'}"
			@change="tabChange"
			>
				<swiper-item v-for="items in 6" :key='items'>
					<scroll-view class="list" scroll-y>
						<block class="list-box" v-for="item in 9" :key='item'>
							<topic-list></topic-list>
						</block>
					</scroll-view>
				</swiper-item>
			</swiper>
			
		</view>
		
	</view>
</template>

<script>
	import swiperTabHead from '@/components/common/swiper-tab-head.vue'
	import topicList from '@/components/common/topic-list.vue'
	export default{
		data() {
			return{
				current: 0, // 	swiper所在的index
				tabIndex: 0,
				navList: ['关注', '推荐', '体育', '热点', '财经', '娱乐'],
				swiperheight: 500,
			}
		},
		components: {
			swiperTabHead,
			topicList
		},
		onLoad() {
			uni.getSystemInfo({
				success: (res)=> {
					let height=res.windowHeight-uni.upx2px(100)
					this.swiperheight=height;
				}
			})
		},
		methods: {
			// 点解导航栏切换
			tabtap(index) {
				this.tabIndex = index
				this.current = index
			},
			// 左右滑动页面
			tabChange(e) {
				this.tabIndex = e.detail.current
			}
		}
	}
</script>

<style scoped lang="scss">
	.content{
		padding: 0 20upx;
	}
</style>
