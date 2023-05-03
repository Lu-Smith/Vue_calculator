<template>
  <CalculatorApp msg="Vue Calculator" />
</template>

<script>
import CalculatorApp from "./components/CalculatorApp.vue";

export default {
  name: "App",
  components: {
    CalculatorApp,
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
