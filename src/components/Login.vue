<template>
<!-- 登陆页面 -->
  <div>
    <Row class="container">
      <i-col span="13" offset="2" class="login-img-box">
        <img src="static/img/sale.jpg" alt="">
      </i-col>
      <loginBox></loginBox>
    </Row>
    <Footer></Footer>
  </div>
</template>

<script>
import Footer from '@/components/footer/Footer';
import loginBox from '@/components/signUp/loginBox';
// import store from '@/vuex/store';
export default {
  name: 'Login',
  data () {
    return {
    };
  },
  components: {
    Footer,
    loginBox
  }
  // store
};
</script>

<style scoped>
.container {
  margin-top: 30px;
  height: 485px;
  background-color: #fff;
}
.login-img-box {
  height: 485px;
  overflow: hidden;
  display: flex;
  align-items: center;
  justify-content: center;
}
.login-img-box>img {
  width: 68%;
}
.login-box {
  height: 485px;
  display: flex;
  align-items: center;
  justify-content: center;
}
.login-container {
  width: 80%;
  height: 280px;
  border: #ED3F14 solid 1px;
}
.login-header {
  height: 50px;
  font-size: 20px;
  text-align: center;
  line-height: 50px;
  letter-spacing: 5px;
  color: #fff;
  background-color: #ED3F14;
}
.form-box {
  width: 80%;
  margin: 30px auto;
}
</style>
