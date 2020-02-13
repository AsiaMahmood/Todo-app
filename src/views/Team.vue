<template>
  <div class="team">
    <h1 class="subtitle-1 mt-4 pr-4 grey--text">فريقي</h1>
  
    <v-container class="my-5">
      <v-layout row wrap>
        <v-flex xs12 sm6 md4 lg3 v-for="person in team" :key="person.name" >
          <v-card flat class="text-center ma-3">
            <v-responsive class="pt-4">
              <v-avatar size='86'>
                <img :src="person.avator" alt="">
              </v-avatar>
            </v-responsive>
            <v-card-text>
              <div class="title">{{ person.name }}</div>
              <div class="grey--text">{{ person.role }}</div>
            </v-card-text>
            <v-card-action>
              <v-btn text class="grey lighten-4 mb-4">
                <v-icon small left>message</v-icon>
                <span class="subtitle-1 font-weight-medium">رسالة</span>
              </v-btn>
            </v-card-action>
          </v-card>
        </v-flex>
      </v-layout>
    </v-container>

  </div>
</template>

<script>

export default {
  components: {
  },
  data(){
    return{
      team: [
        { name: 'نور حسين', role: 'Web developer' , avator: '/avator-1.jpg'},
        { name: 'علي موفق', role: 'Graphic designer' , avator: '/avator-2.jpg'},
        { name: 'محمد', role: 'Web developer' , avator: '/avator-3.jpg'},
        { name: 'احمد', role: 'Social media maverick' , avator: '/avator-4.jpg'},
        { name: 'هاجر محمود', role: 'Sales guru', avator: '/avator-5.jpg'}
      ]
    }
  }
}
</script>
