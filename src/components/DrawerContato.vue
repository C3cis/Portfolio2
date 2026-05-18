<script setup>
import { ref } from 'vue';
const props = defineProps({
  aberto: Boolean
})

const emit = defineEmits(['fechar'])
function fecharContato() {
  emit('fechar')
}
</script>
<template>
    <div id="drawer-contato" :class="{ aberto: props.aberto }">
  <div class="contato-header">
    <h2>Contato</h2>
    <button id="fechar-contato" @click="fecharContato">✕</button>
  </div>
  <div class="contato-card">
    <h3>Conecte-se Comigo</h3>
    <p>Estou aberta a oportunidades, projetos e trocas de conhecimento. 
        Se quiser conversar ou saber mais sobre meu trabalho, é só entrar em contato.
        </p>

    <div class="contato-links">
  <a href="mailto:ceciliaponte0124@gmail.com">
    <i class="fa-solid fa-envelope"></i>
    <span>cecilia@gmail.com</span>
  </a>

  <a href="https://github.com/C3cis" target="_blank">
    <i class="fa-brands fa-github"></i>
    <span>github.com/C3cis</span>
  </a>

  <a href="https://linkedin.com/in/cecis" target="_blank">
    <i class="fa-brands fa-linkedin-in"></i>
    <span>linkedin.com/in/cecis</span>
  </a>
</div>
  </div>
    </div>
</template>

<style lang="css" scoped>


#drawer-contato.aberto {
  transform: translateX(0);
}

.contato-header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 2rem;
   
}

#drawer-contato h2 {
  font-size: 1.5rem;
  background: var(--gradient);
  -webkit-background-clip: text;
  background-clip: text;  
  -webkit-text-fill-color: transparent;
}
.contato-card {
  background: var(--bg-primary);
  border: 1px solid var(--accent-purple);
  border-radius: 12px;
  padding: 1.5rem;
}
.contato-card h3 {
  font-size: 1.3rem;
  color: var(--accent-pink);
  margin-bottom: 0.8rem;
}
.contato-card p {
  color: var(--text-muted);
  line-height: 1.6;
  margin-bottom: 1.5rem;
}
#fechar-contato {
  background: transparent;
  border: none;
  color: var(--text-primary);
  font-size: 1.5rem;
  cursor: pointer;
}
.contato-links {
  display: flex;
  flex-direction: column; /* empilha os links em coluna */
  gap: 1rem;
}

.contato-links a {
  display: flex;
  align-items: center;
  gap: 0.9rem;
  color: var(--text-primary);
  text-decoration: none;
  font-size: 0.95rem;
  transition: color 0.3s ease; /* animação suave para a cor dos links */
  
}
.contato-links a i {
    font-size: 1.2rem;
    min-width: 20px; 
    border: 1px solid var(--accent-purple); /* borda para destacar os links */
    padding: 0.5rem 1rem; /* deixa os links mais destacados */
    border-radius: 20px; /* bordas arredondadas para um visual mais suave */
  
}

.contato-links a:hover { /* efeito de hover para os links de contato */
  color: var(--accent-pink);
}
</style>