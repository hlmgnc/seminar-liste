<template>
  <div>
    <h>{{ this.title }} / {{ this.text }}</h>
    <p>{{ this.text }}</p>
  </div>
</template>

<script>
// import index from './index.vue'
export default {
  data({ params }) {
    const title = params.title
    const text = params.text
    return { title, text }
  },
}
</script>

<style scoped></style>
