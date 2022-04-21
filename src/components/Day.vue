<script setup>
import { ref, computed } from "vue";
const props = defineProps({
  dayOfMonth: Number,
});
const emit = defineEmits(["onselect"]);
const selected = ref(false);
const toggleDay = () => {
  selected.value = !selected.value;
  emit('onselect', {dayOfMonth: props.dayOfMonth, isSelected: selected.value})
};
const selectedClass = computed(() => {
  return selected.value ? "selected" : "";
});
</script>
<template>
  <span :class="selectedClass" @click="toggleDay">{{ dayOfMonth }}</span>
</template>

<style>
span {
  background-color: var(--color-primary-30);
  padding: 16px;
  color: white;
}
span.selected {
  background-color: var(--color-primary-40);
}
</style>
