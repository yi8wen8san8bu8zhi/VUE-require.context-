<template>
  <div id="app">
    <A />
    <B />
    <C />
  </div>
</template>

<script>
const path = require("path");
const files = require.context("@/components", false, /\.vue$/);
const modules = {};
files.keys().forEach(key => {
  const name = path.basename(key, ".vue");
  modules[name] = files(key).default || files(key);
});


export default {
  components: modules
};
</script>

<style>
</style>