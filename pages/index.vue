<script setup lang="ts">
const { data } = await useFetch('/api/endpoint', {
  transform(input) {
    return {
      name: input.item.name,
      flavorText: input.item.flavorText,
      iconSrc: input.item.iconSrc
    }
  }
})
</script>

<template>
  <div>
    <h1>{{ data?.name }}</h1>
    <h2>{{ data?.flavorText }}</h2>
    <img :src="data?.iconSrc">
  </div>
</template>