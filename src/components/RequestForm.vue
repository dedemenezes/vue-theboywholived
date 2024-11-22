<script setup>
import { onBeforeMount, ref } from 'vue'

const baseUrl = 'https://shielded-cliffs-65656-a314194ea4d1.herokuapp.com/api/v1/'
const props = defineProps({
  msg: {
    type: String,
  },
})
const path = ref(props.msg)

const sendResquest = () => {
  // console.log(path.value)
  fetch(`${baseUrl}${path.value}`)
    .then((response) => response.json())
    .then((data) => {
      console.log(data)
      new JsonViewer({
        value: data,
        displayDataTypes: false,
        rootName: false,
        indentWidth: 4,
        enableClipboard: true,
        defaultInspectDepth: 3,
      }).render('.tree')
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
