<template>
  <div id="app">
    <img src="../resource/1-10.png">
    <h1>{{ msg }}</h1>
    <Header></Header>
    <button @click="change">点击改变</button>

    <div class="tabbar">
      <ul>
        <li><router-link to="/my">我的</router-link></li>
        <li><router-link to="/list">列表</router-link></li>
        <li><router-link to="/shopcar">购物车</router-link></li>
        <li><router-link to="/edit">修改信息</router-link></li>
      </ul>
      <router-view></router-view>
    </div>
  </div>
</template>

<script>
import VueRouter from 'vue-router'
import Header from '../src/components/Header.vue'
const My = {template: '<div>foo</div>'};
const List = {template: '<div>foo</div>'};
const Shopcar = {template: '<div>foo</div>'};
const Edit = {template: '<div>修改</div>'};
const routes=[
  {path:'/my',component:My},
  {path:'/list',component:List},
  {path:'/shopcar',component:Shopcar},
  {path:'/edit',component:Edit}
]
const router = new VueRouter({
      routes // （缩写）相当于 routes: routes
    })

    // 4. 创建和挂载根实例。
    // 记得要通过 router 配置参数注入路由，
    // 从而让整个应用都有路由功能
    const app = new Vue({
      router
    }).$mount('#app')

export default {
  name: 'app',
  data () {
    return {
      msg: '第一个项目开始'
    }
  },
  methods:{
    change (){
      this.msg = this.msg.split('').reverse().join('');
    }
  }
}
</script>

<style lang="scss">
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

h1, h2 {
  font-weight: normal;
}

ul {
  list-style-type: none;
  padding: 0;
}
.tabbar>ul{
  display:flex;
  width:100%;
  margin-bottom:-1px;
}

.tabbar>ul>li{
  width:20%;
  display:inline-block;
  margin:50px 50px 0 0 ;
}

button{
  height:60px;
  font-size:20px;
}
a {
  color: #42b983;
}
</style>
