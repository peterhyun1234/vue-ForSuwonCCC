

<template>
  <v-app id="inspire">
    <v-container>
      <v-row>
        <v-col>
          <v-card>
            <v-expansion-panels 
              class="mb-6"
              v-model="panel"
              multiple
            >
<!-- 
            질문에 대해 답변하면 
            1. panel 닫기
            2. panel icon 변경
            3. 선택한 option에 하이라이트!
            4. 답변한 질문은 초록색 배경으로 바꿔주는 것도 괜찮을 듯 -->
<!-- 
            각 질문과 그 답을 담을 Array!

            결과는 Pie chart로 -->
              <v-expansion-panel
                v-for="(item,i) in 30"
                :key="i"
              >
                <v-expansion-panel-header expand-icon="mdi-menu-down">
                  질문 {{i+1}}
                  <template v-slot:actions>
                    <v-icon color="primary">$expand</v-icon>
                  </template>
                </v-expansion-panel-header>
                <v-divider></v-divider>
                <v-expansion-panel-content
                  class= "mt-5">
                  <v-radio-group v-model="questions[i]">
                    {{questions[i]}}
                    <v-radio value="opt1">
                      <template v-slot:label>
                        <div>{{questions[i].option1}}</div>
                      </template>
                    </v-radio>
                    <v-radio value="opt2">
                      <template v-slot:label>
                        <div>{{questions[i].option2}}</div>
                      </template>
                    </v-radio>
                  </v-radio-group>
                </v-expansion-panel-content>
              </v-expansion-panel>
            </v-expansion-panels>
                <!-- <div>
      <v-expansion-panels>
        <v-expansion-panel>
          <v-expansion-panel-header>
            Item
            <template v-slot:actions>
              <v-icon color="primary">$expand</v-icon>
            </template>
          </v-expansion-panel-header>
        </v-expansion-panel>
  
        <v-expansion-panel>
          <v-expansion-panel-header disable-icon-rotate>
            Item
            <template v-slot:actions>
              <v-icon color="teal">mdi-check</v-icon>
            </template>
          </v-expansion-panel-header>
          <v-expansion-panel-content>
            Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.
          </v-expansion-panel-content>
        </v-expansion-panel>
  
        <v-expansion-panel>
          <v-expansion-panel-header disable-icon-rotate>
            Item
            <template v-slot:actions>
              <v-icon color="error">mdi-alert-circle</v-icon>
            </template>
          </v-expansion-panel-header>
          <v-expansion-panel-content>
            Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.
          </v-expansion-panel-content>
        </v-expansion-panel>
      </v-expansion-panels>
    </div> -->
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

const degreeOfQ = 30;

export default {
  components: {
  },
  data () {
    return {
      panel: [],
      radios: ['','',''], 
      questions: [
        {
          option1: "나는 나를 인정하는 내용의 쪽지 받기를 좋아한다.", 
          option2: "나는 안기는 것이 좋다.", 
          choice: "", 
        },   
        {
          option1: "특별한 사람과 일대일로 시간을 보내는 게 좋다.", 
          option2: "누군가 내게 실제적인 도움을 줄 때 사랑 받는다고 느낀다.", 
          choice: "", 
        },   
        {
          option1: "사람들로부터 선물을 받는 게 좋다.", 
          option2: "친구들과 사랑하는 사람들을 만나 여유 있게 시간을 보내는 게 좋다.", 
          choice: "", 
        },     
      ],
    }
  },


  mounted() {
    this.init();
  },
  methods: {
    init () {
      for(let i = 0; i < 3; i++){
        this.panel.push(i);
      }
      //console.log(this.panel);
    },
  }
}

</script>

