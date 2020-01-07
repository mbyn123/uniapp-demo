<template>
	<view>
		<view style="display: flex;border:1px solid red;">
			<view class='left' style="border:1px solid red;width: 50px;">
				<view v-for="(item,index) in items" :key='item.index' @click="te(index)" :class="{active:index===aidx}">{{item.title}}</view>
			</view>
			<view class="right" style="flex:1">
				<scroll-view scroll-y="true" :scroll-into-view='idx' style="height: 120px;" scroll-with-animation='true'
				 @scrolltolower='tt' @scroll='scoll'>
					<view v-for="(item,index) in items" :key='index'>
						<view :id="'p'+index" class='titles' style="background: #4CD964;">{{item.title}}</view>
						<view v-for="it in item.list" :key='it.index'>{{it}}</view>
					</view>
				</scroll-view>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				idx: '',
				aidx: 0,
				list: [],
				items: [{
						title: '第一',
						list: ['1', '2', '3']
					},
					{
						title: '第二',
						list: ['4', '5', '6']
					},
					{
						title: '第三',
						list: ['7', '8', '9', '10']
					}
				],
				dw: 640

			}
		},
		onReady() {
			this.query()
			console.log(this.px(100))
		},
		methods: {
			// 点击改变index
			te(index) {
				this.idx = 'p' + index
				this.aidx = index
				console.log(this.aidx)
			},
			// 监听滚动触底事件
			tt() {
				setTimeout(() => {
					this.aidx = this.list.length - 1
				}, 80);
			},
			// 监听滚动时的事件
			scoll(e) {
				const s = e.target.scrollTop
				for (let i = 0; i < this.list.length; i++) {
					console.log(i)
					let h1 = this.list[i]
					let h2 = this.list[i + 1];
					if (s >= h1 && s < h2) {
						this.aidx = i
					}
				}
			},
			query() {
				// dom 选择器
				const query = uni.createSelectorQuery().in(this);
				// 获取所有 class名称位 title 的节点信息
				query.selectAll('.titles').boundingClientRect(data => {

					const rel = []
					data.map(item => {
						rel.push(item.top)
					})
					this.list = rel
				}).exec();
			},
			px(w) {
				return 750 * w / this.dw +'upx'
			}
		}
	}
</script>

<style lang="scss">
	.active {
		background: #007AFF;
	}
	
</style>
