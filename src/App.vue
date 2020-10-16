<template>
  <div id="app">
    <h3>Dropbox Demo</h3>
    <img alt="Vue logo" src="./assets/logo.png" />
    <Upload/>
    <Files />
  </div>
</template>

<script>
import Files from "./components/Files.vue";
import Upload from "./components/Upload.vue";

export default {
  name: "App",
  components: {
    Upload,
    Files,
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
