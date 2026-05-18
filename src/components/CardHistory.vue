<script setup>
defineProps({
  titulo: String,
  data: String,
  conteudo: String
})
</script>

<template>
    <div class="card-history">
        <span class="data-artigo">{{ data }}</span>
        <h3>{{ titulo }}</h3>
        <p>{{ conteudo }}</p>
    </div>
</template>

<style lang="css" scoped>
.card-history {
  background: var(--bg-primary);
  border: 1px solid var(--accent-purple);
  border-radius: 12px; /* bordas arredondadas para um visual mais suave */
  padding: 1.2rem;
  margin-bottom: 1rem;

  

}

.card-history h3 {
  color: var(--accent-pink);
  margin-bottom: 0.3rem;
  font-size: 1rem;
}

.card-history p {
  color: var(--text-muted);
  font-size: 0.9rem;
  line-height: 1.5;
  margin-top: 0.5rem;
}
</style>