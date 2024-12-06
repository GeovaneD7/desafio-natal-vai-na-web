<script setup>
import Logo from "./Logo.vue"
import loja from "../assets/loja.png"
import Doar from "./Doar.vue"
</script>

<template>
  <header>
    <section>
      <div id="conteudo">
        <Logo/>
        <h1>Uma <span>plataforma de doação</span> para espalhar alegria</h1>
        <p>Nessas festas de fim de ano mande um presente para a pessoa amada e compartilhe a alegria do Natal.</p>
        <Doar/>
      </div>
      <img id="loja" :src="loja" alt="">
    </section>
  </header>
</template>

<style scoped lang="scss">
header {
  background-color: #FFE9E8;
  height: 53vh;
}

section {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  padding: 5% 15%;

  #conteudo{
    display: flex;
    flex-direction: column;
    justify-content: space-around;
    align-items: start;
    width: 50%;
  }
}

#loja{
  width: 40%;
}
</style>
