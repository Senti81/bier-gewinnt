<template>
  <v-container class="pt-5" height="500">
    <h2 class="text-center">Ende in:</h2>
    <FlipCountdown deadline="2021-05-31 23:59:59"/>
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