<template>
  <!-- 电脑专场 -->
  <div class="item-class">
    <div class="item-class-head">
      <span class="item-class-title">{{sectionData.title}}</span>
      <ul>
        <li v-for="(item, index) in sectionData.link" :key="index">
          <router-link to="/goodsList">{{item}}</router-link>
        </li>
      </ul>
    </div>
    <div class="item-class-content" v-for="(item, index) in sectionData.detail" :key="index">
      <div class="item-content-top">
        <div class="item-big-img">
          <router-link to="/goodsList">
            <img :src="item.bigImg" alt="">
          </router-link>
        </div>
        <div class="item-four-img">
          <div class="item-four-detail" v-for="(subItem, index) in item.itemFour" :key="index">
            <div class="item-four-detail-text">
              <p class="pt_bi_tit">{{subItem.title}}</p>
              <p class="pt_bi_promo">{{subItem.intro}}</p>
            </div>
            <div class="item-four-detail-img">
              <router-link to="/goodsList">
                <img :src="subItem.img" alt="">
              </router-link>
            </div>
          </div>
        </div>
      </div>
      <div class="item-content-bottom">
        <div class="item-content-bottom-img" v-for="(subImg, index) in item.itemContent" :key="index">
          <router-link to="/goodsList">
            <img :src="subImg">
          </router-link>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'indexSection',
  props: ['sectionData']
};
</script>

<style scoped>

  .seckill-icon img {
    width: 35px;
    height: 35px;
    margin-top: 6px;
    margin-left: 15px;
    animation-name: shake-clock;
    animation-duration: 0.3s;
    animation-iteration-count: infinite; /*设置无限循环*/
  }
  /*定义闹钟震动动画关键帧*/
  @keyframes shake-clock {
    0% {
      transform: rotate(-8deg);
    }
    50% {
      transform: rotate(8deg);
    }
    100% {
      transform: rotate(-8deg);
    }
  }

  .seckill-item-img img {
    width: 130px;
    height: 130px;
    margin-left: 15px;
    margin-top: 15px;
    transition: margin-top 0.3s;
  }
  .seckill-item-img:hover img {
    margin-top: 6px;
    transition: margin-top 0.3s;
  }

  .seckill-item-info i:first-child {
    font-size: 14px;
  }

  .item-class {
    width: 100%;
    height: 470px;
    margin-top: 15px;
    background-color: #fff;
  }
  .item-class-head {
    width: 100%;
    height: 50px;
    background-color: #4488a7;
  }

  .item-class-head ul {
    list-style: none;
    float: right;
    margin-right: 30px;
    line-height: 50px;
  }
  .item-class-head a {
    padding: 6px;
    margin-left: 15px;
    font-size: 12px;
    background-color: #6da6be;
    border: 1px solid #6da6be;
    text-decoration: none;
    color: #fff;
  }
  .item-class-eat-head a {
    background-color: #eeb955;
    border: 1px solid #eeb955;
  }
  .item-class-head a:hover {
    border: 1px solid #fff;
  }
  .item-class-head li {
    float: left;
  }
  .item-class-title {
    font-size: 25px;
    line-height: 50px;
    color: #fff;
    margin-left: 15px;
  }
  .item-class-content {
    width: 49%;
    cursor: pointer;
    border-right: 1px solid #ccc;
    margin-left: 0.9%;
    float: left;
  }
  .item-class-content:nth-child(odd) {
    border: none;
  }
  .item-content-top {
    width: 100%;
    height: 260px;
  }
  .item-big-img {
    width: 180px;
    height: 260px;
    overflow: hidden;
    float: left;
  }
  .item-big-img img {
    margin-left: 0px;
    transition: margin-left 0.3s;
  }
  .item-big-img:hover img {
    margin-left: -15px;
    transition: margin-left 0.3s;
  }
  .item-four-img {
    width: 303px;
    margin-left: 8px;
    float: left;
  }
  .item-four-detail img {
    margin-left: 0px;
    transition: margin-left 0.3s;
  }
  .item-four-detail:hover img {
    margin-left: -6px;
    transition: margin-left 0.3s;
  }
  .item-four-detail {
    width: 152px;
    height: 130px;
    margin-left: -1px;
    float: left;
  }
  .item-four-detail:first-child {
    border-right: 1px solid #ccc;
    border-bottom: 1px solid #ccc;
  }
  .item-four-detail:last-child {
    border-top: 1px solid #ccc;
    border-left: 1px solid #ccc;
  }
  .item-four-detail-text {
    width: 50px;
    margin-left: 5px;
    margin-top: 15px;
    float: left;
  }
  .item-four-detail-img {
    width: 96px;
    margin-top: 15px;
    overflow: hidden;
    float: left;
  }
  .item-four-detail-img img {
    margin-left: 5px;
    width: 90px;
  }
  .pt_bi_tit {
    font-weight: bold;
    font-size: 12px;
    color: #4488a7;
  }
  .pt_bi_promo {
    color: #00695c;
  }
  .item-content-bottom {
    width: 100%;
    margin-top: 8px;
  }
  .item-content-bottom-img {
    width: 156px;
    margin-right: 8px;
    overflow: hidden;
    float: left;
  }
  .item-content-bottom-img img {
    margin-left: 0px;
    transition: margin-left 0.3s;
  }
  .item-content-bottom-img:hover img {
    margin-left: -15px;
    transition: margin-left 0.3s;
  }

</style>
