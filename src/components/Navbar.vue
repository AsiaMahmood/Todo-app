<template>

<nav>
  <v-card
    color="grey lighten-4"
    flat
    tile
  >
    <v-toolbar  app flat>
      <v-app-bar-nav-icon @click="drawer= !drawer" class='grey--text'></v-app-bar-nav-icon>
      <span class='_title primary--text font-weight-bold pl-2'>إدارة</span> 
      <span class="_sub-title primary--text font-weight-light">المشاريع</span>
      <v-spacer></v-spacer>
    </v-toolbar>
  </v-card>

  <v-navigation-drawer 
    app
    clipped
    right
    v-model="drawer"  
    class="primary secondary--text"
  >
    <v-list-item-group color="primary">

      <v-layout column align-center justify-center>
        <v-flex class="mt-5">
          <v-avatar size="100">
            <img src="/avator-4.jpg">
          </v-avatar>
          <p class="headline secondary--text mt-3 pr-8">اسيا محمود احمد</p>
        </v-flex>
        <v-flex class="mt-4 mb-3">
          <Popup />
        </v-flex>
      </v-layout>

      <v-list-item
        v-for="(link, i) in links"
        :key="i"
        router
        :to="link.route"
      >
        <v-list-item-icon>
          <v-icon v-text="link.icon" class="secondary--text"></v-icon>
        </v-list-item-icon>
        <v-list-item-content>
          <v-list-item-title v-text="link.text" class="secondary--text"></v-list-item-title>
        </v-list-item-content>
      </v-list-item>
    </v-list-item-group>
  </v-navigation-drawer>
</nav>

</template>

<script>
import Popup from '../components/Popup.vue'

export default {
  components:{
    Popup
  },
  data(){
    return{
      drawer:false,
      links: [
        { icon : 'dashboard' , text:'dashboard', route:'/'},
        { icon : 'folder' , text:'مشاريعي', route:'/project'},
        { icon : 'person' , text:'فريقي', route:'/team'}
      ]
    }
  }
}
</script>

<style scoped>

._title{
  font-size: 24px;
  line-height: 44px;

}
._sub-title{
    font-size: 24px;
    line-height: 44px;
}

</style>
