<template>
  <v-container class="px-auto">  
    <v-expansion-panels accordion>
      <v-expansion-panel class="amber lighten-5">
        <v-expansion-panel-header>
          Konzept / Idee
        </v-expansion-panel-header>
        <v-expansion-panel-content>
          Eine Komination aus Bingo / Vier Gewinnt und Schnitzeljagd als kompetetives Echtzeitspiel im "Real Life"
        </v-expansion-panel-content>
      </v-expansion-panel>
      <v-expansion-panel class="amber lighten-5">
        <v-expansion-panel-header>
          Ziel
        </v-expansion-panel-header>
        <v-expansion-panel-content>
          Als erster Spieler 4 Felder in horizontaler / vertikaler / diagonaler Reihe für sich zu gewinnen
        </v-expansion-panel-content>
      </v-expansion-panel>
      <v-expansion-panel class="amber lighten-5">
        <v-expansion-panel-header>
          Übersicht
        </v-expansion-panel-header>
        <v-expansion-panel-content class="text-justify">
          Auf einem Spielfeld sind 36 Felder quadratisch angeordnet (6x6 Felder).
          Jedes Feld beinhaltet eine Aufgabe.<br>Die Aufgaben sind in Form einer "Mini-Schnitzeljagd",
          so dass der Spieler einen bestimmten Ort finden oder ein bestimmtes Ereignis festhalten muss.<br>
          Um diese Aufgabe erfolgreich zu erfüllen, müssen die Spieler ein Foto der Lösung einsenden.
          Ist die Lösung korrekt, gewinnt der Spieler das entsprechende Feld.<br>Sobald ein Spieler 4 Felder
          in vertikaler, horizontaler oder diagonaler Reihe für sich entscheiden kann, gewinnt dieser Spieler.
        </v-expansion-panel-content>
      </v-expansion-panel>
      <v-expansion-panel class="amber lighten-5">
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
      <v-expansion-panel class="amber lighten-5">
        <v-expansion-panel-header>
          Hinweise zu den Aufgaben
        </v-expansion-panel-header>
        <v-expansion-panel-content class="text-justify">
          Die Aufgaben sind so gestaltet, dass sie sich zwar einfach und machbar anhören aber die Lösung ist nicht immer einfach zu finden.
          Das Spiel ist auch darauf ausgelegt, dass es über einen längeren Zeitraum (mehrere Wochen) andauert.
          Um ein Foto eindeutig einem Spieler zuordnen zu können ist es wichtig, dass der Spieler selbst auf dem Foto zu sehen ist. 
        </v-expansion-panel-content>
      </v-expansion-panel>
    </v-expansion-panels>
  </v-container>
</template>

<script>
export default {
  
  }
</script>