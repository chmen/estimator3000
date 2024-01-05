<template>
  <div>
    <h1>{{ estimate.id }} {{ estimate.title }}</h1>

    <p>{{ estimate.body }}</p>
  </div>
</template>

<script setup lang="ts">
  const { data: estimate } = await useFetch('http://localhost:3000/api/v1/estimates/1')
</script>
