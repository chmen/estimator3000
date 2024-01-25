<template>
  <div>
    <h1>Create your estimate</h1>
    <form @submit.prevent="handleSubmit">
      <input type="text" v-model="formData.title" placeholder="Title" >
      <button type="submit">Submit</button>
    </form>
  </div>
</template>

<script>
  export default {
    data() {
      return {
          formData: {
          title: ''
        }
      };
    },
    methods: {
    handleSubmit() {
      console.log('Form submitted with data:', this.formData);
      }
    }
  }
</script>
