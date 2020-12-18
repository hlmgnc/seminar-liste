<template>
  <div class="container">
    <div>
      <h1 class="title">Aktuelle Seminare</h1>
      <ul>
        <nuxt-link
          to="/seminar"
          v-for="seminar in seminars"
          :key="seminar._id"
          class="semi"
        >
          {{ seminar.title }}
          <p>{{ seminar.from }}</p>
          <li>{{ seminar.to }}</li>
          <img src="https://backend.neue-gruppe.com/seminar.image.url " />
          <button class="btn">mehr erfahren</button>
          <br />
          <br />
        </nuxt-link>
      </ul>
    </div>
  </div>
</template>

<script>
import axios from 'axios'
// import seminar from './seminar'
export default {
  async asyncData() {
    const api = 'https://backend.neue-gruppe.com/seminars'
    const seminars = await axios.get(api).then((response) => {
      return response.data
    })
    return { seminars }
  },
  data() {
    return {
      seminars: [],
    }
  },
}
</script>

<style>
.container {
  margin: 0 auto;
  min-height: 15vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
}

.title {
  font-family: 'Quicksand', 'Source Sans Pro', -apple-system, BlinkMacSystemFont,
    'Segoe UI', Roboto, 'Helvetica Neue', Arial, sans-serif;

  display: block;
  font-weight: 100;
  font-size: 50px;
  color: #35495e;
  letter-spacing: 1px;
}
</style>
