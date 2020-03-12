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
          xs12
        >
          <p>사랑의 언어에 대한 설명~~</p>
        </v-flex>
      </v-layout>
      <v-layout 
        align-center 
        justify-center
        row 
        wrap
      >
        <v-flex
          xs12
        >
          <v-btn 
            text
            to="/langOflove/test"
          >
            사랑의 언어 테스트 시작하기
          </v-btn>
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
    }
  },
}
</script>

