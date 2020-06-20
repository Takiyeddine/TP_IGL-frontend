<template>
  <body class="home" style="backgrounf-image=src('../assets/home.png')">
   <form class="cf" action="./home"><input  type="submit" value="Découvrir les fonctionnalités" id="input-submit"></form>
  </body>
</template>

<script>
import axios from "axios";

export default {
  data() {
    return {
      user: {
        firstname: "",
        lastname: "",
        phone: ""
      }

    };
  },
  methods: {
    handleSubmit() {
      axios.post("/submit", this.$data).then(() => {
        this.$data.user = {};
      });
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

html {
  font-family: 'Source Sans Pro', -apple-system, BlinkMacSystemFont, 'Segoe UI',
    Roboto, 'Helvetica Neue', Arial, sans-serif;
  font-size: 16px;
  word-spacing: 1px;
  -ms-text-size-adjust: 100%;
  -webkit-text-size-adjust: 100%;
  -moz-osx-font-smoothing: grayscale;
  -webkit-font-smoothing: antialiased;
  box-sizing: border-box;
   background: url(../assets/home.png) no-repeat center center fixed; 
  -webkit-background-size: cover;
  -moz-background-size: cover;
  -o-background-size: cover;
  background-size: cover;
}




form {
  max-width: 200px;
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
  margin-top: 550px;
  color: white;
  background: #f6921e;
  cursor: pointer;
}
form #input-submit:hover {
  -moz-box-shadow: 0 1px 1px 1px rgba(170, 170, 170, 0.6);
  -webkit-box-shadow: 0 1px 1px 1px rgba(170, 170, 170, 0.6);
  box-shadow: 0 1px 1px 1px rgba(170, 170, 170, 0.6);
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