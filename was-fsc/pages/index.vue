<template>
  <v-app id="inspire">
    <div>
      <v-app-bar
        color="deep-purple accent-4"
        dense
        dark
        hide-on-scroll
        collapse-on-scroll
      >
        <v-app-bar-nav-icon></v-app-bar-nav-icon>
  
        <v-toolbar-title>Page title</v-toolbar-title>
  
        <v-spacer></v-spacer>
  
        <v-btn icon>
          <v-icon>mdi-heart</v-icon>
        </v-btn>
  
        <v-btn icon>
          <v-icon>mdi-magnify</v-icon>
        </v-btn>
  
        <v-menu
          left
          bottom
        >
          <template v-slot:activator="{ on }">
            <v-btn icon v-on="on">
              <v-icon>mdi-dots-vertical</v-icon>
            </v-btn>
          </template>
  
          <v-list>
            <v-list-item
              v-for="n in 5"
              :key="n"
              @click="() => {}"
            >
              <v-list-item-title>Option {{ n }}</v-list-item-title>
            </v-list-item>
          </v-list>
        </v-menu>
      </v-app-bar>
    </div>
    <div>
      <v-container fluid class="pa-0">
      <v-row align="center">
        <v-col cols="12" sm="6">
          <div class="text-center">
            <div class="my-2">
              <v-btn x-small color="secondary" dark>Extra small Button</v-btn>
            </div>
            <div class="my-2">
              <v-btn small color="primary" dark>Small Button</v-btn>
            </div>
            <div class="my-2">
              <v-btn color="warning" dark>Normal Button</v-btn>
            </div>
            <div class="my-2">
              <v-btn color="error" dark large>Large Button</v-btn>
            </div>
            <div class="my-2">
              <v-btn x-large color="success" dark>Extra large Button</v-btn>
            </div>
          </div>
        </v-col>
        <v-col cols="12" sm="6">
          <div class="text-center">
            <div class="my-2">
              <v-btn color="secondary" fab x-small dark>
                <v-icon>mdi-television</v-icon>
              </v-btn>
            </div>
            <div class="my-2">
              <v-btn color="primary" fab small dark>
                <v-icon>mdi-pencil</v-icon>
              </v-btn>
            </div>
            <div class="my-2">
              <v-btn color="warning" fab dark>
                <v-icon>mdi-account-circle</v-icon>
              </v-btn>
            </div>
            <div class="my-2">
              <v-btn color="error" fab large dark>
                <v-icon>mdi-alarm</v-icon>
              </v-btn>
            </div>
            <div class="my-2">
              <v-btn color="success" fab x-large dark>
                <v-icon>mdi-domain</v-icon>
              </v-btn>
            </div>
          </div>
        </v-col>
      </v-row>
    </v-container>
    </div>
    <div>
      <v-footer
    dark
    padless
  >
    <v-card
      flat
      tile
      class="indigo lighten-1 white--text text-center"
    >
      <v-card-text>
        <v-btn
          v-for="icon in icons"
          :key="icon"
          class="mx-4 white--text"
          icon
        >
          <v-icon size="24px">{{ icon }}</v-icon>
        </v-btn>
      </v-card-text>

      <v-card-text class="white--text pt-0">
        Phasellus feugiat arcu sapien, et iaculis ipsum elementum sit amet. Mauris cursus commodo interdum. Praesent ut risus eget metus luctus accumsan id ultrices nunc. Sed at orci sed massa consectetur dignissim a sit amet dui. Duis commodo vitae velit et faucibus. Morbi vehicula lacinia malesuada. Nulla placerat augue vel ipsum ultrices, cursus iaculis dui sollicitudin. Vestibulum eu ipsum vel diam elementum tempor vel ut orci. Orci varius natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus.
      </v-card-text>

      <v-divider></v-divider>

      <v-card-text class="white--text">
        {{ new Date().getFullYear() }} — <strong>Vuetify</strong>
      </v-card-text>
    </v-card>
  </v-footer>
    </div>
  </v-app>
  </template>

<script>

export default {
  components: {
  }
}
</script>

<style>
.container {
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
}
</style>

