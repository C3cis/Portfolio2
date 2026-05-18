<script setup>
import { ref } from 'vue';

const abaAtiva = ref('desenvolvimento'); // aba ativa por padrão
const abas = ['desenvolvimento', 'banco-de-dados', 'web-frontend']; // lista de abas para facilitar o controle
const cards = {
  desenvolvimento: ['Java', 'Spring Boot', 'Linux'],
  'banco-de-dados': ['MySQL', 'SQL Oracle'],
  'web-frontend': ['HTML', 'CSS', 'JavaScript', 'Vue.js']
};


</script>
<template> 
    <section id="habilidades">
            <h2>Habilidades & Tecnologias</h2>
            <p> Habilidades adquiridas e em aprendizado</p>

            <div class="abas-habilidades">
                <button :class="{ ativa: abaAtiva === 'desenvolvimento' }" @click="abaAtiva = 'desenvolvimento'">Desenvolvimento</button>
                <button :class="{ ativa: abaAtiva === 'banco-de-dados' }" @click="abaAtiva = 'banco-de-dados'">Banco de Dados</button>
                <button :class="{ ativa: abaAtiva === 'web-frontend' }" @click="abaAtiva = 'web-frontend'">Web & Front-end </button>
            </div>
            <div class="card-habilidades">
                <div 
                    v-for="card in cards[abaAtiva]" 
                    :key="card" 
                    class="card" >
                    {{ card }}
                </div>
                </div>
        </section>

</template>
<style lang="css" scoped>
#habilidades h2 {
  font-size: 2rem; /* título maior e mais impactante */
  margin-bottom: 1rem; /* espaço entre o título e o parágrafo */
  background: linear-gradient(135deg, var(--accent-purple), var(--accent-pink));
   -webkit-background-clip: text;
  background-clip: text;  
  -webkit-text-fill-color: transparent;
} 
#habilidades p {
  color: var(--text-muted); /* cor mais suave para o parágrafo */
  line-height: 1.2; /* melhora a legibilidade */
  margin-bottom: 2.5rem; /* espaço entre o parágrafo e as habilidades */
}

.abas-habilidades {
  display: flex; /* ativa o Flexbox */
  justify-content: center; /* centraliza horizontalmente as abas */
  gap: 1rem; /* espaço entre as abas */
  margin-bottom: 2rem; /* espaço entre as abas e o conteúdo */
  scale: 1.6/* aumenta o tamanho das abas para destacar mais */
  
}
.abas-habilidades button {
  background-color: transparent; /* cor de fundo para as abas */
  border: 1px solid var(--accent-purple); /* borda para destacar as abas */
  color: var(--text-primary); /* cor do texto das abas */
  padding: 0.5rem 1rem; /* espaço interno para as abas */
  border-radius: 20px;
  cursor: pointer;
}
.abas-habilidades button:hover { /* efeito de hover para os links de contato */
  color: var(--accent-purple);
  
}

.card-habilidades {
  display: flex; /* ativa o Flexbox para os cards de habilidades */
  flex-wrap: wrap; /* permite que os cards quebrem para a próxima linha se necessário */
  justify-content: center; /* centraliza horizontalmente os cards */
  gap: 1rem; /* espaço entre os cards */
}

/* Estilo dos cards de cada habilidade */
.card {
  background: var(--bg-card2); /* cor de fundo para os cards */
  padding: 3.2% 4.7%;/* espaço interno para os cards */
  border-radius: 20px; /* bordas arredondadas para um visual mais suave */
  border: 1px solid var(--accent-purple);
  color: var(--text-primary);
  font-size: 1.0rem; /* fonte legível para os cards */
}
</style>