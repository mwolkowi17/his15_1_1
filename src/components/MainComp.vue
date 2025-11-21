<script setup lang="ts">
import { useMainCompStore } from "../stores/mainCompStore";
import SceneStart from "./SceneStart.vue";
import SceneInstruction from "./SceneInstruction.vue";
import SceneLevelChose1 from "./SceneLevelChose1.vue";
import SceneMain1 from "./SceneMain1.vue";

const store = useMainCompStore();
</script>
<template>
  <SceneStart v-if="store.ifStart" />
  <SceneInstruction v-if="store.ifInstruction" />
  <SceneLevelChose1 v-if="store.ifSceneChose1" />
  <SceneMain1 v-if="store.ifMain1" />
</template>
<style scoped></style>
