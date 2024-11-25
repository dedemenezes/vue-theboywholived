<script setup>
import { onMounted, ref } from 'vue'

const baseUrl = 'https://shielded-cliffs-65656-a314194ea4d1.herokuapp.com/api/v1/'

const cache = new Map()

const path = ref('/books/1')

const emits = defineEmits(['response'])
const sendResquest = async () => {
  if (!cache.has(path.value)) {
    const response = await fetch(`${baseUrl}${path.value}`)
    const data = await response.json()
    cache.set(path.value, data)
    emits('response', data)
  } else {
    console.log('CACHED:::', cache)
    emits('response', cache.get(path.value))
  }
}

onMounted(() => {
  sendResquest()
})
</script>
<template>
  <div class="mb-3">
    <form @submit.prevent="sendResquest" action="#">
      <div class="input-group" data-bs-theme="dark">
        <span class="input-group-text" id="basic-addon3">base url</span>
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
