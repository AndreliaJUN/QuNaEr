<template>
  <div>
   <home-header></home-header>
   <home-swiper></home-swiper>
   <home-icon></home-icon>
   <home-recommand></home-recommand>
   <home-weekend></home-weekend>
  </div>
</template>

<script>
import HomeHeader from './components/Header'
import HomeSwiper from './components/Swiper'
import HomeIcon from './components/Icons'
import HomeRecommand from './components/Recommand'
import HomeWeekend from './components/Weekend'
    export default {
 name:'Home',
 components:{
     HomeHeader,
     HomeSwiper,
     HomeIcon,
	 HomeRecommand,
	 HomeWeekend
 }
}
</script>

<style>

</style>
