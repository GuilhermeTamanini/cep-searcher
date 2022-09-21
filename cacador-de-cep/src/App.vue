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
        <button type="submit" id="ho" class="form-control btn btn-primary">Procurar</button>
      </div>
    </form>
    <form class="end">
      <label for="rua">Rua</label>
      <input class="form-control" type="text" v-model="endereco.logradouro" />
      <label for="=num">bairro</label>
      <input class="form-control" type="text" v-model="endereco.bairro" />
      <label for="cidade">cidade</label>
      <input class="form-control" type="text" v-model="endereco.localidade" />
      <label for="uf">UF</label>
      <input class="form-control" type="text" v-model="endereco.uf" />
      <label for="=ibge">ibge</label>
      <input class="form-control" type="text" v-model="endereco.ibge" />
      <label for="ddd">DDD</label>
      <input class="form-control" type="text" v-model="endereco.ddd" />
      <label for="siafi">siafi</label>
      <input class="form-control" type="text" v-model="endereco.siafi" />
    </form>
  </div>
</template>
<style>
button {
  max-width: 100px;
  padding-left: 200px;
}
div {
  flex-direction: row;
}
h2 {
  text-align: center;
}
#ho {
  margin-left: 600px;
}
</style>
