<template>
 
  <v-app>
 
    
    
      <v-card 
    color="grey lighten-4"
    flat
    class="mb-0"
    tile
  >
    <v-app-bar 
      dense 
      elevation="1"
      outlined
      flat
      >
      <v-app-bar-nav-icon 
      @click="drawer = !drawer"
      >
        
      </v-app-bar-nav-icon>
      
      <v-toolbar-title>Ctrl Z
        
      </v-toolbar-title>

      <v-spacer></v-spacer>

      <v-btn icon>
        <v-icon>mdi-magnify</v-icon>
      </v-btn>

      <v-btn icon>
        <v-icon>mdi-content-save</v-icon>
      </v-btn>
      
      <v-btn icon>
        <v-icon>mdi-dots-vertical</v-icon>
        
      </v-btn>
    </v-app-bar>
    
  </v-card>
    <v-row class="my-0">
    
    <v-navigation-drawer 
     

    v-model="drawer"  
    >
      <v-list-item>
        
        <v-list-item-content>
          
          <v-list-item-title class="text-h6">
            <v-avatar color="primary"
            ></v-avatar>
            Name
            
          </v-list-item-title>
          <v-list-item-subtitle>
            email@gmail.com
          </v-list-item-subtitle>
        </v-list-item-content>
        <v-btn
        elevation="2"
        x-small
        >logout
        </v-btn>
      </v-list-item>
      <v-list-item>
        
        <v-system-bar>
          <v-switch
            v-model="$vuetify.theme.dark"
            inset
            label="Dark Mode"
            persistent-hint
          ></v-switch>
        </v-system-bar>
      </v-list-item>
      <v-divider></v-divider>

      <v-list
        dense
        nav
      >
        <v-list-item
          v-for="item in items"
          :key="item.title"
          link
          :to="item.to"
        >
        
          <v-list-item-icon>
            <v-icon>{{ item.icon }}</v-icon>
          </v-list-item-icon>

          <v-list-item-content>
            <v-list-item-title>{{ item.title }}</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
        
      </v-list>
      
    </v-navigation-drawer>
    <v-content><router-view/></v-content>
  </v-row>
  
  </v-app>
</template>


<script>
  export default {
    data () {
      return {
        drawer: false,
        items: [
          { title: 'Login', icon: 'mdi-view-dashboard', to:'/login' },
          { title: 'Photos', icon: 'mdi-image' },
          { title: 'About', icon: 'mdi-help-box' },
          { title: 'Information', icon:'mdi-information', to:'/info'}
        ],
        right: null,
        
      }
    },
  }
</script>