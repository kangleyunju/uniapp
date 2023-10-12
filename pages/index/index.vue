<template>
	<view class="content">
		<view class="item">1. 默认垂直滚动</view>
		<xzw-notice :list="list" />
		<view class="item">2. 不同主题色theme</view>
		<xzw-notice theme="error" direction="row" speed="slow" :list="list" />
		<view class="item">3. 水平滚动</view>
		<xzw-notice theme="info" direction="row" :list="list" />
		<view class="item">4. 滚动速度，快中慢三档，fast，normal，slow</view>
		<xzw-notice theme="primary" :list="list" theKey="title" speed="fast" direction="row" />
		<view class="item">5. 点击公告，点击更多触发事件</view>
		<xzw-notice theme="warning" :list="list" @goItem="goItem" @goMore="goMore" />
		<view class="item">6. 绑定公告数组，默认取每一项的title字段，可以通过theKey改变读取的字段</view>
		<xzw-notice theme="success" :list="list" theKey="title" speed="fast" />
		<view class="item">7. 是否显示左侧喇叭，是否显示右侧更多</view>
		<xzw-notice theme="primary" :list="list" theKey="title" :showIcon="false" :showMore="false" speed="slow" />
	</view>
</template>
<script>
	export default {
		data() {
			return {
				list: [{ id: 1, title: '白日依山尽，黄河入海流' }, { id: 2, title: '欲穷千里目，更上一层楼' }, { id: 3, title: '床前明月光，疑是地上霜' }, { id: 4, title: '举头望明月，低头思故乡' }]
			}
		},
		methods: {
			goItem() {
				console.log('跳转详情')
			},
			goMore() {
				console.log('跳转更多')
			}
		}
	}
</script>
<style lang="scss">
	.content {
		.item {
			font-size: 28upx;
			line-height: 24px;
			padding: 20upx 30upx;
			font-weight: bold;
		}
	}
</style>