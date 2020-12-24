<template>
  <v-container class="mt-6">
    <v-row
      v-for="(y, iY) in rows" :key="iY"
      no-gutters
    >
      <v-col
        v-for="(x, iX) in cols" :key="iX"
        cols="2"
      >
        <v-card       
          class="text-center"
          outlined
          tile
          elevation="6"
          width="200"
          height="100"
          @click="sendEmail(x, y, tasks[iX + cols*iY])"
        >
          <v-img v-if="tasks[iX + cols*iY].done"
            :src="`/img/${x}-${y}.jpg`"
            height="100px"            
          >
          </v-img>
          <div class="center" v-else>
            <p class="subtitle-2">
              {{tasks[iX + cols*iY].description}}
            </p>
          </div>
        </v-card>
      </v-col>
    </v-row>
  </v-container>
</template>


<style scoped>
  .center {
    margin: 0;
    position: absolute;
    top: 50%;
    left: 50%;
    -ms-transform: translate(-50%, -50%);
    transform: translate(-50%, -50%);
  }
</style>

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
        done: false,        
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
    sendEmail(x, y, index) {
      if(!index.done) {
        window.open('mailto:'+this.email+'?subject='+index.description+' ('+x+'-'+y+')')
      }
    }
  }
}
</script>