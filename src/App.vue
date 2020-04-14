<template>
  <div id="app">
    <caixas :caixinhas="caixinhas"/>
    <ferramentas :caixinhas="caixinhas" @alteraCor="alteraCor($event)" @alterarTexto="alterarTexto($event)"/>
  </div>
</template>

<script>
import Caixas from "./components/Caixas.vue";
import Ferramentas from "./components/Ferramentas.vue"
export default {
  name: "App",
  components: {
    Caixas, 
    Ferramentas
  },
  data: function() {
    return {};
  },
  methods: {
    alteraCor: function(cor) {
      this.$emit("alteraCor", {
        cor: cor,
        caixa: this.caixaSel
      });
    },
    alterarTexto: function() {
      this.$emit("alterarTexto", {
        titulo: this.titulo,
        caixa: this.caixaSel
      });
    }
  }
};
</script>

<style>
</style>
