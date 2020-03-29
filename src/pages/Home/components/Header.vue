<template>
    <div class="main_login">
        <div class="check_box">
            <el-link :underline="false"
                     class="check_box_login"
                     @click="click_login"
                     id="login"
            >
                登录
            </el-link>
            <div class="check_box_center">·</div>
            <el-link :underline="false"
                     class="check_box_register"
                     @click="click_register"
                     id="register"
            >
                注册
            </el-link>
        </div>

<!--        登录界面-->
        <div class="container" v-if="click=='login'">
            <el-input placeholder="请输入账户名" prefix-icon="el-icon-user" v-model="user_name"  clearable class="user_input_style"></el-input>
            <el-input placeholder="请输入密码" prefix-icon="el-icon-lock" v-model="pwd" show-password class="pwd_input_style"></el-input>
            <div class="pwd_container">
                <el-checkbox v-model="remember_pwd" class="rem_pwd_style">记住密码</el-checkbox>
                <el-link type="primary" :underline="false" class="forget_pwd_style">忘记密码</el-link>
            </div>
            <el-button type="primary" @click="open" class="login_button_style" round>登录</el-button>
        </div>
<!--        注册界面-->
        <div  class="container" v-if=" click=='register'">
            <el-input placeholder="请输入账户名" prefix-icon="el-icon-user" v-model="user_name"  clearable class="register"></el-input>
            <el-input placeholder="请输入学号" prefix-icon="el-icon-notebook-1" v-model="student_id"  clearable class="register"></el-input>
            <el-input placeholder="请输入邮箱" prefix-icon="el-icon-postcard" v-model="email"  clearable class="register"></el-input>
            <el-input placeholder="请输入密码" prefix-icon="el-icon-lock" v-model="pwd" show-password class="register"></el-input>
            <el-button type="primary" @click="open" class="login_button_style" round>登录</el-button>
        </div>
    </div>
</template>
<script>
// import $ from 'jquery'
export default {
  name: 'HomeHeader',
  data () {
    return {
      student_id: '',
      user_name: '',
      pwd: '',
      email: '',
      remember_pwd: false,
      click: 'login'
    }
  },
  methods: {
    open () {
      this.$message('登陆成功')
    },
    click_login: function () {
      this.click = 'login'
      // $('#login').addClass('click_under_Line')
      // $('#register').removeClass('click_under_Line')
    },
    click_register: function () {
      this.click = 'register'
      // $('#login').removeClass('click_under_Line')
      // $('#register').addClass('click_under_Line')
    }

  }
}
</script>

<style lang="stylus" scoped>
    .main_login
        margin 80px auto
        width 580px
        height 480px
        background-color rgba(234,244,252,0.7)
        border-radius  30px
        display flex
        flex-direction: column
        align-items center
    .container
        display flex
        flex-direction: column
        align-items center
    .check_box
        width 200px
        height 50px
        margin-top 60px
        /*background aqua*/
    .check_box_login
        float left
        font-size 32px
        line-height 50px
    .check_box_center
        float left
        font-size 40px
        margin-left 30px
        line-height 50px
    .check_box_register
        float right
        font-size 32px
        line-height 50px
    .pwd_container
        margin-top 10px
        display block
        width 280px
    .rem_pwd_style
        float left
    .forget_pwd_style
        float right
    .user_input_style
        width: 300px
        margin-top 60px
    .pwd_input_style
        width 300px
        margin-top 40px
    .login_button_style
        margin-top 30px
        width 150px
    .register
        width: 300px
        margin-top 30px
    .click_under_Line
        border-bottom red 5px solid
</style>
