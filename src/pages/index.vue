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
  <Child @click-count="handleClickCount"></Child>
  <!-- <ReloadPrompt></ReloadPrompt>
  hello ppp -->
</template>

<script setup lang="ts">
import { RouterLink } from 'vue-router'
import { registerSW } from 'virtual:pwa-register'

onMounted(() => {
  registerSW({
    immediate: true,
    // onNeedRefresh() {
    //   console.log('need refresh')
    // },
    onRegisteredSW(_url, registration) {
      // 每五秒请求服务器资源，并自动更新
      setInterval(() => {
        registration?.update()
      }, 5000)
    }
  })
})
const handleClickCount = (count: number) => {
  console.log('click count:', count)
}
// vue-macros
// defineOptions({ name: 'HomeIndex' })
// defineRender(() => <div>Hello World</div>)
const msg = ref('AUTO-import')

const target = ref(null)

const { x, y, isOutside } = useMouseInElement(target)
</script>

<style scoped></style>
<route lang="yaml">
meta:
  layout: default
</route>
