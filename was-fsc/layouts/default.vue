<template>
  <div>
      <v-app id="inspire">
      <v-navigation-drawer app v-model="navdrawer">
        <v-list-item>
          <v-list-item-content>
            <v-list-item-title class="title">
              아주대 CCC
              <v-btn icon to="/">
                <v-icon>mdi-home</v-icon>
              </v-btn>
            </v-list-item-title>
          </v-list-item-content>
        </v-list-item>
  
        <v-divider></v-divider>
  
        <v-list
          dense
          nav
        >
          <v-list-item
            v-for="item in items"
            :key="item.title"
            :to="item.to"
          >
            <v-list-item-icon>
              <v-icon>{{ item.icon }}</v-icon>
            </v-list-item-icon>
  
            <v-list-item-content>
              <v-list-item-title>{{ item.title }}</v-list-item-title>
            </v-list-item-content>
          </v-list-item>
        </v-list>
      </v-navigation-drawer>

      <v-app-bar
        color="#0091EA"
        dense
        dark
        collapse-on-scroll
      >
        <v-app-bar-nav-icon @click="navdrawer = !navdrawer"></v-app-bar-nav-icon>

        <v-toolbar-title>아주대 CCC</v-toolbar-title>
  
        <v-spacer></v-spacer>
  
        <v-btn icon to="/donation">
          <v-icon>mdi-heart</v-icon>
        </v-btn>
  
        <v-btn icon to="/sendMessage">
          <v-icon>mdi-email-send-outline</v-icon>
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
<div>
  <nuxt/>
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
  </div>
</template>

<script>

export default {
  components: {
  },
  data () {
    return {
      navdrawer: false,
      items: [
        { title: '브릿지 카드', icon: 'mdi-bridge', to: '/bridge'},
        { title: '아주대 기도제목', icon: 'mdi-sprout' , to: '/bridge'},
        { title: '개인 기도제목', icon: 'mdi-sprout-outline' , to: '/bridge'},
        { title: '대표단에게 건의', icon: 'mdi-email-send-outline', to: '/bridge'},
        { title: '간사님에게 건의', icon: 'mdi-email-send', to: '/bridge'},
        { title: 'About', icon: 'mdi-help-box', to: '/bridge'},
      ],
    }
  },
}
</script>

<style>
html {
  font-family: "Source Sans Pro", -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, "Helvetica Neue", Arial, sans-serif;
  font-size: 16px;
  word-spacing: 1px;
  -ms-text-size-adjust: 100%;
  -webkit-text-size-adjust: 100%;
  -moz-osx-font-smoothing: grayscale;
  -webkit-font-smoothing: antialiased;
  box-sizing: border-box;
}

*, *:before, *:after {
  box-sizing: border-box;
  margin: 0;
}

.button--green {
  display: inline-block;
  border-radius: 4px;
  border: 1px solid #3b8070;
  color: #3b8070;
  text-decoration: none;
  padding: 10px 30px;
}

.button--green:hover {
  color: #fff;
  background-color: #3b8070;
}

.button--grey {
  display: inline-block;
  border-radius: 4px;
  border: 1px solid #35495e;
  color: #35495e;
  text-decoration: none;
  padding: 10px 30px;
  margin-left: 15px;
}

.button--grey:hover {
  color: #fff;
  background-color: #35495e;
}
</style>

