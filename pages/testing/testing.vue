<template>
	<view class="">
		<TabHeader :nowTit="nowTit"></TabHeader>
	</view>
	
	
</template>

<script>
	import TabHeader from '../../components/TabHeader.vue'
	export default{
		components: {TabHeader},
		data(){
			return{
				nowTit: "定期检测",
			}
		},
		
	}
</script>

<style>
</style>
