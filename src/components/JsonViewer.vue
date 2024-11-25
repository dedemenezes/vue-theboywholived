<script setup>
import { defineProps, onMounted, watch } from 'vue'

const props = defineProps({
  value: Object,
})

const renderResponse = () => {
  new JsonViewer({
    value: props.value,
    displayDataTypes: false,
    rootName: false,
    indentWidth: 4,
    enableClipboard: true,
    defaultInspectDepth: 3,
  }).render('.tree')
}

watch(
  () => props.value,
  () => {
    renderResponse()
  },
)

onMounted(() => {
  renderResponse()
})
</script>

<template>
  <pre class="response tree" id="response"></pre>
</template>
