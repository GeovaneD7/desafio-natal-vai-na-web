<template>
  <div id="contagem">
    <h3>
      {{ tempoRestante.dias }}d -
      {{ tempoRestante.horas }}h -
      {{ tempoRestante.minutos }}m -
      {{ tempoRestante.segundos }}s
    </h3>
  </div>
</template>

<script setup>
import { ref, onBeforeUnmount, onMounted } from 'vue';

// Declaração da variável reativa
const tempoRestante = ref({
  dias: 0,
  horas: 0,
  minutos: 0,
  segundos: 0,
});

// Definição da função dentro do script
function calcularTempo() {
  const dataHoje = new Date();
  const anoAtual = dataHoje.getFullYear();
  const dataNatal = new Date(`${anoAtual}-12-25T00:00:00`);

  // Ajusta para o Natal do próximo ano se já passou o Natal atual
  if (dataHoje > dataNatal) {
    dataNatal.setFullYear(anoAtual + 1);
  };

  const diferenca = dataNatal - dataHoje;

  // Calcula cada segmento da data para o Natal
  tempoRestante.value = {
    dias: Math.floor(diferenca / (1000 * 60 * 60 * 24)),
    horas: Math.floor((diferenca / (1000 * 60 * 60)) % 24),
    minutos: Math.floor((diferenca / (1000 * 60)) % 60),
    segundos: Math.floor((diferenca / 1000) % 60 )
  };
};

// Intervalo para atualizar o tempo
let intervalo;

onMounted(() => {
  calcularTempo(); // Chama a função ao montar o componente
  intervalo = setInterval(calcularTempo, 1000); // Atualiza a cada segundo
});

onBeforeUnmount(() => {
  clearInterval(intervalo); // Limpa o intervalo ao desmontar o componente
});
</script>

<style scoped lang="scss">
#contagem {
  margin-top: 3vh;
}

h3 {
  font-size: 5rem;
  color: #CD3C32;
}
</style>
