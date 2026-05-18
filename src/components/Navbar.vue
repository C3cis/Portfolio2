<script setup>
const emit = defineEmits(['abrirBlog', 'abrirContato'])
</script>

<template>
    <header>
        <nav>
            <span class="logo">Meu Portfólio</span>
            <ul>
                <li><a href="#" @click.prevent="emit('abrirBlog')">Blog</a></li>
                <li><a href="#" @click.prevent="emit('abrirContato')">Contatos</a></li>

            </ul>
        </nav>
    </header>
    </template>

<style lang="css">

.logo {
  font-size: 1.2rem;
  font-weight: bold;
  background: var(--gradient);
  -webkit-background-clip: text;
  background-clip: text;  
  -webkit-text-fill-color: transparent;
  
}
nav a {
  color: var(--text-primary);
  text-decoration: none;
  border: 1px solid var(--accent-purple); /* borda para destacar os links */
  padding: 0.5rem 0.5rem; /* deixa os links mais destacados */
  border-radius: 10px; /* bordas arredondadas para um visual mais suave */
  margin-right: 1rem;
  font-size:  1rem; /* aumenta o tamanho dos links para destacar mais */
}
nav ul {
  list-style: none;    /* remove os pontinhos */
  display: flex;       /* coloca os itens lado a lado */
  gap: 0.1rem;    /* espaço entre os itens */
  margin-left: auto;   /* espaço entre os itens */

}
</style>
