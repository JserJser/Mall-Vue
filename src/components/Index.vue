<template>
  <div class="container">
    <!--搜索栏-->
    <Sreach></Sreach>
    <!--导航栏-->
    <HomeNav></HomeNav>
    <!-- 商品显示区域 -->
    <div class="content">
      <Section v-for="item in indexSections" :key="item.id" :sectionData="item"></Section>
    </div>
    <!--footer-->
    <Footer></Footer>
  </div>
</template>

<script>
import Sreach from '@/components/Sreach';
import HomeNav from '@/components/nav/HomeNav';
import Footer from '@/components/footer/Footer';
import Section from '@/components/index/section';
import store from '@/vuex/store';
import {mapState, mapActions} from 'vuex';

export default {
  name: 'Index',
  created () {
    this.loadCarouselItems();
    this.loadIndexSections();
    this.loadShoppingCart();
  },

  methods: {
    ...mapActions(['loadIndexSections', 'loadCarouselItems', 'loadShoppingCart'])

  },
  computed: {
    ...mapState(['indexSections'])
  },
  components: {
    Sreach,
    HomeNav,
    Footer,
    Section
  },

  store
};
</script>

<style scoped>
  .container {
    background-color: #F6F6F6;
  }

  .content {
    width: 1008px;
    margin: 0px auto;
  }

</style>
