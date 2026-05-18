
<script setup>
import { ref } from 'vue';
import CardHistory from './CardHistory.vue';

const props = defineProps({
  aberto: Boolean,
  blogs: Array  // recebe a lista inteira, não item por item
})
const blogs = ref([
  { data: '4 de Maio, 2026', titulo: 'Postagem 1', conteudo: 'Teste dos componetes' },
  { data: '5 de Maio, 2026', titulo: 'Postagem 2', conteudo: 'Teste dos componetes' },
  { data: '17 de Maio, 2026', titulo: 'Postagem 3', conteudo: 'Primeira requisição via Vue.js. Chato de se escrever mas muito util :3' }
])
const emit = defineEmits(['fechar'])

function fecharBlog() {
  emit('fechar')  // avisa o App.vue para fechar
}
</script>

<template>
  <aside id="drawer-blog" :class="{ aberto: props.aberto }">
    
    <div class="blog-view">
      <h2>Blog</h2>
      <button id="fechar-blog" @click="fecharBlog">X</button>
    </div>

    <!-- aqui ficam os cards -->
    <CardHistory 
      v-for="blog in blogs"
      :key="blog.data"
      :titulo="blog.titulo"
      :data="blog.data"
      :conteudo="blog.conteudo"
    />

  </aside>
</template>


<style lang="css" scoped>

/* Quando o drawer tem a classe .aberto, desliza para dentro da tela */
#drawer-blog.aberto {
  transform: translateX(0);
}

/* Cabeçalho do drawer com título e botão X */
.blog-view {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 2rem;
}

.blog-view h2 {
  background: var(--gradient);
  -webkit-background-clip: text;
  background-clip: text;  
  -webkit-text-fill-color: transparent;
  font-size: 1.5rem;
}
.card-blog h3 {
  color: var(--accent-pink);
  margin-bottom: 0.3rem;
  font-size: 1rem;
}

.card-blog p {
  color: var(--text-muted);
  font-size: 0.9rem;
  line-height: 1.5;
  margin-top: 0.5rem;
}

/* Botão de fechar */
#fechar-blog {
  background: transparent;
  border: none;
  color: var(--text-primary);
  font-size: 1.5rem;
  cursor: pointer;
}
</style>