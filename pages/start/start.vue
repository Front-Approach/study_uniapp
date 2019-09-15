<template>
	<view class="start">
		<image src="/static/index/start.jpg" mode=""></image>
	</view>
</template>

<script>
	export default{
		data(){
			return{
				
			}
		},
		onReady(){
			setTimeout(function(){
				uni.redirectTo({
					url: '../index/index',
					success(){
						
					},
					fail(){
						
					},
					complete(){
						
					}
				})
			},3000);
		}
	}
</script>

<style>
	page{width: 100%;height: 100%;}
	.start{width: calc(100%);height: calc(100%);display: block;}
	.start image{width: 100%;height: 100%;}
</style>
