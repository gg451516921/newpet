<template>
<div class="water">
<md-card :md-theme="'white'" v-for="item in banner">
  <md-card-header>{{item.header}}</md-card-header>
  <md-card-content>
  	<div class="title">
  		<img :src="item.title"/>
  	</div>
  	<div class="big">
  		<img :src="item.big"/>
  	</div>
  	<div class="middle">
  		<img v-for="m in item.middle" :src="m" alt="" />
  		
  	</div>
  	<div class="small">
		<img v-for="s in item.small" :src="s" alt="" />  		  		  		
  	</div>
  </md-card-content>
</md-card>

</div>
</template>

<script>
import Vue from 'vue'
import VueAwesomeSwiper from 'vue-awesome-swiper'
Vue.use(VueAwesomeSwiper)
import { swiper, swiperSlide } from 'vue-awesome-swiper'
import prod from "../../../static/product.json"
export default{
	 components: {
        swiper,
         swiperSlide
   },
	data(){
		return{
		banner:prod.banner4,
		water:prod.water,
		swiperOption: {
             setWrapperSize :true,
             mousewheelControl : true,
             observeParents:true,
             slidesPerView : 4,
        }
		}
	},
	mounted:function(){
		var text=this.$el.querySelectorAll(".text");
		for(var i=0;i<text.length;i++){
			text[i].innerText=text[i].innerText.substring(0,10).concat("....")
		}
	}
}
</script>

<style type="text/css" lang="scss" scoped="scoped" >
@import "../../assets/func.scss";
.md-card-header{
	font-size:px2em(30px) ;
	font-family: simhei;
	padding: 20px 10px;
}
.md-card-content{
	overflow:hidden;
	padding-left: 0;
	padding-right: 0;
	.big{
		width:px2em(335px);
		float: left;
	}
	.middle{
		width:px2em(335px);
		float:right;
	}
	.small{
		float: left;
	}
	.small img
	{
		width:px2em(375px);
		float: left;
	}
}
.myswiper{
	width: px2em(750px);
	img{
		width:100%
	}
	.text{
		font-size: px2em(25px);
		width:px2em(160px);
		line-height: px2em(30px);
		margin: px2em(15px) auto;
		height:px2em(55px);
		font-family: "small fonts";
		color: black;
	}
	.price{
		font-size: px2em(30px);
		text-align: center;
		color: red;
		width:px2em(160px);
		margin:0 auto;
		height:px2em(35px);
	}
}
</style>