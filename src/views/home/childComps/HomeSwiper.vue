<template>
<div>
  <swiper>
    <swiper-item v-for="(item, id) in banners" :key="id">
      <a :href="item.link">
        <img :src="item.image" alt="" @load="imageLoad">
      </a>
    </swiper-item>
  </swiper>
</div>
</template>

<script>
  import {Swiper, SwiperItem} from 'components/common/swiper'

 export default {
  name: 'HomeSwiper',
  props: {
    banners: {
      type: Array,
      default() {
        return []
      }
    }
  },
  data() {
    return {
      isLoad: false
    }
  },  
  components: {
    Swiper,
    SwiperItem
  },
  methods: {
    // 监听轮播图加载完成
    imageLoad() {
      if(!this.isLoad) { //减少轮播图监听事件的频率
        this.$emit('swiperImageLoad')
        this.isLoad = true
      }
    }
  }
 }
</script>