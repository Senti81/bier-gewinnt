<template>
  <v-app>
    <v-main class="amber lighten-4">
      <NavBar/>
      <Countdown v-if="new Date().getTime() < new Date(this.startTime).getTime()"/>
      <CountdownEnd v-else/>
      <Dummy v-if="new Date().getTime() < new Date(this.startTime).getTime()"/>
      <Main v-else/>
    </v-main>
  </v-app>
</template>

<script>
import Main from './components/Main'
import Dummy from './components/Dummy'
import NavBar from './components/NavBar'
import Countdown from './components/Countdown'
import CountdownEnd from './components/CountdownEnd'

export default {
  name: 'App',

  components: {
    Main,
    Dummy,
    NavBar,
    Countdown,
    CountdownEnd
  },

  data: () => ({
    started: false,
    startTime: "2021-03-23 15:16:00",
    endTime: "2021-05-21 15:16:00"   
  }),
};
</script>
