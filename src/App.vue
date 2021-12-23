<template>
  <v-app>
    <v-main>
      <router-view :key="$route.fullPath"/>
    </v-main>
  </v-app>
</template>

<script>

export default {
  name: 'App',
};
</script>

<style lang="scss">
  @import url('https://fonts.googleapis.com/css2?family=Raleway&family=Righteous&family=Roboto&display=swap');
  * {
    padding: 0;
    margin: 0;
    font-family: 'Raleway', sans-serif;
    scroll-behavior: smooth;
  }

  #wrap {
    overflow-x: hidden;
  }
  #app {
    font-family: Avenir, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
  }
</style>
