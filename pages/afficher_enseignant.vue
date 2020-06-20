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
    <input type="submit" value="Accueil" id="input-submit">
     </form>
    </v-card-title>
    <v-data-table
      :headers="headers"
      :items="dataens"
      :search="search"
    ></v-data-table>
    
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
            value: 'nom',
          },
          { text: 'Prénom', value: 'prenom' },
          { text: 'Email', value: 'email' },
          { text: 'Date de naissance', value: 'date_naissance' },
          { text: 'Spécialité', value: 'specialite' },
          { text: 'Master ', value: 'master' },
          { text: 'Licence', value: 'licence' },
          { text: 'Doctorat ', value: 'doctorat' },
          { text: 'Experience', value: 'experience' },
        ],
      dataens:[{id:''}]
      }
    },
    methods :{
      afficherEns()
      {
        this.$axios.get("http://127.0.0.1:8000/api/enseignants").then(responce=>(this.dataens=responce.data)).catch(
          error=>{console.log(error)})
      }
      

    }
  }
</script>