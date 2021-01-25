<template>
  <v-container class="pa-auto" height="500">
    <hr class="black">
    <p class="text-left my-4">Nachfolgend ein Beispiel, wie das Spielfeld im Laufe des Spiels aussehen könnte:</p>
    <p class="text-left my-4">Klickt auf ein Feld, um die Funktionalität zu testen.</p>
    <v-row>
      <v-col
        v-for="n in tasks.length"
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
                :color="setColor(n)"
              >
                <v-card-text v-if="!isDone(n)" class="fill-height content text-lg-h6">
                  {{createPreview(n)}}
                </v-card-text>
                <v-card-title v-else class="fill-height content pa-0">
                  {{tasks[n-1].owner}}
                </v-card-title>
              </v-card>
            </template>              
            <v-card color="amber lighten-5">
              <v-card-title>
                {{isDone(n) ? "Beispiel: Aufgabe erfüllt" : "Beispiel: Aufgabe offen"}}
              </v-card-title>
              <v-divider/>
              <v-img v-if="isDone(n)" :src="tasks[n-1].src" :lazy-src="tasks[n-1].src">
                <template v-slot:placeholder>
                  <v-row
                    class="fill-height ma-0"
                    align="center"
                    justify="center"
                  >
                    <v-progress-circular
                      indeterminate
                      color="grey lighten-1"
                    ></v-progress-circular>
                  </v-row>
                </template>
              </v-img>                        
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

    <!-- Feedback -->
    <v-btn fab fixed small top right color="primary" @click="sendFeedback">            
      <v-icon>mdi-email</v-icon>
    </v-btn>

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
        text: 'Hier steht der Aufgabentext',
        src: 'img/image3.jpg',
        owner: 'S3',
        color: 'green darken-2',
        dialog: false
      },
      {
        text: 'Hier steht der Aufgabentext',
        src: null,
        owner: null,
        color: '#CCDD12',
        dialog: false
      },
      {
        text: 'Hier steht der Aufgabentext',
        src: null,
        owner: null,
        color: '#CCDD12',
        dialog: false
      },
      {
        text: 'Hier steht der Aufgabentext',
        src: null,
        owner: null,
        color: '#CCDD12',
        dialog: false
      },
      {
        text: 'Hier steht der Aufgabentext',
        src: null,
        owner: null,
        color: '#CCDD12',
        dialog: false
      },
      {
        text: 'Hier steht der Aufgabentext',
        src: null,
        owner: null,
        color: '#CCDD12',
        dialog: false
      },
      {
        text: 'Hier steht der Aufgabentext',
        src: null,
        owner: null,
        color: '#CCDD12',
        dialog: false
      },
      {
        text: 'Hier steht der Aufgabentext',
        src: 'img/image3.jpg',
        owner: 'S3',
        color: 'green darken-2',
        dialog: false
      },
      {
        text: 'Hier steht der Aufgabentext',
        src: null,
        owner: null,
        color: '#CCDD12',
        dialog: false
      },
      {
        text: 'Hier steht der Aufgabentext',
        src: null,
        owner: null,
        color: '#CCDD12',
        dialog: false
      },
      {
        text: 'Hier steht der Aufgabentext',
        src: 'img/image1.jpg',
        owner: 'S1',
        color: 'red lighten-2',
        dialog: false
      },
      {
        text: 'Hier steht der Aufgabentext',
        src: null,
        owner: null,
        color: '#CCDD12',
        dialog: false
      },
      {
        text: 'Hier steht der Aufgabentext',
        src: null,
        owner: null,
        color: '#CCDD12',
        dialog: false
      },
      {
        text: 'Hier steht der Aufgabentext',
        src: null,
        owner: null,
        color: '#CCDD12',
        dialog: false
      },
      {
        text: 'Hier steht der Aufgabentext',
        src: 'img/image1.jpg',
        owner: 'S4',
        color: 'amber lighten-2',
        dialog: false
      },
      {
        text: 'Hier steht der Aufgabentext',
        src: null,
        owner: null,
        color: '#CCDD12',
        dialog: false
      },
      {
        text: 'Hier steht der Aufgabentext',
        src: 'img/image1.jpg',
        owner: 'S1',
        color: 'red lighten-2',
        dialog: false
      },
      {
        text: 'Hier steht der Aufgabentext',
        src: null,
        owner: null,
        color: '#CCDD12',
        dialog: false
      },
      {
        text: 'Hier steht der Aufgabentext',
        src: null,
        owner: null,
        color: '#CCDD12',
        dialog: false
      },
      {
        text: 'Hier steht der Aufgabentext',
        src: null,
        owner: null,
        color: '#CCDD12',
        dialog: false
      },
      {
        text: 'Hier steht der Aufgabentext',
        src: null,
        owner: null,
        color: '#CCDD12',
        dialog: false
      },
      {
        text: 'Hier steht der Aufgabentext',
        src: null,
        owner: null,
        color: '#CCDD12',
        dialog: false
      },
      {
        text: 'Hier steht der Aufgabentext',
        src: null,
        owner: null,
        color: '#CCDD12',
        dialog: false
      },
      {
        text: 'Hier steht der Aufgabentext',
        src: null,
        owner: null,
        color: '#CCDD12',
        dialog: false
      },
      {
        text: 'Hier steht der Aufgabentext',
        src: null,
        owner: null,
        color: '#CCDD12',
        dialog: false
      },
      {
        text: 'Hier steht der Aufgabentext',
        src: null,
        owner: null,
        color: '#CCDD12',
        dialog: false
      },
      {
        text: 'Hier steht der Aufgabentext',
        src: 'img/image2.jpg',
        owner: 'S2',
        color: 'blue lighten-1',
        dialog: false
      },
      {
        text: 'Hier steht der Aufgabentext',
        src: 'img/image2.jpg',
        owner: 'S2',
        color: 'blue lighten-1',
        dialog: false
      },
      {
        text: 'Hier steht der Aufgabentext',
        src: 'img/image2.jpg',
        owner: 'S2',
        color: 'blue lighten-1',
        dialog: false
      },
      {
        text: 'Hier steht der Aufgabentext',
        src: null,
        owner: null,
        color: '#CCDD12',
        dialog: false
      },
      {
        text: 'Hier steht der Aufgabentext',
        src: null,
        owner: null,
        color: '#CCDD12',
        dialog: false
      },
      {
        text: 'Hier steht der Aufgabentext',
        src: null,
        owner: null,
        color: '#CCDD12',
        dialog: false
      },
      {
        text: 'Hier steht der Aufgabentext',
        src: null,
        owner: null,
        color: '#CCDD12',
        dialog: false
      },
      {
        text: 'Hier steht der Aufgabentext',
        src: null,
        owner: null,
        color: '#CCDD12',
        dialog: false
      },
      {
        text: 'Hier steht der Aufgabentext',
        src: null,
        owner: null,
        color: '#CCDD12',
        dialog: false
      },
      {
        text: 'Hier steht der Aufgabentext',
        src: null,
        owner: null,
        color: '#CCDD12',
        dialog: false
      },
    ]
  }),
  methods: {
    isDone(n) {
      return this.tasks[n-1].src !== null
    },
    sendEmail(n) {
      this.tasks[n-1].dialog = false
      window.open('mailto:'+this.email+'?subject=Lösung für Nr. '+n)    
    },
    sendFeedback() {
      window.open('mailto:'+this.email+'?subject=Feedback')    
    },
    setColor(n) {
      return (this.tasks[n-1].src === null) ? 'brown lighten-4' : this.tasks[n-1].color
    },
    createPreview(n) {
      switch (this.$vuetify.breakpoint.name) {
        case 'xs': return "🤔"
        case 'sm': return this.tasks[n-1].text.substring(0, 22) + "..."
        case 'md': return this.tasks[n-1].text.substring(0, 32) + "..."
        case 'lg': return this.tasks[n-1].text.substring(0, 47) + "..."
        case 'xl': return this.tasks[n-1].text.substring(0, 127)
      }        
      return this.tasks[n-1].text
    }
  },
}
</script>