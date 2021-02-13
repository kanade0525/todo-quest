<template>
  <div id="app">
    <h1 class="mb-5"><i class="nes-jp-logo"></i>TODO QUEST<i class="snes-jp-logo"></i></h1>
    <router-view/>
  </div>
</template>

<script>
export default {
  name: 'App'
}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Press+Start+2P&display=swap');
@import url('../src/assets/fonts/style');
#app {
  padding: 4rem 1rem;
  height: 100%;
  min-height: 100vh;
  font-family: Japanese8bit, 'Press Start 2P';
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #fff;
  background: rgb(33, 37, 41);
};
</style>
