<template>
  <div>Valor: {{saturateInputValue}}</div>
  <label for="saturateInputValue">{{label}}</label>
  <input type="range" @input="$emit('updateSaturateFilter', $event.target.value)" :min="min" :max="max" :step="step" v-model="saturateInputValue" />
</template>

<script setup>
import { ref } from "vue";

const props = defineProps({
  label: {
    type: String,
    default: ''
  },
  min: {
    type: Number,
    default: 0
  },
  max: {
    type: Number,
    default: 100,
  },
  step: {
    type: Number,
    default: 1
  }
})

const emits = defineEmits(['updateSaturateFilter'])

const saturateInputValue = ref(0);
</script>