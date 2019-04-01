<template>
  <v-app>
    <v-content>
      <SuperiorToolbar />
      <MyFooter />
    </v-content>    
  </v-app>
</template>

<script>
import SuperiorToolbar from '@/components/SuperiorToolbar'
import MyFooter from '@/components/MyFooter'

export default {
  name: 'App',
  components: { SuperiorToolbar, MyFooter },
  data () {
    return {
      //
    }
  }
}
</script>
