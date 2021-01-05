<template>

  <div class="form-todo form-group">
  <p>
    <input placeholder="nome" type="text" name="author" class="form-control" id="foto" v-model="name" />
  </p>
  <p>
    <input placeholder="email" type="text" name="email" class="form-control" id="foto" v-model="email" />
  </p>
  <p>
    <input placeholder="senha" type="text" name="senha" class="form-control" id="foto" v-model="senha" />
  </p>
  <p>
    <input placeholder="cpf" type="text" name="cpf" class="form-control" id="foto" v-model="cpf" />
  </p>
  <button type="submit" class="btn btn-dark" id="botao">Criar usuário</button>
  </div>
</template>

<script>
  export default {
    data() {
      return {
        name: '',
      }
    },
    methods: {
      addComment() {
        if (this.name.trim() === '') {
          return;
        }
        
        this.$emit('add-todo', {
          name: this.name,
        });
        this.name = '';
      }
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