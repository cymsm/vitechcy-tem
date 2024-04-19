<template>
  <div>home</div>
</template>

<script setup lang="ts">
import { registerSW } from 'virtual:pwa-register'

onMounted(() => {
  registerSW({
    immediate: true,
    onRegisteredSW(_url, registration) {
      // 每五秒请求服务器资源，并自动更新
      setInterval(() => {
        registration?.update()
      }, 3600000)
    }
  })
})
</script>

<style scoped></style>
<route lang="yaml">
meta:
  layout: default
</route>
