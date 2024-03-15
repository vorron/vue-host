<script setup lang="ts">
import { onMounted, ref } from 'vue'
import ReactDOMServer from 'react-dom/server'

const componentHtml = ref()

onMounted(
  async () =>
    (componentHtml.value = ReactDOMServer.renderToString((await import('home/Home')).default()))
)
</script>

<template>
  <div v-html="componentHtml"></div>
</template>
