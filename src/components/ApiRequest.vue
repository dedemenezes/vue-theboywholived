<script setup>
import RequestForm from './RequestForm.vue'
import JsonViewer from './JsonViewer.vue'

import { ref } from 'vue'
const responseData = ref(null)

const handleUpdate = (data) => {
  // console.log(data)
  responseData.value = data
}
</script>
<template>
  <div class="container">
    <RequestForm @response="handleUpdate" />
    <JsonViewer v-if="responseData" :value="responseData" />
  </div>
</template>
