<template>
  <v-container class="pa-auto" height="500">
    <v-row>
      <v-col
        v-for="n in 36"
        :key="n"
        class="d-lg-flex child-flex pa-1"
        cols="2"
      >         
        <v-responsive :aspect-ratio="1">
          <v-dialog v-model="tasks[n-1].dialog" max-width="500">
            <template v-slot:activator="{ on, attrs }">
              <v-card class="
                ma-auto
                fill-height                  
                text-lg-h5"                  
                v-bind="attrs"
                v-on="on"
                outlined                              
                :color="setColor(n)">

                <v-card-text v-if="!isDone(n)" class="fill-height content text-lg-h6">
                  {{createPreview(n)}}
                </v-card-text>
                <v-card-title v-else class="fill-height content pa-0">
                  {{tasks[n-1].owner}}
                </v-card-title>
              </v-card>
            </template>              
            <v-card color="amber lighten-5">
              <v-img v-if="isDone(n)" :src="tasks[n-1].src" />
              <v-card-text v-else class="pa-5">
                <h3 class="content">
                  {{tasks[n-1].text}}
                </h3>
              </v-card-text>
              <v-divider/>
              <v-card-actions>
                <v-spacer></v-spacer>
                <v-btn color="primary" text @click="tasks[n-1].dialog = false">
                  Zurück
                </v-btn>
                <v-btn v-show="!isDone(n)" color="primary" text @click="sendEmail(n)">
                  Einsenden
                </v-btn>
              </v-card-actions>
            </v-card>              
          </v-dialog>
        </v-responsive>
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
        owner: 'CK',
        color: '#CCDD12',
        dialog: false
      },
      {
        text: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Odit, non?',
        src: null,
        owner: 'FB',
        color: '#0000FF'
      },
      {
        text: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Odit, non?',
        src: 'img/pexels-stein-egil-liland-3408744.jpg',
        owner: 'EL',
        color: '#FEEF44',
        dialog: false
      },
      {
        text: '123456789 123456789 123456789 123456789 123456789',
        src: null,
        owner: 'Foo Bar',
        color: '#BCAAA4',
        dialog: false
      },
      {
        text: 'Lorem ipsum dolor sit amet.',
        src: null,
        owner: 'Foo Bar',
        color: '#BCAAA4',
        dialog: false
      },
      {
        text: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Odit, non?',
        src: null,
        owner: 'Foo Bar',
        color: '#BCAAA4',
        dialog: false
      },
      {
        text: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Odit, non?',
        src: null,
        owner: 'Foo Bar',
        color: '#BCAAA4',
        dialog: false
      },
      {
        text: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Odit, non?',
        src: null,
        owner: 'Foo Bar',
        color: '#BCAAA4',
        dialog: false
      },
      {
        text: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Odit, non?',
        src: null,
        owner: 'Foo Bar',
        color: '#BCAAA4',
        dialog: false
      },
      {
        text: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Odit, non?',
        src: null,
        owner: 'Foo Bar',
        color: '#CCCCCC',
        dialog: false
      },
      {
        text: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Odit, non?',
        src: null,
        owner: 'Foo Bar',
        color: '#CCDD12',
        dialog: false
      },
      {
        text: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Odit, non?',
        src: 'img/pexels-paul-ijsendoorn-33041.jpg',
        owner: 'PI',
        color: '#12AB34',
        dialog: false
      },
            {
        text: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Odit, non?',
        src: 'img/pexels-chokniti-khongchum-2280571.jpg',
        owner: 'CK',
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
        owner: 'EL',
        color: '#FEEF44',
        dialog: false
      },
      {
        text: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Qui, at quidem fuga id distinctio omnis?',
        src: null,
        owner: 'Foo Bar',
        color: '#BCAAA4',
        dialog: false
      },
      {
        text: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Odit, non?',
        src: null,
        owner: 'Foo Bar',
        color: '#BCAAA4',
        dialog: false
      },
      {
        text: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Odit, non?',
        src: null,
        owner: 'Foo Bar',
        color: '#BCAAA4',
        dialog: false
      },
      {
        text: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Qui, at quidem fuga id distinctio omnis?',
        src: null,
        owner: 'Foo Bar',
        color: '#BCAAA4',
        dialog: false
      },
      {
        text: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Odit, non?',
        src: null,
        owner: 'Foo Bar',
        color: '#BCAAA4',
        dialog: false
      },
      {
        text: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Odit, non?',
        src: null,
        owner: 'Foo Bar',
        color: '#BCAAA4',
        dialog: false
      },
      {
        text: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Odit, non?',
        src: null,
        owner: 'Foo Bar',
        color: '#CCCCCC',
        dialog: false
      },
      {
        text: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Odit, non?',
        src: null,
        owner: 'Foo Bar',
        color: '#CCDD12',
        dialog: false
      },
      {
        text: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Qui, at quidem fuga id distinctio omnis?',
        src: 'img/pexels-paul-ijsendoorn-33041.jpg',
        owner: 'PI',
        color: '#12AB34',
        dialog: false
      },
      {
        text: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Odit, non?',
        src: null,
        owner: 'Foo Bar',
        color: '#BCAAA4',
        dialog: false
      },
      {
        text: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Odit, non?',
        src: null,
        owner: 'Foo Bar',
        color: '#BCAAA4',
        dialog: false
      },
      {
        text: 'Lorem ipsum dolor sit amet.',
        src: null,
        owner: 'Foo Bar',
        color: '#BCAAA4',
        dialog: false
      },
      {
        text: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Odit, non?',
        src: null,
        owner: 'Foo Bar',
        color: '#BCAAA4',
        dialog: false
      },
      {
        text: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Odit, non?',
        src: null,
        owner: 'Foo Bar',
        color: '#BCAAA4',
        dialog: false
      },
      {
        text: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Odit, non?',
        src: null,
        owner: 'Foo Bar',
        color: '#CCCCCC',
        dialog: false
      },
      {
        text: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Odit, non?',
        src: null,
        owner: 'Foo Bar',
        color: '#CCDD12',
        dialog: false
      },
      {
        text: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Odit, non?',
        src: 'img/pexels-paul-ijsendoorn-33041.jpg',
        owner: 'PI',
        color: '#12AB34',
        dialog: false
      },
      {
        text: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Odit, non?',
        src: null,
        owner: 'Foo Bar',
        color: '#BCAAA4',
        dialog: false
      },
      {
        text: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Odit, non?',
        src: null,
        owner: 'Foo Bar',
        color: '#BCAAA4',
        dialog: false
      },
      {
        text: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Odit, non?',
        src: null,
        owner: 'Foo Bar',
        color: '#BCAAA4',
        dialog: false
      },
      {
        text: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Odit, non?',
        src: null,
        owner: 'Foo Bar',
        color: '#BCAAA4',
        dialog: false
      }
    ]
  }),
  methods: {
    isDone(n) {
      return this.tasks[n-1].src !== null
    },
    sendEmail(n) {
      this.tasks[n-1].dialog = false
      window.open('mailto:'+this.email+'?subject='+n)    
    },
    setColor(n) {
      return (this.tasks[n-1].src === null) ? 'grey lighten-1' : this.tasks[n-1].color
    },
    createPreview(n) {
      switch (this.$vuetify.breakpoint.name) {
        case 'xs': return "🤔"
        case 'sm': return this.tasks[n-1].text.substring(0, 22) + "..."
        case 'md': return this.tasks[n-1].text.substring(0, 32) + "..."
        case 'lg': return this.tasks[n-1].text.substring(0, 47) + "..."
      }        
      return this.tasks[n-1].text
    }
  },
}
</script>