
## 前言
动画效果启蒙

## 有疑问
微信搜索“慢慢向好”小程序，找客服反馈，相应问题。
				  

## 素材
[图片资源](https://pixabay.com)
 
## 开始使用
下载源码解压，复制`/components` 下的组件至项目根目录的 `/components` 文件夹下


页面 引入 `ay-dropdown-filter` 组件。
```
import dropdownFilter from '@/components/ay-dropdown-filter/ay-dropdown-filter.vue'
	

components: {
			dropdownFilter,
			
		},
```

页面`index.vue` 引入关键标签
```
<view style="position: fixed;top: 0;left: 0;z-index: 99999;">
			<view style="position: relative;">
				<dropdownFilter :filterData='filterData' :defaultIndex='defaultIndex' :composeList="composeList" @onSelected='onSelected' :themeColor="themeColor" ></dropdownFilter>
			</view>
		</view>
```

页面`index.vue` 定义数据
```
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
```
页面`index.vue` 定义函数
```
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
```


页面`index.vue` 引入背景色
```
page {
		background-color: #f2f2f2;
	}
```

引入阿里矢量图，复制示例源码`/style` 下的`/iconfont.css`至项目根目录的 `/style` 文件夹下
页面`App.vue` 引入css
```
<style>
	/*每个页面公共css */
	@import './style/iconfont.css';
</style>
```

## 参考
[参考插件](https://ext.dcloud.net.cn/plugin?id=2315)
 