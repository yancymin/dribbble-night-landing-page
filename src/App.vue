<template>
  <div id="app">
    <router-view />
    <loading />
  </div>
</template>

<script>
import loading from '@/components/loading.vue'

export default {
  name: "app",
  components: {
    loading
  }
};
</script>

<style lang="scss">
@import url("https://fonts.googleapis.com/css?family=Montserrat:200,300&display=swap");
@import "./style/reset.css";
@import "./style/mobile.scss";

#app {
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #ffffff;
}

body {
  font-family: "Montserrat", sans-serif;
  font-weight: 300;
  width: 100vw;
  background-color: #1a1a1a;
  overflow-x: hidden;
  box-sizing: border-box;
}

::selection {
  background-color: #ea4c89;
  color: white;
}

*::-webkit-scrollbar {
  width: 0;
  display: none;
  opacity: 0;
  visibility: hidden;
}
</style>
