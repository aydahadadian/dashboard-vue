<template>
  <v-app id="inspire">
    <v-layout style="height: 100vh">
     <Drawer />

      <v-main style="padding-left: 280px;flex:1 0">
        
        <Appbar />
        <v-container class="py-8 px-6" fluid>
          <v-row>
            <v-col v-for="card in cards" :key="card" cols="12">
              <v-card> </v-card>
            </v-col>
          </v-row>
        </v-container>
      </v-main>
    </v-layout>
  </v-app>
</template>

<script lang="jsx">

import Appbar from './Appbar.vue';
import Drawer from './Drawer.vue'

export default {
    data: () => ({
        
    }),
    components: { Appbar,Drawer }
}
</script>

<style src="./style.css"></style>