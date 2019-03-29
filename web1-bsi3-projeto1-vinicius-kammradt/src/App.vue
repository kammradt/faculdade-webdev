<template>
  <v-app>
    <v-toolbar app>
      <v-toolbar-title class="headline text-uppercase">
        <span>Vinicius</span>
        <span class="font-weight-light">Kammradt</span>
      </v-toolbar-title>
      <v-spacer></v-spacer>
      <v-btn
        flat
        small
        href="https://github.com/kammradt/faculdade-webdev"
        target="_blank"
      >
        <v-icon left>
          code
        </v-icon>
        <span class="mr-2">Github</span>
      </v-btn>
    </v-toolbar>

  </v-app>
</template>

<script>

export default {
  name: 'App',
  data () {
    return {
      //
    }
  }
}
</script>
