<template>
	<view class="content">
		<list>
				<template  v-slot:default="{item,index}">
					<view>
						<text>{{item.name}}</text>
						<text>{{item.age}}</text>
					</view>
				</template>
		</list>
	</view>
</template>

<script>
		import List from "@/components/List.vue";
	export default {
		data() {
			return {
				title: 'Hello'
			}
		},
		components:{
			List
		},
		onLoad() {

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
