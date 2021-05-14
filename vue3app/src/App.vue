<template>
  <div id="nav">
    <button @click="sayHelloFromVueFile()">Breakpoint in vue file</button>
    <button @click="sayHello()">Breakpoint in ts file</button>
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";
import { sayHello } from "./utils";

export default defineComponent({
  setup() {
    const sayHelloFromVueFile = () => {
      debugger
      console.log("Hello from Vue file");
    };
    return { sayHelloFromVueFile, sayHello };
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
