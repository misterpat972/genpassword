<template>
  <div>
    <h1>Générateur de Mot de Passe</h1>
    <form>
      <label  for="password" v-if="password">Mot de passe Généré !</label>      
     <!--si la génération du nouveau mot de passe n'a pas été faite on affichera ceci-->
     <label  for="password" v-else>Cliquer sur Générer</label><br/>
      <input class="input1" type="text" id="password" name="password" v-model="password"> <br/>
      <input class="button" type="submit" value="Générer un mot de passe" v-on:click="generatePassword">
    </form>
  </div>  
</template>

<script>
export default {
  name: 'genePassword',
  data () {
    return {
      password: '',
    }    
  },  
  methods :{  

    generatePassword(e){
      e.preventDefault();
      var length = 12,
      charset = "abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ0123456789*_+!@#$%&",
      retVal = "";
      for (var i = 0, n = charset.length; i < length; ++i) {
          retVal += charset.charAt(Math.floor(Math.random() * n));
      }
      this.password = retVal;
    }
  }
}
</script>


<style scoped>
form{
  width: 50%;
  margin: 50px auto;
}
  

/* Titre */
h1{
  color: rgb(71, 109, 221);
}
/* Bouton */
.button{
  width: 50%;
  background-color: #4CAF50; 
  border: none;
  color: white;
  padding: 15px 32px;
  text-align: center;
  text-decoration: none;
  display: inline-block;
  font-size: 16px;
  margin: 4px 2px;
  cursor: pointer;
  border-radius: 5px;
}
/* Input */
.input1{
  width: 50%;
  padding: 12px 20px;
  margin: 8px 0;
  box-sizing: border-box;
  border: 2px solid #ccc;
  -webkit-transition: 0.5s;
  transition: 0.5s;
  outline: none;
  border-radius: 5px;
}
</style>
