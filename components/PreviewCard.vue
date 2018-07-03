<template>

  <v-layout>
    <v-flex xs12 sm6 offset-sm3 >
      <v-card class="preview-card"> 
      
        <v-card-media 
          :src = thumbnail 
          height="200px"
        ></v-card-media>

        <v-card-title primary-title>
          <div>
            <h3 class="headline mb-0">{{ title }}</h3>
            <div>{{ teaserTxt }}</div>
          </div>
  </v-card-title>

        <v-card-actions>
          <v-btn flat color="green">Share</v-btn>
          <v-btn flat color="indigo darken-4" :to="'/posts/' + id">Read</v-btn>
          <v-btn flat color="orange">Explore</v-btn>
        </v-card-actions>
      </v-card>
    </v-flex>
  </v-layout>
   
</template>

<script>
  export default {
    name: 'PreviewCard',
    props: {
      id: {
        type: String,
        required: true
      },
      title: {
        type: String,
        required: true
      },
      teaserTxt: {
        type: String,
        required: true
      },
      thumbnail: {
        type: String,
        required: true
      },
    }
        
      
    
  }
</script>