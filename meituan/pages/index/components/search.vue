<template>
	<view>
		<!-- 定位 -->
		<view class="search-view">
			<image src="../../../static/coen/dingwei.svg" mode="widthFix"></image>
			<text class="search-text">阿里巴巴淘宝城2期西溪园区</text>
			<text>></text>
		</view>
		<!-- 搜索框 -->
		<view class="search-cont">
			<view class="search">
				<image src="../../../static/coen/sousuo.svg" mode="widethFix" class="search-img"></image>
				<input type="text" placeholder="麻辣烫" disabled />
			</view>
		</view>
		<!-- 自定义轮播 -->
		<view class="">
			<swiper :autoplay="false" interval="2000" duration="1000" @change="changepPoint">
				<block v-for="(items, index) in lable" :key="index">
					<swiper-item class="swiper-item">
						<block v-for="(item, index) in items" :key="index">
							<view class="conteng-img">
								<image :src="item.img" mode="widthFix"></image>
								<text>{{ item.title }}</text>
							</view>
						</block>
					</swiper-item>
				</block>
			</swiper>
			<!-- 指示点 @change	-->
			<view class="instruct-view">
				<block v-for="(item, index) in lable" :key="index">
					<view class="instuct" :class="{ active: index == num }"></view>
				</block>
			</view>
		</view>
	</view>
</template>

<script>
export default {
	data() {
		return {
			// 轮播数组
			lable: [
				[
					{
						img: '../../../static/inster/meishi.png',
						title: '美食'
					},
					{
						img: '../../../static/inster/chaoshi.png',
						title: '超市便利'
					},
					{
						img: '../../../static/inster/shuiguo.png',
						title: '蔬菜水果'
					},
					{
						img: '../../../static/inster/meituan.png',
						title: '美团专送'
					},
					{
						img: '../../../static/inster/paotui.png',
						title: '跑腿代购'
					},
					{
						img: '../../../static/inster/yexiao.png',
						title: '夜宵'
					},
					{
						img: '../../../static/inster/jintie.png',
						title: '津贴联盟'
					},
					{
						img: '../../../static/inster/pinping.png',
						title: '甜点饮品'
					},
					{
						img: '../../../static/inster/shaokao.png',
						title: '龙虾烧烤'
					},
					{
						img: '../../../static/inster/dangao.png',
						title: '甜蜜蛋糕'
					}
				],
				[
					{
						img: '../../../static/inster/hanbao.png',
						title: '汉堡披萨'
					},
					{
						img: '../../../static/inster/liaoli.png',
						title: '日韩料理'
					},
					{
						img: '../../../static/inster/malatang.png',
						title: '麻辣烫'
					},
					{
						img: '../../../static/inster/kuaican.png',
						title: '快食简餐'
					},
					{
						img: '../../../static/inster/xianhua.png',
						title: '浪漫鲜花'
					},
					{
						img: '../../../static/inster/lazi.png',
						title: '无辣不欢'
					},
					{
						img: '../../../static/inster/jiaozi.png',
						title: '饺子馆'
					},
					{
						img: '../../../static/inster/xiaochi.png',
						title: '小吃馆'
					},
					{
						img: '../../../static/inster/baofan.png',
						title: '煲仔饭'
					},
					{
						img: '../../../static/inster/qita.png',
						title: '其他'
					}
				]
			],
			num: 0
		};
	},
	methods: {
		changepPoint(event) {
			console.log("当前指示点索引：",event.detail.current);
			this.num=event.detail.current
		}
	}
};
</script>

<style scoped>
/* 定位 */
.search-view {
	font-size: 30upx;
	font-weight: bold;
	display: flex;
	align-items: center;
	padding: 20upx 0;
}
.search-view image {
	width: 35upx;
	height: 35upx;
	height: 80upx;
}
.search-text {
	padding: 0 10upx;
}
/* 搜索 */
.search-img {
	margin: auto 0 auto 20upx;
	width: 40upx;
	height: 40upx;
}
.search {
	width: 100%;
	height: 60upx;
	display: flex;
	align-items: center;
	background: #e6e6e6;
	border-radius: 15upx;
}
.search input {
	width: calc(100% - 65upx); //css函数
	font-size: 28upx;
}
/* 轮播图 */
swiper {
	height: 360upx !important;
}
.swiper-item {
	display: flex;
	justify-content: space-between;
	flex-wrap: wrap;
	align-items: center;
}
.conteng-img {
	display: flex;
	flex-direction: column;
	align-items: center;
	justify-content: center;
	font-size: 27upx;
	padding: 8upx 20upx;
}
.conteng-img image {
	width: 90upx;
}
.conteng-img text {
	padding-top: 5upx;
}
/* 指示点 */
.instruct-view {
	display: flex;
	justify-content: center;
	padding-top: 10upx;
}
.instuct {
	background: #e6e6e6;
	height: 10upx;
	width: 30upx;
	border-radius: 50upx;
	margin: 0 10upx;
}
.active {
	background: #fbae22 !important;
}
</style>
