<template>
  <div class="left-sidenav">
    <el-menu class="el-menu-demo" mode="horizontal">
      <el-menu-item index="1">Homework 2</el-menu-item>
      <el-menu-item index="2" @click="homePage"><i class="el-icon-document"></i>Posts</el-menu-item>
      <el-menu-item index="3" @click="newPost"><i class="el-icon-edit"></i>New post</el-menu-item>
      <el-menu-item index="4" @click="logout"><i class="el-icon-setting"></i>Log Out</el-menu-item>
    </el-menu>

  </div>

</template>

<script>
import UsersApi from './api/users.js'
import router from './router'

export default {
  methods: {
    toggleLeftSidenav () {
      this.$refs.leftSidenav.toggle()
    },
    newPost () {
      router.push({ name: 'Posts.new' })
    },
    homePage () {
      router.push({ name: 'Posts.index' })
    },
    logout () {
      UsersApi.logout()
    }
  }
}
</script>

<style lang="css">
  font-family: 'Open Sans', sans-serif;
</style>
