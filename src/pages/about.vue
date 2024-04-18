<template>
  <div>about</div>
  <RouterLink to="/">home</RouterLink>
  <RouterLink to="/about">about</RouterLink>
</template>

<script setup lang="ts">
import { RouterLink } from 'vue-router'
</script>

<style scoped></style>
<route lang="yaml">
meta:
  layout: home
</route>
