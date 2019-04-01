<template>
  <VApp>
    <VContent>
      <h1>
        <!--Aqui é o indice da noticia que o cara clicou, /2 por ex -->
        {{ $route.params.id }}
      </h1>
      <div>
        <!--Aqui é a notícia usando o indice -->
        {{ news }}
      </div>
      <div>
        <!--Aqui é o titulo da noticia que o cara clicou -->
        <!--Ele mostrar o título uma vez, e depois se atualizar a pagina da pau-->
        {{ news.title }}
      </div>
    </VContent>
  </VApp>
</template>

<script>
import axios from 'axios'
export default {
  asyncData({ app, route }) {
    console.log(route.params.id)
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
