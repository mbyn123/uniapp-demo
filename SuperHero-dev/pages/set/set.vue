<template>
	<view style="display: flex;flex-direction: column;text-align: center;">
		<image :src="list.img" style="width: 100%;"></image>
		 <text>{{list.name}}</text>
	</view>
</template>

<script>
	export default {
		data() {
			return {
			  list:{}
			}
		},
		methods: {
			
		},
		onLoad(options){
			const item = JSON.parse(decodeURIComponent(options.value));
			this.list=item
			
			uni.request({
			    url: 'http://192.168.8.110:8081/epub/Biomedicine', 
			    data: {
			        // text: 'uni.request'
			    },
			    header: {
			        // 'custom-header': 'hello' //自定义请求头信息
			    },
			    success: (res) => {
			        console.log(res.data);
			    }
			});
		}
	}
</script>

<style>

</style>
