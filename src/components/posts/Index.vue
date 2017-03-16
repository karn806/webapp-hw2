<template>
  <div class="posts">
    <!-- <el-table :data="posts" style="width: 100%" @row-click="toShow">
      <el-table-column label="Posts">
        <template scope='scope'>
          <iccs340-post :post='scope.row'></iccs340-post>
        </template>
      </el-table-column>
    </el-table> -->
    <el-table :data="posts" style="width: 80%" @row-click="toShow">
      <el-table-column prop="id" label="#" width="80"></el-table-column>
      <el-table-column prop="name" label="Title" width="320"></el-table-column>
      <el-table-column prop="user.email" label="User" width="306"></el-table-column>
      <!-- <el-table-column prop="created_at" label="Created at" width="280"></el-table-column> -->
      <!-- <iccs340-post :post='post.name'></iccs340-post> -->
    </el-table>


  </div>
</template>

<script>
import PostsApi from '../../api/posts.js'
// import router from '../../router'

export default {
  name: 'posts',
  components: {
    Iccs340Post: require('./Post')
  },
  data () {
    return {
      posts: null,
      error: null
    }
  },
  beforeRouteEnter (to, from, _next) {
    PostsApi.getPosts(_posts => {
      _next(vm => {
        vm.posts = _posts
      })
    })
  },
  watch: {
    $route () {
      PostsApi.getPosts(_posts => {
        this.posts = _posts
      })
    }
  },
  methods: {
    toShow (row) {
      this.$router.push(this.$route.path + '/' + row.id)
    }
  }
}
</script>

<style scoped>
  .posts {
    margin-top: 30px;
    margin-left: 20%;
    margin-right: 10%;
  }
</style>
