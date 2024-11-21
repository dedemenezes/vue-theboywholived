<script setup>
import jsonview from '@pgrabovets/json-view'
import { onBeforeMount, ref } from 'vue'
const baseUrl = 'https://theboywholived.com/api/v1/'
const path = ref('/books/4')
const sendResquest = () => {
  console.log(path.value)
  fetch(`http://127.0.0.1:3000/api/v1/${path.value}`)
    .then((response) => response.json())
    .then((data) => {
      console.log(data)
      // create json tree object
      const tree = jsonview.create(data)
      // render tree into dom element
      document.getElementById('response').innerText = ''
      jsonview.render(tree, document.getElementById('response'))
      jsonview.expand(tree)
    })
}
onBeforeMount(() => {
  sendResquest()
})
</script>
<template>
  <div class="mb-3">
    <form @submit.prevent="sendResquest" action="#">
      <div class="input-group" data-bs-theme="dark">
        <span class="input-group-text" id="basic-addon3">{{ baseUrl }}</span>
        <input
          v-model="path"
          type="text"
          class="form-control"
          id="basic-url"
          aria-describedby="basic-addon3 basic-addon4"
        />
        <button type="submit" class="btn btn-primary">Submit</button>
      </div>
      <div class="form-text" id="basic-addon4">
        Need a hint? <em>books, /characters/4, /species?page=2, wands/44...</em>
      </div>
    </form>
  </div>
</template>
