<template>
  <i-col span="7" class="login-box">
    <div class="login-container">
      <div class="login-header">
        <p>欢迎登陆</p>
      </div>
      <div class="form-box">
        <Form ref="formInline" :model="formDate" :rules="ruleInline">
          <FormItem prop="username">
            <i-input type="text" v-model="formDate.username" clearable size="large" placeholder="用户名">
              <Icon type="person" slot="prepend"></Icon>
            </i-input>
          </FormItem>
          <FormItem prop="password">
            <i-input type="password" v-model="formDate.password" clearable size="large" placeholder="密码">
              <Icon type="ios-locked-outline" slot="prepend"></Icon>
            </i-input>
          </FormItem>
          <FormItem>
            <Button type="error" size="large" @click="handleSubmit('formInline')" long>登陆</Button>
          </FormItem>
        </Form>
      </div>
    </div>
  </i-col>

</template>

<script>
import { mapMutations, mapActions } from 'vuex';
import store from '@/vuex/store';

export default {
  name: 'loginBox',
  data () {
    return {
      formDate: {
        username: '',
        password: ''
      },
      ruleInline: {
        username: [
          {required: true, message: '请输入用户名', trigger: 'blur'}
        ],
        password: [
          {required: true, message: '请输入密码', trigger: 'blur'},
          {type: 'string', min: 6, message: '密码不能少于6位', trigger: 'blur'}
        ]
      }
    };
  },
  methods: {
    ...mapMutations(['SET_USER_LOGIN_INFO']),
    ...mapActions(['login']),
    handleSubmit (name) {
      const father = this;
      console.log(this.formDate.username);
      this.$refs[name].validate((valid) => {
        if (valid) {
          this.login(father.formDate).then(result => {
            console.log('result', result);
            if (result) {
              console.log('denglucehnggongla');
              this.$Message.success('登陆成功');
              father.$router.push('/');
            } else {
              this.$Message.error('用户名或密码错误');
            }
          });
        } else {
          this.$Message.error('请填写正确的用户名或密码');
        }
      });
    }
  },
  store

};
</script>

<style scoped>

</style>
