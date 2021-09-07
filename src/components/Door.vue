<template>
  <div class="area">
    <div class="frame" :class="{ selected: selected && !open }">
      <Gift v-if="hasGift" />
    </div>
    <div class="door" v-if="!open" @click="selected = !selected">
      <div class="number" :class="{ selected: selected }">{{ number }}</div>
      <div
        class="knob"
        :class="{ selected: selected }"
        @click="open = true"
      ></div>
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
    const selected = ref(false);

    return { open, selected };
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

  border-bottom: 10px solid #aaa;
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

.frame.selected {
  border-left: var(--selected-border);
  border-top: var(--selected-border);
  border-right: var(--selected-border);
}

.door {
  position: absolute;
  top: 5px;
  width: 170px;
  height: 295px;
  background-color: chocolate;

  display: flex;
  flex-direction: column;
  align-items: center;
}

.knob {
  height: 20px;
  width: 20px;
  border-radius: 10px;
  background-color: brown;
  align-self: flex-start;
  margin-top: 65px;
}

.knob.selected {
  background-color: yellow;
}

.number.selected {
  color: yellow;
}
</style>