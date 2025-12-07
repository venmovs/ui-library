<script setup lang="ts">
import ButtonUI from "./components/ButtonUI";
import BreadcrumbUI from "./components/BreadcrumbUI/BreadcrumbUI.vue";

const breadcrumbs = [ 
  {name:'Breadcrumb_1',href:'/'},
  {name:'Breadcrumb_2',href:'/'}, 
  {name:'Breadcrumb_3'}
]; 

</script>

<template>
  <ButtonUI label="Кнопка" rounded disabled />
  <input type="range" />
  <BreadcrumbUI :breadcrumbs="breadcrumbs"/>
</template>
