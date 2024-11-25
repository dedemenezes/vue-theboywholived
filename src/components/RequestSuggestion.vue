<script setup>
const props = defineProps({
  msg: {
    type: String,
    required: true,
  },
})

const emit = defineEmits(['path-selected'])
</script>

<template>
  <em @click="emit('path-selected', props.msg)" :path="props.msg">{{ props.msg }}</em>
</template>

<style scoped>
em:hover {
  cursor: pointer;
  text-decoration: underline;
  text-decoration-color: #eeba30;
  text-underline-offset: 2px;
}
</style>
