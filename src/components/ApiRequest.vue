<script setup>
import RequestForm from './RequestForm.vue'
</script>
<template>
  <div class="container">
    <RequestForm />
    <pre class="response tree" id="response" data-request-target="pre"></pre>
  </div>
</template>
