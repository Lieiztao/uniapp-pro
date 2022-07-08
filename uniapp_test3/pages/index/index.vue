<template>
	<view class="content">
		<!-- <image class="logo" src="/static/logo.png"></image> -->
		<div id="luckysheet" style="margin:0px;padding:0px;position:absolute;width:100%;height:100%;left: 0px;top: 0px;">
			</div>
		<view class="text-area">
			<text class="title">{{title}}</text>
		</view>
	</view>
</template>

<script>
	import LuckyExcel from 'luckyexcel'
	import luckysheet from "../../common/luckysheet_import.js"
	export default {
		data() {
			return {
				title: 'Hello'
			}
		},
		onLoad() {

		},
		created(){
			const script= document.createElement('script');
			script.type = 'text/javascript';
			script.src = `https://cdn.jsdelivr.net/npm/luckysheet/dist/plugins/js/plugin.js`;
			document.head.appendChild(script);
		},
		mounted(){
			var options = {
					container: 'luckysheet', //luckysheet为容器id
					title: '',
					lang: 'zh',
					showinfobar: false,
					plugins: ['chart']
			}
			luckysheet.create(options)
		},
		methods: {

		}
	}
</script>

<style>
	.content {
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
	}

	.logo {
		height: 200rpx;
		width: 200rpx;
		margin-top: 200rpx;
		margin-left: auto;
		margin-right: auto;
		margin-bottom: 50rpx;
	}

	.text-area {
		display: flex;
		justify-content: center;
	}

	.title {
		font-size: 36rpx;
		color: #8f8f94;
	}
</style>
