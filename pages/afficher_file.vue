<template>
  <v-card
   
     class="justify-center"
     color=""
  >
    <v-card-title>
     Liste Enseignants
     <v-spacer>  </v-spacer>
      <v-btn  @click="afficherEns">Afficher</v-btn>
      <v-spacer>  </v-spacer>
      <v-text-field
        v-model="search"
        
        label="Search"
        single-line
        hide-details
      ></v-text-field>
       <form class="cf" action="./home">
    <input type="submit" value="Revenir à l'accueil" id="input-submit">
     </form>
    </v-card-title>
    <v-data-table
      :headers="headers"
      :items="dataens"
      :search="search"
      
    >  <template v-slot:item.file_path="{item}">
       <v-btn :href="'http://127.0.0.1:8020/'+item.file_path" target="_blank">ICI</v-btn>
   </template></v-data-table>
  
  </v-card>
  
  
</template>
<script>
import axios from "axios";
  export default {
    data () {
      return {
        search: '',
         
        headers: [
          {
            text: 'Nom',
            align: 'left',
            sortable: false,
            value: 'name',
          },
          { text: 'Piece Jointe',  value:'file_path' },
          
          
    
        ],
      dataens:[{id:''}]
      }
    },
    methods :{
      afficherEns()
      {
        this.$axios.get("http://127.0.0.1:8020/api/fichiers").then(responce=>(this.dataens=responce.data)).catch(
          error=>{console.log(error)})
      }
      

    }
  }
</script>