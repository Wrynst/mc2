<template>
  <v-app>
    <v-navigation-drawer
      :mini-variant="miniVariant"
      :clipped="clipped"
      v-model="drawer"
      fixed
      app 
      dark
    >
      <v-list>
        <v-list-tile
          router
          :to="item.to"
          :key="i"
          v-for="(item, i) in items"
          exact
        >
          <v-list-tile-action>
            <v-icon v-html="item.icon"></v-icon>
          </v-list-tile-action>
          <v-list-tile-content>
            <v-list-tile-title v-text="item.title"></v-list-tile-title>
          </v-list-tile-content>
        </v-list-tile>
      </v-list>
    </v-navigation-drawer>
    <v-toolbar fixed app :clipped-left="clipped" dark color="red darken-4
																														 ">
      <v-toolbar-side-icon @click="drawer = !drawer"></v-toolbar-side-icon>
      <v-btn
        icon
        @click.stop="miniVariant = !miniVariant"
      >
        <v-icon v-html="miniVariant ? 'mdi-menu-right' : 'mdi-menu-left'"></v-icon>
      </v-btn>
      <nuxt-link to="/"><v-toolbar-title class="white--text" v-text="title"/></nuxt-link><v-spacer></v-spacer>
   
      
    </v-toolbar>
    <v-content>
      <v-container>
        <nuxt />
      </v-container>
    </v-content>
    <v-footer :fixed="fixed" app dark>
      <small>&copy; 2018 <a href="https://wrynst.com" class="foot-link">Wrynst <v-icon small color="blue darken-4">mdi-vector-polyline</v-icon></a></small>
    </v-footer>
  </v-app>
</template>
<script>
  export default {
    data() {
      return {
        clipped: true,
        drawer: true,
        fixed: true,
        items: [{
            icon: 'mdi-home-circle',
            title: 'Home',
            to: '/'
          },
        ],
        miniVariant: true,
        title: 'AdminCount'
      }
    }
  }
</script>
<style>
	html {
		font-family: 'Amatic SC', cursive;
		
	}

  a {
    text-decoration: none;
  }
  a.foot-link:link {color:#06a;}
  a.foot-link:visited {color:#0ac;}
    
  a.foot-link:hover {font-weight: bold;}

  .bg-style {
   
  }
</style>