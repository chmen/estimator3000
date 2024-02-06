<template>
  <div>
    <h1>Create your estimate</h1>
    <form>
      <input type="text" v-model="formData.title" placeholder="Title" >
      <button type="button" @click="handleSubmit">Submit</button>
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
    async handleSubmit() {
      const { data: response } = await useFetch('http://localhost:3000/api/v1/estimates', {
        method: 'post',
        body: {
          data: this.formData
        }
      })

      if (response) {
        alert(response.status);
      }
      }
    }
  }
</script>
