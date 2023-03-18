<template>
    <div class="row justify-content-center">
        <div class="col-md-6">
            <h1>Novo Produto</h1>
            <form @submit.prevent="handleSubmitForm">
                <div class="form-group">
                    <label>Nome</label>
                    <input type="text" class="form-control" v-model="produto.nome" required>
                </div>
                <div class="form-group">
                    <label for="descricaoproduto">Descrição</label>
                    <input type="text" class="form-control" v-model="produto.descricaoproduto" required maxlength="30">
                </div>
                <div class="form-group">
                    <label for="valorunitario">Valor Unitário</label>
                    <input type="text" class="form-control" v-model="produto.valorunitario" required maxlength="10">
                </div>
                <div class="form-group">
                    <label for="valortotal">Valor Total</label>
                    <input type="text" class="form-control" v-model="produto.valortotal" required maxlength="10">
                </div>
                <div class="form-group">
                    <label for="obs">Observações</label>
                    <input type="text" class="form-control" v-model="produto.obs">
                </div>                
                <div class="form-group mt-3">
                    <button class="btn btn-success btn-block w-100" type="submit">Criar</button>
                </div>
            </form>
        </div>
    </div>
</template>

<script>

import axios from 'axios'

export default {
    data() {
        return {
            produto: {
                id: '',
                nome: '',
                descricaoproduto: '',
                valorunitario: '',
                valortotal: '',
                obs: ''
            }
        }
    },
    methods: {
        handleSubmitForm() {
            let apiURL = 'http://localhost:3000/produtos'

            axios.post(apiURL, this.produto).then(() => {
                alert('Produto registrado!!')
            }).catch(error => {
                console.log(error)
            })

        }

    }
}
</script>