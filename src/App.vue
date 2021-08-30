<template>
  <div class="monty-hall">
    <div class="doors">
      <Door number="1" :hasGift="false" /> <Door number="2" :hasGift="true" />
      <Door number="3" :hasGift="false" />
    </div>
  </div>
</template>

<script>
import Door from "./components/Door";
export default {
  name: "App",
  components: { Door },
};
</script>

<style>
* {
  box-sizing: border-box;
}

:root {
  --frame-border: 5px solid brown;
}

body {
  background: linear-gradient(to right, rgb(21, 153, 87), rgb(21, 87, 153));
}

.doors {
  display: flex;
  justify-content: space-around;
}
</style>
