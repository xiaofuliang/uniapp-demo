<template>
	<view style="width: 100%;">
		<view class="grace-border-b" :key="item.code" v-for="item in groups">
			<view>
				<text class="grace-title">{{item.name}}</text>
			</view>
			<view :class="item.funcList.length<5?'grace-grids four':'grace-grids five'">
				<view @tap="toNext(item2.mwurl,item2.funcid)" v-for="item2 in item.funcList" :key="item2.id">
					{{item2.mwurl}}
					{{item2.funcid}}
					<view class="grace-grids-items">
						
						<view class="grace-grids-icon" mode="widthFix">
							<text class="exam-icons" :class="[item2.mwicon,{'grace-grids-d':!item2.opening}]"></text>
						</view>
						<text class="grace-grids-text" :class="{'grace-grids-d':!item2.opening}">{{item2.funcname}}</text>
					</view>
				</view>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		props: {
			value: Object,
			all: Boolean
		},
		data() {
			return {
				groups: []
			};
		},
		created() {
			this.loadData();
		},

		methods: {
			loadData() {

				this.groups = [{"name":"题库练习","code":"1","funcList":[{"funcid":"1175342994124050432","funcname":"章节练习","type":"1","subjectscode":"105-100","pcicon":"iconzhangjie","mwicon":"iconzhangjie","pcurl":"/practice/chapter","mwurl":"/practice/chapter","opening":true,"opentime":"2019-09-21 17:46:24","duetime":"2020-02-23 23:59:59"},{"funcid":"1175343437021581312","funcname":"模拟考试","type":"1","subjectscode":"105-100","pcicon":"iconlilunxuexi","mwicon":"iconlilunxuexi","pcurl":"/examination/mock","mwurl":"/examination/mock","opening":true,"opentime":"2019-09-21 17:46:24","duetime":"2020-02-23 23:59:59"},{"funcid":"1175343632723611648","funcname":"历年真题","type":"1","subjectscode":"105-100","pcicon":"iconmonikaoshi","mwicon":"iconmonikaoshi","pcurl":"/examination/old","mwurl":"/examination/old","opening":true,"opentime":"2019-09-21 17:46:24","duetime":"2020-02-23 23:59:59"},{"funcid":"1175343853834735616","funcname":"随机练习","type":"1","subjectscode":"105-100","pcicon":"iconxitiku","mwicon":"iconxitiku","pcurl":"/practice/random-practice","mwurl":"/practice/random-practice","opening":true,"opentime":"2019-09-21 17:46:24","duetime":"2020-02-23 23:59:59"},{"funcid":"1175344021434929152","funcname":"错题集","type":"1","subjectscode":"105-100","pcicon":"iconcuotiku","mwicon":"iconcuotiku","pcurl":"/wrong-question","mwurl":"/wrong-question","opening":true,"opentime":"2019-09-21 17:46:24","duetime":"2020-02-23 23:59:59"}]},{"name":"实操练习","code":"2","funcList":[{"funcid":"1183618032547794944","funcname":"识别","type":"2","subjectscode":"105-100","pcicon":"iconshibie","mwicon":"iconshibie","pcurl":"/practice/chapter-practice?chapter=识别题","mwurl":"/practice/chapter-practice?chapter=识别题","opening":true,"opentime":"2019-11-07 11:43:24","duetime":"2020-02-08 23:59:59"},{"funcid":"1183618823408979968","funcname":"指认","type":"2","subjectscode":"105-100","pcicon":"iconzhiren1","mwicon":"iconzhiren1","pcurl":"/practice/chapter-practice?chapter=指认题","mwurl":"/practice/chapter-practice?chapter=指认题","opening":true,"opentime":"2019-11-07 11:43:24","duetime":"2020-02-08 23:59:59"},{"funcid":"1183619307339386880","funcname":"口述","type":"2","subjectscode":"105-100","pcicon":"iconkoushu","mwicon":"iconkoushu","pcurl":"/practice/chapter-practice?chapter=口述题","mwurl":"/practice/chapter-practice?chapter=口述题","opening":true,"opentime":"2019-11-07 11:43:24","duetime":"2020-02-08 23:59:59"}]},{"name":"主机学习","code":"3","funcList":[{"funcid":"1182476040476430336","funcname":"松江主机","type":"3","subjectscode":"105-100","pcicon":"iconsongjiang","mwicon":"iconsongjiang","pcurl":"/zhuji/songjiang.html","mwurl":"/zhuji/songjiang.html","opening":true,"opentime":"2019-11-07 11:43:24","duetime":"2020-02-08 23:59:59"},{"funcid":"1175344272615018496","funcname":"蓝天主机","type":"3","subjectscode":"105-100","pcicon":"iconlantian","mwicon":"iconlantian","pcurl":"/zhuji/lantian.html","mwurl":"/zhuji/lantian.html","opening":true,"opentime":"2019-09-21 17:46:24","duetime":"2020-02-23 23:59:59"},{"funcid":"1175344597983956992","funcname":"海湾主机","type":"3","subjectscode":"105-100","pcicon":"iconhaiwan1","mwicon":"iconhaiwan1","pcurl":"/zhuji/haiwan.html","mwurl":"/zhuji/haiwan.html","opening":true,"opentime":"2019-09-21 17:46:24","duetime":"2020-02-23 23:59:59"},{"funcid":"1182829841876127744","funcname":"北大青鸟","type":"3","subjectscode":"105-100","pcicon":"iconbeidaqingniao","mwicon":"iconbeidaqingniao","pcurl":"/zhuji/beidaqingniao.html","mwurl":"/zhuji/beidaqingniao.html","opening":true,"opentime":"2019-11-07 11:43:24","duetime":"2020-02-08 23:59:59"}]},{"name":"视频学习","code":"4","funcList":[{"funcid":"1183367045446766592","funcname":"基础理论","type":"4","subjectscode":"105-100","pcicon":"/sys/common/download//files/20191105/20160722094140586_1572927461720.jpg","mwicon":"iconxitiku","pcurl":"/video","mwurl":"/video","opening":true,"opentime":"2019-11-07 11:43:24","duetime":"2020-02-08 23:59:59"}]},{"name":"3D学习","code":"5","funcList":[{"funcid":"1202784628847546368","funcname":"333","type":"5","subjectscode":"105-100","pcicon":null,"mwicon":"iconhaiwan1","pcurl":"111","mwurl":"sss","opening":false,"opentime":null,"duetime":null}]},{"name":"资料","code":"6","funcList":[{"funcid":"1199629284659040256","funcname":"试卷","type":"6","subjectscode":"105-100","pcicon":null,"mwicon":"iconlilunxuexi","pcurl":"11","mwurl":"/datum","opening":true,"opentime":"2019-11-28 14:28:38","duetime":"2020-01-29 23:59:59"}]},{"name":"电子书","code":"7","funcList":[{"funcid":"1201696583515770880","funcname":"初级消防","type":"7","subjectscode":"105-100","pcicon":null,"mwicon":"iconhaiwan1","pcurl":"1111","mwurl":"/ebook","opening":true,"opentime":"2019-12-03 10:58:37","duetime":"2020-01-03 23:59:59"}]}];

			
			},
			toNext(mwurl,funcid){
				console.log(mwurl)
				console.log(funcid)
			},
			replaceUrl(url) {
				return url.replace('/practice/chapter-practice', '/pages/tiku/chapterPractice')
					.replace('/practice/chapter', '/pages/tiku/chapter')
					.replace('/examination/mock','/pages/tiku/mock')
					.replace('/practice/random-practice','/pages/tiku/randomPractice')
					.replace('/wrong-question','/pages/tiku/wrongQuestion');
			},

			getPathRoute(funcItem) {

				const {
					mwurl,
					funcid
				} = funcItem;
				let url = this.replaceUrl(mwurl);
			
				return url;

			}


		}
	};
</script>
<style scoped>
	.grace-title {
color: #333333;
	
	}
	.grace-title {
	line-height: 2em;
	display: -webkit-box;
	display: -webkit-flex;
	display: flex;
	-webkit-flex-wrap: nowrap;
	flex-wrap: nowrap;
	font-size: 28rpx;
	-webkit-box-pack: justify;
	-webkit-justify-content: space-between;
	justify-content: space-between;
	font-weight: bold;
	-webkit-box-align: center;
	-webkit-align-items: center;
	align-items: center;
	
	}
	
	.grace-grids {
	padding: 0;
	display: -webkit-box;
	display: -webkit-flex;
	display: flex;
	-webkit-flex-wrap: wrap;
	flex-wrap: wrap;
	
	}

.grace-grids-items {
width: 175rpx;
padding: 20rpx 0;
display: -webkit-box;
display: -webkit-flex;
display: flex;
box-sizing: border-box;
-webkit-box-orient: vertical;
-webkit-box-direction: normal;
-webkit-flex-direction: column;
flex-direction: column;
-webkit-box-align: center;
-webkit-align-items: center;
align-items: center;

}

.grace-grids-icon {
width: 100%;
height: 80rpx;
font-size: 60rpx;
line-height: 80rpx;
text-align: center;

}

.grace-grids-text {
line-height: 50rpx;
width: 100%;
text-align: center;
font-size: 24rpx;
margin-top: 2px;

}




	.grace-grids-icon {
		font-size: 80rpx
	}

	.grace-grids-d {
		color: #A2A8AC !important;
	}


	.iconzhangjie,
	.iconsongjiang,
	.iconkoushu,
	.iconshibie {
		color: #F9B11C;
	}

	.iconmonikaoshi,
	.iconlantian,
	.iconshicaojiaoxue {
		color: #3CBC9C;
	}

	.iconlinianzhenti,
	.iconhaiwan1,
	.iconkoushu {
		color: #FF7979;
	}

	.iconxitiku,
	.iconbeidaqingniao,
	.iconxiaofeijineng {
		color: #F673C6;
	}

	.iconcuotiku,
	.iconlilunxuexi,
	.iconzhiren1 {
		color: #9BB1FF;
	}

	.five .grace-grids-items {
		width: 140rpx;
	}
</style>
