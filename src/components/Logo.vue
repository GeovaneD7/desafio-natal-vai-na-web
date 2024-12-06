<script setup>
import noel from "../assets/noel.png"
</script>

<template>
<div id="logo">
  <img v-bind:src="noel" alt="">
  <p>Feliz Natal</p>
</div>
</template>

<style scoped lang="scss">
  #logo {
    display: flex;
    align-items: center;
    justify-content: center;
  }

  img {
    height: 3.5vh;
  }

  p {
    font-size: 1.7rem;
    font-weight: 500;
    margin-left: 7%;
    width: 150px;
  }
</style>
