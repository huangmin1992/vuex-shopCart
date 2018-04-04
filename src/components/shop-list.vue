<template>
	<div class="shop-list">
		<table>
			<tr class="shop-listtitle">
				<td>id</td>
				<td>名称</td>
				<td>价格</td>
				<td>操作</td>
			</tr>
			<tr v-for="item in shopList" class="shop-listinfo">
				<td>{{item.id}}</td>
				<td>{{item.name}}</td>
				<td>{{item.price}}</td>
				<td><button @click="addToCart(item)">加入购物车</button></td>
			</tr>
		</table>
	</div>
</template>

<script>
	import{mapActions} from "vuex";
	export default{
		name:'shopList',
		data(){
			return{

			}
		},
		computed:{
			shopList(){
				return this.$store.getters.getShopList
			}
		},
		methods:{
			...mapActions(['addToCart'])
		}
	}
</script>
<style lang="less" scoped>
	@import url('../../static/public.less');
</style>