<template>
  <div class="recommend">
    <div v-for="(item, index) in recommends" :key="index" class="recommend-item">
      <a :href="item.link">
        <img :src="item.image" alt="">
        <div>{{item.title}}</div>
      </a>
    </div>
  </div>
</template>

<script>
  export default {
    name: 'RecommendView',
    props: {
      recommends: {
        type: Array,
        default() {
          return []
        }
      }
    }
  }
</script>

<style scoped>
 .recommend {
    display: flex;
    padding: 10px 0 20px;
    font-size: 14px;
    text-align: center;
    border-bottom: 8px solid #eee;
    /* width: 100%; */
  }
  .recommend-item {
    flex: 1
  }
  .recommend-item img {
    width: 70px;
    height: 70px;
    margin-bottom: 8px;
  }
</style>