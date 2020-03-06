<template>
  <v-app id="inspire">
    <v-container grid-list-md>
      <v-layout row wrap>
        <v-flex xs12>
          <v-card
            elevation="20"
            max-width="444"
            class="mx-auto"
          >
            <v-carousel
              :continuous="true"
              :cycle="cycle"
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
                <v-list-item-content>
                  <v-list-item-title>
                    <v-chip
                      class="ma-2"
                      color="green"
                      outlined
                      pill
                    >
                      브릿지 설명
                      <v-icon right>mdi-folder-information-outline</v-icon>
                    </v-chip>
                  </v-list-item-title>
                </v-list-item-content>
                <v-list-item-content>
                  <v-list-item-title>
                    <v-chip
                      class="ma-2"
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
            elevation="20"
            max-width="444"
            class="mx-auto"
          >
            <v-carousel
              :continuous="true"
              :cycle="cycle"
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
                <v-list-item-content>
                  <v-list-item-title>
                    <v-chip
                      class="ma-2"
                      color="green"
                      outlined
                      pill
                    >
                      브릿지 설명서 보기
                      <v-icon right>mdi-folder-information-outline</v-icon>
                    </v-chip>
                  </v-list-item-title>
                </v-list-item-content>
                <v-list-item-content>
                  <v-list-item-title>
                    <v-chip
                      class="ma-2"
                      color="primary"
                      outlined
                      pill
                    >
                      브릿지 시작하기
                      <v-icon right>mdi-clock-start</v-icon>
                    </v-chip>
                  </v-list-item-title>
                </v-list-item-content>
              </v-list-item>
            </v-list>
          </v-card>
        </v-flex>
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

