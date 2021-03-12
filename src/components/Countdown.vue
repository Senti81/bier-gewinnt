<template>
  <v-container class="pt-5" height="500">
    <h2 class="text-center">Start in:</h2>
    <FlipCountdown deadline="2021-04-23 15:16:00"/>
  </v-container>
</template>

<style lang="css">
  .content {
    display: flex;
    text-align: center;
    justify-content: center;
    align-items: center;
  }
</style>

<script>
import FlipCountdown from 'vue2-flip-countdown'

export default {
  components: {
    FlipCountdown
  }
}
</script>