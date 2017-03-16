<template>
  <div id="app">
    <div v-if="$store.getters.loggedIn">
      <iccs340-left-sidenav></iccs340-left-sidenav>
    </div>
    <!-- <iccs340-left-sidenav></iccs340-left-sidenav> -->
    <router-view></router-view>
  </div>
</template>

<script>
export default {
  name: 'app',
  components: {
    Iccs340LeftSidenav: require('./LeftSidenav')
  }
}
</script>

<style lang="css">
  #app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  }
  .container {
    margin-top: 30px;
    margin-right: 140px;
  }
</style>
