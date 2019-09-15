<template>
	<view class="tabw">
		<TabHeader :nowTit="nowTit"></TabHeader>
		<Picker></Picker>
	</view>
	
	
</template>

<script>
	import TabHeader from '../../components/TabHeader.vue'
	import Picker from '../../components/Picker.vue'
	export default{
		components: {TabHeader, Picker},
		data(){
			return{
				nowTit: "定期维护",
			}
		},
		methods: {
			
		}
		
	}
</script>

<style>
	page{background-color: #f5f5f5;}
</style>
