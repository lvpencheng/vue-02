<template>
	<div class="home" v-if="data.data">
		<!-- 页头 -->
	
		<div class="div4">
			
			<van-sticky>
				<van-button  style="width: 100%; position: relative;">
					<img class="img06" src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAEwAAAAyCAYAAAD2vz2aAAAAGXRFWHRTb2Z0d2FyZQBBZG9iZSBJbWFnZVJlYWR5ccllPAAAAyhpVFh0WE1MOmNvbS5hZG9iZS54bXAAAAAAADw/eHBhY2tldCBiZWdpbj0i77u/IiBpZD0iVzVNME1wQ2VoaUh6cmVTek5UY3prYzlkIj8+IDx4OnhtcG1ldGEgeG1sbnM6eD0iYWRvYmU6bnM6bWV0YS8iIHg6eG1wdGs9IkFkb2JlIFhNUCBDb3JlIDUuNi1jMTM4IDc5LjE1OTgyNCwgMjAxNi8wOS8xNC0wMTowOTowMSAgICAgICAgIj4gPHJkZjpSREYgeG1sbnM6cmRmPSJodHRwOi8vd3d3LnczLm9yZy8xOTk5LzAyLzIyLXJkZi1zeW50YXgtbnMjIj4gPHJkZjpEZXNjcmlwdGlvbiByZGY6YWJvdXQ9IiIgeG1sbnM6eG1wPSJodHRwOi8vbnMuYWRvYmUuY29tL3hhcC8xLjAvIiB4bWxuczp4bXBNTT0iaHR0cDovL25zLmFkb2JlLmNvbS94YXAvMS4wL21tLyIgeG1sbnM6c3RSZWY9Imh0dHA6Ly9ucy5hZG9iZS5jb20veGFwLzEuMC9zVHlwZS9SZXNvdXJjZVJlZiMiIHhtcDpDcmVhdG9yVG9vbD0iQWRvYmUgUGhvdG9zaG9wIENDIDIwMTcgKE1hY2ludG9zaCkiIHhtcE1NOkluc3RhbmNlSUQ9InhtcC5paWQ6MjQ2OUE2MkU0RTQ4MTFFNzgxOTZBRDJFQjk4Qjk0NjQiIHhtcE1NOkRvY3VtZW50SUQ9InhtcC5kaWQ6MjQ2OUE2MkY0RTQ4MTFFNzgxOTZBRDJFQjk4Qjk0NjQiPiA8eG1wTU06RGVyaXZlZEZyb20gc3RSZWY6aW5zdGFuY2VJRD0ieG1wLmlpZDpCOUQ0QkM2RjREQ0MxMUU3ODE5NkFEMkVCOThCOTQ2NCIgc3RSZWY6ZG9jdW1lbnRJRD0ieG1wLmRpZDpCOUQ0QkM3MDREQ0MxMUU3ODE5NkFEMkVCOThCOTQ2NCIvPiA8L3JkZjpEZXNjcmlwdGlvbj4gPC9yZGY6UkRGPiA8L3g6eG1wbWV0YT4gPD94cGFja2V0IGVuZD0iciI/PiL8gcIAAAF1SURBVHja7Ju/LwRRFEbf+FVsQ0dBdJKNSksUSqVCr6AhKxGVwn+gVUpQEI1So5XoZUOhEbKMDiESIeOTzPbvzpoxz5wvOd3duzsn++7cSXajZMU9OOeGXPmTiHtxIU7FoYh/oe+ZmPKsjSMJS1yY+RS7YrNDcTdi1Le4y4WbHrEorsRcUW8asrB2BsSxWEeYLVtiCWG2bIsJhPmnV+zkeV3/TZhLv2HzCLNlFWG2TIqRvHYZa97FR84XXEvnUSeZEft/LexZDIvXnIVFop6uCQ3RnaHHeBmO5FMBstrPjZdiTUyLlww9Bqs6w87FcobX9Vd56B+IZoZjXVlhP0f0qAwfJKS1ookw+w0HYaEFYQVs+j4ZE7Oed6o3sVfA00OphW2IBUN9S5xU+Uhad6A+ZhhDnyAMYQhDGMIQRhCGMIQhDGEEYQhDGMIQhjCCMIQhDGEIIwhDWFHCLP81vPOsezT0/BK3nj0tP1i59qxrGXrG3wIMAK5yNsqRAjAyAAAAAElFTkSuQmCC" alt="">
					<van-search  class="sousuo" placeholder="请输入搜索关键词"  />
					
				</van-button>
				
				<van-tabs v-model="active">
						<van-tab v-for="(item, index) in data.data.tabs" :title="item.name" ></van-tab>
				</van-tabs>
	
			</van-sticky>
		</div>

		
	
	
		<!-- 轮播图 -->
		
	
		
		<div v-show="active==0">
			<van-swipe :autoplay="3000">
			  <van-swipe-item v-for="(image, index) in data.data.data.sections[0].body.items" :key="index">
				<img class="img1" :src="image.img_url_webp" />
			  </van-swipe-item>
			</van-swipe>
			
			
			<!-- 宫格 -->
			<van-grid :column-num="5" icon-size="80">
			  <van-grid-item
			    v-for="value in data.data.data.sections[1].body.items"
			    :key="value.img_url_webp"
			    :icon="value.img_url_webp"
			    text=""
			  />
			</van-grid>
			
			<van-grid :column-num="5" icon-size="80">
			  <van-grid-item
			    v-for="value in data.data.data.sections[2].body.items"
			    :key="value.img_url_webp"
			    :icon="value.img_url_webp"
			    text=""
				
			  />
			</van-grid>
			<!-- 布局 -->
			<br>
			<br>
			<!-- 推荐 -->
			<div class="div1">
				<img :src="data.data.data.sections[4].body.items[0].img_url_webp" alt="" class="img02">
				<img :src="data.data.data.sections[4].body.items[1].img_url_webp" alt="" class="img03">
				<img :src="data.data.data.sections[4].body.items[2].img_url_webp" alt="" class="img03">
				
				
				<img :src="data.data.data.sections[6].body.items[0].img_url_webp" alt=""  class="img04">
				<img :src="data.data.data.sections[8].body.items[0].img_url_webp" alt=""  class="img04">
				
				
				
				<img :src="data.data.data.sections[10].body.items[0].img_url_webp" alt=""  class="img05">
				<img :src="data.data.data.sections[10].body.items[1].img_url_webp" alt=""  class="img05">
				
			
				
				<div class="div2">
					{{data.data.data.sections[10].body.items[0].product_name}}
					<br>
					{{data.data.data.sections[10].body.items[0].product_brief}}
					<br>
					<van-button type="danger">立即购买</van-button>
				</div>
				<div class="div2">
					{{data.data.data.sections[10].body.items[1].product_name}}
					<br>
					{{data.data.data.sections[10].body.items[1].product_brief}}
					<br>
					<van-button type="danger">立即购买</van-button>
				</div>
			
				<img :src="data.data.data.sections[12].body.items[0].img_url_webp" alt=""  class="img05">
				<img :src="data.data.data.sections[12].body.items[1].img_url_webp" alt=""  class="img05">
				<div class="div2">
					{{data.data.data.sections[12].body.items[0].product_name}}
					<br>
					{{data.data.data.sections[12].body.items[0].product_brief}}
					<br>
					<van-button type="danger">立即购买</van-button>
				</div>
				
				<div class="div2">
					{{data.data.data.sections[12].body.items[1].product_name}}
					<br>
					{{data.data.data.sections[12].body.items[1].product_brief}}
					<br>
					<van-button type="danger">立即购买</van-button>
					<br>
					<br>
				</div>
				<br>
				<br>
				<div>
					<img :src="data.data.data.sections[18].body.items[0].img_url_webp" alt="" class="img1">
					<br>
					<img :src="data.data.data.sections[20].body.items[0].img_url_webp" alt="" class="img04">
					<br>
					<br>
					<router-link to="/about" class="router02"><img :src="data.data.data.sections[69].body.items[0].img_url_webp" alt="" class="img04"></router-link>
					<br>
					<br>
				</div>
			</div>
		</div>

		<div class="shouji" v-show="active==1" style="height: 2000px;">
			<div style="background-color:  rgb(37, 1, 104);" class="div2-1">
				<img :src="data1.data.data.sections[0].body.items[0].img_url_webp" alt="" style="width: 100%;">
				<img style="width: 100%;" src="https://cdn.cnbj1.fds.api.mi-img.com/mi-mall/d14ef6575c3f5f1ed66753ffe13ee702.jpg?thumb=1&w=720&h=91" alt="">
			</div>
			<div class="div2-2">
				<van-swipe @change="onChange" :width="500" :touchable= "true">
					<div>
						<van-swipe-item><img :src=" data1.data.data.sections[6].body.items[0].img_url_webp" alt="">1111</van-swipe-item>
					
					</div>
					<div>
						<van-swipe-item><img :src=" data1.data.data.sections[6].body.items[1].img_url_webp" alt="">11111</van-swipe-item>
					</div>
					<div>
						<van-swipe-item><img :src=" data1.data.data.sections[6].body.items[2].img_url_webp" alt=""></van-swipe-item>
					</div>
					<div>
						<van-swipe-item><img :src=" data1.data.data.sections[6].body.items[3].img_url_webp" alt=""></van-swipe-item>
					</div>
					<div>
						<van-swipe-item><img :src=" data1.data.data.sections[6].body.items[4].img_url_webp" alt=""></van-swipe-item>
					</div>
				  
				  
				  
				</van-swipe>
				
			</div>
			
		
		</div>

	</div>
</template>

<script>
// @ is an alias to /src
// import HelloWorld from '@/components/HelloWorld.vue'

import {data1} from '../data.js'


export default {
	methods: {
	onChange(index) {
	  this.current = index;
	  console.log(this.current)
	}
	},
	data(){
		return {
			active:0,
			data:{},
			data1:{},
			// data2:{},
			value1:0,
			current: 0,
		}
	},
	created(){
		this.$http({
			url:'http://biger.applinzi.com/page.php',
			method:'get'
		}).then(res=>{
			console.log(res)
			this.data=res.data
			this.data1=data1
		})
		
	}

	
}
</script>
<style scoped>
	*{
		margin: 0;
	}
	.home{
		/* height: 4000px; */
	}
	.img1{
		width: 100%;
	}
	.img02{
		float: left;
		width: 50%;
		height: 351px;
	}
	.img03{
		float: right;
		width: 49%;
		height: 175.3px;
	}
	.img04{
		width: 100%;
		margin-top: 5px;
		margin-bottom: 5px;
	}
	.img05{
		float: right;
		width: 47%;
		margin: 7px;
	}
	.sousuo{
		display: inline-block;
		height: 20px;
		margin-right: 80px;
	}
	.img06{
		display: inline-block;
		float: left;
		height: 20px;
	}
	.span1{
		/* display: inline-block; */
		float: right;
		margin-top: -25px;

	}
	.div1{
		/* display: flex; */
	}
	.div2{
		float: left;
		width: 50%;
	}
	.router01{
		width: 100%;
	}
	.van-button--normal{
		position: relative;
	}

</style>