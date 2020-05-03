<template>
  <div id="app">
    <Bingo></Bingo>
  </div>
</template>

<script>
import Bingo from "./components/Bingo.vue";

export default {
  name: "App",
  components: {
    Bingo
  }
};
</script>

<style>
body {
  background-color: #efefef;
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  margin: 60px auto 0;
  max-width: 980px;
  text-align: center;
}
</style>
