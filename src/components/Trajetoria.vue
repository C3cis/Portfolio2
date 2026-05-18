<script setup>
import { ref } from 'vue';
import CardHistory from './CardHistory.vue';
import { onMounted } from 'vue'

onMounted(() => {
  const itens = document.querySelectorAll('.card-history') // seleciona os itens da linha do tempo
  
  const observer = new IntersectionObserver((entries) => {
    entries.forEach((entry) => {
      if (entry.isIntersecting) {
        entry.target.classList.add('visivel')
      }
    })
  }, { threshold: 0.2 })

  itens.forEach((item) => observer.observe(item))
})

const trajetoria = ref([
  { data: 'Janeiro de 2020', titulo: 'Início da Jornada', conteudo: 'Comecei minha jornada no mundo da tecnologia, explorando diferentes áreas e descobrindo minha paixão por desenvolvimento de software.' },
  { data: 'Agosto de 2021', titulo: 'Primeira Experiência Profissional', conteudo: 'Consegui meu primeiro estágio em uma empresa de tecnologia, onde pude aplicar meus conhecimentos e aprender na prática sobre desenvolvimento web.' },
])
</script>
<template>
    <section id="trajetoria">
  <h2>Minha Jornada</h2>
  <p>Minha trajetória de aprendizado e crescimento profissional.</p>
    <div class="timeline-container">
        <CardHistory 
            v-for="item in trajetoria"
            :key="item.data"
            :titulo="item.titulo"
            :data="item.data"
            :conteudo="item.conteudo"
        />
    </div>
</section>
</template>
<style lang="css" scoped>   
#trajetoria h2 {
    font-size: 2rem; /* título maior e mais impactante */
  margin-bottom: 1rem; /* espaço entre o título e o parágrafo */
  background: linear-gradient(100deg, var(--accent-purple), var(--accent-pink));
   -webkit-background-clip: text;
  background-clip: text; 
  -webkit-text-fill-color: transparent;
}
#trajetoria p {
  color: var(--text-muted); /* cor mais suave para o parágrafo */
  line-height: 1.2; /* melhora a legibilidade */
  margin-bottom: 1.5rem; /* espaço entre o parágrafo e a linha do tempo */

}

#trajetoria > p { /* estilo específico para o parágrafo introdutório da seção */
  color: var(--text-muted); /* cor mais suave para o parágrafo */
  margin-bottom: 3rem;
}

/* Contêiner — position relative permite criar a linha do meio */
.timeline-container  {
  position: relative; /* necessário para a linha vertical do meio */
  max-width: 800px; /* largura máxima para a linha do tempo */
  margin: 0 auto; /* centraliza a linha do tempo horizontalmente */
}
.timeline-container::before {
  content: '';
  position: absolute;
  left: 50%;
  top: 0;
  bottom: 0;
  width: 2px;
  background: var(--gradient);
  transform: translateX(-50%);
  z-index: 0; /* fica atrás dos cards */
}

/* Cada card ocupa metade da largura */
.card-history {
  width: 45%;
  background: var(--bg-card);
  border: 1px solid var(--accent-purple);
  border-radius: 12px;
  padding: 1.5rem;
  margin-bottom: 2rem;
  text-align: left;
   

  /* animação de scroll */
  opacity: 0;
  transform: translateY(40px);
  transition: opacity 0.6s ease, transform 0.6s ease;
}

/* Itens ímpares — ficam na esquerda */
.card-history:nth-child(odd) { /* seleciona os itens ímpares da linha do tempo */
  margin-right: auto;
}

/* Itens pares — ficam na direita */
.card-history:nth-child(even) { /* seleciona os itens pares da linha do tempo */
  margin-left: auto;
}
/* Quando o JS adiciona .visivel */
.card-history.visivel {
  opacity: 1;
  transform: translateY(0);
}

.card-history h3 { /* título de cada item da linha do tempo */
  color: var(--accent-pink);
  font-size: 1.0rem;
  margin-bottom: 0.5rem;
}

.card-history p { /* parágrafo de cada item da linha do tempo */
  color: var(--text-muted);
  font-size: 0.95rem;
  line-height: 1.5;
}

.data-artigo { /* estilo para a data de cada artigo na linha do tempo */
  font-size: 0.99rem;
  color: var(--accent-purple);
  display: block;
  margin-bottom: 0.5rem;
}
.card-history.visivel {
  opacity: 1; /* torna a linha totalmente opaca quando visível */
  transform: translateY(0); /* move a linha para sua posição original quando visível */
}

</style>