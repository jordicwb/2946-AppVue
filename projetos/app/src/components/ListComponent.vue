<template>
    <div class="justify-content-center">
        <h1>Lista de Produtos</h1>
        <div class="row">
            <div class="col-md-12">
                <div class="table-responsive">
                    <table class="table table-striped">
                        <thead class="table-dark">
                            <tr>
                                <th>Nome</th>
                                <th>Descrição</th>
                                <th>Valor Unitário</th>
                                <th>Valor Total</th>
                                <th>Observações</th>
                                <th class="text-end">Ações</th>
                            </tr>
                        </thead>
                        <tbody>
                            <tr v-for="produto in produtos" :key="produto.id">
                                <td>{{ produto.nome }}</td>
                                <td>{{ produto.descricaoproduto }}</td>
                                <td>{{ produto.valorunitario }}</td>
                                <td>{{ produto.valortotal }}</td>
                                <td>{{ produto.obs }}</td>
                                <td class="text-end">
                                    <router-link :to="{ name: 'edit', params: { id: produto.id } }"
                                        class="btn btn-success me-2">
                                        Editar
                                    </router-link>

                                    <button @click.prevent="excluir(produto)" class="btn btn-danger">Excluir </button>
                                </td>
                            </tr>
                        </tbody>
                    </table>
                </div>
            </div>
        </div>
    </div>
</template>

<script>

import axios from "axios"

export default {
    data() {
        return {
            produtos: []
        }
    },
    created() {
        let apiURL = 'http://localhost:3000/produtos'
        axios.get(apiURL).then((res) => {
            this.produtos = res.data
        }).catch(error => {
            console.log(error)
        })
    },
    methods: {
        excluir(produto) {
            alert(JSON.stringify(produto))
        }
    }


}

</script>