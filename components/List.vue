<template>
		<view>
			<view class="grace-border-b" :key="index" v-for="(item,index) in list">
				<slot :item="item" :index="index">
				</slot>
			</view>
		</view>
</template>

<script>
	export default {
		props: {
		},
		data() {
			return {
				list: []
			};
		},
		created() {
			this.loadData();
		},

		methods: {
			loadData() {
				
				this.list = [{name:'张三',age:'12'},{name:'张三',age:'12'},{name:'张三',age:'12'},{name:'张三',age:'12'},{name:'张三',age:'12'}]
			},
			


		}
	};
</script>
<style scoped>
	
</style>
