<template>
  <div class="container table-style">
    <button type="button" class="btn btn-danger mt-3" data-toggle="modal" data-target="#novoHeroi">Adicionar Herói</button>
    <NovoHeroi id="novoHeroi" @cadastroHeroi="adicionarHeroi" />
      <div id="herois-component" class="row">
        <div class="col-sm">
          <table class="table mt-2">
            <thead>
              <tr>
                <th scope="col">Heróis da Marvel</th>
              </tr>
            </thead>
            <tbody v-for="(heroi, indice) in herois" :key="indice">
              <tr scope="row" v-if="heroi.empresa==='Marvel'">
                <td>{{ heroi.nome }}</td>
              </tr>
            </tbody>
          </table>
        </div>
        <div class="col-sm">
          <table class="table mt-2">
              <thead>
                <tr>
                  <th scope="col">Heróis da DC</th>
                </tr>
              </thead>
            <tbody v-for="(heroi, indice) in herois" :key="indice">
              <tr scope="row" v-if="heroi.empresa==='DC'">
                <td>{{ heroi.nome }}</td>
              </tr>
            </tbody>
          </table>
        </div>
      </div>
  </div>
</template>

<script>
import NovoHeroi from './NovoHeroi.vue'

export default {
  name: "herois-component",
  components: {
    NovoHeroi
  },
  data() {
    return {
      herois: [
        {
          nome: "Hulk",
          empresa: "Marvel",
        },
        {
          nome: "Flash",
          empresa: "DC",
        },
      ],
    };
  },
  methods: {
    adicionarHeroi(heroi) {
      let novoHeroi = {
        nome: heroi.nome,
        empresa: heroi.empresa
      }
      this.herois.push(novoHeroi);
    }
  }
};
</script>

<style>
  .table-style {
    background-color: white;
  }
</style>
