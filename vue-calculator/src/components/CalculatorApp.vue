<template>
  <div>
    <h1>{{ msg }}</h1>
    <p>
      With just a few clicks, you can add, subtract, multiply, and divide to
      your heart's content -
      <strong>pure math magic at your fingertips</strong>.
    </p>
    <div
      class="p-3"
      style="max-width: 400px; margin: 50px auto; background: #234"
    >
      <!--Calculatr Resuls-->
      <div
        class="w-full rounded m-1 p-3 text-right lead font-wieght-bold text-white bg-vue-dark"
      >
        000
      </div>
    </div>
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
.bg-vue-dark {
  background: #31475e;
}
</style>
