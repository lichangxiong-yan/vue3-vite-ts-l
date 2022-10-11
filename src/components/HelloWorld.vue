<script setup lang="ts">
import { ref, computed } from 'vue'

defineProps<{ msg: string }>()

const count = ref(0)
const counts = ref(0)
const list = ref(['葡萄', '香蕉', '橘子'])
const lists = ref({
  title: '111',
  author: '22222',
  pub: '2022-10-8'
})


const handleClick = () => {
  return counts.value++
}
const countComputed = computed(() => {
  return counts.value++
})
</script>

<template>
  <h1>{{ msg }}</h1>

  <div class="card">
    <button type="button" @click="count++">count is {{ count }}</button>
    <button type="button" @click="handleClick">counts is {{ countComputed }}</button>
    <ul>
      <li v-for="ele, index in list">
      {{index}} - {{ele}}</li>
    </ul>
    <ul>
      <li v-for="c, k in lists">
      {{k}} - {{c}}</li>
    </ul>
  </div>
</template>

<style scoped>
.read-the-docs {
  color: #888;
}
</style>
