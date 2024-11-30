//这个是那个登录界面的东西，这玩意不会干扰到别人
<template>
  <el-form :model="ruleForm2" :rules="rules2" ref="ruleForm2" label-position="left" label-width="0px"
      class="demo-ruleForm login-container">
      <div style="position: absolute; top: 70; left: 0; margin: 0;"> <img src="./xiaohui.png" alt="同济大学校徽123" style="width: 250px; height: 200px;"> 
      </div>
            <div style="position: absolute; top: 70; right: 0; margin: 0;"> <img src="./xiaohui.png" alt="同济大学校徽123" style="width: 250px; height: 200px;"> 
      </div>
    <h3 class="title">{{$t('m.Welcome_to_Login')}}</h3>
    <el-form-item prop="account">
      <el-input type="text" v-model="ruleForm2.account" auto-complete="off" :placeholder="$t('m.username')" @keyup.enter.native="handleLogin"></el-input>
    </el-form-item>
    <el-form-item prop="password">
      <el-input type="password" v-model="ruleForm2.password" auto-complete="off" :placeholder="$t('m.password')" @keyup.enter.native="handleLogin"></el-input>
    </el-form-item>
    <el-form-item style="width:100%;">
      <el-button type="primary" style="width:100%;" @click.native.prevent="handleLogin" :loading="logining">{{$t('m.GO')}}
      </el-button>
    </el-form-item>
  </el-form>
</template>

<script>
  import api from '../../api'

  export default {
    data () {
      return {
        logining: false,
        ruleForm2: {
          account: '',
          password: ''
        },
        rules2: {
          account: [
            {required: true, trigger: 'blur'}
          ],
          password: [
            {required: true, trigger: 'blur'}
          ]
        },
        checked: true
      }
    },
    methods: {
      handleLogin (ev) {
        this.$refs.ruleForm2.validate((valid) => {
          if (valid) {
            this.logining = true
            api.login(this.ruleForm2.account, this.ruleForm2.password).then(data => {
              this.logining = false
              this.$router.push({name: 'dashboard'})
            }, () => {
              this.logining = false
            })
          } else {
            this.$error('Please check the error fields')
          }
        })
      }
    }
  }
</script>

<style lang="less" scoped>
  .login-container {
    /*box-shadow: 0 0px 8px 0 rgba(0, 0, 0, 0.06), 0 1px 0px 0 rgba(0, 0, 0, 0.02);*/
    -webkit-border-radius: 5px;
    border-radius: 5px;
    -moz-border-radius: 5px;
    background-clip: padding-box;
    margin: 180px auto;
    width: 350px;
    padding: 35px 35px 15px 35px;
    background: #fff;
    border: 1px solid #eaeaea;
    box-shadow: 0 0 25px #cac6c6;
    .title {
      margin: 0px auto 40px auto;
      text-align: center;
      color: #505458;
    }
    .remember {
      margin: 0px 0px 35px 0px;
    }
  }
</style>

