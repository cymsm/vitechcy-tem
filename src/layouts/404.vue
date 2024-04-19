<template>
  <div>
    <h1>404</h1>
    <router-view></router-view>
    <button @click="router.back()">返回首页</button>
  </div>
</template>

<script setup lang="ts">
import { useRouter } from 'vue-router'

const router = useRouter()
</script>

<style scoped></style>
