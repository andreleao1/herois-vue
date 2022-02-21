<template>
  <div
    class="modal fade"
    id="novoHeroi"
    tabindex="-1"
    role="dialog"
    aria-labelledby="adicionar-novo-heroi"
    aria-hidden="true"
  >
    <div class="modal-dialog" role="document">
      <div class="modal-content">
        <div class="modal-header">
          <h5 class="modal-title" id="adicionar-novo-heroi">Adicionar Novo Herói</h5>
          <button type="button" class="close" data-dismiss="modal" aria-label="Close">
            <span aria-hidden="true">&times;</span>
          </button>
        </div>
        <div class="modal-body">
          <form>
            <div class="form-group">
              <label for="nomeHeroi">Nome</label>
              <input type="text" class="form-control" id="nomeHeroi" v-model="heroi.nome"/>
            </div>
            <div class="form-group">
              <label for="empresaHeroi">Empresa</label>
              <div class="input-group mb-3">
                <select class="custom-select" id="empresaHeroi" v-model="heroi.empresa">
                  <option value="null" selected disabled>Escolha uma opção</option>
                  <option value="Marvel">Marvel</option>
                  <option value="DC">DC</option>
                </select>
              </div>
            </div>
          </form>
        </div>
        <div class="modal-footer">
          <button type="button" class="btn btn-primary" @click="cadastrarHeroi" data-dismiss="modal">Cadastrar</button>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "herois-component",
  data() {
    return {
      heroi: {
          nome: null,
          empresa: null
      }, 
    };
  },
  methods: {
    cadastrarHeroi() {
        this.$emit('cadastroHeroi', this.heroi);
        this.limparDados();
    },
    limparDados() {
      this.heroi.nome = null;
      this.heroi.empresa = null;
    }
  },
};
</script>

<style></style>
