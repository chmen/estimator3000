<template>
  <header>
    <nav>

    </nav>
    <n-button>naive-ui</n-button>
  </header>

  <div>
    <NuxtPage />
  </div>
</template>

<script>
  import { defineComponent } from 'vue'
  import { NButton } from 'naive-ui'

  export default defineComponent({
    components: {
      NButton
    }
  })
</script>
