<script setup>
const { data } = await useAsyncData('ssr', () => $fetch('http://43.140.248.221:3000/dj/program?rid=336355127'))
const { programs } = toRaw(data.value)
console.log(programs)
</script>

<template>
  Page visits:
  <div v-for="(item, index) in programs" :key="index">{{ item.name }}</div>
</template>