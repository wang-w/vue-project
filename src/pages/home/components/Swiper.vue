<template>
  <div class="wrapper">
    <swiper :options="swiperOption">
      <swiper-slide v-for="slide in swiperList" :key="slide.id">
        <img class="swiper-img" :src="slide.imgUrl" />
      </swiper-slide>
      <div class="swiper-pagination"  slot="pagination"></div>
    </swiper>
  </div>
</template>
<script>
export default {
  name: 'HomeSwiper',
  data () {
    return {
      swiperOption: {
        pagination: '.swiper-pagination',
        loop: true
      },
      swiperList: [
        {
          id: '0001',
          imgUrl: 'http://img1.qunarzz.com/piao/fusion/1807/c6/44fce1467be17702.jpg_750x200_406f5fc3.jpg'
        },
        {
          id: '0002',
          imgUrl: 'http://img1.qunarzz.com/piao/fusion/1806/5a/a7fc8e091190d602.jpg_750x200_e3aae50d.jpg'
        }]
    }
  }
}
</script>
<style lang="stylus" scoped>
  .wrapper >>> .swiper-pagination-bullet-active
    background: #fff;
  .wrapper
    width: 100%
    height: 0
    overflow: hidden
    padding-bottom: 26.6%
    background: #eee
    .swiper-img
      width: 100%;
</style>
