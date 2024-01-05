<script setup>
const pros = defineProps(['tarefas', 'filtro']);
</script>

<template>
    <h2 class="mt-4">Lista de tarefas</h2>
    <ul class="list-group mt-4">
        <li class="list-group-item" v-for="tarefa in pros.tarefas">
            <input @change="evento => tarefa.finalizada = evento.target.checked" :checked="tarefa.finalizada"
                :id="tarefa.titulo" type="checkbox">
            <label :class="{ done: tarefa.finalizada }" class="ms-2" :for="tarefa.titulo">
                {{ tarefa.titulo }}
            </label>
        </li>
    </ul>
</template>

<style scoped>
.done {
    text-decoration: line-through;
}
</style>