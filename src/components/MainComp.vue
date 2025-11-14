<script setup lang="ts">
import { useMainCompStore } from "../stores/mainCompStore";
import SceneStart from "./SceneStart.vue";

const store = useMainCompStore();
</script>
<template>
  <SceneStart v-if="store.ifStart" />
</template>
<style scoped></style>
