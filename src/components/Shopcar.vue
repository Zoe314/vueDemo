<template>
	<table id="container" width=500; border=1;>
		<tr>
			<th>编号</th>
			<th>名称</th>
			<th>图片</th>
			<th>价格</th>
			<th>数量</th>
			<th>小计价格</th>
			<th>操作</th>
		</tr>
		<tr v-for="shop in shoplist">
			<td>{{shop.id}}</td>
			<td>{{shop.title}}</td>
			<td><img v-bind:src="shop.img" width="200" alt="" /></td>
			<td>{{shop.price}}</td>
			<td><input type="number" v-model="shop.num"/></td>
			<td>{{(shop.num*shop.price).toFixed(2)}}</td>
			<td><button>删除</button></td>
		</tr>
	</table>
</template>

<script>
	export default{
		data () {
			return{
				shoplist:[
					{id:1,title:"臭豆腐",img:"../resource/1.jpg",price:3.99,num:44},
					{id:2,title:"与豆腐",img:"../resource/1.jpg",price:3.99,num:21},
					{id:3,title:"豆浆",img:"../resource/1.jpg",price:3.99,num:20},
					{id:4,title:"豆福闹",img:"../resource/1.jpg",price:3.99,num:10},
				]
			}
		},
		methods:{

		}
	}
</script>

<style>
	
</style>