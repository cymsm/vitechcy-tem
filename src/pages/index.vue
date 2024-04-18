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
    <!-- A basic anchor icon from Phosphor icons -->
    <div class="i-ph-anchor-simple-thin" />
    <!-- An orange alarm from Material Design Icons -->
    <div class="i-mdi-alarm text-orange-400" />
    <!-- A large Vue logo -->
    <div class="i-logos-vue text-3xl" />
    <!-- Sun in light mode, Moon in dark mode, from Carbon -->
    <button class="i-carbon-sun dark:i-carbon-moon" />
    <!-- Twemoji of laugh, turns to tear on hovering -->
    <div class="i-twemoji-grinning-face-with-smiling-eyes hover:i-twemoji-face-with-tears-of-joy" />
    <div class="i-ph:airplane w-1em h-1em" style="color: red"></div>
  </div>
</template>

<script setup lang="ts">
import { RouterLink } from 'vue-router'
const msg = ref('AUTO-import')

const target = ref(null)

const { x, y, isOutside } = useMouseInElement(target)
</script>

<style scoped></style>
