<template>
  <div class="wrapper">
     <swiper :options="swiperOptions" v-if="showSwiper">
    <swiper-slide v-for="item of swiperList"  :key="item.id">
       <img  class="swiper-img" :src="item.imgUrl" />
    </swiper-slide>
    <div class="swiper-pagination" slot="pagination"></div>
  </swiper>
  </div>
</template>

<script>
export default {
  name:'HomeSwiper',
  props: {
	  swiperList:Array
  },
  data () {
      return {
          swiperOptions:{
              pagination:'.swiper-pagination',
              loop:true
          }
      }
  },
  computed: {
	  showSwiper () {
		  return this.swiperList.length
	  }
  }
}
</script>

<style scoped lang="stylus">
.wrapper >>> .swiper-pagination-bullet-active 
  background:#fff
.wrapper
 width:100%
 height:31.25vw
 background:#eee
 .swiper-img
   width:100%

</style>
