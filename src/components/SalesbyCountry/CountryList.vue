<template>
<v-card>
    <v-list>
        <template v-for="(item, index) in items" >
            <v-divider
          v-if="item.divider"
          :key="index"
          inset
        
        ></v-divider>
        <v-list-item v-else >
            <v-list-item-content class="d-flex flex-column align-start">
                <v-img
                :width="width" :src="item.flag"></v-img>
          </v-list-item-content>

            <v-list-item-content class="d-flex flex-column align-start">
            <v-list-item-title style="align-self:normal">country</v-list-item-title>
            <v-list-item-subtitle>{{ item.country }}</v-list-item-subtitle>
          </v-list-item-content>

            <v-list-item-content class="d-flex flex-column">
            <v-list-item-title>Sales</v-list-item-title>
            <v-list-item-subtitle>{{ item.Sales }}</v-list-item-subtitle>
          </v-list-item-content>

            <v-list-item-content class="d-flex flex-column">
            <v-list-item-title>Value</v-list-item-title>
            <v-list-item-subtitle>${{ item.Value }}</v-list-item-subtitle>
          </v-list-item-content>
            <v-list-item-content class="d-flex flex-column">
            <v-list-item-title>Bounce</v-list-item-title>
            <v-list-item-subtitle>{{ item.Bounce }}%</v-list-item-subtitle>
          </v-list-item-content>

        </v-list-item>
        </template>
    </v-list>
</v-card>
</template>


<script lang="jsx">
import usaFlag from "../../assets/usa.png"
import enFlag from "../../assets/en.png"
import germanFlag from "../../assets/german.png"
import brasilFlag from "../../assets/brasil.png"


export default {
    data: () => ({

        items:[
{flag:usaFlag,country:'United State',Sales:'2.500',Value:'230,900',Bounce:'29.9'},
{divider:true},
{flag:enFlag,country:'Germany',Sales:'3.900',Value:'440,000',Bounce:'40.22'},
{divider:true},
{flag:germanFlag,country:'Great Britain',Sales:'1.400',Value:'190,700',Bounce:'23.44'},
{divider:true},
{flag:brasilFlag,country:'Brasil',Sales:'562',Value:'143,960',Bounce:'32.14'},


]
    })}
    </script>
<style>
.v-card{    box-shadow: none !important;}

.v-list-item:hover{
    background-color: transparent !important;

}
</style>
