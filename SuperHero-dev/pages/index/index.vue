<template>
	<view class="page">
		<swiper :indicator-dots="true" :autoplay="true">
			<swiper-item>
				<image src="../../static/carousel/batmanvssuperman.png" class='swiper-item-img'></image>
			</swiper-item>
			<swiper-item>
				<image src="../../static/carousel/spiderman.png" class='swiper-item-img'></image>
			</swiper-item>
		</swiper>
		<Hot title='热门超英' :imgSrc='imgSrc'>
			<scroll-view scroll-x="true" class='scroll-wrapper' scroll-left='50'>
				<view class="item-wrapper" v-for='(value,index) in items'  @click="set(value)" :key="index">
					<view class='item' >
						<image :src="value.img"></image>
						<text class="name">{{value.name}}</text>
						<view class='grade'>
							<uni-rate size="18" max="5" :value="value.x" disabled="false"></uni-rate>
							<text>{{value.grade}}</text>
						</view>
					</view>
				</view>
			</scroll-view>
		</Hot>
	</view>
</template>

<script>
	import Hot from '../../components/Hot/Hot.vue'
	import uniRate from '../../components/uni-rate/uni-rate.vue'
	export default {
		components: {
			Hot,
			uniRate
		},
		data() {
			return {
				imgSrc: '../../static/icos/hot.png',
				items:[
					{
						img:'https://dss1.baidu.com/6ONXsjip0QIZ8tyhnq/it/u=1843027213,4091283601&fm=58&app=83&f=JPG?w=400&h=533&s=C1C5D30E1A37BEDE4ED14A9F0300F086',
						name:'南方车站的聚会',
						grade:'7.4',
						x:'3'
					},
					{
						img:'https://dss0.baidu.com/6ONWsjip0QIZ8tyhnq/it/u=164951256,3171893138&fm=58&app=83&f=JPEG?w=400&h=533&s=BF904CCFD40458FC6B94843003002053',
						name:'小丑',
						grade:'8.7',
						x:'4'
					},
					{
						img:'https://dss2.baidu.com/6ONYsjip0QIZ8tyhnq/it/u=2975901083,2518363767&fm=58',
						name:'少年的你',
						grade:'8.3',
						x:'4'
					},
					{
						img:'https://dss1.baidu.com/6ONXsjip0QIZ8tyhnq/it/u=3509770954,1274935860&fm=58&s=D2C060AF4E22D0DE0438888103008087',
						name:'驯龙高手：归家',
						grade:'8.3',
						x:'4'
					},
					{
						img:'https://dss1.baidu.com/6ONXsjip0QIZ8tyhnq/it/u=3623058577,1291143084&fm=58&s=ECCA7A2B481307F9479CE11E0100C091',
						name:'爱尔兰人',
						grade:'9.0',
						x:'4.5'
					},
					{
						img:'https://dss2.baidu.com/6ONYsjip0QIZ8tyhnq/it/u=3717282104,1079711651&fm=58&s=6A292DC0420F22FA2A73CB08030040CD',
						name:'寄生虫',
						grade:'8.7',
						x:'4'
					},
					{
						img:'https://dss1.baidu.com/6ONXsjip0QIZ8tyhnq/it/u=2585813656,2994285865&fm=58&s=C5649A468F378ECC266911AC03008012',
						name:'千与千寻',
						grade:'9.3',
						x:'4.5'
					},
					{
						img:'https://dss1.baidu.com/6ONXsjip0QIZ8tyhnq/it/u=914484844,2960965311&fm=58&app=83&f=JPEG?w=400&h=533&s=DAA620C4E812EECC12AF09910300D09A',
						name:'天气之子',
						grade:'7.1',
						x:'3.5'
					},
				]
			}
		},
		methods: {
           set(value){
			   uni.navigateTo({
			       url:`../set/set?value=${ encodeURIComponent(JSON.stringify(value))}`
			   });
		   }
		}
	}
</script>

<style lang="scss">
	.swiper-item-img {
		width: 100%;
		height: 100%;
	}

	.scroll-wrapper {
		border: 1px solid red;
		width: 100%;
		white-space: nowrap;

		.item-wrapper {
			display: inline-block;
             margin: 5upx 10upx;
			.item {
				display: flex;
				flex-direction: column;
                text-align: center; 
				image {
					width: 200upx;
					height: 240upx;
				}

				.name {
					font-size: 16px;
				}

				.grade {
					display: flex;
					align-items: center;
					margin: 5upx 0;

					text {
						font-size: 14px;
						color: #999999
					}
				}
			}
		}

	}
</style>
