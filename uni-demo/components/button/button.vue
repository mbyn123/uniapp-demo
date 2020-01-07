<template>
	<view>
		<button type="primary" @click="textx">{{text}}</button>
	</view>
</template>

<script>
	export default {
		props:{
			text:{
				type:String,
				default:''
			}
		},
		data() {
			return {
				
			}
		},
		methods: {
			textx(){
				uni.$emit('testEmit',{name:'121231231'})
			}
		}
	}
</script>

<style>

</style>
