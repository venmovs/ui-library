<script setup lang="ts">
</script>


<template>
 <div class="card">
    <slot/>
 </div>
</template>


<style scoped>

.card {
    display: inline-block;
    border: 1px solid;
    border-color: rgba(0, 0, 0, 0.05);
    border-radius: 16px;
    padding: 24px;
    background-color: #fff;
}

</style>