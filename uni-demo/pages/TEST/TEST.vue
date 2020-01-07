<template>
	<view>
		<!-- <image src='http://p2.music.126.net/7eM5kUB7RBbggMKAJTDrYQ==/92358976750427.jpg'></image>
		<uni-icons type="contact" size="30"></uni-icons>
		<uni-rate size="18" value="5"></uni-rate> -->

		<view class='text'></view>
		<view class='text2'></view>

	</view>
</template>

<script>
	import uniIcons from '../../components/uni-icons/uni-icons.vue'
	import uniRate from '../../components/uni-rate/uni-rate.vue'
	import uniDrawer from '../../components/uni-drawer/uni-drawer.vue'
	export default {
		data() {
			return {

			};
		},
		components: {
			uniIcons,
			uniRate,
			uniDrawer
		},
		onReady() {
			uni.request({
				url: 'https://bird.ioliu.cn/netease/song', //仅为示例，并非真实接口地址。
				data: {
					id: '222222'
				},
				header: {
					'token': 'hello' //自定义请求头信息
				},
				success: (res) => {
					console.log(res.data);
				}
			});
		}
	}
</script>

<style lang="scss">
	@import '../../style/mixin.scss';

	.text {
		width: px(375);
		height: px(375);
		box-sizing: border-box;
		border: 1px solid green
	}

	.text2 {
		width: 375px;
		height: 375px;
		box-sizing: border-box;
		border: 1px solid red
	}
</style>
