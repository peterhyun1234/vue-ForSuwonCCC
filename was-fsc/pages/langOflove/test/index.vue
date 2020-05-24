

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
                <v-expansion-panel-header expand-icon="mdi-menu-down" disable-icon-rotate>
                  질문 {{i+1}} /{{QDegree}}
                  <template 
                    v-slot:actions
                    v-if="radios[i]"
                  >
                    <v-icon color="teal">mdi-check</v-icon>
                  </template>
                  <template 
                    v-slot:actions
                    v-else
                  >
                    <v-icon color="error">mdi-alert-circle</v-icon>
                  </template>
                </v-expansion-panel-header>
              
                <v-divider></v-divider>
                <v-expansion-panel-content
                  class= "mt-5">
                  <v-radio-group v-model="radios[i]">
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
          </v-card>
        </v-col>
      </v-row>
      <v-row>
        <v-col 
          class="my-2"
          style="text-align: center;"
        >
          <v-dialog v-model="refreshDialog" persistent max-width="290">
            <template v-slot:activator="{ on }">
              <v-btn 
                :class="[computedMargin]"
                class="subtitle-1 font-weight-bold" 
                color="warning" 
                large 
                v-on="on">
                <v-icon large>mdi-cached</v-icon> 
                응답 초기화
              </v-btn>
            </template>
            <v-card>
              <v-card-title class="headline">응답 초기화</v-card-title>
              <v-card-text>동의하시면 지금까지 열심히 작성한 질문들에 대한 답변이 초기화 됩니다. 초기화 하시겠습니까?</v-card-text>
              <v-card-actions>
                <v-spacer></v-spacer>
                <v-btn color="blue darken-1" text @click="refreshDialog = false" class="subtitle-1 font-weight-bold" >아니오</v-btn>
                <v-btn color="pink darken-1" text @click="refreshDialog = false; refresh()" class="subtitle-1 font-weight-bold" >초기화</v-btn>
              </v-card-actions>
            </v-card>
          </v-dialog>

          <v-btn 
            :class="[computedMargin]"
            class="subtitle-1 font-weight-bold white--text" 
            color="green"
            @click="carculateResult()"
            large >
            <v-icon large>mdi-arrow-right-circle-outline</v-icon> 
            결과 확인!
          </v-btn>
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
      QDegree: degreeOfQ,
      refreshDialog: false,
      resultDialog: false,
      panel: [],
      radios: [], 
      questions: [
        {
          option1: "나는 나를 인정하는 내용의 문자나 카톡을 받는 것을 좋아한다.", 
          option2: "나는 안기는 것이 좋다.", 
          option1_prop: "A", 
          option2_prop: "E", 
        },   
        {
          option1: "특별한 사람과 일대일로 시간을 보내는 게 좋다.", 
          option2: "누군가 내게 도움을 줄 때 사랑 받는다고 느낀다.", 
          option1_prop: "B", 
          option2_prop: "D", 
        },   
        {
          option1: "사람들로부터 의미있는 선물을 받는 게 좋다.", 
          option2: "친구들과 사랑하는 사람들을 만나 여유 있게 시간을 보내는 게 좋다.", 
          option1_prop: "C", 
          option2_prop: "B", 
        },     
        {
          option1: "사람들이 나를 도와줄 때 사랑 받고 있다고 느낀다.", 
          option2: "사람들이 나를 쓰다듬어 줄 때 사랑 받는다고 느낀다.", 
          option1_prop: "D", 
          option2_prop: "E", 
        },
        {
          option1: "내가 사랑하는 사람이 내 어깨에 팔을 두르면 사랑 받는다고 느낀다.", 
          option2: "내가 사랑하는 사람의 선물을 받을 때 사랑 받는다고 느낀다.", 
          option1_prop: "E", 
          option2_prop: "C", 
        },     
        {
          option1: "친구들, 사랑하는 사람들과 함께 여기저기 다니는 것이 좋다.", 
          option2: "내게 특별한 사람들과 하이파이브를 하거나 손을 잡는 게 좋다.", 
          option1_prop: "B", 
          option2_prop: "E", 
        },
        {
          option1: "나에겐 눈에 보이는 사랑의 상징(선물)이 아주 중요하다.", 
          option2: "사람들이 인정해줄 때 사랑 받는다고 느낀다.", 
          option1_prop: "C", 
          option2_prop: "A", 
        },      
        {
          option1: "좋아하는 사람 곁에 가까이 앉는 게 좋다.", 
          option2: "내가 매력적이라고/잘생겼다고 말해 주는 사람이 좋다.	", 
          option1_prop: "E", 
          option2_prop: "A", 
        },
        {
          option1: "친구 및 사랑하는 사람들과 시간을 보내는 게 좋다.", 
          option2: "친구 및 사랑하는 사람들로부터 작은 선물을 받는 게 좋다.", 
          option1_prop: "B", 
          option2_prop: "C", 
        },     
        {
          option1: "인정하는 말을 중요하게 생각한다.", 
          option2: "누군가 나를 도와주면 그 사람이 나를 사랑한다고 생각한다.", 
          option1_prop: "A", 
          option2_prop: "D", 
        },
        {
          option1: "친구 및 사랑하는 사람들과 함께 있거나 함께 어떤 일을 하는 걸 좋아한다.", 
          option2: "친절한 언행을 보거나 들을 때가 좋다.", 
          option1_prop: "B", 
          option2_prop: "A", 
        },     
        {
          option1: "상대방이 하는 말보다 그 사람의 행동이 내게 더 큰 영향을 준다.", 
          option2: "포옹을 하면 친밀한 느낌, 상대방이 나를 소중히 여긴다는 느낌이 든다.", 
          option1_prop: "D", 
          option2_prop: "E", 
        },
        {
          option1: "나는 칭찬을 소중히 여기고 비판을 피하려 든다.", 
          option2: "커다란 선물 하나보다 작은 선물 여러 개가 더 의미 있다.", 
          option1_prop: "A", 
          option2_prop: "C", 
        },      
        {
          option1: "누군가와 함께 이야기를 하거나 뭔가를 같이하면 그와 가깝게 느껴진다.", 
          option2: "친구들과 사랑하는 사람들이 나를 쓰담쓰담 해주면 더욱 친밀감을 느낀다.", 
          option1_prop: "B", 
          option2_prop: "E", 
        },
        {
          option1: "사람들이 내가 한 일에 대해 칭찬하는 게 좋다.", 
          option2: "사람들이 날 위해 하기 싫은 일을 할 때 그들의 사랑을 느낀다.", 
          option1_prop: "A", 
          option2_prop: "D", 
        },       
        {
          option1: "친구 및 사랑하는 사람들이 나를 터치하면서 지나가는 게 좋다.", 
          option2: "사람들이 내 말을 경청하고 내 말에 진정한 관심을 보이는 게 좋다.", 
          option1_prop: "E", 
          option2_prop: "B", 
        },
        {
          option1: "친구들과 사랑하는 사람들이 내 업무나 일을 도와줄 때 그들의 사랑을 느낀다.", 
          option2: "친구와 사랑하는 사람들로부터 선물을 받는 게 정말 좋다.", 
          option1_prop: "D", 
          option2_prop: "C", 
        },     
        {
          option1: "사람들이 내 외모를 칭찬하는 게 좋다.", 
          option2: "사람들이 내 기분을 이해하기 위해 시간을 낼 때 그들의 사랑을 느낀다.", 
          option1_prop: "A", 
          option2_prop: "B", 
        },
        {
          option1: "특별한 사람이 나를 쓰다듬을 때 안정감을 느낀다.", 
          option2: "누군가 나를 위해 봉사를해준다고 생각하면 사랑을 느낀다.", 
          option1_prop: "E", 
          option2_prop: "D", 
        },      
        {
          option1: "특별한 사람들이 나를 위해 하는 많은 일들에 감사한다.", 
          option2: "특별한 사람들이 날 위해 만든 선물을 받는 걸 좋아한다.", 
          option1_prop: "D", 
          option2_prop: "C", 
        },
        {
          option1: "누군가의 온전한 관심을 받을 때 기분이 정말 좋다.", 
          option2: "누군가 나를 위해 헌신할 때 기분이 정말 좋다.", 
          option1_prop: "B", 
          option2_prop: "D", 
        },       
        {
          option1: "생일날 선물로 축하를 받을 때 사랑 받는다고 느낀다.", 
          option2: "생일날 뜻 깊은 말로 축하를 받을 때 사랑 받는다고 느낀다.", 
          option1_prop: "C", 
          option2_prop: "A", 
        },
        {
          option1: "상대방이 선물을 주면 그 사람의 특별한 마음이 느껴진다.", 
          option2: "상대방이 나의 허드렛일을 도와줄 때 사랑 받는다고 느낀다.", 
          option1_prop: "C", 
          option2_prop: "D", 
        },     
        {
          option1: "누군가 내 말을 끊지 않고 참을성 있게 들어줄 때 고마움을 느낀다.", 
          option2: "누군가 특별한 날을 기억하고 선물을 줄 때 고마움을 느낀다.", 
          option1_prop: "B", 
          option2_prop: "C", 
        },
        {
          option1: "사랑하는 사람들이 내게 관심을 갖고 내 일상 업무를 도와줄 때 기분이 좋다.", 
          option2: "특별한 사람과 함께 장기여행을 다니는 게 좋다.", 
          option1_prop: "D", 
          option2_prop: "B", 
        },      
        {
          option1: "가까운 사람에게 가벼운 뽀뽀를 하거나 받는 것이 좋다.", 
          option2: "특별한 이유 없이 선물을 받으면 신이 난다.", 
          option1_prop: "E", 
          option2_prop: "C", 
        },
        {
          option1: "고맙다는 말을 듣는 게 좋다.", 
          option2: "대화를 나누는 사람이 나를 쳐다보는 게 좋다.", 
          option1_prop: "A", 
          option2_prop: "B", 
        },       
        {
          option1: "친구나 사랑하는 사람이 준 선물은 내게 언제나 특별하다.", 
          option2: "친구나 사랑하는 사람이 나를 터치할 때 기분이 좋다.", 
          option1_prop: "C", 
          option2_prop: "E", 
        },
        {
          option1: "상대방이 내가 요청한 어떤 일을 열정적으로 할 때 그 사람의 사랑을 느낀다.", 
          option2: "너무나 고맙다는 말을 들을 때 사랑 받고 있음을 느낀다.", 
          option1_prop: "D", 
          option2_prop: "A", 
        },     
        {
          option1: "나는 매일 가까운 사람이 스킨쉽으로 다가오는 것이 좋다.", 
          option2: "나는 매일 특별한 사람이 나를 인정해주는 말을 해주는 게 좋다.", 
          option1_prop: "E", 
          option2_prop: "A", 
        },
      ],
      windowSize: {
        x: 0,
        y: 0,
        mobile: false
      },
    }
  },

  mounted() {
    this.init();
    this.onResize();
  },

  computed: {
    computedMargin(){
      if(this.windowSize.mobile){
        return `ma-1`
      }else{
        return `mb-3 ml-5 mr-5`
      }
    },
  },

  methods: {
    init () {
      for(let i = 0; i < degreeOfQ; i++){
        this.panel.push(i);
      }
      
      //console.log(this.panel);
    },
    onResize () {
      this.windowSize = { x: window.innerWidth, y: window.innerHeight }
      if(window.innerWidth < 650){
        this.windowSize.mobile = true
      }
    },
    refresh(){
      this.radios = [];
    },
    carculateResult(){
      // 하나라도 check 안한 항목이 있는지
      console.log("carculateResult");


      // 참고: https://stackoverflow.com/questions/35664550/vue-js-redirection-to-another-page
      this.$router.push('./test/result')
    },

  }
}

</script>

<style>

</style>
