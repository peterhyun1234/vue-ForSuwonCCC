<template>
  <v-app id="inspire">
    <v-container grid-list-xl fluid>
      <v-layout row wrap
        class="mx-0">
        <v-flex xs12 px-0>
          <v-img 
            src="https://i.imgur.com/P9eD47N.png" 
            aspect-ratio="1.14"
            max-height="700"
            contain
          ></v-img>
        </v-flex>

        <v-card
          class="pa-4 ma-3"
          outlined
        >
          <v-layout 
            row
            align-center 
            justify-center
          >
            <v-flex xs12 sm6 md4>
              <iframe 
                width="560" height="200" 
                src="https://www.youtube.com/embed/kbs37nqO7G4" 
                frameborder="0"
                allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" 
                allowfullscreen
                style="width: 100%; margin-left:auto; margin-right:auto;"
              ></iframe>
            </v-flex>
            
            <v-flex xs12 sm6 md4>
              <p>CCC 정보</p>
              <p>Paint your app to life in milliseconds with Stateful Hot Reload. Use a rich set of fully-customizable widgets to build native interfaces in minutes.</p>
            </v-flex>
          </v-layout>
        </v-card>

        <v-card
          class="pa-4 ma-3"
          outlined
        >
          <v-layout 
            row
            align-center 
            justify-center
          >
            <v-flex xs12 sm6 md6>
              <v-card
                elevation="10"
                max-width="300"
                class="mx-auto"
              >
                <v-carousel
                  :continuous="true"
                  :cycle="true"
                  :show-arrows-on-hover="true"
                  hide-delimiter-background
                  delimiter-icon="mdi-minus"
                  height="245"
                >
                <v-carousel-item
                  v-for="(item,i) in bridgeItems"
                  :key="i"
                  :src="item.src"
                ></v-carousel-item>
                </v-carousel>
              </v-card>
            </v-flex>
            <v-flex xs12 sm6 md6>
              <p>브릿지 카드</p>
                질문을 통해 서로를 알아가도록 돕는 카드입니다.
                처음 만난 사람과 대화를 이어가기 어려워하는 
                요즘 세대들이 일상의 소소한 질문부터 깊은 영적인 
                대화까지 나눌 수 있도록 만들어줍니다.
                각기 다른 49장의 질문카드+ 설명서 1장으로 
                구성되어 있습니다.
            </v-flex>
          </v-layout>
        </v-card>

        <v-card
          class="pa-4 ma-3"
          outlined
        >
          <v-layout 
            row
            align-center 
            justify-center
          >
            <v-flex xs12 sm6 md6>
              <p>사랑의 언어 테스트</p>
              <p>Paint your app to life in milliseconds with Stateful Hot Reload. Use a rich set of fully-customizable widgets to build native interfaces in minutes.</p>
            </v-flex>
            <v-flex xs12 sm6 md6>
              <v-card
                elevation="10"
                max-width="300"
                class="mx-auto"
              >
                <v-carousel
                  :continuous="true"
                  :cycle="true"
                  :show-arrows-on-hover="true"
                  hide-delimiter-background
                  delimiter-icon="mdi-minus"
                  height="245"
                >
                <v-carousel-item
                  v-for="(item,i) in bridgeItems"
                  :key="i"
                  :src="item.src"
                ></v-carousel-item>
                </v-carousel>
              </v-card>
            </v-flex>
          </v-layout>
        </v-card>

        <v-card
          class="pa-4 ma-3"
          outlined
        >
          <v-layout 
            row
            align-center 
            justify-center
          >
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

        <v-card
          class="pa-4 mt-3 mx-3 mb-8"
          outlined
        >
          <v-layout 
            row
          >
            
            <v-flex
              xs12 sm6 md4
              v-for="(item,i) in otherAppsItems"
              :key="i"
            >
              <v-card>

                <v-list-item three-line>

                  <v-list-item-avatar
                    class="ma-1 pa-0"
                    size="80"
                    tile
                  >
                   <v-img :src="item.src"></v-img> 
                  </v-list-item-avatar>

                  <v-list-item-content>
                    <v-list-item-title class=" mb-1">{{item.title}}</v-list-item-title>

                    <v-list-item-subtitle v-if="item.android">
                      <v-btn 
                        icon 
                        :href="item.android"
                      >
                        <v-icon>mdi-android</v-icon>
                      </v-btn>
                      <v-btn 
                        icon 
                        :href="item.ios"
                      >
                        <v-icon>mdi-apple</v-icon>
                      </v-btn>

                    </v-list-item-subtitle>
                    
                    <v-list-item-subtitle v-else>
                      <v-btn 
                        icon 
                        :href="item.href"
                      >
                        <v-icon>mdi-instagram</v-icon>
                        바로가기
                      </v-btn>

                    </v-list-item-subtitle>
                  </v-list-item-content>

                </v-list-item>

              </v-card>
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
      bridgeItems: [
        {
          src: 'https://i.imgur.com/V0Pggmc.png',
        },
        {
          src: 'https://i.imgur.com/4pgyWuV.png',
        },
        {
          src: 'https://i.imgur.com/XjOcZDE.png',
        },        
        {
          src: 'https://i.imgur.com/O7qf6ZY.png',
        },
        {
          src: 'https://i.imgur.com/slW2DVU.png',
        },
      ],
      otherAppsItems: [
        {
          src: 'https://i.imgur.com/lQFjIgH.png', 
          title: "순장노트 다운로드", 
          android: "https://play.google.com/store/apps/details?id=org.kccc.sj", 
          ios: "itms-services://?action=download-manifest&url=https://dl.dropboxusercontent.com/s/ylream78zwpf0qa/soonjang_note.plist",
        },
        {
          src: 'https://i.imgur.com/3KpYGE0.png', 
          title: "Gateway 다운로드", 
          android: "https://play.google.com/store/apps/details?id=org.kccc.gateway", 
          ios: "https://itunes.apple.com/kr/app/gateway/id1164352459?mt=8", 
        },
        {
          src: 'https://i.imgur.com/78KTHI1.png', 
          title: "아주대CCC 인스타그램", 
          href: "https://www.instagram.com/ajou_ccc/", 
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

