<template>
  <div>Valor: {{ modelValue }}</div>
  <label for="saturateInputValue"><slot /></label>
  <input
    type="range"
    :value="modelValue"
    @input="$emit('update:modelValue', $event.target.value)"
    :min="min"
    :max="max"
    :step="step"
  />
  <div class="info">
    <slot name="info"></slot>
  </div>
</template>

<script setup>
import { ref } from "vue";

const props = defineProps({
  modelValue: {
    default: 0,
  },
  label: {
    type: String,
    default: "",
  },
  min: {
    type: Number,
    default: 0,
  },
  max: {
    type: Number,
    default: 100,
  },
  step: {
    type: Number,
    default: 1,
  },
});

const emits = defineEmits(["update:modelValue"]);
</script>
