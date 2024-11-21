<script setup>
// const data = '{"name": "json-view","version": "1.0.0"}'

import NavBar from './components/NavBar.vue'
import HomeBanner from './components/HomeBanner.vue'
import RequestForm from './components/RequestForm.vue'
</script>

<template>
  <NavBar />
  <HomeBanner />

  <div class="container">
    <RequestForm />
    <pre class="response tree" id="response" data-request-target="pre"></pre>
  </div>
</template>

<style>
.response {
  color: #3a3f44;
  background-color: #f5f5f5;
  border-radius: 4px;
  tab-size: 4;
  word-break: break-all;
  word-wrap: break-word;
  display: block;
  padding: 9.5px;
  margin: 0 0 10px;
  font-size: 0.825rem;
  max-height: 80vh;
}
.tree .json-container {
  background-color: #f5f5f5 !important;
}
</style>
