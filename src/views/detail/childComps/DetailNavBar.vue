<template>
  <div class="nav-bar">
    <nav-bar>
      <div slot="left" class="left" @click="backClick">
        <img src="~assets/img/common/back.svg" alt="">
      </div>
      <div slot="center" class="title">
        <div v-for="(item, index) in title" 
             :key="index"
             class="title-item"
             :class="{active: index === currentIndex}"
             @click="itemClick(index)">
          {{item}}
        </div>
      </div>
    </nav-bar>
  </div>
</template>

<script>
  import NavBar from 'components/common/navbar/NavBar'

  export default {
    name: 'DetailNavBar',
    data() {
      return {
        title: ['商品', '参数', '评论', '推荐'],
        currentIndex: 0
      }
    },
    components: {
      NavBar
    },
    methods: {
      itemClick(index) {
        this.currentIndex = index
        this.$emit('itemClick', index)
      },
      backClick() {
        // 路由返回 首页
        this.$router.back()
      }
    }
  }
</script>

<style scoped>
  .title {
    display: flex;
    font-size: 15px;
  }
  .title-item {
    flex:1
  }
  .active {
    color: var(--color-high-text);
  }
  .left img{
    margin-top: 12px;
  }
</style>