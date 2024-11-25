<script setup>
const props = defineProps({
  msg: {
    type: String,
    required: true,
  },
  href: {
    type: String,
    require: true,
  },
})
</script>
<template>
  <a class="btn btn-flat" :href="props.href">{{ msg }}</a>
</template>
<style scoped>
.btn-flat {
  color: white;
  padding: 8px 24px;
  border-radius: 4px;
  background: #2a623d;
  transition: background 0.3s ease;
}

.btn-flat:hover {
  background: #1a472a;
  color: white;
}
</style>
