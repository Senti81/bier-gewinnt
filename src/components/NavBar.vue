<template>
  <div>
    <v-app-bar
      color="amber darken-2"
      dense
      dark
    >
    <v-toolbar-title>Bier Gewinnt</v-toolbar-title>
    <v-spacer></v-spacer>
    <v-dialog
      v-model="dialog"
      width="500"
    >
      <template v-slot:activator="{on, attrs }">
        <v-btn 
          class="mx-auto transparent"      
          v-bind="attrs"
          v-on="on"
          >          
          <v-icon class="pr-2">mdi-cards</v-icon>
          Regeln
        </v-btn>
      </template>

      <!-- Dialog -->
      <v-card>
        <v-container class="px-auto">
            <v-expansion-panels accordion>
              <v-expansion-panel>
                <v-expansion-panel-header>
                  Konzept / Idee
                </v-expansion-panel-header>
                <v-expansion-panel-content>
                  Eine Komination aus Bingo / Vier Gewinnt und Schnitzeljagd / Foto Rallye als kompetetives Echtzeitspiel im "Real Life"
                </v-expansion-panel-content>
              </v-expansion-panel>
              <v-expansion-panel>
                <v-expansion-panel-header>
                  Ziel
                </v-expansion-panel-header>
                <v-expansion-panel-content>
                  Als erster Spieler 4 Felder in horizontaler / vertikaler / diagonaler Reihe für sich zu gewinnen
                </v-expansion-panel-content>
              </v-expansion-panel>   
              <v-expansion-panel>
                <v-expansion-panel-header>
                  Spielablauf          
                </v-expansion-panel-header>
                <v-expansion-panel-content class="text-justify">
                  Man sucht sich irgendein Feld aus, das man für sich beanspruchen möchte. Mit einem Klick auf das Feld,
                  öffnet sich eine Dialogbox und liest sich die Aufgabe gut durch. Durch den Button "Zurück" oder Klick
                  auf einen Bereich ausserhalb des Dialogfeldes gelangt man wieder zur Übersicht<br>
                  Sobald die Aufgabe erfüllt wurde, klick man erneut auf das Feld und drückt den Button "Einsenden".<br>
                  Danach öffnet sich das Standard-Mail-Programm und das Foto kann als Dateianhang versenden werden.
                  Email-Adresse des Empfängers, sowie der Betreff sind schon vorgegeben und müssen nicht angepasst werden.<br>
                  Ist die Lösung korrekt, so wird das Feld mit den Initialen des Spielers markiert und einer entsprechenden Farbe
                  zugeordnet (diese kann man sich gerne auch aussuchen)<br>
                  Dieses Feld ist nun dem entsprechenden Spieler zugeordnet und kann von anderen Spielern nicht mehr beansprucht werden
                </v-expansion-panel-content>
              </v-expansion-panel>

              <!-- RULES -->
              <v-expansion-panel>
                <v-expansion-panel-header>
                  Hinweise
                </v-expansion-panel-header>
                <v-expansion-panel-content class="text-left">
                  <v-list-item>
                    <v-list-item-content>
                      Die Aufgaben sind grundsätzlich an öffentlichen, frei zugänglichen Orten erfüllen.<br>
                      <b>Ausnahme:</b>
                      Ist in der Titelleiste der Aufgabe dieses Symbol angegeben: 🏠 darf die Aufgabe auch von zu Hause aus erfüllt werden.
                    </v-list-item-content>
                  </v-list-item>
                  <v-list-item>
                    <v-list-item-content>
                      Steht bei Aufgaben 'Bier [...] der entsprechenden Farbe', bezieht sich dies immer auf die Farbe des Logos, bzw. Etikettes.
                      Bespiel: rot = Reissdorf, weiß = Früh, blau = Gaffel, grün = Gilden, usw.
                    </v-list-item-content>
                  </v-list-item>
                </v-expansion-panel-content>
              </v-expansion-panel>
             
            </v-expansion-panels>  
            <v-card-actions>
          <v-spacer></v-spacer>
          <v-btn color="blue darken-1" text @click="dialog = false">
            Schliessen
          </v-btn>
        </v-card-actions>
        </v-container>
      </v-card>
    </v-dialog>
    </v-app-bar>    
  </div>
</template>

<script>
  export default {
    data () {
      return {
        dialog: false,
      }
    },
    methods: {
      sendFeedback() {
        window.open('mailto:biergewinnt0@gmail.com?subject=Feedback')    
      },
    }
  }
</script>