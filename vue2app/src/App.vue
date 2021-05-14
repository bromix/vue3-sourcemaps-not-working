<template>
  <div id="app">
    <div id="nav">
      <button @click="sayHelloFromVueFile()">Breakpoint in vue file</button>
      <button @click="sayHelloFromTsFile()">Breakpoint in ts file</button>
    </div>
  </div>
</template>

<script lang="ts">
import Vue from "vue";
import { sayHello } from "./utils";
export default Vue.extend({
  methods: {
    sayHelloFromVueFile() {
      debugger
      console.log("Hello from Vue file");
    },
    sayHelloFromTsFile() {
      sayHello();
    },
  },
});
</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

#nav {
  padding: 30px;

  a {
    font-weight: bold;
    color: #2c3e50;

    &.router-link-exact-active {
      color: #42b983;
    }
  }
}
</style>
