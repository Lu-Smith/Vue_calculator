<template>
  <div>
    <h1>{{ msg }}</h1>
    <p>Hello World</p>
  </div>
</template>

<script>
export default {
  name: "CalculatorApp",
  props: {
    msg: String,
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
p {
  font-style: italic;
}
</style>
