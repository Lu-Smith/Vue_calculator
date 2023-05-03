<template>
  <div>
    <h1>{{ msg }}</h1>
    <p>
      With just a few clicks, you can add, subtract, multiply, and divide to
      your heart's content -
      <strong>pure math magic at your fingertips</strong>.
    </p>
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
