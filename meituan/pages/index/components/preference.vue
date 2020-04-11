<template>
	<view class="prefer-content">
		<view class="prefer-title animition">为你优选</view>
		<scroll-view class="scroll" scroll-x="true" scroll-with-animation>
			<view class="prefer-dis">
				<block v-for="(item, index) in preferdata" :key="index">
					<view class="prefer-view">
						<image :src="item.image" mode="aspectFill"></image>
						<text>{{ item.title }}</text>
						<text>{{ item.lable }}</text>
					</view>
				</block>
			</view>
		</scroll-view>
	</view>
</template>

<script>
export default {
	props:{
		preferdata:Array
	},
	data() {
		return {
		};
	},
	methods: {}
};
</script>

<style scoped>
.prefer-content {
	margin: 30upx 0;
}
.prefer-title {
	display: inline-block;
	font-size: 35upx;
	height: 50upx;
	line-height: 50upx;
	margin-bottom: 20upx;
}
.animition {
	background: linear-gradient(-45deg, #000 40%, #fff 60%, #000 80%);
	-webkit-background-clip: text;
	-webkit-text-fill-color: transparent;
	background-size: 200%;
	animation: toslide 2s linear infinite;
}
@keyframes toslide {
	from {
		background-position: 100%;
	}
	to {
		background-position: 0%;
	}
}
.scroll {
	white-space: nowrap;
	width: 100%;
	height: 300upx;
}
.prefer-dis {
	display: flex;
	justify-content: space-between;
}
.prefer-view {
	height: 300upx;
	width: 300upx;
	padding: 0 8upx;
}
.prefer-view image {
	width: 300upx;
	height: 200upx;
	border-radius: 8upx;
}
.prefer-view text {
	height: 45upx;
	line-height: 45upx;
	display: -webkit-box;
	-webkit-box-orient: vertical;
	-webkit-line-clamp: 1;
	overflow: hidden;
}

.prefer-view text:nth-child(2) {
	font-size: 30upx;
}
.prefer-view text:nth-child(3) {
	font-size: 27upx;
	color: #9c9c9c;
}
.prefer-dis view:nth-child(2) {
	padding: 0 7upx !important;
}
</style>
