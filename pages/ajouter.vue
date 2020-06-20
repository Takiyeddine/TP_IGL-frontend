<template>
  <section>
  <h1>Ajouter un nouvel Enseignant</h1>
  <form class="cf" @submit.prevent="handleSubmit" method="POST" action="http://127.0.0.1:8000/api/save">
   
    <div class="center" >
     
      <input type="text" name="nom" placeholder="Nom" v-model="data.nom">
      <input type="text" name="prenom" placeholder="Prénom" v-model="data.prenom">
      <input type="text" name="email" placeholder="Email" v-model="data.email" >
      <input type="text" name="date_naissance" placeholder="Date de naissance" v-model="data.date_naissance">
      <input type="text" name="specialite" placeholder="Spécialité" v-model="data.specialite">
      <input type="text" name="licence" placeholder="Licence" v-model="data.licence">
      <input type="text" name="master" placeholder="Master" v-model="data.master">
      <input type="text" name="doctorat" placeholder="Doctorat" v-model="data.doctorat">
      <input type="text" name="experience" placeholder="Années d'experience" v-model="data.experience" >
      
    
    
    </div>
 
    <input type="submit" value="Ajouter" id="input-submit">

  </form>
    <form class="cf" action="./home">
    <input type="submit" value="Revenir à l'accueil" id="input-submit">
     </form>
  </section>
</template>

<script>
import axios from "axios";

export default {
  data() {
    return {
      data :{
        nom:'',
        prenom:'',
        email:'',
        date_naissance:'',
        specialite:'',
        licence:'',
        master:'',
        doctorat:'',
        experience:''

      }
     
    };
  },
  methods: {
    handleSubmit() {
      console.log(this.data);
      this.$axios.post("http://127.0.0.1:8000/api/save",{nom:this.data.nom,prenom:this.data.prenom,email:this.data.email,date_naissance:this.data.date_naissance,specialite:this.data.specialite,licence:this.data.licence,master:this.data.master,doctorat:this.data.doctorat,experience:this.data.experience});
      console.log(this.data);
    }
  }
};
</script>

<style>
@import url(https://fonts.googleapis.com/css?family=Merriweather);
*,
*:before,
*:after {
  -moz-box-sizing: border-box;
  -webkit-box-sizing: border-box;
  box-sizing: border-box;
}

html,
body {
  background: #f1f1f1;
  font-family: "Merriweather", sans-serif;
  padding: 1em;
}

h1 {
  text-align: center;
  color: #a8a8a8;
  text-shadow: 1px 1px 0 white;
}

form {
  max-width: 600px;
  text-align: center;
  margin: 20px auto;
}
form input,
form textarea {
  border: 0;
  outline: 0;
  padding: 1em;
  -moz-border-radius: 8px;
  -webkit-border-radius: 8px;
  border-radius: 8px;
  display: block;
  width: 100%;
  margin-top: 1em;
  font-family: "Merriweather", sans-serif;
  -moz-box-shadow: 0 1px 1px rgba(0, 0, 0, 0.1);
  -webkit-box-shadow: 0 1px 1px rgba(0, 0, 0, 0.1);
  box-shadow: 0 1px 1px rgba(0, 0, 0, 0.1);
  resize: none;
}
form input:focus,
form textarea:focus {
  -moz-box-shadow: 0 0px 2px #e74c3c !important;
  -webkit-box-shadow: 0 0px 2px #e74c3c !important;
  box-shadow: 0 0px 2px #e74c3c !important;
}
form #input-submit {
  color: white;
  background: #f6921e;
  cursor: pointer;
}
form #input-submit:hover {
  -moz-box-shadow: 0 1px 1px 1px rgba(170, 170, 170, 0.6);
  -webkit-box-shadow: 0 1px 1px 1px rgba(170, 170, 170, 0.6);
  box-shadow: 0 1px 1px 1px rgba(170, 170, 170, 0.6);
}
form textarea {
  height: 126px;
}

.half {
  float: left;
  width: 48%;
  margin-bottom: 1em;
}

.right {
  width: 50%;
}

.left {
  margin-right: 2%;
}

@media (max-width: 480px) {
  .half {
    width: 100%;
    float: none;
    margin-bottom: 0;
  }
}
/* Clearfix */
.cf:before,
.cf:after {
  content: " ";
  /* 1 */
  display: table;
  /* 2 */
}

.cf:after {
  clear: both;
}
</style>
