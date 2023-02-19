<template>
  <v-app id="inspire">
    <v-layout style="height: 100vh">
     <Drawer />

      <v-main style="padding-left: 280px;flex:1 0">
        
        <Appbar />
        <v-container class="py-8 px-6" fluid>
         <Dashboard />
        </v-container>
      </v-main>
    </v-layout>
  </v-app>
</template>

<script lang="jsx">

import Dashboard from '../views/Dashboard.vue';
import Appbar from './Appbar.vue';
import Drawer from './Drawer.vue'

export default {
    data: () => ({
        
    }),
    components: { Appbar, Drawer, Dashboard }
}
</script>

<style src="./style.css"></style>