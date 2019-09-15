<template>
	<view class="login-w">
		<view class="topbg">
			<image src="../../static/login/login_bg.png" mode=""></image>
		</view>
		<view class="log-input">
			<view class="tit">
				<image src="../../static/login/tit.png" mode=""></image>
			</view>
			<view class="login">
				<input type="text" class="user-name" placeholder="请输入用户名" v-model="user.userName">
				<input type="text" password="true" class="user-pass" placeholder="请输入密码" v-model="user.passWord">
			</view>
			<view class="forget">
				<text>忘记密码？</text>
			</view>
			<view class="btn" :class="{'cur':isActive}" @click="login"></view>
		</view>
		
		
	</view>
</template>

<script>
	export default{
		data(){
			return {
				user:{
					userName: "",
					passWord: ""
				},
				isActive: false, //登录按钮激活状态
			}
		},
		methods: {
			login: function() {
				let self = this;
				self.isActive = true;
				uni.request({
					url: "",
					data: self.user,
					method: "POST",
					header: {
						
					},
					success: (res) => {
						self.isActive = false;
					},
					fail: (res) => {
						
					},
					complete: (res) => {
						//登陆成功后跳转，提供接口后用放在成功调用
						uni.reLaunch({
							url: "../../pages/index/index"
						})
					},
				})

			}
		}
	}
</script>

<style>
	page{width: 100%;height: 100%;}
	.login-w{}
	.login-w .log-input{display: flex; flex-direction: column;padding: 0 100upx;}
	.login-w .topbg{width: 100%;height: 650upx;}
	.login-w .topbg image{width: 100%;height: 100%;}
	.login-w .tit{width: 528upx;height: 80upx;margin: 0 auto;}
	.login-w .tit image{width: 100%;height: 100%;}
	.login-w .login{margin: 0 auto;margin-top: 60upx;}
	.login-w .login input{width: 400upx;height: 100upx;border-bottom: 1upx solid #e5e5e5;padding: 0 70upx 0upx;box-sizing: content-box;font-size: 30upx;line-height: 60upx;margin-bottom: 30upx;background-size: 30upx 30upx;background-position: 15upx 35upx;background-repeat:  no-repeat;}
	.login-w .login .user-name{background-image: url(../../static/login/user.png);}
	.login-w .login .user-pass{background-image: url(../../static/login/lock.png);}
	.login-w .forget{font-size: 22upx;color: #66b3ff;text-align: right;}
	.login-w .btn{width: 100%;height: 80upx;background-image: url('../../static/login/dlbtn.png');background-repeat: no-repeat;background-size: 100% 100%;margin-top: 60upx;}
	.login-w .btn.cur{background-image: url('../../static/login/dlbtn_cur.png');}
</style>
