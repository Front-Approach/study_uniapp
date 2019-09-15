<template>
	<view class="zdTabBar">
		<view class="ul">
			<view :class="['li',current == index?'cur' :'']" v-for="(item,index) in taBbarList" :key="index" @tap="navigatorTo(item.url)">
				<view class="img" v-if="item.type == 0">
					<image :src="current == index ? item.selectIcon : item.icon" mode="widthFix"></image>
				</view>
				<view class="ic" v-if="item.type == 1">+</view>
				<view class="p">{{item.name}}</view>
			</view>
		</view>
	</view>

</template>

<script>
	export default {
		props: {
			current: {
				type: Number,
				default: 0
			}
		},
		data() {
			return {
				taBbarList: [{
						type: 0,
						icon: '/static/logo.png',
						selectIcon: '/static/logo_cur.png',
						name: '首页',
						url: '/pages/index/index'
					},
					{
						type: 1,
						icon: '/static/logo.png',
						selectIcon: '/static/logo_cur.png',
						name: '列表',
						url: '/pages/list/list'
					},
					{
						type: 0,
						icon: '/static/logo.png',
						selectIcon: '/static/logo_cur.png',
						name: '我的',
						url: '/pages/my/my'
					}
				]
			}
		},
		methods: {
			navigatorTo(e) {
				uni.redirectTo({
					url: e,
				});
			}
		}
	}
</script>
<style>
	.zdTabBar {
		position: fixed;
		left: 0;
		bottom: 0;
		right: 0;
		z-index: 20;
		background: #ffffff;

		.ul {
			.df;

			.li {
				flex: 1;
				padding-top: 5px;
				position: relative;

				.img {
					width: 25px;
					height: 25px;
					overflow: hidden;
					margin: 0 auto;
				}

				.ic {
					width: 40px;
					height: 40px;
					.bgja;
					border-radius: 50%;
					text-align: center;
					font-size: 20px;
					line-height: 40px;
					font-weight: bold;
					color: #ffffff;
					margin: -20px auto 5px;
				}

				.p {
					margin-top: 2px;
					text-align: center;
					font-size: 10px;
					line-height: 18px;
				}

				&.cur {
					.p {
						color: @redc;
					}
				}
			}
		}
	}
</style>
