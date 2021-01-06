<template>

  <div class="container nav-container">
      <nav class="navbar nav-pills flex-column flex-sm-row">
      <div class="container-fluid ">
      <a class="navbar-brand" href="#" >
        <!---<img src="../assets/..." alt="" width="50" height="24" class="d-inline-block align-top"> --->
        Inicio
      </a>
      <button class="btn btn-light" type="submit">Sair</button>
    </div>
  </nav>

    <div class="textos">
    <p>Menu principal</p>
    <h2>Bem vindo(a) !</h2>
    <h2>O que vamos fazer hoje?</h2>
    </div>

    <FormTodo v-on:add-todo="addComment"></FormTodo>
    <div class="list-group">
    <div class="list-group-item col-md-9 col-md-push-3" v-for="(comment, index) in allComments" v-bind:key="index">
        <span class="comment__author">Name: <strong>{{ comment.poke }}</strong></span>
        <p>{{ comment.poke }}</p>
        <span class="comment__author">Url: <strong>{{ comment.url }}</strong></span>
        <p>{{ comment.poke }}</p>
        <div>
        <a href="#" title="Excluir" v-on:click.prevent="removeComment(index)">Excluir Usuário</a>
        </div>
    </div>
    </div>
  </div>

  
</template>

<script>
import FormTodo from './FormTodo';

export default {
  components: {
    FormTodo
  },
  data() {
    return {
      comments: [],
    }
  },
  methods: {
    addComment(comment) {
      this.comments.push(comment);
    },
    removeComment(index) {
      this.comments.splice(index, 1);
    }
  },
  computed: {
    allComments() {
      return this.comments.map(comment => ({
        ...comment,
        poke: comment.poke.trim() === '' ? 'Anônimo' : comment.poke
      }))
    }
  },
  watch: {
    comments(val) {
      console.log('val', val)
    }
  },
}
</script>
<style scoped>

.container-fluid, .navbar{
    background-color: #800000;
}
.textos{
    color: #4e4e4e;
    font-family: 'Roboto', sans-serif;
}
.btn{
  color: #520303;
  background-color: #f0eeee;
  border-radius: 40px;
  margin: 5;
  width: 10%;
  border: 0;
}
.btn:hover{
  background-color: #520303;
  color: #f0eeee;
}
</style>