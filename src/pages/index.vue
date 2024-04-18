<template>
  <div ref="target">
    <div>Hello World</div>
    <RouterLink to="/">home</RouterLink>
    <RouterLink to="/about">about</RouterLink>
    <div class="p-4">Hello World</div>
    <h1 class="text-3xl font-bold underline">Hello world!</h1>
    <div>{{ msg }}</div>
    <p>x:{{ x }}</p>
    <p>y:{{ y }}</p>
    <p>isOutside:{{ isOutside }}</p>
    <HelloWorld></HelloWorld>
    <!-- <UserUserComonents></UserUserComonents> -->
    <UserComonents></UserComonents>
  </div>
</template>

<script setup lang="ts">
import { RouterLink } from 'vue-router'
const msg = ref('AUTO-import')

const target = ref(null)

const { x, y, isOutside } = useMouseInElement(target)
</script>

<style scoped></style>
