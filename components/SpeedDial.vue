<template>
  
  
    <v-speed-dial
      fab
    >
      <v-btn
        slot="activator"
         v-model="fab"
        color="blue darken-2"
        dark
        
             small
            fab
      >
        <v-icon>account_circle</v-icon>
        <v-icon>close</v-icon>
      </v-btn>
      <v-btn
        fab
        dark
        small
        color="green"
      
      >
        <v-icon>edit</v-icon>
      </v-btn>
      <v-btn
        fab
        dark
        small
        color="indigo"
      >
        <v-icon>add</v-icon>
      </v-btn>
      <v-btn
    
        fab
        dark
        small
        color="red"
      >
        <v-icon>delete</v-icon>
      </v-btn>
    </v-speed-dial>
 
</template>
<script>
  export default {
    data: () => ({
      direction: 'left',
      fab: false,
      fling: false,
      hover: true,
  
      right: true,

      transition: 'slide-x-reverse-transition'
    })}