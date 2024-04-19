<template>
  <div>
    <p>ChildComponent</p>
    <button @click="handleClick">click me</button>
  </div>
</template>

<script setup lang="ts">
const num = ref(0)
const emits = defineEmits<{
  (e: 'clickCount', num: number): void
}>()
// const emits = defineEmits<
//   SE<{
//     clickCount(num: number): void
//   }>
// >()
const handleClick = () => {
  emits('clickCount', ++num.value)
}
</script>

<style scoped></style>
