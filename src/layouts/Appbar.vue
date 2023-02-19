<template>
    <v-app-bar
      color="transparent">
    <v-toolbar-items class="me-5">
    <v-breadcrumbs :items="items" class="pa-0" >
    <template v-slot:item="{ item }" >
      <v-breadcrumbs-item
        :href="item.href"
        :disabled="item.disabled"
      >
        {{ item.text && item.text }}
        <v-icon v-if="item.icon">{{ item.icon }}</v-icon>
      </v-breadcrumbs-item>
    </template>
  </v-breadcrumbs>

      <v-toolbar-title  >Analytics</v-toolbar-title>
    </v-toolbar-items>
 
          <v-btn
            icon
            v-bind="attrs"
            v-on="on"
          >
            <v-icon>mdi-menu-open</v-icon>
          </v-btn>


      <v-spacer></v-spacer>
          
      <v-text-field
        label="Insert a number"
        outlined
        color="red"
        hide-details
        height="40px"
      ></v-text-field>
        <v-btn icon v-for="icon in iconList">
            <v-badge
            v-if="icon.badge"
            color="error"
            content="6"
            
            >
        <v-icon>{{ icon.icon }}</v-icon>
    </v-badge>
    <v-icon v-else="">{{ icon.icon }}</v-icon>
  

      </v-btn>




    </v-app-bar>
</template>


<script>

export default{
    data: () => ({
        iconList: 
            [  
            { icon: 'mdi-account-circle' }, 
            { icon: 'mdi-cog'},
            { icon: 'mdi-bell', badge:15},
            ],
        items: [
        {
          icon: 'mdi-store',
          disabled: false,
          href: '',
        },
        {
          text: 'Dashboard',
          disabled: true,

        },
        {
          text: 'Analytics',
          disabled: true,
       
        },
      ],
        
    }),
}

</script>

<style>
.v-toolbar{
   box-shadow: none!important;
    
}
.v-toolbar__items{
    flex-direction: column;
    height: auto;
    
}

/* .v-breadcrumbs li{
    font-size:13px
} */
.v-toolbar__title{
    font-size: 1rem;
}
.v-input{

    flex: none;
}

 .v-input__slot{
     min-height: auto !important;
}
.v-text-field--outlined .v-label{
    top: auto !important;
}
</style>