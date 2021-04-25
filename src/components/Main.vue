<template>
  <v-container class="pa-auto" height="500">
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
              <v-card-title v-if="tasks[n-1].home">
                🏠
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
              <v-card-text class="pa-5">
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
                  Lösung einsenden
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
        text: 'Öffentliche Uhr, die 15:16 Uhr anzeigt',
        src: null,
        owner: null,
        color: '#CCDD12',
        dialog: false
      },
      {
        text: 'Finde eine Hausnummer mit einer Schnapszahl (3-stellig)',
        src: 'img/IMG_20210423_204731652.jpg',
        owner: 'AW',
        color: '#42A5F5',
        dialog: false
      },
      {
        text: 'Uhr, die 23:04 Uhr anzeigt',
        src: 'img/20210424_230403.jpg',
        owner: 'DR',
        color: '#CCDD12',
        dialog: false
      },
      {
        text: 'Trinke ein Bier vor einem Verkehrsschild der entsprechenden Farbe',
        src: null,
        owner: null,
        color: '#CCDD12',
        dialog: false
      },
      {
        home: true,
        text: 'Leere Bierflaschen in 3 unterschiedlichen Farben',
        src: null,
        owner: null,
        color: '#CCDD12',
        dialog: false
      },
      {
        text: 'Craft Bier mit Hopfensorte: Simcoe',
        src: 'img/IMG_20210423_154328.JPG',
        owner: 'KG',
        color: '#FFCD13',
        dialog: false
      },
      {
        home: true,
        text: 'Bierdeckel von 5 unterschiedlichen Biersorten',
        src: 'img/IMG_20210423_203631686.jpg',
        owner: 'AW',
        color: '#42A5F5',
        dialog: false
      },
      {
        home: true,
        text: 'Platziere 15 Kronkorken auf 16 Bierdeckel',
        src: null,
        owner: null,
        color: '#CCDD12',
        dialog: false
      },
      {
        text: 'Speisekarte (Aushang) wo ein 0,2er Kölsch 1,60 € oder weniger kostet',
        src: null,
        owner: null,
        color: '#CCDD12',
        dialog: false
      },      
      {
        text: 'Bier mit IBU > 50',
        src: null,
        owner: null,
        color: '#CCDD12',
        dialog: false
      },
      {
        text: 'Craft Biere mit Köln im Namen',
        src: null,
        owner: null,
        color: '#CCDD12',
        dialog: false
      },
      {
        text: 'Trinke ein Bier, das mit dem gleichen Buchstaben beginnt wie der aktuelle Wochentag',
        src: 'img/20210423_162140.jpg',
        owner: 'NR',
        color: '#BA68C8',
        dialog: false
      },
      {
        text: 'Genieße ein Bier im Freien auf einer gestifteten Parkbank',
        src: null,
        owner: null,
        color: '#CCDD12',
        dialog: false
      },
      {
        home: true,
        text: 'Besitze 5 Bierflaschen in unterschiedlichen Formen / Größen',
        src: 'img/IMG_20210423_154725.jpg',
        owner: 'KG',
        color: '#FFCD13',
        dialog: false
      },
      {
        text: 'Trinke ein Bier in einem Einkaufswagen, der in freier Wildbahn steht',
        src: null,
        owner: null,
        color: '#CCDD12',
        dialog: false
      },
      {
        text: 'Kassenzettel mit Summe: 15,16€ oder 23,04€',
        src: null,
        owner: null,
        color: '#CCDD12',
        dialog: false
      },
      {
        text: 'Trinke vor eine Gaststätte das Bier, welches dort ausgeschenkt wird',
        src: null,
        owner: null,
        color: '#CCDD12',
        dialog: false
      },
      {
        text: 'Trinke ein Bier vor einem Zigarettenautomaten',
        src: null,
        owner: null,
        color: '#CCDD12',
        dialog: false
      },
      {
        text: 'Trinke ein Bier vor einem Hinweisschild zu Strasseneinbauten der entsprechenden Farbe',
        src: null,
        owner: null,
        color: '#CCDD12',
        dialog: false
      },
      {
        text: 'Trinke ein Radler auf dem Rad. #dontkdrinkanddrive',
        src: 'img/IMG-20210425-WA0007.jpg',
        owner: 'MG',
        color: '#C62828',
        dialog: false
      },
      {
        text: 'Stelle ein Pils neben einen Pilz (Im Wald, dort wo die Tannen zapfen 😂😂😂)',
        src: null,
        owner: null,
        color: '#CCDD12',
        dialog: false
      },
      {
        text: 'Besitze ein Bier, welches in deinem Geburtsmonat abläuft (Und nicht vergessen das Bier rechtzeitig zu trinken. Sonst: Disqualifikation wegen Bierquälerei!)',
        src: 'img/IMG_20210423_154917.jpg',
        owner: 'KG',
        color: '#FFCD13',
        dialog: false
      },
      {
        home: true,
        text: 'Baue eine Pyramide aus 10 Dosenbieren',
        src: null,
        owner: null,
        color: '#CCDD12',
        dialog: false
      },
      {
        home: true,
        text: 'Bierdeckel in 5 unterschiedlichen Formen / Größen',
        src: null,
        owner: null,
        color: '#CCDD12',
        dialog: false
      },
      {
        text: 'Trinke vor einem E-Scooter ein Bier der entsprechenden Farbe',
        src: null,
        owner: null,
        color: '#CCDD12',
        dialog: false
      },
      {
        text: 'Schreibe deine Initialen mit Kronkorken',
        src: 'img/20210423_153645.jpg',
        owner: 'DR',
        color: '#CCDD12',
        dialog: false
      },
      {
        home: true,
        text: 'Baue eine Pyramide aus Bierdeckeln (Basis 3)',
        src: 'img/IMG_20210423_211046647.jpg',
        owner: 'AW',
        color: '#42A5F5',
        dialog: false
      },
      {
        home: true,
        text: 'Balanciere 23 Kronkorken auf 4 Bierflaschen',
        src: null,
        owner: null,
        color: '#CCDD12',
        dialog: false
      },
      {
        text: 'Kfz-Kennzeichen mit einer der folgenden Zahlen: 04, 15, 16, 23, 1516 oder 2304',
        src: 'img/20210423_160210.jpg',
        owner: 'DR',
        color: '#CCDD12',
        dialog: false
      },
      {
        text: 'Bier mit dem Name eines Tieres',
        src: 'img/IMG_20210423_155145.jpg',
        owner: 'KG',
        color: '#FFCD13',
        dialog: false
      },
      {
        text: 'Craft Bier mit Hopfensorte: Citra',
        src: 'img/20210424_230651.jpg',
        owner: 'DR',
        color: '#CCDD12',
        dialog: false
      },
      {
        text: 'Trinke ein Bier unter einem Vogelhäuschen',
        src: 'img/IMG_20210423_202011_763.jpg',
        owner: 'AW',
        color: '#42A5F5',
        dialog: false
      },
      {
        text: 'Trinke ein Bier vor einem Straßenschild, das mit dem selben Buchstaben beginnt, wie der Name der Straße',
        src: null,
        owner: null,
        color: '#CCDD12',
        dialog: false
      },
      {
        text: 'Schreibe mit Steinen das Wort Bier',
        src: 'img/20210423_200034.jpg',
        owner: 'NR',
        color: '#BA68C8',
        dialog: false
      },
      {
        home: true,
        text: 'Tɿinʞɘ ɘin 𐐒iɘɿ voɿ ɘinɘm Ƨqiɘϱɘl',
        src: 'img/IMG_20210423_203020671.jpg',
        owner: 'AW',
        color: '#42A5F5',
        dialog: false
      },
      {
        text: 'Bier mit einer Abbildung eines Tieres auf dem Etikett',
        src: 'img/IMG_20210423_155257.jpg',
        owner: 'KG',
        color: '#FFCD13',
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
        case 'xs': return "🍺"
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