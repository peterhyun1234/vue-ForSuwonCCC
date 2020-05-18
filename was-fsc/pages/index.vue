<template>
  <v-app id="inspire">
    <v-container grid-list-xl>
      <v-layout 
        align-center 
        justify-center
        row 
        wrap
      >
        <v-flex 
          xs12 px-0 
          v-if="!windowSize.mobile">
          <v-img 
            src="https://i.imgur.com/pqKHHID.png" 
            aspect-ratio="1.77"
            max-height="700"
            contain
          ></v-img>
        </v-flex>

        <v-flex 
          xs12 px-0 
          v-else>
          <v-img 
            src="https://i.imgur.com/P9eD47N.png" 
            aspect-ratio="1.14"
            max-height="700"
            contain
          ></v-img>
        </v-flex>


        <v-card
          class="pa-4 ma-3 text-center"
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
              <v-card-text>
                <p class="headline text--primary mt-3">
                  아주대 CCC 웹페이지
                </p>
                <p class="subheading text--primary mt-3">
                  아주대 CCC에 오신 여러분을 하나님의 이름으로 축복하고, 환영합니다 :D
                  하나님은 당신을 사랑하시며 당신을 위한 놀라운 계획을 가지고 계십니다!
                </p>
                <v-btn
                  text
                  color="deep-purple accent-4"
                  href="https://www.youtube.com/user/soontvccc"
                >
                  <strong>다른 영상 보기</strong>
                </v-btn>
              </v-card-text>
            </v-flex>
          </v-layout>
        </v-card>

        <v-card
          class="pa-4 ma-3 text-left"
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
              <v-card-text>
                <v-avatar 
                  color="#FFE0B2"
                  size="50"
                  >
                  <v-icon
                    color="#FFA726"
                    > mdi-bridge</v-icon>
                </v-avatar>
                <p class="headline text--primary mt-3">
                  브릿지 카드
                </p>
                <p class="subheading text--primary mt-3">
                  질문을 통해 서로를 알아가도록 돕는 카드입니다.
                  처음 만난 사람과 대화를 이어가기 어려워하는
                  요즘 세대들이 일상의 소소한 질문부터 깊은 영적인
                  대화까지 나눌 수 있도록 만들어줍니다.
                  각기 다른 49장의 질문카드 + 설명서 1장으로
                  구성되어있습니다.
                  </p>
                <v-btn
                  text
                  color="green accent-4"
                  to="/bridge/description"
                >
                  <strong>브릿지 설명</strong>
                </v-btn>
                <v-btn
                  text
                  color="deep-purple accent-4"
                  to="/bridge/play"
                >
                  <strong>브릿지 시작</strong>
                </v-btn>
              </v-card-text>
            </v-flex>
          </v-layout>
        </v-card>

        <v-card
          class="pa-4 ma-3 text-right"
          outlined
        >
          <v-layout 
            row
            align-center 
            justify-right
          >
            <v-flex xs12 sm6 md6>
              <v-card-text>
                <v-avatar 
                  color="#FFE0B2" 
                  size="50"
                  >
                  <v-icon 
                    color="#FFA726"
                    > mdi-account-heart-outline</v-icon>
                </v-avatar>
                <p class="headline text--primary mt-3">
                  사랑의 언어
                </p>
                <p class="subheading text--primary ma-0 font-weight-bold">
                  "모든 사람은 사랑받고, 사랑하기 원하는 마음을 갖고 있다.
                  각 사람의 생김새와 성격이 다르듯 사람마다 사랑하는 방식이 다르다.
                  사랑하는 사람과의 관계를 원만하게 하기 위해서는 '사랑의 언어'를 이해해야 한다."</p>
                <p class="subheading text--primary font-weight-bold">
                  (게리 채프먼 목사, 1992)</p>
                <p class="subheading text--primary mt-3">
                  채프먼 박사가 연구한 사랑의 언어는 총 다섯 가지로 아래와 같습니다.</p>
                <p class="subheading text--primary mt-3">
                  <code>인정하는 말</code>/
                  <code>함께하는 시간</code>/
                  <code>스킨십</code>/
                  <code>봉사(헌신)</code>/
                  <code>선물</code></p>
                <v-divider>
                </v-divider>
                <v-btn
                  text
                  color="deep-purple accent-4"
                  to="/langOflove/test"
                >
                  <strong>사랑의 언어 테스트 시작</strong>
                </v-btn>
              </v-card-text>
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
          class="pa-4 ma-3 text-center"
          outlined
        >
          <v-layout 
            row
            align-center 
            justify-center
          >
            <v-flex xs12 sm6 md4>
              <v-card-text>
                <v-avatar 
                  color="#FFE0B2" 
                  size="50"
                  >
                  <v-icon 
                    color="#FFA726"
                    > mdi-folder-information-outline</v-icon>
                </v-avatar>
                <p class="headline text--primary ma-5">
                  CCC 정보
                </p>
                <p class="subheading text--primary ma-3">
                  CCC는 'Movements Everywhere'라는 비전을 가지고 
                  성령의 능력으로 사람들에게 그리스도를 전하고 믿음을 훈련시키고, 
                  이들이 다른 사람들을 전도하고 제자화 할 수 있도록 파송하여, 
                  지상 명령을 성취하도록 돕는 단체입니다.</p>
                <v-btn
                  text
                  color="deep-purple accent-4"
                  to="/info/ccc"
                >
                  <strong>더 알아보기</strong>
                </v-btn>
              </v-card-text>
              <v-divider>
              </v-divider>
            </v-flex>
            <v-flex xs12 sm6 md4>
              <v-card-text>
                <v-avatar 
                  color="#FFE0B2" 
                  size="50"
                  >
                  <v-icon 
                    color="#FFA726"
                    >mdi-sprout-outline</v-icon>
                </v-avatar>
                <p class="headline text--primary ma-5">
                  기도제목 공유
                </p>
                <p class="subheading text--primary ma-3">
                  아주대 CCC는 사랑하는 씨맨들이 가진 여러 문제들을 놓고 
                  우리의 중보자가 되어주시는 예수님의 이름으로 합심하여 기도합니다.  
                  바라기는 하나님과의 지속적인 교제로 
                  우리 씨맨들의 기도가 응답받아 우리의 삶 가운데 하나님의 살아계심이 증거되기를 소망합니다.</p>
                <v-btn
                  text
                  color="deep-purple accent-4"
                  to="/prayer"
                >
                  <strong>더 알아보기</strong>
                </v-btn>
              </v-card-text>
              <v-divider>
              </v-divider>
            </v-flex>
            <v-flex xs12 sm6 md4>
              <v-card-text>
                <v-avatar 
                  color="#FFE0B2" 
                  size="50"
                  >
                  <v-icon 
                    color="#FFA726"
                    >mdi-email-send-outline</v-icon>
                </v-avatar>
                <p class="headline text--primary ma-5">
                  리더십에게 건의
                </p>
                <p class="subheading text--primary ma-3">
                  아주대 CCC는 간사님과 리더십 순장님들의 노력만으로 부족합니다.
                  모든 아주대 씨맨들이 같은 마음으로 사역하기를 원하며
                  지속적인 피드백을 적극적으로 건의해주시기 바랍니다. 
                  그리고 신앙적인 궁금증도 익명으로도 질문하실 수 있습니다.
                </p>
                <v-btn
                  text
                  color="deep-purple accent-4"
                  to="/request"
                >
                  <strong>더 알아보기</strong>
                </v-btn>
              </v-card-text>
              <v-divider>
              </v-divider>
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

                <v-list-item 
                  three-line>

                  <v-list-item-avatar
                    class="ma-1 pa-0"
                    size="80"
                    tile
                  >
                   <v-img :src="item.src"></v-img> 
                  </v-list-item-avatar>

                  <v-list-item-content
                    class="text-center"
                  >
                    <v-list-item-title class=" mb-1">{{item.title}}</v-list-item-title>

                    <v-list-item-subtitle 
                      v-if="item.android">
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
      windowSize: {
        x: 0,
        y: 0,
        mobile: false
      },
    }
  },
  mounted () {
    this.onResize()
  },
  methods: {
    onResize () {
      this.windowSize = { x: window.innerWidth, y: window.innerHeight }
      if(window.innerWidth < 650){
        this.windowSize.mobile = true
      }
    }
  }
}
</script>
