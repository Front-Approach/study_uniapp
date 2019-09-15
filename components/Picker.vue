<template>
	<view class="devPicker">
		<!-- <view class="uni-title uni-common-pl">设备类型</view>
		<view class="uni-list">
			<view class="uni-list-cell">
				<view class="uni-list-cell-db">
					<picker @change="bindPickerChange" :value="index" :range="devItem">
						<view class="uni-input">{{devItem[index]}}</view>
					</picker>
					<view class="arrow"><image src="/static/iconFont/sanjiao.png" mode=""></image></view>
				</view>
			</view>
		</view> -->
	</view>
</template>

<script>
	// 交通情况调查设备
	// LED可变信息标志设备
	// 视频监控设备
	// 车牌自动识别设备
	// 气象检测设备
	// 轴载检测设备
	// 移动车载视频设备
	// 手持移动视频设备
	// 积水监测设备
	// 公共设备
	export default{
		data(){
			return{
				// devItem: [
				// 	'交通情况调查设备', 
				// 	'LED可变信息标志设备', 
				// 	'视频监控设备', 
				// 	'车牌自动识别设备',
				// 	'气象检测设备', 
				// 	'轴载检测设备', 
				// 	'移动车载视频设备',
				// 	'手持移动视频设备',
				// 	'积水监测设备',
				// 	'公共设备'
				// ],
				devItem: ['中国', '美国', '巴西', '日本'],
				index: 0,
				checInfo: {
					devCode: ""
				}
			}
		},
		methods: {
			bindPickerChange: function(e) {
				let self = this;
				console.log('picker发送选择改变，携带值为', e.target.value)
				// this.index = e.target.value+1;
				// // this.checInfo.devCode= (this.index >= 9？this.index.toString():"0"+this.index);
				// if(self.index >= 10){
				// 	self.checInfo.devCode = self.index.toString()
				// }else{
				// 	self.checInfo.devCode = "0"+self.index;
				// }
				// console.log(self.checInfo.devCode);
			},
		}
	}
</script>

<style>
	.devPicker{width: 690upx;padding: 0 30upx;height: 95upx;background-color: #fff; display: flex;justify-content: space-between;align-items: center;}
	.uni-title{font-size: 32upx;line-height: 70upx;}
	picker{width: 550upx;padding: 0 40upx 0 20upx;height: 70upx;background-color: #f5f5f5;border-radius: 35upx;font-size: 32upx;color: #838182;line-height: 70upx;}
	.uni-list-cell-db{position: relative;}
	.arrow{width: 20upx;height: 10upx;position: absolute;right: 20upx;top: 28upx;}
	.arrow image{width: 100%;height: 100%;float: left;}
</style>
