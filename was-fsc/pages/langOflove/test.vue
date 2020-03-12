

<template>
  <v-app id="inspire">
    <v-container class="grey lighten-5">
      <v-row>
        <v-col>
          <v-card>
            One of two columns
          </v-card>
        </v-col>
        <v-col>
          <v-card>
            One of two columns
          </v-card>
        </v-col>
        <v-col>
          <v-card>
            One of two columns
          </v-card>
        </v-col>
      </v-row>
      <v-row>
        <v-col>
          <v-card>
            One of two columns
          </v-card>
        </v-col>
        <v-col>
          <v-card>
            One of two columns
          </v-card>
        </v-col>
        <v-col>
          <v-card>
            One of two columns
          </v-card>
        </v-col>
      </v-row>
      <v-row>
        <v-col
          v-for="n in 3"
          :key="n"
          cols="sm"
        >
          <v-card
            class="pa-2"
            outlined
            tile
          >
            col
          </v-card>
        </v-col>
      </v-row>
    </v-container>
  </v-app>
</template>


<script>

export default {
  components: {
  },
  data () {
    return {
    }
  },
}
</script>

