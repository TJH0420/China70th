<template>
  <div class="China">
    <div class="Star"></div>
  </div>
</template>

<script>
import { setInterval } from "timers";
export default {
  name: "Star",
  props: {},
  data() {
    return {};
  },
  created() {},
  methods: {}
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.Star {
  width: 0; /* 第一步代码 */
  height: 0; /* 第一步代码 */
  border-right: 5vw solid transparent; /* 第一步代码 */
  border-left: 5vw solid transparent; /* 第一步代码 */
  border-top: 3.5vw solid #ff0; /* 第一步代码 */
  position: relative; /* 第二步代码 */
}
.Star::after,
.Star::before {
  content: ""; /* 第一步代码 */
  width: 0; /* 第一步代码 */
  height: 0; /* 第一步代码 */
  border-right: 5vw solid transparent; /* 第一步代码 */
  border-left: 5vw solid transparent; /* 第一步代码 */
  border-top: 3.5vw solid #ff0; /* 第一步代码 */
  position: absolute; /* 第二步代码 */
  top: -3.5vw; /* 第二步代码 */
  left: -5vw; /* 第二步代码 */
}
.Star::before {
  transform: rotate(70.5deg); /* 第三步代码 */
}
.Star::after {
  transform: rotate(-70.5deg); /* 第三步代码 */
}
</style>
