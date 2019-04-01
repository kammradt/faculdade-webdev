<template>
  <VApp>
    <VContent>
      <h1>
        {{ news.title }}
      </h1>
    </VContent>
  </VApp>
</template>

<script>
import axios from 'axios'
export default {
  asyncData({ app, route }) {
    return Promise.all([
      axios.get('https://newsapi.org/v2/top-headlines?country=br&apiKey=df575fbf5083481f828502affa15caf6')
    ])
      .then((response) => {
        return {
          news: response[0].data.articles[route.params.id]
        }
      })
  }
}
</script>
