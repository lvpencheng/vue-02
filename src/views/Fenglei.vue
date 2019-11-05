<template>
	<div >
	
		<div class="dingbu">
			<van-nav-bar
			  title="分类"
			  left-text=""
			  right-text="搜索"
			  left-arrow
			  @click-left="onClickLeft"
			  @click-right="onClickRight"
			  
			/>
		</div>
		<!-- 布局 -->
		<div class="div1">
			<van-row>
				<van-col span="6">
					<div>
						<van-sidebar v-model="activeKey" >
							<van-sidebar-item :title="item.category_name.toString()" v-for="(item,index) in data3.data" />
						</van-sidebar>
					</div>
					
				</van-col>
					
				<van-col span="18" v-for="(item1, index1) in data3.data" v-show="activeKey==index1">
					<div class="div2"  >
						<div class="div3" v-for="item2 in item1.category_list">
							<div v-if="item2.view_type=='cells_auto_fill' " >
								<img :src="item2.body.items[0].img_url_webp" style="width: 100%;" >
							</div>
							<div v-if="item2.view_type=='category_title'">
								<van-divider>{{item2.body.category_name}}</van-divider>
							</div>
							<div v-if="item2.view_type=='category_group'">
								<div >
									<van-grid :column-num="3" :icon-size="70">
									  <van-grid-item
									    v-for="value in item2.body.items"
									    :icon="value.img_url_webp"
									    :text="value.product_name"
										
									  />
									</van-grid>
								</div>
								
								
							</div>
						</div>
					</div>
				</van-col>
			</van-row>
			
			
		</div>
		<div class="div2">
		
		</div>
		{{data3.data[0].category_name}}
		

	</div>
</template>

<script>
	import {data3} from '../data.js'
	 
	import 	Vue from 'vue';
	import { NavBar } from 'vant';
	
	Vue.use(NavBar);
	
	export default({
		  data() {
		    return {
		      data3:data3,
			  activeKey: 0,
			  ppp:0
		    };
		  },
		methods: {
		onClickLeft() {
		  // Toast('返回');
		  this.$router.go(-1);
		  
		},
		onClickRight() {
		  // Toast('按钮');
		  this.$toast('sousuo');
		}
		}
	})
</script>

<style>
</style>
