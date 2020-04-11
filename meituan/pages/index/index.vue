<template>
	<view class="contening">
		<Search></Search>
		<Preference :preferdata="preferdata"></Preference>
		<Takeout></Takeout>
		<Title></Title>
		<Delicacy></Delicacy>
	</view>
</template>

<script>
import Search from './components/search.vue';
import Preference from './components/preference.vue';
import Takeout from './components/takeout.vue';
import Title from './components/title.vue';
import Delicacy from './components/delicacy.vue';
export default {
	components: {
		Search,
		Preference,
		Takeout,
		Title,
		Delicacy
	},
	data() {
		return {
			title: 'Hello',
			// 为你优选
			preferdata:[]
		};
	},
	onLoad() {},
	mounted() {
		this.preference();
	},
	methods: {
		// 为你优选
		preference() {
			uni.request({
				url: 'http://meituan.thexxdd.cn/api/forshop/getprefer', //仅为示例，并非真实接口地址。
				method: 'GET'
			})
				.then(res => {
					// console.log(res[1].data);
					this.preferdata=res[1].data
				})
				.catch(err => {
					console.log(err);
				});
		}
	}
};
</script>

<style scoped>
.contening {
	margin: 0 15upx;
}
</style>
