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
<style scoped>
  .container {
    max-width: 600px;
  }
span {
  max-width: 100px;
  width: 60px;
  justify-content: center;
  background-color: #0d6efd;
  background-color: white;
  border: none;
  font-size: 50px;
}

button {
  max-width: 100px;
}

h2 {
  text-align: center;
}
#ho {
  margin-left:230px ;
}

</style>
