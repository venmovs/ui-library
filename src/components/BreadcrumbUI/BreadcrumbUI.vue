<script setup lang="ts">
import { useAttrs } from 'vue'

interface BreadcrumbItem {
  name: string;
  href?: string;
}

interface BreadcrumbProps {
  breadcrumbs: BreadcrumbItem[]
}

defineProps<BreadcrumbProps>()
const attrs = useAttrs()
</script>

<template>
 <nav v-bind="attrs">
    <ol class="breadcrumbs">
        <li 
            class="breadcrumb"
            v-for="(breadcrumb, index) in breadcrumbs"
            :key="index">
            <a 
                v-if="index !== breadcrumbs.length - 1"
                :href="breadcrumb.href">
                {{ breadcrumb.name }}
            </a>
            <span v-else>{{ breadcrumb.name }}</span>
        </li>
    </ol>
 </nav>
</template>

<style scoped>

.breadcrumb {
    list-style: none;
    display: flex;
    align-items: center;
}

.breadcrumb a {
    text-decoration: none;
    font-size: 14px;
    font-weight: 400;
    line-height: 20px;
    letter-spacing: 0px;
    color: rgba(28, 28, 28, 0.4);
    cursor: pointer;
}

.breadcrumb span {
    font-size: 14px;
    font-weight: 400;
    line-height: 20px;
    letter-spacing: 0px;
    color: rgba(28, 28, 28, 1);
    cursor: pointer;
}

.breadcrumb:not(:last-child)::after {
    content: '/';
    color: rgba(28, 28, 28, 0.4);
    margin-left: 8px;
}

.breadcrumbs {
    display: flex;
    align-items: center;
    gap: 8px;
    list-style: none;
    margin: 0;
    padding: 0;
}

</style>