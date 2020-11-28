<template>
	<view class="container">
		<view class="banner">
			<image class="bg" src="https://img-shop.qmimg.cn/s23107/2020/04/26/3eb7808bf105262604.jpg"></image>
			<view class="intro">
				<view class="greet">您好，{{ isLogin ? userInfo.nickName : '游客' }}</view>
				<view class="note">一杯奶茶，一口软欧包，在奈雪遇见两种美好</view>
			</view>
		</view>
		<view class="content"></view>
	</view>
</template>

<script>
import { mapState } from 'vuex';
export default {
	data() {
		return {
			title: 'Hello'
		};
	},
	computed: {
		...mapState(['isLogin', 'orderType', 'userInfo', 'chooseStore'])
	},
	onLoad() {},
	methods: {}
};
</script>

<style lang="scss">
.content {
	display: flex;
	flex-direction: column;
	align-items: center;
	justify-content: center;
}

.banner {
	position: relative;
	height: 600rpx;
	width: 100%;
	.bg {
		height: 600rpx;
		width: 100%;
	}
	.intro {
		position: absolute;
		display: flex;
		flex-direction: column;
		color: #ffffff;
		top: calc(50rpx + var(--status-bar-height));
		left: 40rpx;
		.greet {
			font-size: $font-size-lg;
			margin-bottom: 10rpx;
		}
		.note {
			font-size: $font-size-sm;
		}
	}
}
</style>
