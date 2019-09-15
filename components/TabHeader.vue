<template>
	<view class="tab-header">
		<view class="backBtn" @click="backToIndex"> <image src="/static/iconFont/icon_back.png" mode=""></image></view>
		<text>{{nowTit}}</text>
		<view class="location" @click="location"><image src="/static/iconFont/icon_local.png" mode=""></image></view>
	</view>
</template>

<script>
	export default{
		props: {
			nowTit: ""
		},
		data(){
			return {
				locationInfo:{
					longitude: "",
					latitude: ""
				}
			}
		},
		methods: {
			backToIndex(){
				//关闭所有页面，打开到应用内的某个页面。
				uni.reLaunch({
				    url: '../../pages/index/index'
				});
			},
			location(){
				let self = this;
				uni.getLocation({
					type: 'wgs84',
					success: function (res) {
						self.locationInfo.longitude = res.longitude;
						self.locationInfo.latitude = res.latitude;
						alert(self.locationInfo.longitude +":"+ self.locationInfo.latitude);
					},
					fail(){
						
					},
					complete(){
						
					}
				})
			}
		}
	}
</script>

<style>
	.tab-header{width: 690upx;padding: 0 30upx;height: 100upx;padding-top: 60upx;box-sizing: content-box;background: linear-gradient(left,#0384fc,#22a8ff);display: flex;justify-content: space-between;align-items: center;}
	.backBtn{width: 40upx;height: 40upx;}
	.backBtn image{width: 100%;height: 100%;}
	.location{width: 40upx;height: 40upx;}
	.location image{width: 100%;height: 100%;}
	.tab-header text{font-size: 40upx;color: #fff;line-height: 100upx;}
</style>
