<template>
  <div id="list">
    <div v-for="(item, index) in listData" :key="index" class="item">
      <span class="icon">
        <svg :fill="item.iconColor"><use :xlink:href="item.icon"></use></svg>
      </span>
      <div class="info">{{item.info}}</div>
    </div>
  </div>
</template>

<script>
  export default {
    name: 'ListView',
    props: {
      listData: {
        type: Array,
        default() {
          return []
        }
      }
    }
  }
</script>

<style scoped>
  #list {
    background-color: #fff;
    font-size: 18px;
    color: #333;
    margin-bottom: 10px;
  }

  #list .item {
    height: 50px;
    line-height: 50px;
    position: relative;
  }

  .icon svg {
    width: 22px;
    height: 22px;
  }

  .item .icon {
    margin-top: 10px;
    position: absolute;
    left: 16px;
    top: -7px;
  }

  .item .info {
    margin-left: 45px;
    border-bottom: 1px solid rgba(100, 100, 100, .1);
    padding-left: 5px;
  }

  .item:last-of-type .info {
    border-bottom: none;
  }
</style>