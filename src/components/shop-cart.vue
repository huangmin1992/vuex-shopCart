<template>
	<div class="shop-list">
		<table>
			<tr class="shop-listtitle">
				<td>id</td>
				<td>名称</td>
				<td>价格</td>
				<td>数量</td>
				<td>操作</td>
			</tr>
			<tr v-for="item in cartData" class="shop-listinfo">
				<td>{{item.id}}</td>
				<td>{{item.name}}</td>
				<td>{{item.price}}</td>
				<td>{{item.num}}</td>
				<td><button class="shop-dele dele-btn" @click="deletShop(item)">删除</button></td>
			</tr>
			<tr v-if="cartData.length<=0">
				<td colspan="5">暂无数据</td>
			</tr>
			<tr>
				<td colspan="2">总数：{{totalNum}}</td>
				<td colspan="2">总价格：{{totalPrice}}</td>
				<td><button class="dele-cart dele-btn" @click="clearCart">清空购物车</button></td>
			</tr>
		</table>
	</div>
</template>

<script>
	import {mapGetters,mapActions} from "vuex";
	export default{
		name:'shopCart',
		data(){
			return{
				
			}
		},
		computed:{
			...mapGetters({
				cartData:'addShopList',
				totalNum:'totalNum',
				totalPrice:'totalPrice'
			})
		},
		methods:{
			...mapActions({
				clearCart:'clearToCart',
				deletShop:'deletToShop'
			})
		}
	}
</script>

<style lang="less" scoped>
	@import url('../../static/public.less');
	.dele-btn{
		background-color: red !important;
	}
	.dele-btn:hover{
		background-color: #bd0000 !important;
	}
</style>