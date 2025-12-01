<script setup lang="ts">
import {useAttrs, useSlots} from "vue";

interface Props {
  label?: string;
  size?: 'small' | 'medium' | 'large';
  rounded?: boolean;
}

interface Emits {
  click: () => void;
}

defineEmits<Emits>();
defineProps<Props>();

const attrs = useAttrs();
const slots = useSlots();
</script>

<template>
  <button
      v-bind="attrs"
      class="button"
      :class="{ 'button_rounded': rounded }"
      @click="$emit('click')"
  >
    <span>{{ label }}</span>
    <slot v-if="slots.icon" name="icon" />
  </button>
</template>

<style scoped>
.button {
  width: 100%;
  height: 56px;
  border-radius: 6px;
}

.button_rounded {
  border-radius: 100%;
}
</style>