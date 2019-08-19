<template>
  <div id="app">
    <router-view/>
  </div>
</template>

<style lang="scss">
@import url('https://fonts.googleapis.com/css?family=Montserrat:200,300&display=swap');


#app {
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #ffffff;
}

body {
  font-family: 'Montserrat', sans-serif;
  width: 100vw;
  background-color: #1A1A1A;
  overflow-x: hidden;
  box-sizing: border-box;
}

::selection {
  background-color: #ea4c89;
  color: white;
}


*::-webkit-scrollbar {
  width:0;
  display: none;
  opacity: 0;
}
</style>
