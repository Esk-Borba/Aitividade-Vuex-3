<template>
  <div id="ferramentas">
    <select v-model="caixaSel">
      <option value selected disabled>Selecione uma caixa</option>
      <option v-for="(caixa,index) in caixinhas" :key="index" :value="index">{{ caixa.titulo }}</option>
    </select>

    <div id="paleta">
      <div
        class="cor"
        :style="cor"
        v-for="(cor,index) in cores"
        :key="index"
        @click="alteraCor(cor)"
      ></div>
    </div>

    <input type="text" placeholder="Digite o nome da caixa" v-model="titulo" />
    <button @click="alterarTexto">OK</button>
  </div>
</template>

<script>
export default {
  name: "Ferramentas",
  computed: {
    caixinhas() {
      return this.$store.state.caixinhas;
    }
  },
  data: function() {
    return {
      cores: ["background: brown", "background: yellow", "background: green"],
      caixaSel: "",
      titulo: ""
    };
  },
  methods: {
    alteraCor: function(cor) {
      this.$store.commit("alteraCor", {
        cor: cor,
        caixa: this.caixaSel
      });
    },
    alterarTexto: function() {
      this.$store.commit("alterarTexto", {
        titulo: this.titulo,
        caixa: this.caixaSel
      });
    }
  }
};
</script>

<style>
#ferramentas {
  width: 390px;
  height: 140px;
  border: solid black 2px;
  margin: 5px auto 0 auto;
  padding: 10px;
}
#ferramentas select {
  width: 300px;
}
#paleta {
  width: 390px;
  height: 140px;
  display: flex;
}
.cor {
  width: 50px;
  height: 50px;
  border: solid black 2px;
  margin: 10px auto 0 auto;
}
</style>