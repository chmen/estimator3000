<template>
  <div>
    <h1>Estimates</h1>

    <p>{{ count }}</p>
    <div v-for="estimate in estimates">
      {{ estimate.id }} {{ estimate.title }}
      <span><NuxtLink :to="'/estimates/' + estimate.id">Show/Edit</NuxtLink></span>
    </div>
      <router-view :key="$route.path"></router-view>
  </div>
</template>

<script setup lang="ts">
  const { data: estimates } = await useFetch('http://localhost:3000/api/v1/estimates')
</script>
