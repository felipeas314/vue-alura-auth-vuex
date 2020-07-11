<template>
  <div class="container">
    <h1>Novo usuário</h1>
    <form @submit.prevent="sendForm">
      <div class="form-group">
        <label for="nome">Nome</label>
        <input type="text" class="form-control" v-model="usuario.nome">
      </div>
      <div class="form-group">
        <label for="nome">Email</label>
        <input type="email" class="form-control" v-model="usuario.email">
      </div>
      <div class="form-group">
        <label for="nome">Senha</label>
        <input type="password" class="form-control" v-model="usuario.senha">
      </div>
      <button class="btn btn-primary" type="submit">Salvar</button>
    </form>
  </div>
</template>

<script>

import axios from 'axios';

export default {
  data() {
    return {
      usuario : {
        nome: '',
        senha: '',
        email: ''
      }
    }
  },
  methods: {
    sendForm() {
      axios.post('http://localhost:8000/auth/register',this.usuario)
        .then(response => console.log('qwer',response))
        .catch(err => console.log('asdf',err));
    }
  }  
}
</script>

<style scoped>

</style>