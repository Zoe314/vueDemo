<template>
  <div id="app">
    <img src="../resource/1-10.png">
    <h1>{{ msg }}</h1>
    <Header></Header>
    <button @click="change">点击改变</button>

    <div class="tabbar">
      <ul>
        <li>我的</li>
        <li>列表</li>
        <li>购物车</li>
        <li>修改信息</li>
      </ul>
    </div>
  </div>
</template>

<script>
import Header from '../src/components/Header.vue'

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
