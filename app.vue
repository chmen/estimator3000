<template>
  <header>
    <nav>
      <ul>
        <li><NuxtLink to="/">Estimate</NuxtLink></li>
        <li><NuxtLink to="/coding">Coding</NuxtLink></li>
        <li><NuxtLink to="/manual">Manual</NuxtLink></li>
        <li><NuxtLink to="/automation_tests">Automation tests</NuxtLink></li>
        <li><NuxtLink to="/open_questions">Open questions</NuxtLink></li>
      </ul>
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
