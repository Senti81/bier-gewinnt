<template>
  <v-container>
    <v-row>
      <v-col
        v-for="n in 16"
        :key="n"
        class="d-sm-flex child-flex"
        cols="3"
      >           
        <v-img
          :src="`/img/${n}.png`"
          aspect-ratio="1"
          class="grey lighten-2"
          @click="sendEmail(n)"
        >
          <template v-slot:placeholder>
            <v-row
              class="fill-height ma-0"
              align="center"
              justify="center"
            >
              <div class="ma-1">
                <h6 class="text-center">
                  {{tasks[n-1].description}}
                </h6>
              </div>
            </v-row>
          </template>
        </v-img>
      </v-col>
    </v-row>
  </v-container>
</template>



<script>
export default {
  data:() => ({
    cols: 4,
    rows: 4,
    email: "biergewinnt0@gmail.com",
    tasks: [
      {
        description: 'Lorem Ipsum A1',
        done: false,        
      },
      {
        description: 'Lorem Ipsum A2',
        done: false,        
      },
      {
        description: 'Lorem Ipsum A3',
        done: true,        
      },
      {
        description: 'Lorem Ipsum A4',
        done: false,        
      },
      {
        description: 'Lorem Ipsum B1',
        done: false,        
      },
      {
        description: 'Lorem Ipsum B2',
        done: false,        
      },
      {
        description: 'Lorem Ipsum B3',
        done: false,        
      },
      {
        description: 'Lorem Ipsum B4',
        done: false,        
      },
            {
        description: 'Lorem Ipsum C1',
        done: false,        
      },
      {
        description: 'Lorem Ipsum C2',
        done: false,        
      },
      {
        description: 'Lorem Ipsum C3',
        done: false,        
      },
      {
        description: 'Lorem Ipsum C4',
        done: false,        
      },
            {
        description: 'Lorem Ipsum D1',
        done: false,        
      },
      {
        description: 'Lorem Ipsum D2',
        done: false,        
      },
      {
        description: 'Lorem Ipsum D3',
        done: false,        
      },
      {
        description: 'Lorem Ipsum D4',
        done: false,        
      },
    ]
  }),
  methods: {
    sendEmail(index) {
      if(!this.tasks[index-1].done) {
        window.open('mailto:'+this.email+'?subject='+this.tasks[index-1].description)
      }
    }
  }
}
</script>