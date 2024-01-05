<script setup>
const props = defineProps(['cadastraTarefa', 'tarefaTemp', 'trocarFiltro', 'editarTarefaTemp']);
</script>

<template>
    <form @submit.prevent="props.cadastraTarefa">
        <div class="row">
            <div class="col">
                <input :value="props.tarefaTemp" @change="props.editarTarefaTemp" required
                    type="text" class="form-control" placeholder="Digite aqui a descrição da tarefa" />
            </div>
            <div class="col-md-2">
                <button type="submit" class="btn btn-primary">Adicionar</button>
            </div>
            <div class="col-md-2">
                <select @change="props.trocarFiltro" class="form-select">
                    <option value="todas">Todas tarefas</option>
                    <option value="pendentes">Pendentes</option>
                    <option value="finalizadas">Finalizadas</option>
                </select>
            </div>
        </div>
    </form>
</template>