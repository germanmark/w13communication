<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <PostContainer/>
    <SmartContainer/>
  </div>
</template>

<script>
import PostContainer from '@/components/PostContainer.vue'
import SmartContainer from '@/components/SmartContainer.vue'
export default {
  name: 'App',
  components: {
    PostContainer,
    SmartContainer
  }
}
</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

html{
  background-color: bisque;
}
</style>
