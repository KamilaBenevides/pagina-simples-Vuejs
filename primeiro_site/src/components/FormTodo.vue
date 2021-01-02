<template>
  <div class="form-todo form-group">
  <p>
    <input placeholder="nome" type="text" name="author" class="form-control" v-model="name" />
  </p>
  <p>
    <input placeholder="Email" type="text"  name="email"  class="form-control" v-model="email" />
  </p>
  <p>
    <input placeholder="CPF" type="text"  name="cpf"  class="form-control" v-model="cpf" />
  </p>
  <p>
    <input placeholder="Senha" type="text"  name="senha"  class="form-control" v-model="senha" />
  </p>
  <p>
    <input placeholder="Confirmar Senha" type="text"  name="confirmarSenha"  class="form-control" v-model="confirmarSenha" />
  </p>
  <button v-on:click="addComment" type="submit" class="btn btn-primary">Comentar</button>
  </div>
</template>

<script>
  export default {
    data() {
      return {
        name: '',
        email: '',
        cpf: '',
        senha:'',
        confirmarSenha: ''
      }
    },
    methods: {
      addComment() {
        if (this.email.trim() === '') {
          return;
        }
        if (this.cpf.trim() === ''){
            return;
        }
        if (this.senha.trim() === ''){
            return;
        }
        if (this.confirmarSenha.trim() === ''){
            return;
        }
        this.$emit('add-todo', {
          name: this.name,
          email: this.email,
          cpf: this.cpf,
          senha: this.senha,
          confirmarSenha: this.confirmarSenha,
        });
        this.name = '';
        this.email = '';
        this.cpf = '';
        this.senha = '';
        this.confirmarSenha = '';
      }
    }
  }
</script>