<template>
	<view class="content">
		
		
		<view class="text-area">
			<text class="title">{{title}}</text>
			<navigator url="/pages/about/about?id=1&name=uniapp" >
		  	   <but text='按钮'></but>
			</navigator>
		</view>
		<scroll-view scroll-x="true" class="view" show-scrollbar='true'>
			<view id="demo1" class="scroll-view-item uni-bg-red">A</view>
			<view id="demo2" class="scroll-view-item uni-bg-green">B</view>
			<view id="demo3" class="scroll-view-item uni-bg-blue">C</view>
			<view id="demo1" class="scroll-view-item uni-bg-red">A</view>
			<view id="demo2" class="scroll-view-item uni-bg-green">B</view>
			<view id="demo3" class="scroll-view-item uni-bg-blue">C</view>
			<view id="demo1" class="scroll-view-item uni-bg-red">A</view>
			<view id="demo2" class="scroll-view-item uni-bg-green">B</view>
			<view id="demo3" class="scroll-view-item uni-bg-blue">C</view>
			<view id="demo1" class="scroll-view-item uni-bg-red">A</view>
			<view id="demo2" class="scroll-view-item uni-bg-green">B</view>
			<view id="demo3" class="scroll-view-item uni-bg-blue">C</view>
			<view id="demo1" class="scroll-view-item uni-bg-red">A</view>
			<view id="demo2" class="scroll-view-item uni-bg-green">B</view>
			<view id="demo3" class="scroll-view-item uni-bg-blue">C</view>
		</scroll-view>

	</view>
</template>

<script>
	import but from '../../components/button/button.vue'
	export default {
		data() {
			return {
				title: 'nishdfsdfsdfia',
				scrollTop: 0,
				background: ['color1', 'color2', 'color3'],
				indicatorDots: true,
				autoplay: true,
				interval: 2000,
				duration: 500
			}
		},
		components: {
			but
		}
	}
</script>

<style>
	.content {
		justify-content:center;
        align-items: center;
	}

	.view {
		border: 1px solid green;
		padding: 10px;
		height: 100px;
		overflow: hidden;
		width: 100%;
		white-space: nowrap;
	}

	.scroll-view-item {
		display: inline-block;
		width: 100px;
		height: 100px;
		background: red;
		margin: 2px;
	}
</style>
