<template>
  <v-container
    fluid
    class="pa-6"
    >
    <v-row>
      <v-col
        v-for="n in 12"
        :key="n"
        class="d-xs-flex child-flex pa-1"
        cols="2"
      >         
        <v-card class="fill-height" :color="setColor(n)">
          <v-responsive :aspect-ratio="1">

            <!-- Aufgabe noch offen -->
            <v-card-subtitle v-if="tasks[n-1].src === null" class="              
              fill-height
              content
              text-caption"
              @click="sendEmail(n)"              
            >
              {{tasks[n-1].text}}
            </v-card-subtitle>

            <!-- Aufgabe gelöst -->
            <v-dialog v-else v-model="tasks[n-1].dialog" max-width="750">
              <template v-slot:activator="{ on, attrs }">
                <v-card-subtitle class="
                  fill-height
                  content"
                  v-bind="attrs"
                  v-on="on"
                >
                  {{tasks[n-1].owner}}
                </v-card-subtitle>
              </template>
              <v-img            
                :src="tasks[n-1].src"
                aspect-ratio="1.67"
              >
              </v-img>
            </v-dialog>
          </v-responsive>
        </v-card>           
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
    email: "biergewinnt0@gmail.com",
    tasks: [
      {
        text: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Odit, non?',
        src: 'img/pexels-chokniti-khongchum-2280571.jpg',
        owner: 'Chokniti Khongchum',
        color: '#CCDD12',
        dialog: false
      },
      {
        text: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Odit, non?',
        src: null,
        owner: 'Foo Bar',
        color: '#0000FF'
      },
      {
        text: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Odit, non?',
        src: 'img/pexels-stein-egil-liland-3408744.jpg',
        owner: 'Egil Liland',
        color: '#FEEF44',
        dialog: false
      },
      {
        text: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Odit, non?',
        src: null,
        owner: 'Foo Bar',
        color: '#BCAAA4'
      },
      {
        text: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Odit, non?',
        src: null,
        owner: 'Foo Bar',
        color: '#BCAAA4'
      },
      {
        text: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Odit, non?',
        src: null,
        owner: 'Foo Bar',
        color: '#BCAAA4'
      },
      {
        text: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Odit, non?',
        src: null,
        owner: 'Foo Bar',
        color: '#BCAAA4'
      },
      {
        text: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Odit, non?',
        src: null,
        owner: 'Foo Bar',
        color: '#BCAAA4'
      },
      {
        text: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Odit, non?',
        src: null,
        owner: 'Foo Bar',
        color: '#BCAAA4'
      },
      {
        text: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Odit, non?',
        src: null,
        owner: 'Foo Bar',
        color: '#CCCCCC'
      },
      {
        text: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Odit, non?',
        src: null,
        owner: 'Foo Bar',
        color: '#CCDD12'
      },
      {
        text: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Odit, non?',
        src: 'img/pexels-paul-ijsendoorn-33041.jpg',
        owner: 'Paul Ijsendoorn',
        color: '#12AB34',
        dialog: false
      },
    ]
  }),
  methods: {
    sendEmail(n) {
      window.open('mailto:'+this.email+'?subject='+n)    
    },
    showImage(n) {
      alert(`Show Image ${n}`)
    },
    setColor(n) {
      return (this.tasks[n-1].src === null) ? 'blue lighten-1' : this.tasks[n-1].color
    }
  },
}
</script>