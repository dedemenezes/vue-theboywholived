<script setup>
import ButtonFlat from './ButtonFlat.vue'
</script>

<template>
  <div class="banner text-primary text-center">
    <div class="container">
      <h1>The Magical World of <br />Harry Potter<br />at Your Fingertips</h1>
      <p>
        Access comprehensive data about characters, spells, potions, and more from the wizarding
        world through our modern REST API.
      </p>
      <ButtonFlat msg="Try it out!" />
    </div>
  </div>
</template>

<style scoped>
.banner {
  background-size: cover;
  background-position: center;
  padding: 120px 0;
  /* height: 420px; */
  /* display: block; */
}

.banner h1 {
  margin: 0;
  margin-bottom: 1rem;
  text-shadow: 1px 1px 3px rgba(0, 0, 0, 0.2);
  font-size: 62px;
  text-align: center;
  font-weight: bold;
  /* color: $primary; */
}

.banner p {
  font-size: 20px;
  color: white;
  opacity: 0.7;
  text-shadow: 1px 1px 3px rgba(0, 0, 0, 0.2);
  margin-bottom: 2rem;
}
</style>
