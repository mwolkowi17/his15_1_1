<script setup lang="ts">
import { useMainCompStore } from "../stores/mainCompStore";
import SceneStart from "./SceneStart.vue";
import SceneInstruction from "./SceneInstruction.vue";
import SceneLevelChose1 from "./SceneLevelChose1.vue";
import SceneLevelChose2 from "./SceneLevelChose2.vue";
import SceneMain1 from "./SceneMain1.vue";
import PrzegranaSilver from "./PrzegranaSilver.vue";
import SceneWinSilver from "./SceneWinSilver.vue";

const store = useMainCompStore();
</script>
<template>
  <SceneStart v-if="store.ifStart" />
  <SceneInstruction v-if="store.ifInstruction" />
  <SceneLevelChose1 v-if="store.ifSceneChose1" />
  <SceneLevelChose2 v-if="store.ifSceneChose2" />
  <SceneMain1 v-if="store.ifMain1" />
  <PrzegranaSilver v-if="store.ifPrzegranaSilver" />
  <SceneWinSilver v-if="store.ifWinSilver" />
</template>
<style scoped></style>
