<template>
  <v-app>
    <v-main class="amber lighten-4">
      <Header/>
      <Rules/>
      <Main/>
    </v-main>
  </v-app>
</template>

<script>
import Main from './components/Main'
import Header from './components/Header'
import Rules from './components/Rules'

export default {
  name: 'App',

  components: {
    Main,
    Rules,
    Header
  },

  data: () => ({
    //
  }),
};
</script>
