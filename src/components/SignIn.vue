<template>
  <div class="sign-in" style="
    margin: auto;
    margin-top: 60px;
    width: 35%;
    text-align: center;">
    <el-form>
      <h2>Sign In</h2>
      <el-form-item label="Email">
        <el-input v-model="email" placeholder="Email"></el-input>
      </el-form-item>
      <el-form-item label="Password">
        <el-input v-model="password" type="password" placeholder="Password"></el-input>
      </el-form-item>
      <el-form-item>
        <el-button :plain="true" type="success" @click="login">Log In</el-button>
      </el-form-item>
    </el-form>
  </div>
</template>

<script>
import UsersApi from '../api/users.js'
import router from '../router'

export default {
  name: 'sign-in',
  data () {
    return {
      email: '',
      password: ''
    }
  },
  methods: {
    login () {
      console.log('methods.login')
      UsersApi.login(this.email, this.password, function (_response) {
        // NOTE: Posts.index is not yet implemented
        router.push({ name: 'Posts.index' })
      })
    }
  }
}
</script>

<style scoped>
</style>
