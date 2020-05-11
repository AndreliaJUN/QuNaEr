<template>
  <div class="wrapper">
     <swiper :options="swiperOptions">
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
  data () {
      return {
          swiperOptions:{
              pagination:'.swiper-pagination',
              loop:true
          },
          swiperList:[{
              id:'0001',
              imgUrl:'https://imgs.qunarzz.com/vs_ceph_vs_vacation_pm/e4fd6ba9-84ad-4b6d-a73a-15298e8c3fcd.jpg'
          }, {
              id:'0002',
              imgUrl:'https://img1.qunarzz.com/qs/2001/d9/8844a335554e1c02.jpg'
          }]
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
