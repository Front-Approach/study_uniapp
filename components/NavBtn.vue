<template>
	<view class="out">
		<view class="out-line">
			<view class="index-icon" @click="dqwh">
				<view class="img">
					<image src="/static/index/dqwh_index.png"></image>
				</view>
				<text>定期维护</text>
			</view>
			<view class="index-icon" @click="dqjc">
				<view class="img">
					<image src="/static/index/dqjc_index.png"></image>
				</view>
				<text>定期监测</text>
			</view>
		</view>
		<view class="out-line">
			<view class="index-icon" @click="wqgl">
				<view class="img">
					<image src="/static/index/wxgl_index.png"></image>
				</view>
				<text>维修管理</text>
			</view>
			<view class="index-icon"  @click="jdtq">
				<view class="img">
					<image src="/static/index/jdtq_index.png"></image>
				</view>
				<text>极端天气</text>
			</view>
		</view>
		
	</view>
	
</template>

<script>
	export default{
		props:{},
		methods:{
			 dqwh(){
				 uni.switchTab({
				     url: '/pages/maintenance/maintenance'
				 });
			 },
			 dqjc(){
				 uni.switchTab({
					 url: '/pages/testing/testing'
				 });
			 },
			 wxgl(){
				 uni.switchTab({
					 url: '/pages/management/management'
				 });
			 },
			 jdtq(){
				 uni.switchTab({
					 url: '/pages/weather/weather'
				 });
			 }
		}
	}
</script>

<style>
	.out{width: 500upx;margin: 0 auto;display: flex;flex-flow:wrap;justify-content: space-between}
	.out-line{width: 500upx;margin: 0 auto;display: flex;flex-flow:wrap;justify-content: space-between;margin-top: 80upx;}
	.index-icon{width: 160upx;height: 200upx;text-align: center;padding: 0upx;}
	.index-icon .img{width: 140upx;height: 140upx;}
	.index-icon image{width: 140upx;height: 140upx;}
	.index-icon text{font-size: 28upx;text-align: center;color: #828081;}
</style>
