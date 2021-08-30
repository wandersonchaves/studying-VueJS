<template>
  <div class="area">
    <div class="frame"><Gift v-if="hasGift" /></div>
    <div class="door" v-if="!open">
      <div class="number">{{ number }}</div>
      <div class="knob" @click="open = true"></div>
    </div>
  </div>
</template>

<script>
import { ref } from "vue";
import Gift from "./Gift";

export default {
  props: { number: {}, hasGift: { type: Boolean } },
  components: { Gift },
  setup() {
    const open = ref(false);

    return { open };
  },
};
</script>

<style>
.area {
  position: relative;
  width: 200px;
  height: 310px;
  font-size: 3rem;

  display: flex;
  justify-content: center;
}

.frame {
  position: absolute;
  width: 180px;
  height: 300px;

  border-left: var(--frame-border);
  border-top: var(--frame-border);
  border-right: var(--frame-border);

  display: flex;
  justify-content: center;
  align-items: flex-end;
}

.door {
  position: absolute;
  top: 5px;
  width: 170px;
  height: 295px;
  background-color: chocolate;
}

.knob {
  height: 20px;
  width: 20px;
  border-radius: 10px;
  background-color: brown;
}
</style>