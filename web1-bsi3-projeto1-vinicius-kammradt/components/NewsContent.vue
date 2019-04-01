<template>
  <vContainer
    grid-list-xs
  >
    <VFlex
      text-xs-center
      font-weight-light
      display-2
      pb-
      v-text="'Trending news from Brazil'"
    />
    <VFlex
      text-xs-center
      font-weight-light
      subheading
      pb-3
      v-text="'Click on title to read more'"
    />
    <VLayout wrap>
      <VFlex
        v-for="_ in news"
        :key="_.title"
        xs12
        pa-3
      >
        <VCard>
          <VFlex
            title
            pa-2
            class="grey--text"
            v-text="_.title"
          />
          <VFlex
            caption
            pl-2
            class="primary--text"
            v-text="'Source: ' + _.source.name"
          />
          <VFlex
            xs12
            body-2
            font-weight-light
            pa-1
            text-justify-center
            v-text="_.content"
          />
        </VCard>
      </VFlex>
    </VLayout>
  </vContainer>
</template>

<script>
import axios from 'axios'
export default {
  data() {
    return {
      news: {}
    }
  },
  mounted() {
    axios
      .get('https://newsapi.org/v2/top-headlines?country=br&apiKey=df575fbf5083481f828502affa15caf6')
      .then(response => (this.news = response.data.articles))
  }
}
</script>
