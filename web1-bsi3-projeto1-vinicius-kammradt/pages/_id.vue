<template>
  <VApp>
    <VContent>
      <SuperiorToolbar />
      <vContainer
        grid-list-xs
      >
        <VLayout
          grid-list-xs
          wrap
          row
        >
          <VFlex
            xs12
            text-xs-left
            font-weight-regular
            display-2
            v-text="news.title"
          />
          <VFlex
            xs12
            text-xs-left
            font-weight-light
            subheading
            v-text="news.description"
          />
          <VFlex
            xs12
            text-xs-center
            pa-3
          >
            <img :src="news.urlToImage" width="600" :alt="news.title">
          </VFlex>
          <VFlex
            v-for="i in 10"
            :key="i"
            xs12
            text-xs-left
            font-weight-light
            subheading
            pa-1
            v-text="news.content"
          />
        </VLayout>
      </vContainer>
      <MyFooter />
    </VContent>
  </VApp>
</template>

<script>
import axios from 'axios'
import SuperiorToolbar from '@/components/SuperiorToolbar'
import MyFooter from '@/components/MyFooter'
export default {
  components: { SuperiorToolbar, MyFooter },
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
