<script setup>
import { defineProps, onMounted } from 'vue'

const props = defineProps({
  value: Object,
})

onMounted(() => {
  new JsonViewer({
    value: props.value,
    displayDataTypes: false,
    rootName: false,
    indentWidth: 4,
    enableClipboard: true,
    defaultInspectDepth: 3,
  }).render('.tree')
})
</script>

<template>
  <pre class="response tree" id="response" data-request-target="pre"></pre>
</template>
