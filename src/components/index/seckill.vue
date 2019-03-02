<template>
  <!-- 秒杀 -->
  <div class="seckill">
    <!-- 头部 -->
    <div class="seckill-head">
      <div class="seckill-icon">
        <img src="static/img/index/clock.png">
      </div>
      <div class="seckill-text">
        <span class="seckill-title">限时秒杀</span>
        <span class="seckill-remarks">总有你想不到的低价</span>
      </div>
      <div class="count-down">
        <span class="count-down-text">当前场次</span>
        <span class="count-down-num count-down-hour">{{ seckillsHours }}</span>
        <span class="count-down-point">:</span>
        <span class="count-down-num count-down-minute">{{ seckillsMinutes }}</span>
        <span class="count-down-point">:</span>
        <span class="count-down-num count-down-seconds">{{ seckillsSeconds }}</span>
        <span class="count-down-text">后结束抢购</span>
      </div>
    </div>
    <!-- 内容 -->
    <div class="seckill-content">
      <div class="seckill-item" v-for="(item, index) in seckills.goodsList" :key="index">
        <div class="seckill-item-img">
          <router-link to="/goodsList"><img :src="item.img"></router-link>
        </div>
        <div class="seckill-item-info">
          <p>{{item.intro}}</p>
          <p>
            <span class="seckill-price text-danger"><Icon type="social-yen"></Icon>{{item.price}}</span>
            <span class="seckill-old-price"><s>{{item.realPrice}}</s></span>
          </p>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'seckill',
  props: ['seckillData']
};
</script>

<style scoped>

</style>
