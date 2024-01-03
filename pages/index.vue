<template>
  <div>
    <h1>Estimate</h1>

    <p>{{ count }}</p>
    <AppAlert>
      It is a good day to die
    </AppAlert>
  </div>
</template>

<script setup lang="ts">
  const { data: count } = await useFetch('http://localhost:3000/api/v1/estimates')
</script>
