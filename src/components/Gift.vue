<template>
  <div class="gift">
    <div class="top"></div>
    <div class="body"></div>
    <div class="tie-1"></div>
    <div class="tie-2"></div>
  </div>
</template>

<script>
export default {
  name: "Gift",
};
</script>

<style>
.gift {
  position: relative;
  display: flex;
  flex-direction: column;
  align-items: center;
}

.top {
  width: 100px;
  height: 25px;
  background-color: #7aa944;
}

.body {
  width: 90px;
  height: 60px;
  background-color: #5c7e32;
}

.tie-1 {
  position: absolute;
  width: 15px;
  height: 85px;
  background-color: red;
}

.tie-2 {
  position: absolute;
  top: 40px;
  width: 90px;
  height: 15px;
  background-color: red;
}
</style>