<template>
  <v-container>
    <v-card>
      <v-text-field outlined v-model="ideaTitle" label="아이디어 제목">
      </v-text-field>
      <v-text-field outlined v-model="ideaText" label="아이디어 내용">
      </v-text-field>
      <v-card-actions>
        <v-spacer></v-spacer>
        <v-btn @click="addData"> 아이디어 추가</v-btn>
        <!--  
        <v-btn @click="getData"> get test </v-btn>
        -->
      </v-card-actions>
    </v-card>
    <v-card v-for="(item, i) in list" :key="i" outlined>
      <v-card-title v-if="!updateState">
        {{ item.ideaTitle }} <v-spacer></v-spacer>
        <v-btn
          icon
          @click="(ideaTitle = ''), (ideaText = ''), (updateState = true)"
          ><v-icon color="green">mdi-pen</v-icon></v-btn
        >
        <v-btn icon @click="deleteData(item.id)"
          ><v-icon color="red">mdi-close</v-icon></v-btn
        >
      </v-card-title>
      <v-card-title v-else>
        <v-text-field
          v-model="item.ideaTitle"
          outlined
          label="아이디어 제목"
        ></v-text-field>
      </v-card-title>
      <v-card-text v-if="!updateState">
        {{ item.ideaText }}
      </v-card-text>
      <v-card-text v-else>
        <v-text-field
          v-model="item.ideaText"
          outlined
          label="아이디어 내용"
        ></v-text-field>
      </v-card-text>
      <v-card-text v-if="item.createdTimestamp">
        {{ new Date(item.createdTimestamp.seconds * 1000) }}
      </v-card-text>
      <v-card-actions v-if="updateState">
        <v-btn @click="updateData(item)">수정완료</v-btn>
      </v-card-actions>
    </v-card>
  </v-container>
</template>

<script>
// @ is an alias to /src

export default {
  
  data: () => ({
    updateState: false,
    ideaTitle: "",
    ideaText: "",
    list: [{ideaTitle:"test", ideaText:"test"}],
    unsubscribe: false,
  }),
  components: {},

  methods: {
    
  },
  distroyed() {
  
  },
};
</script>
