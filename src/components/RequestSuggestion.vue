<script setup>
const props = defineProps({
  msg: {
    type: String,
    required: true,
  },
})

const emit = defineEmits(['update-path'])
</script>

<template>
  <em @click="emit('update-path', props.msg)" :path="props.msg">{{ props.msg }}</em>
</template>

<style scoped>
em:hover {
  cursor: pointer;
  text-decoration: underline;
  text-decoration-color: #eeba30;
  text-underline-offset: 2px;
}
</style>
