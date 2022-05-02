<template>
  <v-app>
     <v-app-bar app dark>
      <v-app-bar-title> 아이디어 앱 </v-app-bar-title> <v-spacer></v-spacer>
      
      <v-btn v-if="user" text @click="logout()">로그아웃</v-btn>
      <v-btn v-else text to="/login">로그인</v-btn>
    </v-app-bar>

   

    <v-main>
      <router-view/>
    </v-main>
  </v-app>
</template>

<script>

export default {

  data: () => ({
    user: null,
  }),
  computed:{
    // 자동으로 바뀌어야 하는 변수들 
  },
  methods:{
    // 함수들
  },
  created(){
    // 페이지에 진입했을때 자동으로 실행될 함수들(페이지 구현전 실행)
  },
  mounted(){
    // 페이지에 진입했을때 페이지가 구현된후 자동으로 실행될 함수들 
  },
  watch:{
    // 특정 값이 변경될경우 실행되어야 할 함수들
  }
};
</script>

<style lang="">
  
</style>
