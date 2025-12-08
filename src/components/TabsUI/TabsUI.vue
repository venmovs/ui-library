<script setup lang="ts">
interface Props {
    tabs: string [];
}

defineProps<Props>();

const modelValue = defineModel<string>();

const changeTab = (tab:string) => modelValue.value = tab;

</script>


<template>
    <div class="tabs">
        <div
            class="tab"
            :class="{'tab_active': modelValue === tab }"
            v-for="tab in tabs"
            :key="tab"
            @click="changeTab(tab)"
            >
        <strong>{{ tab }}</strong>
        </div>
    </div>
</template>



<style scoped>

.tabs {
    display: flex;
    border: 1px solid rgba(0, 0, 0, 0.05);;
    border-radius: 5px;
    box-sizing: border-box;
    overflow: hidden;
    max-width: max-content;
}

.tab {
    height: 37px;
    padding: 8px;
    background-color: green;
    cursor: pointer;
    border-right: 1px solid rgba(0, 0, 0, 0.05);
    background-color: white;
    display: flex;
    justify-content: center;
    align-items: center;
}

.tab_active {
    background-color: #fbfbfb;
}

.tab:hover {
    background-color: #fffdfd;
}

.tab:last-child {
  border-right: none;
}
</style>