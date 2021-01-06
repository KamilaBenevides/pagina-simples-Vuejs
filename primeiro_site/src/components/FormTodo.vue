<template>

  <div class="form-todo form-group">
      <p>
        <input placeholder="poke" type="text" poke="author" class="form-control" id="foto" v-model="poke" />
      </p>
      <button v-on:click="addComment" type="submit" class="btn btn-dark" id="botao">Buscar Pokemon</button>
    </div>
  

</template>

<script>
  import axios from 'axios';
  export default {
    data() {
      return {
        poke: '',
        url: '', 
        str: 0,
        pokemons: []
      }
    },
    methods: {
      addComment() {
        if (this.poke.trim() === '') {
          return;
        }
        for(var i = 0 ; i < 151; i++){
          if(this.pokemons[i].name === this.poke)
            this.str = i;
        }

         this.$emit('add-todo', {
          poke: this.pokemons[this.str].name,
          url: this.pokemons[this.str].url
         });
         this.poke = '';
         this.url = '';
        }
    },
       created: function(){
       axios.get("https://pokeapi.co/api/v2/pokemon?limit=151&offset=0").then(res =>{
         //console.log(res.data.results);
         this.pokemons = res.data.results;
       })
     }
  }
</script>
<style>
#botao{
  color: #f0eeee;
  background-color: #800000;
  border-radius: 40px;
  margin: 0;
  width: 150px;
  border: 0;
}
#botao:hover{
  background-color: #520303;
  color: #f0eeee;
}
#foto{
  max-width: 400px;
}

</style>