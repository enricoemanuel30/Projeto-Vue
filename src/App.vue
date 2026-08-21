<script setup lang="ts">
const obras = [
  {
    titulo: 'The Call of Cthulhu',
    ano: '1926',
    categoria: 'Conto',
    imagem: 'https://commons.wikimedia.org/wiki/Special:FilePath/Weirdtales-1928-02-thecallofcthulhu.jpg',
    descricao:
      'Um culto secreto, sonhos perturbadores e a descoberta de uma entidade ancestral adormecida nas profundezas do Pacífico.',
  },
  {
    titulo: 'The Shadow over Innsmouth',
    ano: '1936',
    categoria: 'Conto',
    imagem: 'https://commons.wikimedia.org/wiki/Special:FilePath/The_Shadow_over_Innsmouth.png',
    descricao:
      'Uma cidade decadente, habitantes estranhos e uma linhagem que esconde uma ligação aterradora com o oceano.',
  },
  {
    titulo: 'At the Mountains of Madness',
    ano: '1936',
    categoria: 'Novela',
    imagem: 'https://commons.wikimedia.org/wiki/Special:FilePath/At_the_Mountains_of_Madness.jpg',
    descricao:
      'Uma expedição à Antártida encontra vestígios de uma civilização alienígena muito mais antiga que a humanidade.',
  },
  {
    titulo: 'The Colour Out of Space',
    ano: '1927',
    categoria: 'Conto',
    imagem: 'https://commons.wikimedia.org/wiki/Special:FilePath/Amazingstories-1927-09-thecolouroutofspace.jpg',
    descricao:
      'Uma estranha presença caída do céu começa a corromper a terra, os animais e tudo aquilo que vive ao seu redor.',
  },
  {
    titulo: 'The Dunwich Horror',
    ano: '1928',
    categoria: 'Conto',
    imagem: 'https://commons.wikimedia.org/wiki/Special:FilePath/The_Dunwich_Horror.jpg',
    descricao:
      'Um segredo familiar, rituais proibidos e uma criatura que não deveria existir entre os homens.',
  },
  {
    titulo: 'The Shadow Out of Time',
    ano: '1936',
    categoria: 'Novela',
    imagem: 'https://commons.wikimedia.org/wiki/Special:FilePath/Shadow_Out_of_Time_Cover.jpg',
    descricao:
      'Memórias impossíveis e uma consciência humana projetada através do tempo revelam horrores inimagináveis.',
  },
]

const entidades = [
  {
    numero: '01',
    nome: 'Cthulhu',
    imagem: 'https://commons.wikimedia.org/wiki/Special:FilePath/Hugh_Rankin_-_The_Call_of_Cthulhu.jpg',
    descricao: 'O Grande Antigo adormecido na cidade submersa de R’lyeh.',
  },
  {
    numero: '02',
    nome: 'Yog-Sothoth',
    imagem: 'https://commons.wikimedia.org/wiki/Special:FilePath/Crab_Nebula.jpg',
    descricao: 'A entidade associada aos portais, ao espaço e ao próprio tempo.',
  },
  {
    numero: '03',
    nome: 'Azathoth',
    imagem: 'https://commons.wikimedia.org/wiki/Special:FilePath/30_Doradus,_Tarantula_Nebula.jpg',
    descricao: 'O caos primordial, situado além dos limites da compreensão humana.',
  },
  {
    numero: '04',
    nome: 'Nyarlathotep',
    imagem: 'https://commons.wikimedia.org/wiki/Special:FilePath/Ant_Nebula.jpg',
    descricao: 'O Caos Rastejante, mensageiro e manifestação dos deuses exteriores.',
  },
]
</script>

<template>
  <div class="site">

    <!-- ================= NAVBAR ================= -->

    <header class="navbar">
      <a href="#inicio" class="brand">
        <span class="brand-symbol">☿</span>
        <span>LOVECRAFT</span>
      </a>

      <nav class="nav-links">
        <a href="#inicio">Início</a>
        <a href="#autor">O Autor</a>
        <a href="#obras">Obras</a>
        <a href="#mythos">Mythos</a>
      </nav>

      <div class="nav-status">
        <span></span>
        THE UNKNOWN AWAITS
      </div>
    </header>

    <!-- ================= HERO ================= -->

    <main>

      <section id="inicio" class="hero">

        <div class="stars"></div>

        <div class="hero-grid"></div>

        <div class="hero-content">

          <div class="hero-label">
            <span></span>
            ARQUIVOS DO DESCONHECIDO
          </div>

          <p class="hero-kicker">
            HOWARD PHILLIPS LOVECRAFT
          </p>

          <h1>
            O HORROR
            <span>ALÉM DA RAZÃO</span>
          </h1>

          <p class="hero-description">
            Nas profundezas do cosmos existem coisas que a humanidade
            jamais deveria conhecer. Explore o universo de H. P. Lovecraft,
            onde o desconhecido é muito mais assustador que a própria morte.
          </p>

          <div class="hero-actions">
            <a href="#obras" class="primary-button">
              EXPLORAR O MYTHOS
              <span>↗</span>
            </a>

            <a href="#autor" class="secondary-button">
              CONHECER O AUTOR
            </a>
          </div>

        </div>

        <!-- SÍMBOLO -->

        <div class="cosmic-symbol">

          <div class="symbol-orbit orbit-one"></div>
          <div class="symbol-orbit orbit-two"></div>
          <div class="symbol-orbit orbit-three"></div>

          <div class="symbol-inner">

            <div class="tentacle t1"></div>
            <div class="tentacle t2"></div>
            <div class="tentacle t3"></div>
            <div class="tentacle t4"></div>
            <div class="tentacle t5"></div>
            <div class="tentacle t6"></div>

            <div class="symbol-eye">
              <div></div>
            </div>

          </div>

        </div>

        <div class="hero-bottom">
          <span>01 — INTRODUÇÃO</span>
          <div></div>
          <span>SCROLL TO DISCOVER</span>
        </div>

      </section>

      <!-- ================= AUTOR ================= -->

      <section id="autor" class="author section">

        <div class="section-header">
          <div>
            <span class="section-number">01 / AUTOR</span>

            <h2>
              O homem que
              <em>olhou para o abismo.</em>
            </h2>
          </div>

          <span class="section-mark">HPL</span>
        </div>

        <div class="author-layout">

          <div class="author-card">

            <div class="portrait-placeholder">
              <img
                class="portrait-photo"
                src="https://commons.wikimedia.org/wiki/Special:FilePath/H._P._Lovecraft,_June_1934.jpg"
                alt="Retrato de H. P. Lovecraft, 1934"
              />
            </div>

            <div class="card-caption">
              <span>HOWARD PHILLIPS LOVECRAFT</span>
              <span>PROVIDENCE, RHODE ISLAND</span>
            </div>

          </div>

          <div class="author-text">

            <p class="lead">
              H. P. Lovecraft transformou o medo do desconhecido em uma
              visão de mundo.
            </p>

            <p>
              Nascido em Providence, Rhode Island, Lovecraft tornou-se uma
              das figuras mais influentes da literatura de horror do século XX.
            </p>

            <p>
              Ao invés de monstros tradicionais, suas histórias apresentam
              entidades antigas, dimensões incompreensíveis e civilizações
              esquecidas.
            </p>

            <p>
              Em seu universo, o ser humano não é o centro da criação.
              Somos apenas uma pequena presença diante de forças cósmicas
              infinitamente maiores.
            </p>

            <div class="author-signature">
              <span>H. P.</span>
              <span>LOVECRAFT</span>
            </div>

          </div>

        </div>

      </section>

      <!-- ================= FRASE ================= -->

      <section class="quote-section">

        <div class="quote-symbol">“</div>

        <blockquote>
          O medo mais antigo e mais forte da humanidade
          <span>é o medo do desconhecido.</span>
        </blockquote>

        <div class="quote-author">
          — H. P. LOVECRAFT
        </div>

      </section>

      <!-- ================= OBRAS ================= -->

      <section id="obras" class="works section">

        <div class="section-header">

          <div>
            <span class="section-number">02 / BIBLIOTECA</span>

            <h2>
              Obras do
              <em>desconhecido.</em>
            </h2>
          </div>

          <p class="section-intro">
            Contos, novelas e pesadelos que ajudaram a definir
            o horror cósmico.
          </p>

        </div>

        <div class="works-grid">

          <article
            v-for="(obra, index) in obras"
            :key="obra.titulo"
            class="work-card"
          >

            <!-- IMAGEM DA OBRA -->

            <div class="work-image">

              <img
                :src="obra.imagem"
                :alt="`Capa original de ${obra.titulo}`"
                loading="lazy"
              />

              <div class="work-image-overlay"></div>

              <span class="work-number">
                0{{ index + 1 }}
              </span>

              <span class="work-year">
                {{ obra.ano }}
              </span>

            </div>

            <!-- CONTEÚDO -->

            <div class="work-content">

              <span class="work-category">
                {{ obra.categoria }}
              </span>

              <h3>
                {{ obra.titulo }}
              </h3>

              <p>
                {{ obra.descricao }}
              </p>

            </div>

            <!-- RODAPÉ -->

            <div class="work-bottom">
              <span>ARQUIVO HPL</span>

              <span class="arrow">
                ↗
              </span>
            </div>

          </article>

        </div>

      </section>

      <!-- ================= MYTHOS ================= -->

      <section id="mythos" class="mythos section">

        <div class="mythos-heading">

          <span class="section-number">
            03 / MITOLOGIA
          </span>

          <h2>
            <span>THE</span>
            CTHULHU
            <strong>MYTHOS</strong>
          </h2>

          <p>
            Uma mitologia fragmentada de deuses antigos,
            dimensões impossíveis e conhecimentos que deveriam
            permanecer esquecidos.
          </p>

        </div>

        <div class="entities">

          <article
            v-for="entidade in entidades"
            :key="entidade.nome"
            class="entity"
          >

            <span class="entity-number">
              {{ entidade.numero }}
            </span>

            <div class="entity-symbol">
              <img
                :src="entidade.imagem"
                :alt="entidade.nome"
                loading="lazy"
              />
            </div>

            <h3>
              {{ entidade.nome }}
            </h3>

            <p>
              {{ entidade.descricao }}
            </p>

            <span class="entity-link">
              CLASSIFIED FILE ↗
            </span>

          </article>

        </div>

      </section>

      <!-- ================= FINAL ================= -->

      <section class="final-section">

        <div class="final-glow"></div>

        <span class="final-label">
          SOMETHING IS WAITING
        </span>

        <h2>
          Não olhe
          <span>para trás.</span>
        </h2>

        <p>
          O conhecimento tem um preço.
        </p>

        <a href="#inicio" class="primary-button">
          VOLTAR AO INÍCIO ↑
        </a>

      </section>

    </main>

    <!-- ================= FOOTER ================= -->

    <footer>

      <div class="footer-brand">
        <span>H.P.L</span>
        <small>ARCHIVES</small>
      </div>

      <div class="footer-center">
        THE UNKNOWN AWAITS
      </div>

      <div class="footer-right">
        <span>1890 — 1937</span>
        <span>PROVIDENCE</span>
      </div>

    </footer>

    <div class="image-credit">
      Imagens: capas originais de Weird Tales / Astounding Stories / Amazing Stories, retrato de H. P. Lovecraft
      e imagens astronômicas NASA/ESA — domínio público, via Wikimedia Commons.
    </div>

  </div>
</template>

<style>
@import url('https://fonts.googleapis.com/css2?family=Cinzel:wght@400;500;600;700;800&family=Inter:wght@300;400;500;600&display=swap');

:root {
  --black: #050706;
  --black-soft: #090d0b;
  --black-card: #0b100d;

  --green: #627f69;
  --green-light: #9eb8a4;
  --green-bright: #b5d0ba;

  --cream: #d8d3c4;
  --muted: #747b75;

  --gold: #9a8c5b;

  --border: rgba(145, 165, 148, 0.15);

  --max-width: 1400px;
}

/* ================= RESET ================= */

* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

html {
  scroll-behavior: smooth;
  background: var(--black);
}

body {
  background: var(--black);
  color: var(--cream);
  font-family: 'Inter', sans-serif;
  overflow-x: hidden;
}

body,
button,
a {
  cursor: default;
}

a {
  color: inherit;
  text-decoration: none;
}

button {
  font-family: inherit;
}

::selection {
  background: var(--green);
  color: var(--black);
}

/* ================= SITE ================= */

.site {
  width: 100%;
  min-height: 100vh;

  background:
    radial-gradient(
      ellipse at 50% -20%,
      rgba(72, 105, 82, 0.15),
      transparent 50%
    ),
    var(--black);
}

/* ================= NAVBAR ================= */

.navbar {
  position: fixed;
  z-index: 1000;

  top: 0;
  left: 0;

  width: 100%;
  height: 76px;

  padding: 0 clamp(24px, 5vw, 80px);

  display: flex;
  align-items: center;
  justify-content: space-between;

  border-bottom: 1px solid var(--border);

  background: rgba(5, 7, 6, 0.75);

  backdrop-filter: blur(18px);
}

.brand {
  display: flex;
  align-items: center;
  gap: 12px;

  font-family: 'Cinzel', serif;

  font-size: 14px;
  letter-spacing: 4px;

  color: var(--green-light);
}

.brand-symbol {
  font-size: 24px;
  color: var(--gold);
}

.nav-links {
  display: flex;
  align-items: center;
  gap: 38px;
}

.nav-links a {
  position: relative;

  color: var(--muted);

  font-size: 10px;
  letter-spacing: 2px;
  text-transform: uppercase;

  transition: color 0.3s ease;
}

.nav-links a::after {
  content: '';

  position: absolute;

  left: 0;
  bottom: -8px;

  width: 0;
  height: 1px;

  background: var(--green-light);

  transition: width 0.3s ease;
}

.nav-links a:hover {
  color: var(--cream);
}

.nav-links a:hover::after {
  width: 100%;
}

.nav-status {
  display: flex;
  align-items: center;
  gap: 9px;

  color: #566158;

  font-size: 8px;
  letter-spacing: 2px;
}

.nav-status span {
  width: 5px;
  height: 5px;

  border-radius: 50%;

  background: var(--green);

  box-shadow: 0 0 12px var(--green);
}

/* ================= HERO ================= */

.hero {
  position: relative;

  min-height: 100svh;

  max-width: var(--max-width);
  margin: auto;

  padding:
    clamp(150px, 18vh, 200px)
    clamp(24px, 7vw, 100px)
    100px;

  display: flex;
  align-items: center;

  overflow: hidden;
}

.hero-grid {
  position: absolute;
  inset: 0;

  opacity: 0.07;

  background-image:
    linear-gradient(
      rgba(126, 155, 133, 0.4) 1px,
      transparent 1px
    ),
    linear-gradient(
      90deg,
      rgba(126, 155, 133, 0.4) 1px,
      transparent 1px
    );

  background-size: 80px 80px;

  mask-image:
    radial-gradient(
      ellipse at center,
      black,
      transparent 75%
    );
}

.stars {
  position: absolute;
  inset: 0;

  opacity: 0.7;

  background-image:
    radial-gradient(circle, #b4c6b8 1px, transparent 1px),
    radial-gradient(circle, #82978a 1px, transparent 1px),
    radial-gradient(circle, #d0d7d0 1px, transparent 1px);

  background-size:
    170px 170px,
    230px 230px,
    310px 310px;

  background-position:
    20px 40px,
    100px 120px,
    50px 200px;

  mask-image:
    radial-gradient(
      ellipse at 70% 40%,
      black,
      transparent 65%
    );
}

.hero::after {
  content: '';

  position: absolute;

  width: 700px;
  height: 700px;

  right: -250px;
  top: 50%;

  transform: translateY(-50%);

  background:
    radial-gradient(
      circle,
      rgba(82, 122, 94, 0.2),
      transparent 65%
    );

  filter: blur(20px);
}

.hero-content {
  position: relative;
  z-index: 5;

  width: min(700px, 60%);

  animation: heroEnter 1s ease forwards;
}

@keyframes heroEnter {
  from {
    opacity: 0;
    transform: translateY(30px);
  }

  to {
    opacity: 1;
    transform: translateY(0);
  }
}

.hero-label {
  display: flex;
  align-items: center;
  gap: 12px;

  margin-bottom: 30px;

  color: var(--green);

  font-size: 9px;
  letter-spacing: 4px;
}

.hero-label span {
  width: 35px;
  height: 1px;

  background: var(--green);
}

.hero-kicker {
  margin-bottom: 14px;

  color: var(--muted);

  font-size: 11px;
  letter-spacing: 6px;
}

.hero h1 {
  font-family: 'Cinzel', serif;

  font-size: clamp(55px, 7.5vw, 115px);

  font-weight: 500;

  line-height: 0.9;

  letter-spacing: -4px;

  color: var(--cream);
}

.hero h1 span {
  display: block;

  color: var(--green-light);

  font-size: 0.72em;

  margin-top: 12px;

  letter-spacing: -2px;
}

.hero-description {
  max-width: 500px;

  margin-top: 38px;

  color: var(--muted);

  font-size: 14px;

  line-height: 1.9;
}

.hero-actions {
  display: flex;
  align-items: center;
  gap: 24px;

  margin-top: 40px;
}

.primary-button {
  display: inline-flex;
  align-items: center;
  gap: 22px;

  padding: 16px 20px;

  border: 1px solid var(--green);

  color: var(--green-light);

  font-size: 9px;
  letter-spacing: 2px;

  transition:
    background 0.3s,
    color 0.3s,
    transform 0.3s;
}

.primary-button span {
  font-size: 16px;
}

.primary-button:hover {
  background: var(--green);
  color: var(--black);

  transform: translateY(-3px);
}

.secondary-button {
  color: var(--muted);

  font-size: 9px;
  letter-spacing: 2px;

  border-bottom: 1px solid transparent;

  padding-bottom: 5px;

  transition: 0.3s;
}

.secondary-button:hover {
  color: var(--cream);
  border-color: var(--green);
}

/* ================= COSMIC SYMBOL ================= */

.cosmic-symbol {
  position: absolute;

  right: clamp(20px, 7vw, 100px);

  top: 50%;

  width: clamp(320px, 36vw, 560px);
  aspect-ratio: 1;

  transform: translateY(-50%);

  display: grid;
  place-items: center;

  opacity: 0.85;
}

.symbol-orbit {
  position: absolute;

  border: 1px solid rgba(126, 155, 133, 0.18);

  border-radius: 50%;
}

.orbit-one {
  width: 100%;
  height: 100%;

  transform: rotate(25deg) scaleY(0.35);
}

.orbit-two {
  width: 80%;
  height: 80%;

  transform: rotate(-45deg) scaleY(0.35);
}

.orbit-three {
  width: 62%;
  height: 62%;

  transform: rotate(90deg) scaleY(0.35);
}

.symbol-inner {
  position: relative;

  width: 45%;
  height: 45%;

  border: 1px solid rgba(158, 184, 164, 0.4);

  border-radius: 50%;

  display: grid;
  place-items: center;

  box-shadow:
    0 0 80px rgba(88, 128, 98, 0.12),
    inset 0 0 50px rgba(88, 128, 98, 0.08);
}

.symbol-eye {
  width: 100px;
  height: 65px;

  border: 2px solid var(--green-light);

  border-radius: 70% 0 70% 0;

  transform: rotate(45deg);

  display: grid;
  place-items: center;

  box-shadow:
    0 0 30px rgba(126, 165, 137, 0.18);
}

.symbol-eye div {
  width: 17px;
  height: 17px;

  background: var(--green-light);

  border-radius: 50%;

  box-shadow:
    0 0 25px rgba(171, 207, 181, 0.8);
}

.tentacle {
  position: absolute;

  width: 2px;
  height: 90px;

  background: linear-gradient(
    transparent,
    var(--green)
  );

  transform-origin: top;
}

.t1 {
  transform: rotate(0deg) translateY(-75px);
}

.t2 {
  transform: rotate(60deg) translateY(-75px);
}

.t3 {
  transform: rotate(120deg) translateY(-75px);
}

.t4 {
  transform: rotate(180deg) translateY(-75px);
}

.t5 {
  transform: rotate(240deg) translateY(-75px);
}

.t6 {
  transform: rotate(300deg) translateY(-75px);
}

.hero-bottom {
  position: absolute;

  bottom: 30px;
  left: clamp(24px, 7vw, 100px);
  right: clamp(24px, 7vw, 100px);

  display: flex;
  align-items: center;
  gap: 20px;

  color: #4d554f;

  font-size: 8px;
  letter-spacing: 3px;
}

.hero-bottom div {
  height: 1px;
  flex: 1;

  background: var(--border);
}

/* ================= SECTION ================= */

.section {
  max-width: var(--max-width);

  margin: auto;

  padding:
    clamp(90px, 12vw, 170px)
    clamp(24px, 7vw, 100px);

  border-top: 1px solid var(--border);
}

.section-header {
  display: flex;
  justify-content: space-between;
  align-items: end;

  margin-bottom: 80px;
}

.section-number {
  display: block;

  margin-bottom: 18px;

  color: var(--green);

  font-size: 9px;
  letter-spacing: 4px;
}

.section-header h2 {
  max-width: 650px;

  font-family: 'Cinzel', serif;

  font-size: clamp(38px, 5vw, 68px);

  font-weight: 400;

  line-height: 1;

  letter-spacing: -2px;
}

.section-header h2 em {
  display: block;

  color: var(--green-light);

  font-style: normal;
}

.section-mark {
  color: rgba(158, 184, 164, 0.08);

  font-family: 'Cinzel', serif;

  font-size: 100px;
  line-height: 0.7;
}

/* ================= AUTHOR ================= */

.author {
  background:
    linear-gradient(
      90deg,
      rgba(19, 28, 22, 0.35),
      transparent
    );
}

.author-layout {
  display: grid;

  grid-template-columns:
    minmax(300px, 0.9fr)
    minmax(300px, 1fr);

  gap: clamp(50px, 10vw, 150px);

  align-items: center;
}

.author-card {
  border: 1px solid var(--border);

  background: var(--black-card);

  box-shadow:
    20px 20px 0 rgba(80, 105, 87, 0.03);
}

.portrait-placeholder {
  min-height: 500px;

  position: relative;

  overflow: hidden;

  background:
    radial-gradient(
      ellipse at 50% 40%,
      rgba(113, 145, 120, 0.18),
      transparent 45%
    ),
    linear-gradient(
      145deg,
      #111813,
      #050706
    );
}

.portrait-placeholder::after {
  content: '';

  position: absolute;

  inset: 20px;

  border: 1px solid rgba(158, 184, 164, 0.08);

  pointer-events: none;

  z-index: 2;
}

.portrait-photo {
  position: relative;
  z-index: 1;

  width: 100%;
  height: 100%;

  min-height: 500px;

  display: block;

  object-fit: cover;
  object-position: top center;

  filter:
    grayscale(85%)
    brightness(0.8)
    contrast(1.12)
    sepia(8%);
}

.card-caption {
  padding: 17px 20px;

  display: flex;
  justify-content: space-between;

  border-top: 1px solid var(--border);

  color: #59615b;

  font-size: 8px;

  letter-spacing: 2px;
}

.author-text {
  color: var(--muted);

  font-size: 14px;

  line-height: 2;
}

.author-text .lead {
  margin-bottom: 30px;

  color: var(--green-light);

  font-family: 'Cinzel', serif;

  font-size: 25px;

  line-height: 1.5;
}

.author-text p {
  margin-bottom: 22px;
}

.author-signature {
  margin-top: 45px;

  display: flex;
  flex-direction: column;

  font-family: 'Cinzel', serif;

  font-size: 25px;

  line-height: 0.9;

  color: rgba(158, 184, 164, 0.35);
}

/* ================= QUOTE ================= */

.quote-section {
  position: relative;

  padding:
    clamp(110px, 15vw, 190px)
    20px;

  text-align: center;

  background:
    radial-gradient(
      ellipse at center,
      rgba(59, 91, 67, 0.16),
      transparent 55%
    );

  border-top: 1px solid var(--border);
  border-bottom: 1px solid var(--border);
}

.quote-symbol {
  position: absolute;

  top: 35px;
  left: 50%;

  transform: translateX(-50%);

  font-family: Georgia, serif;

  font-size: 80px;

  color: rgba(158, 184, 164, 0.08);
}

.quote-section blockquote {
  max-width: 900px;

  margin: auto;

  font-family: 'Cinzel', serif;

  font-size: clamp(25px, 4vw, 48px);

  line-height: 1.4;

  color: var(--cream);
}

.quote-section blockquote span {
  display: block;

  color: var(--green-light);
}

.quote-author {
  margin-top: 35px;

  color: var(--muted);

  font-size: 9px;
  letter-spacing: 4px;
}

/* ================= WORKS ================= */

.works {
  background: var(--black-soft);
}

.section-intro {
  max-width: 280px;

  color: var(--muted);

  font-size: 12px;

  line-height: 1.8;
}

.works-grid {
  display: grid;

  grid-template-columns: repeat(3, 1fr);

  border-top: 1px solid var(--border);
  border-left: 1px solid var(--border);
}

/* CARD */

.work-card {
  position: relative;

  min-height: 560px;

  display: flex;
  flex-direction: column;

  overflow: hidden;

  border-right: 1px solid var(--border);
  border-bottom: 1px solid var(--border);

  background: #080c09;

  transition:
    transform 0.4s ease,
    background 0.4s ease;
}

/* IMAGEM */

.work-image {
  position: relative;

  height: 260px;

  overflow: hidden;

  background: #050706;
}

.work-image img {
  width: 100%;
  height: 100%;

  display: block;

  object-fit: cover;

  filter:
    grayscale(75%)
    brightness(0.55)
    contrast(1.15);

  transform: scale(1.02);

  transition:
    transform 0.8s cubic-bezier(0.2, 0.8, 0.2, 1),
    filter 0.8s ease;
}

.work-image-overlay {
  position: absolute;

  inset: 0;

  background:
    linear-gradient(
      to bottom,
      rgba(5, 7, 6, 0.05),
      rgba(5, 7, 6, 0.35) 45%,
      rgba(5, 7, 6, 0.95)
    );

  z-index: 1;
}

.work-image::after {
  content: '';

  position: absolute;

  inset: 0;

  background:
    radial-gradient(
      circle at center,
      rgba(104, 145, 113, 0.25),
      transparent 65%
    );

  opacity: 0;

  z-index: 2;

  transition: opacity 0.5s ease;
}

/* NUMERO */

.work-number {
  position: absolute;

  top: 20px;
  left: 22px;

  z-index: 3;

  color: var(--green-light);

  font-size: 9px;

  letter-spacing: 3px;
}

/* ANO */

.work-year {
  position: absolute;

  top: 20px;
  right: 22px;

  z-index: 3;

  color: rgba(216, 211, 196, 0.65);

  font-size: 9px;

  letter-spacing: 2px;
}

/* CONTEÚDO */

.work-content {
  position: relative;

  z-index: 3;

  flex: 1;

  padding: 30px;
}

.work-category {
  color: var(--green);

  font-size: 8px;

  letter-spacing: 3px;
}

.work-card h3 {
  max-width: 320px;

  margin: 15px 0;

  color: var(--green-light);

  font-family: 'Cinzel', serif;

  font-size: 27px;

  font-weight: 500;

  line-height: 1.15;

  transition: color 0.3s ease;
}

.work-card p {
  max-width: 330px;

  color: var(--muted);

  font-size: 12px;

  line-height: 1.8;
}

/* RODAPÉ */

.work-bottom {
  position: relative;

  z-index: 3;

  margin: 0 30px;

  padding: 18px 0;

  display: flex;

  justify-content: space-between;

  align-items: center;

  border-top: 1px solid var(--border);

  color: #535b55;

  font-size: 8px;

  letter-spacing: 2px;
}

.arrow {
  font-size: 18px;

  color: var(--green);

  transition:
    transform 0.3s ease,
    color 0.3s ease;
}

/* HOVER */

.work-card:hover {
  transform: translateY(-8px);

  background: #0c120e;

  box-shadow:
    0 20px 60px rgba(0, 0, 0, 0.35);
}

.work-card:hover .work-image img {
  transform: scale(1.1);

  filter:
    grayscale(20%)
    brightness(0.7)
    contrast(1.1);
}

.work-card:hover .work-image::after {
  opacity: 1;
}

.work-card:hover h3 {
  color: var(--cream);
}

.work-card:hover .arrow {
  color: var(--green-light);

  transform: translate(5px, -5px);
}

/* ================= MYTHOS ================= */

.mythos {
  position: relative;

  overflow: hidden;

  background:
    linear-gradient(
      to bottom,
      rgba(5, 7, 6, 0.94),
      rgba(5, 7, 6, 0.8),
      rgba(5, 7, 6, 0.96)
    ),
    url('https://commons.wikimedia.org/wiki/Special:FilePath/Heart_and_Soul_nebulae.jpg') center/cover no-repeat fixed;
}

.mythos::before {
  content: '☿';

  position: absolute;

  right: -100px;
  top: 50%;

  transform: translateY(-50%);

  font-size: 600px;

  color: rgba(158, 184, 164, 0.025);

  pointer-events: none;
}

.mythos-heading {
  position: relative;

  z-index: 2;

  max-width: 750px;

  margin-bottom: 80px;
}

.mythos-heading h2 {
  font-family: 'Cinzel', serif;

  font-size: clamp(55px, 8vw, 110px);

  font-weight: 400;

  line-height: 0.82;

  letter-spacing: -5px;
}

.mythos-heading h2 span {
  display: block;

  font-size: 0.28em;

  letter-spacing: 7px;

  color: var(--muted);

  margin-bottom: 15px;
}

.mythos-heading h2 strong {
  display: block;

  color: var(--green-light);

  font-weight: 400;
}

.mythos-heading > p {
  max-width: 500px;

  margin-top: 40px;

  color: var(--muted);

  font-size: 13px;

  line-height: 1.9;
}

.entities {
  position: relative;

  z-index: 2;

  display: grid;

  grid-template-columns: repeat(4, 1fr);

  border-top: 1px solid var(--border);
  border-left: 1px solid var(--border);
}

.entity {
  min-height: 370px;

  padding: 30px;

  border-right: 1px solid var(--border);
  border-bottom: 1px solid var(--border);

  background: rgba(5, 7, 6, 0.65);

  backdrop-filter: blur(8px);

  transition:
    background 0.4s,
    transform 0.4s;
}

.entity:hover {
  background: rgba(15, 25, 18, 0.85);

  transform: translateY(-5px);
}

.entity-number {
  color: var(--green);

  font-size: 9px;

  letter-spacing: 2px;
}

.entity-symbol {
  margin-top: 25px;

  width: 100%;

  height: 130px;

  overflow: hidden;

  border: 1px solid var(--border);

  position: relative;
}

.entity-symbol img {
  width: 100%;
  height: 100%;

  object-fit: cover;

  filter:
    grayscale(35%)
    brightness(0.75)
    contrast(1.1)
    saturate(1.2);

  transition: transform 0.6s ease, filter 0.6s ease;
}

.entity:hover .entity-symbol img {
  transform: scale(1.08);

  filter:
    grayscale(10%)
    brightness(0.9)
    contrast(1.05)
    saturate(1.3);
}

.entity h3 {
  margin-top: 25px;

  font-family: 'Cinzel', serif;

  font-size: 25px;

  color: var(--green-light);
}

.entity p {
  margin-top: 15px;

  color: var(--muted);

  font-size: 11px;

  line-height: 1.8;
}

.entity-link {
  display: block;

  margin-top: 40px;

  color: #4f5952;

  font-size: 7px;

  letter-spacing: 2px;
}

/* ================= FINAL ================= */

.final-section {
  position: relative;

  min-height: 70vh;

  padding: 120px 20px;

  display: flex;

  flex-direction: column;

  justify-content: center;

  align-items: center;

  text-align: center;

  overflow: hidden;

  border-top: 1px solid var(--border);
}

.final-glow {
  position: absolute;

  width: 600px;
  height: 600px;

  border-radius: 50%;

  background:
    radial-gradient(
      circle,
      rgba(75, 113, 84, 0.17),
      transparent 65%
    );

  filter: blur(30px);
}

.final-label {
  position: relative;

  color: var(--green);

  font-size: 9px;

  letter-spacing: 6px;
}

.final-section h2 {
  position: relative;

  margin: 25px 0;

  font-family: 'Cinzel', serif;

  font-size: clamp(55px, 8vw, 110px);

  font-weight: 400;

  line-height: 0.9;
}

.final-section h2 span {
  display: block;

  color: var(--green-light);
}

.final-section p {
  position: relative;

  margin-bottom: 35px;

  color: var(--muted);

  font-size: 12px;
}

/* ================= FOOTER ================= */

footer {
  min-height: 120px;

  padding: 30px clamp(24px, 7vw, 100px);

  display: flex;

  justify-content: space-between;

  align-items: center;

  border-top: 1px solid var(--border);

  color: #4f5751;

  font-size: 8px;

  letter-spacing: 3px;
}

.footer-brand {
  display: flex;

  flex-direction: column;

  color: var(--green);
}

.footer-brand span {
  font-family: 'Cinzel', serif;

  font-size: 18px;
}

.footer-brand small {
  margin-top: 4px;

  color: #4f5751;

  font-size: 7px;
}

.footer-center {
  color: #4f5751;
}

.footer-right {
  display: flex;

  gap: 25px;
}

/* ================= CRÉDITOS DE IMAGEM ================= */

.image-credit {
  padding: 18px clamp(24px, 7vw, 100px) 30px;

  color: #3d443e;

  font-size: 8px;

  letter-spacing: 1px;

  line-height: 1.7;

  text-align: center;
}

/* ================= RESPONSIVE ================= */

@media (max-width: 1100px) {

  .nav-status {
    display: none;
  }

  .cosmic-symbol {
    right: -100px;

    opacity: 0.45;
  }

  .hero-content {
    width: 70%;
  }

  .works-grid {
    grid-template-columns: repeat(2, 1fr);
  }

  .entities {
    grid-template-columns: repeat(2, 1fr);
  }

}

@media (max-width: 800px) {

  .navbar {
    height: 68px;
  }

  .nav-links {
    display: none;
  }

  .hero {
    min-height: 100svh;

    padding-top: 130px;
  }

  .hero-content {
    width: 100%;
  }

  .cosmic-symbol {
    width: 420px;

    right: -180px;

    opacity: 0.25;
  }

  .hero h1 {
    letter-spacing: -2px;
  }

  .author-layout {
    grid-template-columns: 1fr;
  }

  .section-header {
    align-items: start;

    flex-direction: column;

    gap: 35px;
  }

  .section-mark {
    display: none;
  }

  .works-grid {
    grid-template-columns: 1fr;
  }

  .work-card {
    min-height: 520px;
  }

  .work-image {
    height: 300px;
  }

  .entities {
    grid-template-columns: 1fr;
  }

  .entity {
    min-height: 300px;
  }

  footer {
    flex-direction: column;

    gap: 25px;

    align-items: flex-start;
  }

}

@media (max-width: 500px) {

  .brand {
    font-size: 11px;

    letter-spacing: 3px;
  }

  .hero {
    padding-left: 20px;

    padding-right: 20px;
  }

  .hero h1 {
    font-size: 53px;
  }

  .hero-kicker {
    font-size: 8px;

    letter-spacing: 4px;
  }

  .hero-description {
    font-size: 12px;
  }

  .hero-actions {
    align-items: flex-start;

    flex-direction: column;

    gap: 20px;
  }

  .hero-bottom {
    display: none;
  }

  .section {
    padding-left: 20px;

    padding-right: 20px;
  }

  .section-header h2 {
    font-size: 40px;
  }

  .portrait-placeholder {
    min-height: 400px;
  }

  .portrait-photo {
    min-height: 400px;
  }

  .card-caption {
    flex-direction: column;

    gap: 8px;
  }

  .quote-section {
    padding-left: 25px;

    padding-right: 25px;
  }

  .mythos-heading h2 {
    font-size: 55px;
  }

  .footer-center {
    display: none;
  }

}
</style>
