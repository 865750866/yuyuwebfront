<template>

  <div class="login_body">

    <div class="login_input" style="width: 450px;margin: 0 auto;position: relative;top: 25%;">
      <el-form ref="form" :model="form" label-width="100px">

        <p style="text-align: center;font-size: 24px;margin: 0px;margin-bottom: 10px;">
          <span style="position: relative;left: 30px">煜煜website</span>
        </p>

        <el-form-item label="用户名:">
          <el-col :span="24">
            <el-input v-model="form.username"></el-input>
          </el-col>
        </el-form-item>

        <el-form-item label="密码:">
          <el-col :span="24">
            <el-input type="" v-model="form.password" show-password></el-input>
          </el-col>
        </el-form-item>

        <el-form-item label="验证码:">
          <el-col :span="10">
            <el-input v-model="form.verification_code"></el-input>
          </el-col>
          <label style="position: relative;left: 60px;">验证码图片位置</label>
        </el-form-item>

        <el-form-item>
          <div style="position: relative;left: 80px;">
            <el-button type="primary" @click="submit">登陆</el-button>
            <el-button>重置</el-button>
          </div>
        </el-form-item>

      </el-form>

    </div>

  </div>

</template>

<script>

export default {
  name: 'Login',
  data: function () {
    return {
      form: {
        username: '',
        password: '',
        verification_code: ''
      }
    }
  },
  methods: {
    submit () {
      this.$router.push('/index')
    }
  }
}
</script>

<style scoped>
  .login_body {
    height: 100vh;
  }

</style>
