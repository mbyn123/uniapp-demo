<template>
	<view class='hot'>
		<view class='hot-title'>
			<image :src="imgSrc" class="hot-title-img"></image>
			<text class="hot-title-text">{{title}}</text>
		</view>
		<view>
			<slot></slot>
		</view>
	</view>
</template>

<script>
	export default {
		props: {
			title: {
				type: String,
				default: ''
			},
			imgSrc: {
				type: String,
				default: ''
			}
		},
		data() {
			return {

			}
		},
		methods: {

		}
	}
</script>

<style>

</style>
