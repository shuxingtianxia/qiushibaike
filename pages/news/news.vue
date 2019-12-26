<template>
	<view>
		<news-head :tabBars='tabBars' :tabIndex='tabIndex' @change-tab='changeTab'></news-head>
		<view class="uni--tab-bar">
			<swiper
			:current="tabIndex"
			:style="{height:swiperheight+'px'}"
			:duration="500"
			@change="tabChange"
			>
				<swiper-item>
					<block v-for="item in 2" :key='item'>
						<common-list></common-list>
					</block>
				</swiper-item>
				<swiper-item>
					<!-- 搜索框 -->
					<view class="search-input">
						<input class="uni-input" type="text" placeholder-class="icon iconfont icon-sousuo topic-search" value="" placeholder="搜索内容" />
					</view>
					<!-- 轮播图 -->
					<swiper class="topic-swiper" :indicator-dots="true" :circular="true" :autoplay="true" :interval="3000" :duration="1000">
						<block v-for="item in 3" :key="item">
							<swiper-item>
								<image src="../../static/logo.png" mode="widthFix" lazy-load></image>
							</swiper-item>
						</block>
					</swiper>
					<!-- 热门分类 -->
					<view class="hot-nav">
						<view class="hot-classify u-flex u-f-jcs">
							<view class="hot-title">热门分类</view>
							<view class="u-flex hot-more">更多<view class="icon iconfont icon-jinru"></view></view>
						</view>
						<view class="u-flex u-f-jcc hot-tag">
							<view class="u-flex u-f-jcc" v-for="(item, index) in topic" :key="index">{{item.name}}</view>
						</view>
					</view>
					<!-- 最近更新 -->
					<view class="new-update">
						<view class="hot-title">最近更新</view>
						<topic-list></topic-list>
					</view>
				</swiper-item>
			</swiper>
		</view>
		
	</view>
</template>

<script>
	import newsHead from '@/components/news/news-head.vue'
	import commonList from '@/components/common/common-list.vue'
	import topicList from '@/components/news/topic-list.vue'
	export default {
		components: {
			newsHead,
			commonList,
			topicList
		},
		data() {
			return {
				tabBars: [
					{name: '关注', id: 1},
					{name: '话题', id: 2}
				],
				tabIndex:0,
				topic: [
					{name:"最新"},
					{name:"游戏"},
					{name:"打卡"},
					{name:"情感"},
					{name:"故事"},
					{name:"喜爱"},
				]
			}
		},
		onLoad() {
			uni.getSystemInfo({
				success: (res)=> {
					console.log(res.windowHeight);
					let height=res.windowHeight-uni.upx2px(88)
					this.swiperheight=height;
				}
			})
		},
		methods: {
			// 点击顶部导航
			changeTab(index) {
				this.tabIndex = index
			},
			// 滑动页面
			tabChange(e){
				this.tabIndex = e.detail.current
			},
		}
	}
</script>

<style scoped lang="scss">
// 搜索框
.search-input{
	padding: 20upx;
	.uni-input{
		background: #F4F4F4;
		border-radius:10upx;
	}
	.topic-search{
		display: flex;
		justify-content: center;
		font-size: 27upx;
	}
}
// 轮播图
.topic-swiper{
	padding:0 20upx 20upx 20upx;
	image{
		width: 100%;
		border-radius:10upx;
	}
}
// 热门分类
.hot-nav{
	padding: 20upx;
	border-top: 1upx solid #EEEEEE;
	border-bottom: 1upx solid #EEEEEE;
	.hot-classify{
		margin-bottom: 10upx;
		.hot-title{
			color:#333333;
			font-size: 32upx;
		}
		.hot-more{
			color: #9e9e9e;
		}
	}
	.hot-tag{
		view{
			background: #ddd;
			color: #9e9e9e;
			border-radius: 10upx;
			margin: 0 10upx;
			flex: 1;
		}
	}
}
// 最近更新
.new-update{
	padding: 20upx;
	.hot-title{
		color:#333333;
		font-size: 32upx;
	}
}
</style>
