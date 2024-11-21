<script setup>
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

<style scoped></style>
