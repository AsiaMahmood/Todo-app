<template>
  <v-app>
    <v-content>
      <Navbar/>
      <div class="mx-4 mb-4">
        <router-view/>
      </div>
    </v-content>
  </v-app>
</template>

<script>
import Navbar from './components/Navbar.vue'

export default {
  name: 'App',
  components: { Navbar },
  data: () => ({
    //
  })
};
</script>
<style>
.theme--light.v-application {
  background: #f5f5f5 !important;
}
</style>