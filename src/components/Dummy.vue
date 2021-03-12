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
          <v-card class="
            ma-auto
            fill-height                  
            text-lg-h5"    
            outlined
            color="brown lighten-4"
          >
            <v-card-text class="fill-height content text-lg-h1">
              <v-icon color="blue light-1">mdi-help-circle-outline</v-icon>
            </v-card-text>
          </v-card>
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
    
  })
}
</script>