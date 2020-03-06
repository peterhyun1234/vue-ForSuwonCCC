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
        color="blue"
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
          <v-layout row wrap >
            <v-flex xs12 class="text-center">
              <v-card
                color="#3d3d3d"
                flat
                >

                <v-card-text>
                  <v-btn
                    v-for="f_item in footerItems"
                    :key="f_item.icon"
                    :href="f_item.href"
                    class="mx-3 white--text"
                  >
                    <v-icon size="24px">{{ f_item.icon }}</v-icon>
                  </v-btn>
                </v-card-text>
                <v-card-text class="white--text pt-0">
                  <p>평소에 제가 아주대에서 CCC활동을 하면서 불편했던 부분들을 해소하고 싶다는 마음으로 개발하게 됐습니다.</p>
                  <p>
                    <span>개인적으로 공부하면서 만든 웹페이지라서 부족한 부분이 많이 있습니다. 개선해야 할 부분이나 추가적으로 필요한 기능이 있다면 </span>
                    <a href="/about" style="text-decoration:none">
                      <strong>
                        <span style="color: #919191;">개발자에게 건의사항</span>
                      </strong>
                    </a>
                    <span>기능을 이용해주세요!</span>
                  </p>
                  <p>
                    <span>소스코드는 제 </span>
                    <a href="https://github.com/peterhyun1234/vue-ForSuwonCCC" style="text-decoration:none">
                      <strong>
                        <span style="color: #919191;">Github repository</span>
                      </strong>
                    </a>
                    <span>에 올려뒀고, 개발 관련 지식이나 도움이 필요하신 분들은 제 이메일로 연락주길 바랍니다 :D</span>
                  </p>
                </v-card-text>

                <v-divider></v-divider>

                <v-card-text class="white--text">
                  <p style="font-size: large;">
                      <span>Released under </span>
                      <a href="https://opensource.org/licenses/MIT" style="text-decoration:none">
                        <strong><span style="color: #919191;">MIT License</span></strong>
                      </a>
                  </p>
                  <p style="font-size: large;">
                      <span>Server support from </span>
                      <a href="https://www.netlify.com/" style="text-decoration:none">
                        <strong><span style="color: #919191;">Netlify</span></strong>
                      </a>
                  </p>
                </v-card-text>
              </v-card>
            </v-flex>
          </v-layout>
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
      footerItems: [
        { icon: 'mdi-instagram', href: 'https://www.instagram.com/suwon_ccc/'},
        { icon: 'mdi-github-circle' , href: 'https://github.com/peterhyun1234/vue-ForSuwonCCC'},
        { icon: 'mdi-medium', href: 'https://medium.com/@peterhyun1234'},
        { icon: 'mdi-book-information-variant', href: 'https://ajouccc.netlify.com/about'},
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

