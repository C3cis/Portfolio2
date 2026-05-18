<script setup> 
</script>

<template> 
      <section id="principal">
            <div class="textoPrincipal">
                <h1><br>Desenvolvedora<span> Back-end Júnior</span></h1>
                <p> <br> estudante de Sistemas de Informação, atualmente cursando o 3º semestre. Atuo como estagiária no Centro Brasileiro de Pesquisas Físicas (CBPF).
                Direciono minha formação para desenvolvimento web, com foco em back-end utilizando linguagem Java e framework como Spring Boot. 
                Meus estudos também corroboram para o aprofundamento e experiência em Linux e tecnologias web, buscando desenvolver aplicações cada vez mais estruturadas e eficientes.
                Este portfólio reúne meus primeiros projetos e evolução como desenvolvedora. </p>
                <div class="redesSociais">
    <a href="https://github.com/C3cis" target="_blank">
        <i class="fa-brands fa-github"></i>
    </a>

    <a href="https://www.linkedin.com/feed/" target="_blank">
        <i class="fa-brands fa-linkedin-in"></i>
    </a>
</div>
            </div>
            <div class="imagemPrincipal">
                <img src="/fotoPerfil.jpeg" alt="Imagem Principal">
            </div>
        </section>

</template>

<style lang="css" scoped>  
#principal p {
  font-size: 1.0rem; /* aumenta texto */
  line-height: 1.6; /* melhora a legibilidade */
  color: var(--text-muted); /* cor mais suave para o parágrafo */
  font-family: sans-serif;
  margin-bottom: 2.5rem; /* fonte mais moderna para o parágrafo */
  max-width: 85%;
  text-align: justify; /* justifica o texto para um visual mais limpo */
}
.redesSociais a {
    gap: 1rem; /* espaço entre o ícone e o texto */
    color: var(--text-primary);
    text-decoration: none; /* remove o sublinhado */
    border: 1px solid var(--accent-purple); /* borda para destacar os links */
    padding: 0.5rem 1rem; /* deixa os links mais destacados */
    border-radius: 20px; /* bordas arredondadas para um visual mais suave */
   vertical-align: middle; /* centraliza verticalmente o ícone e o texto */
    margin-right: 1rem;
    font-size:  1.3rem; /* aumenta o tamanho dos links para destacar mais */
    transition: color 0.3s ease; 
}
.redesSociais a:hover { /* efeito de hover para os links de contato */
  color: var(--accent-purple);
}
.imagemPrincipal img {
  display: flex;
  justify-content: center; /* centraliza horizontalmente a imagem */
  width: 100%; /* faz a imagem ocupar toda a largura disponível*/
  max-width: 500px; /* limita o tamanho da imagem */
  height: 200px; /* mantém a proporção da imagem */
  width: 250px;
  height: 250px;
  border-radius: 50%; /* deixa redondo */
  object-fit: cover; /* evita distorção */
  border: 3px solid var(--accent-purple); /* borda para destacar a imagem */
  box-shadow: 0 0 25px rgba(168, 85, 247, 0.4); /* sombra suave para destacar a imagem */
  transition: 0.3s;
  
}
.imagemPrincipal img:hover {
  transform: scale(1.05); /* leve zoom ao passar o mouse */
  box-shadow: 0 0 35px rgba(168, 85, 247, 0.6); /* sombra mais intensa no hover */
} 
</style>