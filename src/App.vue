<template>
  <div id="app">
    <Story/>
  </div>
</template>

<script>
import Story from "./components/Story";

export default {
  name: "App",
  components: {
    Story
  }
};
</script>

<style>
* {
  box-sizing: border-box;
}

html,
body,
#app {
  width: 100%;
  height: 100%;
  margin: 0;
}

#app {
  text-align: center;
}
</style>
