
import IconCard from '../Commons/IconCard.vue';

<template>

<v-card
class="rounded-lg d-flex flex-column"
  elevation="2"
  shaped
  rounded
  tile
>
<div class="px-6 pt-4 pb-0 d-flex">
<IconCard icon="mdi-web" color="red" />
<v-card-title class="ps-4">first box</v-card-title>
</div>
<v-container class="grey lighten-5">
    <v-row
      v-for="n in 1"
      :key="n"
      class= 'mb-6'
      
    >
      <v-col
class="col-md-7 col-lg-6 col"
      >
<CountryList />
      </v-col>
      <v-col
class="col-md-5 col-lg-6 col"
      >

      </v-col>

      </v-row>
      </v-container>
</v-card>

</template>
  
 <script>
import IconCard from '../Commons/IconCard.vue';
import CountryList from './CountryList.vue';


  
 export default {
  components: {
    IconCard,
    CountryList
},
  data() {
    return {
      user: {
        username: 'matt'
      }
    }
  }
 }
 </script>