<script setup>
import curtida from "../src/assets/icon-heart-active.png"
import coracao from "../src/assets/icon-heart.png"
import {ref} from "vue"

// varialvel reativa que armazena o caminho da imagem inicial
const imagem1 = ref(coracao);
const imagem2 = ref(coracao);
const imagem3 = ref(coracao);


// Variáveis para controlar se a section foi clicada
const section1Clicada = ref(false);
const section2Clicada = ref(false);
const section3Clicada = ref(false);


// Variáveis para controlar se a imagem foi clicada



const coracaoNaoCurtido = coracao;
const coracaoCurtido = curtida;
//função que vai alternar as imagens quando clicado

const alternarImagem1 = () => {
  imagem1.value = imagem1.value === coracao ? curtida : coracao;
  section1Clicada.value = !section1Clicada.value;
  
};
const alternarImagem2 = () => {
  imagem2.value = imagem2.value === coracao ? curtida : coracao;
  section2Clicada.value = !section2Clicada.value;
  
};
const alternarImagem3 = () => {
  imagem3.value = imagem3.value === coracao ? curtida : coracao;
  section3Clicada.value = !section3Clicada.value;
  

};



</script>

<template>
 <header>
  <h1>V<span>ue</span></h1>
  <input type="text" placeholder="Pesquisar no blog">
 </header>
 <main>
  <section :style="{ border: section1Clicada ? '2px solid #E07B67' : 'none' }">
    <div >
      <p class=data>17 de ago, 2024</p>
     <!-- como trazer dados de forma dinamica? 
      {{ interpolação }}
      <p>{{}}</p>
      pra inserir em atributos usamos o v-bind
      : atalho para o v-bind
     -->
     <img :src="imagem1" @click="alternarImagem1" alt="coração" />
    </div>
    <h3>O que é linguagem de programação? Conheça as principais</h3>
    <p>Uma das mais populares vertentes da tecnologia da informação, a área de programação segue tendo muita demanda de trabalho justamente pela velocidade com que dispositivos tecnológicos vêm avançando.</p>
  </section>
  <section :style="{ border: section2Clicada ? '2px solid #E07B67' : 'none' }">
    <div>
      <p class=data>17 de ago, 2024</p>
     <!-- como trazer dados de forma dinamica? 
      {{ interpolação }}
      <p>{{}}</p>
      pra inserir em atributos usamos o v-bind
      : atalho para o v-bind
     -->
     <img :src="imagem2" @click="alternarImagem2" alt="coração"  />
    </div>
    <h3>O que é linguagem de programação? Conheça as principais</h3>
    <p>Uma das mais populares vertentes da tecnologia da informação, a área de programação segue tendo muita demanda de trabalho justamente pela velocidade com que dispositivos tecnológicos vêm avançando.</p>
  </section>
  <section :style="{ border: section3Clicada ? '2px solid #E07B67' : 'none' }">
    <div>
      <p class=data>17 de ago, 2024</p>
     <!-- como trazer dados de forma dinamica? 
      {{ interpolação }}
      <p>{{}}</p>
      pra inserir em atributos usamos o v-bind
      : atalho para o v-bind
     -->
     <img :src="imagem3" @click="alternarImagem3" alt="coração" />
      <!--  -->
    </div>
    <h3>O que é linguagem de programação? Conheça as principais</h3>
    <p>Uma das mais populares vertentes da tecnologia da informação, a área de programação segue tendo muita demanda de trabalho justamente pela velocidade com que dispositivos tecnológicos vêm avançando.</p>
  </section>
 </main>
</template>

<style scoped lang="scss">

header{
  background-color: #17171A;
  color: #E07B67;
  display: flex;
  align-items: center;
  justify-content: center;
  flex-direction: column;
  height: 20vh;

  h1{
    font-family: "Space Grotesk", sans-serif;
    font-optical-sizing: auto;

span{
  color: #ffffff;
}
    
  }

  

  input{
    width: 60vw;
    margin-top: 1rem;
    background-color: #202024;
    border: none;
    padding: 8px 0;

    &::placeholder{
      color: rgb(255, 255, 255);
      
    }
  }
}

main {
  margin: 20px auto;
  width: 90%;
  max-width: 800px;
  display: flex;
  flex-direction: column;
  gap: 25px;
 
  
}
section {

  background-color: #17171A;
  padding: 15px 20px;
  border-radius: 10px;
  
 
  display: flex;
  flex-direction: column;
  gap: 20px;



  div {
    display: flex;
  align-items: center;
  justify-content: space-between;
  margin-bottom: 10px;
  font-size: 12px;

    p {
      font-size: 12px;
      color: #A8A8B3;

     
    }

    p.data{
        color:#E07B67;
      }

    img {
      cursor: pointer;
      width: 24px;
      height: 24px;
    }
  }
  h3 {
    font-family: "Space Grotesk", sans-serif;
  font-optical-sizing: auto;
    margin: 0;
    color: #ffffff;
    font-size: 16px;
  }

  p {
    font-family: "Inter", sans-serif;
  font-optical-sizing: auto;
    margin-top: 5px;
    font-size: 14px;
    color: #E1E1E6;
  }
}









</style>
