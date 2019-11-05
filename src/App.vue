<template>
  <div id="app">
    <!-- <div id="nav"> -->
    <!--  <router-link to="/"></router-link> |
      <router-link to="/about"></router-link>
    <!-- </div> -->
    <router-view/>
	<van-tabbar v-model="active">
	  <van-tabbar-item icon="home-o">首页</van-tabbar-item>
	  <van-tabbar-item  icon="description" to="/fenglei">分类</van-tabbar-item>
	  <van-tabbar-item icon="shopping-cart-o">购物车</van-tabbar-item>
	  <van-tabbar-item icon="manager-o">我的</van-tabbar-item>
	</van-tabbar>

  </div>
</template>

<script>
	export default {
	  data() {
	    return {
	      active: 0
	    }
	  }
	}
</script>

<style lang="less">
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

#nav {
  padding: 30px;

  a {
    font-weight: bold;
    color: #2c3e50;

    &.router-link-exact-active {
      color: #42b983;
    }
  }
}
</style>
