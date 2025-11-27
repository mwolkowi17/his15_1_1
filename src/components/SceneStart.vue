<script setup lang="ts">
import { useMainCompStore } from "../stores/mainCompStore";
import { useFocusStore } from "../stores/focusStore";
import { nextTick, onMounted, onUnmounted, useTemplateRef } from "vue";

const storeMainComp = useMainCompStore();
const storeFocus = useFocusStore();

const startRef = useTemplateRef("start");

onMounted(() => {
  if (storeFocus.ifStartInFocus) {
    startRef.value?.focus();
  }
});

onUnmounted(() => {
  storeFocus.ifStartInFocus = false;
});

async function Start() {
  storeFocus.ifInstructionFocus = false;
  await nextTick();
  storeMainComp.ifStart = false;
  storeMainComp.ifInstruction = true;
}

async function StartWithFocus(event: any) {
  event.preventDefault();
  storeFocus.ifInstructionFocus = true;
  await nextTick();
  storeMainComp.ifStart = false;
  storeMainComp.ifInstruction = true;
}
</script>
<template>
  <div class="tlo">
    <div class="title-container">
      <div>
        <p>Polacy na emigracji w XIX wieku</p>
      </div>
    </div>
    <button
      class="button-start my-button"
      ref="start"
      @click="Start"
      @keydown.enter="StartWithFocus"
      aria-label="Gra edukacyjna - uruchom grę"
    >
      Start
    </button>
  </div>
</template>

<style scoped>
.tlo {
  background-image: url("../assets/plansza_his.jpg");
  background-size: 1920px 1080px;
  height: 1080px;
  width: 1920px;
  top: 0px;
  left: 0px;
  position: absolute;
  display: flex;
  flex-direction: column;
  align-items: center;
}

.title-container {
  position: absolute;
  width: 1000px;
  height: 150px;
  background-color: #fff1e6;
  color: #000000;
  font-size: 60px;
  font-style: bold;
  font-weight: 500;
  font-family: "Proxima Nova", sans-serif;
  display: flex;
  justify-content: center;
  align-items: center;
  top: 719px;
}

.button-start {
  position: absolute;
  color: white;
  background-color: #900000;
  width: 260px;
  height: 93px;
  border-radius: 39px;
  font-size: 48px;
  font-style: bold;
  font-weight: 600;
  font-family: "Proxima Nova", sans-serif;
  top: 926px;
}

.button-start:focus {
  outline: 5px solid black;
  outline-offset: 10px;
}
</style>
