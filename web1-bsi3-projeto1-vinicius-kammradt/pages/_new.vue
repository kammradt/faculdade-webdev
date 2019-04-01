<template>
  <VApp>
    <VContent>
      <h1>
        <!--Aqui é o indice da noticia que o cara clicou, /2 por ex -->
        {{ $nuxt.$route.path.substring(1) }}
      </h1>
      <div>
        <!--Aqui é a notícia usando o indice -->
        {{ news[$nuxt.$route.path.substring(1)] }}
      </div>
      <div>
        <!--Aqui é o titulo da noticia que o cara clicou -->
        <!--Ele mostrar o título uma vez, e depois se atualizar a pagina da pau-->
        <!-- {{ news[$nuxt.$route.path.substring(1)].title }} -->
      </div>
    </VContent>
  </VApp>
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
