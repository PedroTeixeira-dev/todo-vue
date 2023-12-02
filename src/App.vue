<script setup>
import { reactive } from 'vue';


const estado = reactive({
  tarefas: [
    {
      titulo: 'Estudar ES6',
      finalizada: false,
    },
    {
      titulo: 'Estudar SASS',
      finalizada: false,
    },
    {
      titulo: 'Ir para a academia',
      finalizada: true,
    }
  ]
})

</script>

<template>
  <div class="container">
    <header class="p-5 mb-4 mt-4 bg-light rounded-3">
      <h1>Minhas Tarefas</h1>
      <p>
        Voce possui 7 tarefas pendentes
      </p>
    </header>
    <form>.
    <div class="row">
      <div class="col">
        <input type="text" placeholder="Digite aqui a descricao da tarefa" class="form-control">
      </div>
      <div class="col-md-2">
        <button type="submit" class="btn btn-primary">Cadastrar</button>
      </div>
      <div class="col-md-3">
        <select class="form-control">
          <option value="todas">Todas tarefas</option>
          <option value="pendentes">tarefas pendentes</option>
          <option value="finalizadas">Tarefas finalizadas</option>
        </select>
      </div>
    </div>
  </form>
  <ul class="list-group mt-4">
    <li class="list-group-item" v-for="tarefa in estado.tarefas">
      <input :checked="tarefa.finalizada" :id="tarefa.titulo" type="checkbox">
      <label :class="{done: tarefa.finalizada === true}" class="ms-2" :for="tarefa.titulo">
        {{ tarefa.titulo }}
      </label>
    </li>
  </ul>
  </div>
</template>

<style scoped>
  .done {
    color: rgb(22, 211, 31);
    text-decoration: line-through;
  }
</style>
