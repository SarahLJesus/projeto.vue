<script setup>
    const nome = 'Sarah'
    const idade = 16

    function inverter(texto) {
        return texto.split('').reverse().join('')
    }

    function saudacao() {
        return `Olá, ${nome}!`
    }
    function alerta(){
    return alert(`Olá ${nome}!`);
  };

  import { ref } from 'vue';

  const contador = ref(0);

  function incrementar() {
    contador.value++;
  }

  function decrementar() {
    if (contador.value > 0) {
      contador.value--;
    }
  }

  function reiniciar() {
    contador.value = 0;
  }

</script>

<template>
    <div class="info">
        <h1>INFORMAÇÕES SARAH</h1>
        <p>Nome: {{ nome }} </p>
        <p>Idade: {{ idade }}  anos</p>
        <hr />
        <p>Para completar 50 anos faltam: {{ 50 - idade }}  anos</p>
        <p>O nome tem {{ nome.length }}  caracteres</p>
        <p>O nome invertido é: {{ inverter(nome.toUpperCase()) }} </p>
        <hr />
        
        <p> {{ saudacao() }}  </p>
        <button v-on:click="alerta">Clique aqui</button>
    </div>
    
    <div class="outro">
    <h1>Contador</h1>
    <p> {{ contador }} </p>
    <button @click="incrementar">Incrementar</button>
    <button @click="decrementar">Decrementar</button>
    <button @click="reiniciar">Reiniciar</button>

    <div
      :style="{ backgroundColor: contador > 10 ? 'green' : 'red' }"
    >
      <p v-if="contador > 10">Seu valor está maior que 10</p>
      <p v-else>Seu valor está menor ou igual que 10</p>
    </div>
  </div>

</template>

<style scoped>
.info {
  background-color: rgba(35,12,22,1);
  padding: 20px 30px;
  color: rgb(183, 210, 219);
  border-radius: 10px;
}

.outro {
  background-color: rgba(35,12,22,1);
  padding: 20px 30px;
  color: rgb(183, 210, 219);
  border-radius: 10px;
  
}

h1 {
  color: white;
  font-weight: bold;
  font-size: 1.5em;
}

button {
  background-color:rgb(71, 45, 56);
  text-emphasis-color: white;
  color: white;
  
}
</style>