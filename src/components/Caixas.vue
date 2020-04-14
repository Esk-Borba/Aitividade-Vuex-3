<template>
  <div id="caixa">
      <div class="caixinhas" v-for="(caixa, index) in caixinhas" :key="index" :style="caixa.cor">
          {{caixa.titulo}}
      </div>
  </div>
</template>

<script>
export default {
    name: "Caixas",
    computed: {
      caixinhas(){
        return this.$store.state.caixinhas
      }
    }
}
</script>

<style>
    #caixa{
        width: 300px;
        height: 120px;
        border: black 2px solid;
        margin: 30px auto 10px auto;
        display: flex;
        flex-wrap: wrap;
    }
    .caixinhas{
        width: 50px;
        height: 50px;
        border: solid black 2px;
        margin: 30px auto auto auto;
        text-align: center;
        line-height: 50px;
        user-select: none;
        cursor: pointer;
    }
</style>