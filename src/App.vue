<script setup lang="ts">
const obras = [
  {
    titulo: 'The Call of Cthulhu',
    ano: '1926',
    descricao:
      'Uma investigação sobre um culto misterioso e uma entidade ancestral que repousa nas profundezas do oceano.',
  },
  {
    titulo: 'The Shadow over Innsmouth',
    ano: '1936',
    descricao:
      'Um viajante chega à decadente cidade de Innsmouth e descobre segredos que deveriam permanecer esquecidos.',
  },
  {
    titulo: 'At the Mountains of Madness',
    ano: '1936',
    descricao:
      'Uma expedição à Antártida revela vestígios de uma civilização muito mais antiga que a própria humanidade.',
  },
]
</script>

<template>
  <div class="site">
    <!-- NAVBAR -->
    <nav class="navbar">
      <div class="logo">H.P.L</div>

      <div class="nav-links">
        <a href="#inicio">Início</a>
        <a href="#autor">O Autor</a>
        <a href="#obras">Obras</a>
        <a href="#mythos">Mythos</a>
      </div>
    </nav>

    <!-- HERO -->
    <main id="inicio">
      <section class="hero">
        <div class="hero-content">
          <p class="eyebrow">O MESTRE DO HORROR CÓSMICO</p>

          <h1>
            H. P.
            <span>LOVECRAFT</span>
          </h1>

          <p class="hero-description">
            Nas profundezas do desconhecido existem horrores que a mente
            humana jamais deveria compreender.
          </p>

          <a href="#obras" class="hero-button">
            EXPLORAR AS OBRAS
          </a>
        </div>

        <div class="hero-symbol">
          <div class="eye">◉</div>
        </div>
      </section>

      <!-- AUTOR -->
      <section id="autor" class="section author">
        <div class="section-title">
          <span>01</span>
          <h2>O Autor</h2>
        </div>

        <div class="author-content">
          <div>
            <p class="quote">
              “O medo mais antigo e mais forte da humanidade é o medo do
              desconhecido.”
            </p>
          </div>

          <div class="author-text">
            <p>
              Howard Phillips Lovecraft foi um escritor americano conhecido
              principalmente por suas histórias de horror cósmico.
            </p>

            <p>
              Suas obras exploram a insignificância da humanidade diante de
              forças antigas e incompreensíveis que existem além da realidade
              conhecida.
            </p>

            <p>
              Seu universo literário deu origem ao chamado
              <strong>Cthulhu Mythos</strong>, uma das maiores influências do
              horror moderno.
            </p>
          </div>
        </div>
      </section>

      <!-- OBRAS -->
      <section id="obras" class="section works">
        <div class="section-title">
          <span>02</span>
          <h2>Obras</h2>
        </div>

        <p class="section-description">
          Alguns dos textos que ajudaram a definir o horror cósmico.
        </p>

        <div class="works-grid">
          <article
            v-for="obra in obras"
            :key="obra.titulo"
            class="work-card"
          >
            <span class="work-year">{{ obra.ano }}</span>

            <h3>{{ obra.titulo }}</h3>

            <p>{{ obra.descricao }}</p>

            <button>LER SOBRE A OBRA →</button>
          </article>
        </div>
      </section>

      <!-- MYTHOS -->
      <section id="mythos" class="section mythos">
        <div class="section-title">
          <span>03</span>
          <h2>O Cthulhu Mythos</h2>
        </div>

        <div class="mythos-content">
          <div class="mythos-text">
            <p>
              Deuses antigos, civilizações esquecidas e entidades que existem
              além da compreensão humana.
            </p>

            <p>
              O Mythos de Lovecraft apresenta um universo onde a humanidade
              ocupa apenas uma pequena e insignificante posição.
            </p>
          </div>

          <div class="entities">
            <div class="entity">
              <span>01</span>
              <h3>CTHULHU</h3>
              <p>A entidade adormecida nas profundezas de R'lyeh.</p>
            </div>

            <div class="entity">
              <span>02</span>
              <h3>AZATHOTH</h3>
              <p>O caos primordial além da compreensão humana.</p>
            </div>

            <div class="entity">
              <span>03</span>
              <h3>YOG-SOTHOTH</h3>
              <p>Aquele que é a chave e o guardião dos portais.</p>
            </div>

            <div class="entity">
              <span>04</span>
              <h3>NYARLATHOTEP</h3>
              <p>O Caos Rastejante, mensageiro dos deuses exteriores.</p>
            </div>
          </div>
        </div>
      </section>
    </main>

    <!-- FOOTER -->
    <footer>
      <p>H.P. LOVECRAFT</p>
      <span>THE UNKNOWN AWAITS</span>
    </footer>
  </div>
</template>

<style>
@import url('https://fonts.googleapis.com/css2?family=Cinzel:wght@400;500;600;700;800&family=Inter:wght@300;400;500;600&display=swap');

:root {
  --background: #080a09;
  --background-light: #101512;
  --green: #6f9279;
  --green-light: #9bb6a1;
  --text: #d8d5c9;
  --text-muted: #858a83;
  --border: #28332c;
}

* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

html {
  scroll-behavior: smooth;
}

body {
  background: var(--background);
  color: var(--text);
  font-family: 'Inter', sans-serif;
}

a {
  color: inherit;
  text-decoration: none;
}

.site {
  min-height: 100vh;
  overflow: hidden;
}

/* NAVBAR */

.navbar {
  height: 80px;
  padding: 0 7%;
  display: flex;
  align-items: center;
  justify-content: space-between;
  border-bottom: 1px solid var(--border);
  position: fixed;
  top: 0;
  width: 100%;
  z-index: 100;
  background: rgba(8, 10, 9, 0.9);
  backdrop-filter: blur(10px);
}

.logo {
  font-family: 'Cinzel', serif;
  font-size: 22px;
  letter-spacing: 4px;
  color: var(--green-light);
}

.nav-links {
  display: flex;
  gap: 35px;
}

.nav-links a {
  font-size: 12px;
  letter-spacing: 2px;
  color: var(--text-muted);
  transition: 0.3s;
}

.nav-links a:hover {
  color: var(--green-light);
}

/* HERO */

.hero {
  min-height: 100vh;
  padding: 150px 10% 80px;
  display: flex;
  align-items: center;
  justify-content: space-between;
  position: relative;
  background:
    radial-gradient(circle at 75% 50%, #17241c 0%, transparent 35%),
    var(--background);
}

.hero::before {
  content: '';
  position: absolute;
  inset: 0;
  opacity: 0.08;
  background-image:
    linear-gradient(var(--green) 1px, transparent 1px),
    linear-gradient(90deg, var(--green) 1px, transparent 1px);
  background-size: 70px 70px;
  mask-image: linear-gradient(to right, transparent, black, transparent);
}

.hero-content {
  max-width: 700px;
  position: relative;
  z-index: 2;
}

.eyebrow {
  color: var(--green);
  font-size: 11px;
  letter-spacing: 5px;
  margin-bottom: 25px;
}

h1 {
  font-family: 'Cinzel', serif;
  font-size: clamp(70px, 10vw, 150px);
  line-height: 0.85;
  font-weight: 500;
  letter-spacing: -5px;
}

h1 span {
  display: block;
  color: var(--green-light);
}

.hero-description {
  max-width: 500px;
  margin-top: 40px;
  color: var(--text-muted);
  line-height: 1.8;
  font-size: 16px;
}

.hero-button {
  display: inline-block;
  margin-top: 35px;
  padding: 16px 28px;
  border: 1px solid var(--green);
  color: var(--green-light);
  font-size: 11px;
  letter-spacing: 2px;
  transition: 0.3s;
}

.hero-button:hover {
  background: var(--green);
  color: #080a09;
}

/* SYMBOL */

.hero-symbol {
  width: 350px;
  height: 350px;
  border: 1px solid var(--border);
  border-radius: 50%;
  display: grid;
  place-items: center;
  position: relative;
}

.hero-symbol::before,
.hero-symbol::after {
  content: '';
  position: absolute;
  border: 1px solid var(--border);
  border-radius: 50%;
}

.hero-symbol::before {
  width: 260px;
  height: 260px;
}

.hero-symbol::after {
  width: 170px;
  height: 170px;
}

.eye {
  font-size: 90px;
  color: var(--green);
  text-shadow: 0 0 30px rgba(111, 146, 121, 0.5);
}

/* SECTIONS */

.section {
  padding: 120px 10%;
  border-top: 1px solid var(--border);
}

.section-title {
  display: flex;
  align-items: center;
  gap: 20px;
  margin-bottom: 60px;
}

.section-title span {
  color: var(--green);
  font-size: 11px;
  letter-spacing: 2px;
}

.section-title h2 {
  font-family: 'Cinzel', serif;
  font-size: 42px;
  font-weight: 500;
}

/* AUTHOR */

.author {
  background: var(--background-light);
}

.author-content {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 100px;
}

.quote {
  font-family: 'Cinzel', serif;
  font-size: 30px;
  line-height: 1.5;
  color: var(--green-light);
}

.author-text {
  color: var(--text-muted);
  line-height: 1.9;
}

.author-text p {
  margin-bottom: 20px;
}

.author-text strong {
  color: var(--green-light);
}

/* WORKS */

.section-description {
  color: var(--text-muted);
  margin-top: -35px;
  margin-bottom: 50px;
}

.works-grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 20px;
}

.work-card {
  min-height: 350px;
  padding: 35px;
  border: 1px solid var(--border);
  background: #0c100e;
  transition: 0.4s;
  display: flex;
  flex-direction: column;
}

.work-card:hover {
  transform: translateY(-8px);
  border-color: var(--green);
}

.work-year {
  color: var(--green);
  font-size: 12px;
  letter-spacing: 2px;
}

.work-card h3 {
  font-family: 'Cinzel', serif;
  font-size: 24px;
  margin: 30px 0 20px;
  color: var(--green-light);
}

.work-card p {
  color: var(--text-muted);
  line-height: 1.7;
  font-size: 14px;
  flex: 1;
}

.work-card button {
  margin-top: 25px;
  padding: 12px 0;
  background: transparent;
  border: none;
  border-top: 1px solid var(--border);
  color: var(--green);
  text-align: left;
  cursor: pointer;
  letter-spacing: 2px;
  font-size: 10px;
}

/* MYTHOS */

.mythos {
  background:
    radial-gradient(circle at 50% 50%, #132019, transparent 60%),
    var(--background);
}

.mythos-content {
  display: grid;
  grid-template-columns: 0.8fr 1.2fr;
  gap: 100px;
}

.mythos-text {
  color: var(--text-muted);
  line-height: 1.9;
  font-size: 16px;
}

.mythos-text p {
  margin-bottom: 25px;
}

.entities {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 20px;
}

.entity {
  padding: 30px;
  border: 1px solid var(--border);
}

.entity span {
  color: var(--green);
  font-size: 10px;
}

.entity h3 {
  font-family: 'Cinzel', serif;
  margin: 20px 0 10px;
  color: var(--green-light);
}

.entity p {
  color: var(--text-muted);
  font-size: 13px;
  line-height: 1.6;
}

/* FOOTER */

footer {
  padding: 50px 10%;
  border-top: 1px solid var(--border);
  display: flex;
  justify-content: space-between;
  color: var(--text-muted);
  font-size: 10px;
  letter-spacing: 3px;
}

footer p {
  color: var(--green);
}

/* RESPONSIVO */

@media (max-width: 900px) {
  .hero {
    flex-direction: column;
    align-items: flex-start;
    gap: 80px;
  }

  .hero-symbol {
    width: 250px;
    height: 250px;
  }

  .works-grid {
    grid-template-columns: 1fr;
  }

  .author-content,
  .mythos-content {
    grid-template-columns: 1fr;
    gap: 50px;
  }
}

@media (max-width: 600px) {
  .navbar {
    padding: 0 5%;
  }

  .nav-links {
    display: none;
  }

  .section {
    padding: 80px 7%;
  }

  h1 {
    font-size: 60px;
  }

  .entities {
    grid-template-columns: 1fr;
  }

  footer {
    flex-direction: column;
    gap: 15px;
  }
}
</style>