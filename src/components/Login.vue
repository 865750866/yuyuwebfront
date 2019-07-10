<template>

  <div class="login_body">

    <div class="login_input">
      <el-form ref="form" :model="form" label-width="100px">

        <el-form-item label="用户名:">
          <el-col :span="12">
          <el-input v-model="form.username" ></el-input>
          </el-col>
        </el-form-item>

        <el-form-item label="密码:">
        <el-input v-model="form.password"></el-input>
      </el-form-item>

        <el-form-item label="验证码:">
          <el-input v-model="form.verification_code" ></el-input>
          <el-form-item label="验证码图片"></el-form-item>
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
  }
}
</script>

<style scoped>

  .login_body{
    background: #B3C0D1;
    height: 100%;

  }

  .login_input{

  }



</style>
