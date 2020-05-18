<template>
  <v-app id="inspire">
    <v-container grid-list-xl>
      <v-card
      class="mt-10"
        >
        <v-layout 
          row
          align-center 
          justify-right
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
        </v-layout>
      </v-card>
    </v-container>
  </v-app>
</template>

<script>

export default {
  components: {
  },
  data () {
    return {
      
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
    }
  },
}
</script>

