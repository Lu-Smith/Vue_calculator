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
      <!-- Formula-->
      <div
        class="w-full rounded mx-1 py-2 px-3 text-end lead font-weight-bold text-black bg-vue-yellow formula"
        style="height: 40px"
      >
        {{ previousCalculatorValue }} {{ operator }} {{ calculatorValue }}
      </div>

      <!-- Calculator Results-->
      <div
        class="w-full rounded mx-1 mb-1 p-3 text-end lead font-weight-bold text-white bg-vue-dark"
        style="height: 60px"
      >
        {{ calculatorValue }}
      </div>

      <!-- Calculator buttons-->
      <div class="row no-gutters">
        <div class="col-3" v-for="n in calculatorElements" v-bind:key="n">
          <div
            class="lead text-white text-center m-1 py-3 bg-vue-dark rounded hover-class"
            :class="{
              'bg-vue-green': ['C', '*', '/', '-', '+', '%', '='].includes(n),
            }"
            @click="action(n)"
          >
            {{ n }}
          </div>
        </div>
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
  data() {
    return {
      calculatorValue: "",
      calculatorElements: [
        "C",
        "*",
        "/",
        "-",
        "7",
        "8",
        "9",
        "+",
        "4",
        "5",
        "6",
        "%",
        "1",
        "2",
        "3",
        "=",
        "0",
        ".",
      ],
      operator: null,
      previousCalculatorValue: "",
    };
  },
  methods: {
    action(n) {
      /*Append value */
      if (!isNaN(n) || n === ".") {
        this.calculatorValue += n + "";
      }
      /*Clear value */
      if (n === "C") {
        this.calculatorValue = "";
        this.previousCalculatorValue = "";
        this.operator = "";
      }
      /*% value */
      if (n === "%") {
        this.calculatorValue = this.calculatorValue / 100 + "";
      }

      /* calculactions */
      if (["/", "*", "-", "+"].includes(n)) {
        if (["/", "*", "-", "+"].includes(this.lastInput)) {
          return;
        }
        this.operator = n;
        this.previousCalculatorValue = this.calculatorValue;
        this.calculatorValue = "";
      }

      if (n === "=") {
        if (["/", "*", "-", "+", "="].includes(this.lastInput)) {
          return;
        }
        this.calculatorValue = eval(
          this.previousCalculatorValue + this.operator + this.calculatorValue
        );

        this.previousCalculatorValue = "";
        this.operator = null;
      }
      this.lastInput = n;
    },
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
.hover-class:hover {
  cursor: pointer;
  background: #3d5875;
}
.bg-vue-green {
  background: #3fb984;
}
.bg-vue-yellow {
  background: #f3ec71;
}
</style>
