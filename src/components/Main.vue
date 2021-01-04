<template>
  <v-container
    fluid
    class="pa-6"
    >
    <v-row>
      <v-col
        v-for="n in 42"
        :key="n"
        class="d-sm-flex child-flex pa-1"
        cols="2"
      >         
        <v-hover v-slot="{ hover }">
          <v-card
            :elevation="hover ? 12 : 2 "
            :class="{ 'on-hover': hover }"
            >
            <v-img
              :src="`/img/${n}.jpg`"
              aspect-ratio="1"
              @click="sendEmail(n)"
            >
              <template v-slot:placeholder>
                <v-card class="fill-height">
                  <v-card-text class="blue lighten-5 fill-height content">
                    {{n}} Lorem ipsum dolor sit amet consectetur adipisicing elit. Architecto, aut.
                  </v-card-text>
                </v-card>
              </template>
            </v-img>
          </v-card>
        </v-hover>  
      </v-col>
    </v-row>
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
export default {
  data:() => ({
    cols: 6,
    rows: 7,
    email: "biergewinnt0@gmail.com",   
  }),
  methods: {
    sendEmail(index) {
      window.open('mailto:'+this.email+'?subject='+index)
    },    
  }  
}
</script>