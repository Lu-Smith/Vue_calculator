<template>
  <p>
    This project was coded by
    <a href="https://www.lunasmithart.com/" target="_blank" class="cool-link"
      >Luna Smith</a
    >
    and is open-source on
    <a
      href="https://github.com/Lu-Smith/Vue_calculator"
      target="_blank"
      class="cool-link"
      >GitHub</a
    >.
  </p>
</template>
<script></script>
<style scoped>
.cool-link {
  position: relative;
  text-decoration: none;
  color: #555;
  transition: all 0.3s ease;
}

.cool-link:before {
  content: "";
  position: absolute;
  width: 100%;
  height: 2px;
  bottom: 0;
  left: 0;
  background-color: #3fb984;
  visibility: hidden;
  transform: scaleX(0);
  transition: all 0.3s ease-in-out 0s;
}

.cool-link:hover:before {
  visibility: visible;
  transform: scaleX(1);
}
</style>
