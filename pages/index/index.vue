<template>
	<view class="content">
		<view style="position: fixed;top: 0;left: 0;z-index: 99999;">
			<view style="position: relative;">
				<dropdownFilter :filterData='filterData' :defaultIndex='defaultIndex' :composeList="composeList" @onSelected='onSelected' :themeColor="themeColor" ></dropdownFilter>
			</view>
		</view>
		
	</view>
</template>

<script>
	import dropdownFilter from '@/components/ay-dropdown-filter/ay-dropdown-filter.vue'
	export default {
		components: {
			dropdownFilter,
			
		},
		data() {
			return {
				themeColor: '#33CCCC', 
				list:[
					
				],
				filterData: [
					[{
							text: '<1折',
							value: '0.9'
						}, {
							text: '1-2折',
							value: '1-2'
						}, {
							text: '2-4折',
							value: '2-4'
						}, {
							text: '4-8折',
							value: '4-8'
						}
					],
					[{
						text: '距离优先',
						value: '距离优先'
					}, {
						text: '价格优先',
						value: '价格优先'
					}]
				],
				defaultIndex: [0, 0],
				composeList: [{
					name: '折扣',
					isHen: true,
				}]
			}
		},
		onLoad() {
			let that = this ;
			
		},
		
		methods: {
			onSelected(res) {
				//[[{"text":"<1折","value":"0.9","select":true}],[{"text":"距离优先","value":"距离优先","select":true}]]
				// console.log('res  ' + JSON.stringify(res))
				// console.log('res  ' + JSON.stringify(res[0]))
				// console.log('res  ' + JSON.stringify(res[0][0].value))
				let that = this;
				let one = res[0][0].value ;
				let two =  res[1][0].value ;
				console.log(' one ' + one + ' two ' +two);
				
				
			},
			
		}
	}
</script>

<style>
	page {
		background-color: #f2f2f2;
	}
</style>
