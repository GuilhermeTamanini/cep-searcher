<script>
import axios from "axios";
export default {
  data() {
    return {
      cdp: "",
      endereco: {},
    };
  },
  methods: {
    async buscar() {
      const url = `https://viacep.com.br/ws/${this.cep}/json/`;
      const res = await axios.get(url);
      this.endereco = res.data;
    },
  },
};
</script>
<template>
  /*25905685 */
  <div class="container">
    <h2>Insira seu CEP</h2>
    <form @submit.prevent="buscar">
      <div class="mb-3">
        <input
          type="number"
          class="form-control"
          placeholder="Ex:89245000"
          v-model="cep"
        />
      </div>

      <div class="mb-3">
        <button type="submit" id="ho" class="form-control btn btn-primary">
          Procurar
        </button>
      </div>
    </form>
    <form class="end">
      <div class="input-group input-group-sm mb-3">
        <span class="input-group-text" id="inputGroup-sizing-sm">Rua</span>
        <input class="form-control" type="text" v-model="endereco.logradouro" />
      </div>

      <div class="input-group input-group-sm mb-3">
        <span class="input-group-text" id="inputGroup-sizing-sm">Bairro</span>
        <input class="form-control" type="text" v-model="endereco.bairro" />
      </div>

      <div class="input-group input-group-sm mb-3">
        <span class="input-group-text" id="inputGroup-sizing-sm">Cidade</span>
        <input class="form-control" type="text" v-model="endereco.localidade" />
      </div>

      <div class="input-group input-group-sm mb-3">
        <span class="input-group-text" id="inputGroup-sizing-sm">UF</span>
        <input class="form-control" type="text" v-model="endereco.uf" />
      </div>

      <div class="input-group input-group-sm mb-3">
        <span class="input-group-text" id="inputGroup-sizing-sm">Ibge</span>
        <input class="form-control" type="text" v-model="endereco.ibge" />
      </div>

      <div class="input-group input-group-sm mb-3">
        <span class="input-group-text" id="inputGroup-sizing-sm">DDD</span>
        <input class="form-control" type="text" v-model="endereco.ddd" />
      </div>

      <div class="input-group input-group-sm mb-3">
        <span class="input-group-text" id="inputGroup-sizing-sm">Siafi</span>
        <input class="form-control" type="text" v-model="endereco.siafi" />
      </div>

    </form>
  </div>
</template>
<style>
span {
  max-width: 100px;
  width: 60px;
  justify-content: center;
  background-color: #0d6efd;
}
button {
  max-width: 100px;
  padding-left: 200px;
}
div {
  flex-direction: row;
  margin-top: 10px;
  margin-bottom: 10px;
}
h2 {
  text-align: center;
}
#ho {
  margin-left: 600px;
}
</style>
