<script setup>
import presentes from "../assets/gifts.png"
import Natal from "./Natal.vue"
</script>

<template>
  <section>
    <div>
      <h2>Tempo limitado</h2>
      <p>Nessas festas de fim de ano mande um presente para a pessoa amada e compartilhe a alegria do Natal.</p>
    </div>

    <Natal/>

    <img :src="presentes" alt="">
  </section>
</template>

<style scoped lang="scss">
  section {
    display: flex;
    justify-content: center;
    align-items: center;
    flex-direction: column;
  }

  div {
    display: flex;
    justify-content: space-between;
    align-items: center;
    flex-direction: column;
    height: 10vh;
    margin: 8vh 0 0;

    h2 {
      font-weight: 600;
      font-size: 3rem;
    }
    p {
      font-size: 1.4rem;
      width: 60%;
      text-align: center;
    }
  }

  img { 
    width: 20vw; 
    margin: 1vh 0 8vh;
  }
</style>
