<template>
  <div class="post">
    <span><b>{{ post.name }}</b></span>
    <p><i class="el-icon-caret-right"></i> {{ post.content }}</p>
  </div>
</template>

<script>

export default {
  name: 'post',
  props: {
    post: {
      type: Object,
      required: false,
      default: {}
    }
  }
}
</script>

<style scoped>

</style>
