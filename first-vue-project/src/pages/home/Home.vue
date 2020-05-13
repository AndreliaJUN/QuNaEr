<template>
  <div>
   <home-header :city="city"></home-header>
   <home-swiper :swiperList="swiperList"></home-swiper>
   <home-icon :iconList="iconList"></home-icon>
   <home-recommand :recommendList="recommendList"></home-recommand>
   <home-weekend :weekendList="weekendList"></home-weekend>
  </div>
</template>

<script>
import HomeHeader from './components/Header'
import HomeSwiper from './components/Swiper'
import HomeIcon from './components/Icons'
import HomeRecommand from './components/Recommand'
import HomeWeekend from './components/Weekend'
import axios from 'axios'
    export default {
 name:'Home',
 components:{
     HomeHeader,
     HomeSwiper,
     HomeIcon,
	 HomeRecommand,
	 HomeWeekend
 },
 data() {
	 return {
		 city:'',
		 swiperList:[],
		 iconList:[],
		 recommendList:[],
		 weekendList:[]
	 }
 },
 methods:{
	 getHomeInfo(){
        axios.get('/static/mock/index.json')
		.then(this.getHomeInfoSucc)
	 },
	 getHomeInfoSucc(res){
		  
		 res=res.data
		 if(res.ret&&res.data){
			 const data=res.data
			 this.city=data.city
			 this.swiperList=data.swiperList
			 this.iconList=data.iconList
			 this.recommendList=data.recommendList
			 this.weekendList=data.weekendList
		 }
		 console.log(res)
	 }
 },
 mounted () {
	 this.getHomeInfo()
 }
} 
</script>

<style>

</style>
