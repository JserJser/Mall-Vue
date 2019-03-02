<template>
  <div>
    <Row class="container">
      <i-col span="12" offset="2" class="signup-img-box">
        <img src="static/img/signup-sale.png" alt="">
      </i-col>
      <signUpBox></signUpBox>
    </Row>
    <Footer></Footer>
  </div>
</template>

<script>
import store from '@/vuex/store';
import signUpBox from '@/components/signUp/signUpBox';
import Footer from '@/components/footer/Footer';
export default {
  name: 'SignUp',
  data () {
    return {
      index: 0
    };
  },
  store,
  mounted () {
  },
  components: {
    Footer,
    signUpBox
  }
};
</script>

<style scoped>
.container {
  margin: 15px auto;
  height: 500px;
  overflow: hidden;
}
.signup-img-box {
  height: 100%;
  display: flex;
  align-items: center;
  justify-content: center;
}
.signup-img-box>img {
  height: 80%;
}

</style>
