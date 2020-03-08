<template>
  <v-app id="inspire">
    <v-container grid-list-xl>
      <v-layout row wrap
        class="mx-0">
        <v-flex xs12>
          <v-img src="https://i.imgur.com/ChYZWha.png" aspect-ratio="1.14"></v-img>
        </v-flex>

        <v-flex xs12>
          <v-card
            elevation="10"
            max-width="444"
            class="mx-auto"
          >
            <v-carousel
              :continuous="true"
              :cycle="true"
              :show-arrows="false"
              hide-delimiter-background
              delimiter-icon="mdi-minus"
              height="300"
            >
            <v-carousel-item
              v-for="(item,i) in items"
              :key="i"
              :src="item.src"
            ></v-carousel-item>
            </v-carousel>
            <v-list two-line>
              <v-list-item>
                <v-list-item-content class="ma-0 pa-0">
                  <v-list-item-title>
                    <v-chip
                      class="ma-0"
                      color="green"
                      outlined
                      pill
                      
                    >
                      브릿지 설명
                      <v-icon right>mdi-folder-information-outline</v-icon>
                    </v-chip>
                  </v-list-item-title>
                </v-list-item-content>
                <v-list-item-content class="ma-0 pa-0">
                  <v-list-item-title>
                    <v-chip
                      class="ma-0"
                      color="primary"
                      outlined
                      pill
                    >
                      브릿지 시작
                      <v-icon right>mdi-clock-start</v-icon>
                    </v-chip>
                  </v-list-item-title>
                </v-list-item-content>
              </v-list-item>
            </v-list>
          </v-card>
        </v-flex>
        
        <v-flex xs12>
          <v-card
            elevation="10"
            max-width="444"
            class="mx-auto"
          >
            <v-carousel
              :continuous="true"
              :cycle="true"
              :show-arrows="false"
              hide-delimiter-background
              delimiter-icon="mdi-minus"
              height="300"
            >
            <v-carousel-item
              v-for="(item,i) in items"
              :key="i"
              :src="item.src"
            ></v-carousel-item>
            </v-carousel>
            <v-list two-line>
              <v-list-item>
                <v-list-item-content class="ma-0 pa-0">
                  <v-list-item-title>
                    <v-chip
                      class="ma-0"
                      color="green"
                      outlined
                      pill
                    >
                      사랑의 언어란?
                      <v-icon right>mdi-folder-information-outline</v-icon>
                    </v-chip>
                  </v-list-item-title>
                </v-list-item-content>
                <v-list-item-content class="ma-0 pa-0">
                  <v-list-item-title>
                    <v-chip
                      class="ma-0"
                      color="primary"
                      outlined
                      pill
                    >
                      테스트 시작
                      <v-icon right>mdi-clock-start</v-icon>
                    </v-chip>
                  </v-list-item-title>
                </v-list-item-content>
              </v-list-item>
            </v-list>
          </v-card>
        </v-flex>

        <v-card
          class="pa-4 ma-3"
          outlined
        >
          <v-layout row>
            <v-flex xs12 sm6 md4>
              <p>CCC 정보</p>
              <p>Paint your app to life in milliseconds with Stateful Hot Reload. Use a rich set of fully-customizable widgets to build native interfaces in minutes.</p>
            </v-flex>
            <v-flex xs12 sm6 md4>
              <p>기도제목 공유</p>
              <p>Quickly ship features with a focus on native end-user experiences. Layered architecture allows for full customization, which results in incredibly fast rendering and expressive and flexible designs.</p>
            </v-flex>
            <v-flex xs12 sm6 md4>
              <p>캠퍼스 리더십에게 건의</p>
              <p>Flutter’s widgets incorporate all critical platform differences such as scrolling, navigation, icons and fonts, and your Flutter code is compiled to native ARM machine code using Dart's native compilers. Thus Flutter gives you full native performance on both iOS and Android.</p>
            </v-flex>
          </v-layout>
        </v-card>
      </v-layout>
    </v-container>
  </v-app>
</template>

<script>

export default {
  components: {
  },
  data () {
    return {
      colors: [
        'green',
        'secondary',
        'yellow darken-4',
        'red lighten-2',
        'orange darken-1',
      ],
      items: [
        {
          src: 'https://i.imgur.com/LHiaee2.png',
        },
        {
          src: 'https://i.imgur.com/8j4BggT.png',
        },
        {
          src: 'https://i.imgur.com/JK52Rzi.png',
        },        
        {
          src: 'https://i.imgur.com/k8YmRbZ.png',
        },
        {
          src: 'https://i.imgur.com/NdaiuTo.png',
        },
      ],
    }
  },
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

