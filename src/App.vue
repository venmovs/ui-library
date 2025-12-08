<script setup lang="ts">
import { ref, watch } from "vue";
import ButtonUI from "./components/ButtonUI";
import TabsUI from "./components/TabsUI";
const tabs = ['ввв', 'лплплплп', 'лвыы', 'щщщщщщщщщщddddddddddddddddddddddddddddddddddщ'];
const activeTab = ref('1');

watch(activeTab, () => {
  console.log(activeTab.value)
})
</script>

<template>
  <ButtonUI label="Кнопка" rounded disabled />
  <input type="range" />
  <TabsUI :tabs="tabs" v-model="activeTab"/>
</template>


