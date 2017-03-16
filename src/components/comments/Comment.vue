<template>
  <div class="comment">
    <div class="container">
      <el-card class="box-card">
        <span><b>From: {{ comment.user.email }}</b></span>
        <br>
        <span>{{ comment.content }}</span>
      </el-card>
    </div>
  </div>
</template>

<script>

export default {
  name: 'comment',
  props: {
    comment: {
      type: Object,
      required: false,
      default: {}
    }
  }
}
</script>

<style scoped>
  .container {
    margin-top: 30px;
    margin-right: 140px;
  }
</style>
