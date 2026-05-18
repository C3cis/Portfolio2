<script setup >
import Navbar from './components/Navbar.vue';
import DrawerBlog from './components/DrawerBlog.vue'; 
import DrawerContato from './components/DrawerContato.vue';
import HeroSection from './components/HeroSection.vue';
import Habilidades from './components/Habilidades.vue';
import Trajetoria from './components/Trajetoria.vue';

import { ref } from 'vue';


const drawerBlogAberto = ref(false)
const drawerContatoAberto = ref(false)

function abrirBlog() {
  drawerBlogAberto.value = true
}

function fecharBlog() {
  drawerBlogAberto.value = false
}

function abrirContato() {
  drawerContatoAberto.value = true
}
function fecharContato() {
  drawerContatoAberto.value = false
}


</script>

<template>
<HeroSection/>
<Habilidades/>
<Trajetoria/>
<Navbar @abrirBlog="abrirBlog" @abrirContato="abrirContato"/>
  <DrawerBlog :aberto="drawerBlogAberto" :blogs="blogs" @fechar="fecharBlog"/>
  <DrawerContato :aberto="drawerContatoAberto" @fechar="fecharContato" />
</template>

<style lang="css">

body {
  background: var(--gradient-body);
  background-attachment: fixed;
  color: var(--text-primary);
  font-family: sans-serif;
}

header {
  position: fixed;
    top: 0;
    width: 100%;
    background-color: var(--bg-card);
    padding: 1rem 2rem;
}
nav {
  display: flex;          /* ativa o Flexbox — sem isso nada funciona */
  align-items: center;    /* centraliza verticalmente logo e links */
  background-color: var(--bg-card2);
    padding: 1rem 2rem;
  
}
#principal {
  display:  grid; /* espaço para o header fixo */
  grid-template-columns: 2fr 1fr; /* 2 partes para o texto, 1 parte para a imagem */
  align-items: center; /* centraliza verticalmente o conteúdo */
  gap: 2rem; /* espaço entre o texto e a imagem */
  padding: 3rem 4rem 5rem; /* espaço para o header fixo*/
  min-height: 60vh; /* garante que a seção ocupe toda a altura da tela */
}
#habilidades {
  padding: 1rem; /* espaço interno para a seção */
  text-align: center; /* centraliza o texto */
  gap: 2rem; /* espaço entre os elementos */
  font-size: 1.3rem; /* fonte moderna e legível */
 
}
#trajetoria {
  padding: 5%; /* espaço interno para a seção */
  text-align: center; /* centraliza o texto */
  gap: 2rem; /* espaço entre os elementos */
}

#drawer-blog {
  position: fixed;
  top: 0;
  right: 0;
  width: 400px;
  height: 100%;
  background: var(--bg-card);
  padding: 2rem;
  transform: translateX(100%); /* escondido fora da tela à direita */
  transition: transform 0.3s ease; /* animação suave ao deslizar */
  z-index: 101; /* fica na frente do overlay */
  overflow-y: auto; /* scroll interno se o conteúdo for longo */
}
#drawer-contato {
  position: fixed;
  top: 0;
  right: 0;
  width: 420px;
  height: 100%;
  background: var(--bg-card);
  
  padding: 2rem;
  transform: translateX(100%);
  transition: transform 0.3s ease;
  z-index: 101;
  overflow-y: auto;
}
</style>