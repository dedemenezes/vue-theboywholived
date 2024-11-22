<script setup>
import RequestForm from './RequestForm.vue'
const props = defineProps({
  msg: {
    type: String,
    required: true,
  },
})
console.log(props.msg)
</script>
<template>
  <div class="container">
    <RequestForm :msg="props.msg" />
    <pre class="response tree" id="response" data-request-target="pre"></pre>
  </div>
</template>
