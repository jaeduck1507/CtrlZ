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
      

      <div class="text-center">
    <v-dialog
      v-model="dialog"
      width="500"
    >
      <template v-slot:activator="{ on, attrs }">
        <v-btn
          icon
          
          
          v-bind="attrs"
          v-on="on"
        >
        <v-icon>mdi-help-box</v-icon>
        </v-btn>
      </template>

      <v-card>
        <v-card-title class="text-h5 grey lighten-2">
          Help
        </v-card-title>

        <v-card-text>
          @@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@이 웹사이트에대한설명
          @@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@
          @@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@
        </v-card-text>

        <v-divider></v-divider>

        <v-card-actions>
          <v-spacer></v-spacer>
          <v-btn
            color="primary"
            text
            @click="dialog = false"
          >
            I accept
          </v-btn>
        </v-card-actions>
       </v-card>
      </v-dialog>
      </div>
      <v-btn 
      icon
      
      >
        <v-icon>mdi-dots-vertical</v-icon>
        
      </v-btn>
    </v-app-bar>
    
  </v-card>
    <v-row class="my-0">
    
    <v-navigation-drawer 
    
    expand-on-hover
    v-model="drawer"  
    >
      <v-list-item>
        
        <v-list-item-content>
          
          <v-list-item-title class="text-h6">
            
            Name
            
          </v-list-item-title>
          <v-list-item-subtitle>
            email@gmail.com
          </v-list-item-subtitle>
        </v-list-item-content>
        <v-row justify="center">
    <v-dialog
      v-model="dialog2"
      persistent
      max-width="290"
    >
      <template v-slot:activator="{ on, attrs }">
        <v-btn
          text
          depressed
          x-small
          v-bind="attrs"
          v-on="on"
          
        >
        <v-icon>mdi-logout</v-icon>
          logout
        </v-btn>
      </template>
      <v-card>
        <v-card-title class="text-h5">
          Logout
        </v-card-title>
        <v-card-text>Are you sure you want to log out? Any changes you haven't made are not saved!</v-card-text>
        <v-card-actions>
          <v-spacer></v-spacer>
          <v-btn
            color="green darken-1"
            text
            @click="dialog2 = false"

          >
            agree
          </v-btn>
          <v-btn
            color="green darken-1"
            text
            @click="dialog2 = false"
          >
            Disagree
          </v-btn>
        </v-card-actions>
      </v-card>
    </v-dialog>
    </v-row>

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
    <v-content permanent
    absolute
    ><router-view/></v-content>
  </v-row>
  
  </v-app>
</template>


<script>
  export default {
    data () {
      return {
        dialog: false,
        dialog2: false,
        drawer: false,
        items: [
          { title: 'Login', icon: 'mdi-view-dashboard', to:'/login' },
          { title: 'Photos', icon: 'mdi-image' },
          { title: 'Drawing', icon:'mdi-draw', to:'/Draw'},
          { title: 'About', icon: 'mdi-help-box', to:'/About' }
        ],
        
        
      }
    },
  }
</script>