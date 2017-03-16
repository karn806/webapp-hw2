<template>
  <div class="new-post">
    <div class="container">
      <el-form>
        <el-form-item>
          <h2>New Post</h2>
          <el-input type="input" v-model="post.name">
            <template slot="prepend">Title: </template>
          </el-input>
        </el-form-item>
        <el-form-item>
          <el-input type="textarea" v-model="post.content" placeholder="Write your content here..."></el-input>
        </el-form-item>
        <el-form-item>
          <el-button type="success" @click="createPost">Create Post</el-button>
        </el-form-item>
      </el-form>
    </div>
  </div>
</template>

<script>
import PostsApi from '../../api/posts.js'
import router from '../../router'

export default {
  name: 'new-post',
  data () {
    return {
      post: {
        name: '',
        content: ''
      }
    }
  },
  methods: {
    createPost () {
      PostsApi.createPost(this.post,
        function (_post) {
          router.push({ name: 'Posts.index' })
        }
      )
    }
  }
}
</script>

<style scoped>
  .container {
    margin-top: 30px;
    margin-left: 20%;
    margin-right: 20%;
  }
</style>
