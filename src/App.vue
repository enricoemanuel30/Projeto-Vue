<script setup lang="ts">
import { ref, onMounted, watch } from 'vue'

const isLightMode = ref(false)

onMounted(() => {
  const savedTheme = localStorage.getItem('lovecraft-theme')

  if (savedTheme === 'light') {
    isLightMode.value = true
  }
})

watch(isLightMode, (value) => {
  localStorage.setItem(
    'lovecraft-theme',
    value ? 'light' : 'dark'
  )
})

const obras = [
  {
    titulo: 'The Call of Cthulhu',
    ano: '1926',
    categoria: 'Conto',
    descricao:
      'Um culto secreto, sonhos perturbadores e a descoberta de uma entidade ancestral adormecida nas profundezas do Pacífico.',
  },
  {
    titulo: 'The Shadow over Innsmouth',
    ano: '1936',
    categoria: 'Conto',
    descricao:
      'Uma cidade decadente, habitantes estranhos e uma linhagem que esconde uma ligação aterradora com o oceano.',
  },
  {
    titulo: 'At the Mountains of Madness',
    ano: '1936',
    categoria: 'Novela',
    descricao:
      'Uma expedição à Antártida encontra vestígios de uma civilização alienígena muito mais antiga que a humanidade.',
  },
  {
    titulo: 'The Colour Out of Space',
    ano: '1927',
    categoria: 'Conto',
    descricao:
      'Uma estranha presença caída do céu começa a corromper a terra, os animais e tudo aquilo que vive ao seu redor.',
  },
  {
    titulo: 'The Dunwich Horror',
    ano: '1928',
    categoria: 'Conto',
    descricao:
      'Um segredo familiar, rituais proibidos e uma criatura que não deveria existir entre os homens.',
  },
  {
    titulo: 'The Shadow Out of Time',
    ano: '1936',
    categoria: 'Novela',
    descricao:
      'Memórias impossíveis e uma consciência humana projetada através do tempo revelam horrores inimagináveis.',
  },
]

// Cada Antigo recebe um pequeno glifo desenhado à mão em SVG,
// coerente com a descrição do próprio mito — nenhuma arte externa,
// tudo vetorial e herdando as cores do tema (claro/escuro).
const entidades = [
  {
    numero: '01',
    nome: 'Cthulhu',
    descricao:
      'O Grande Antigo adormecido na cidade submersa de R’lyeh.',
    icon: `<svg viewBox="0 0 64 64" fill="none" stroke="currentColor" stroke-width="1.4" stroke-linecap="round">
      <circle cx="32" cy="35" r="15" />
      <path d="M21 23 Q14 8 23 3 Q20 14 24 24" />
      <path d="M43 23 Q50 8 41 3 Q44 14 40 24" />
      <path d="M22 46 Q25 54 21 60" />
      <path d="M28 49 Q29 57 26 62" />
      <path d="M36 49 Q35 57 38 62" />
      <path d="M42 46 Q39 54 43 60" />
      <ellipse cx="32" cy="33" rx="2" ry="5.5" fill="currentColor" stroke="none" />
    </svg>`,
  },
  {
    numero: '02',
    nome: 'Yog-Sothoth',
    descricao:
      'A entidade associada aos portais, ao espaço e ao próprio tempo.',
    icon: `<svg viewBox="0 0 64 64" fill="none" stroke="currentColor" stroke-width="1.4">
      <circle cx="32" cy="32" r="21" />
      <circle cx="32" cy="32" r="13" />
      <circle cx="32" cy="32" r="5" />
      <circle cx="19" cy="18" r="2.4" fill="currentColor" stroke="none" />
      <circle cx="47" cy="16" r="1.8" fill="currentColor" stroke="none" />
      <circle cx="49" cy="44" r="2.2" fill="currentColor" stroke="none" />
      <circle cx="15" cy="46" r="1.8" fill="currentColor" stroke="none" />
    </svg>`,
  },
  {
    numero: '03',
    nome: 'Azathoth',
    descricao:
      'O caos primordial, situado além dos limites da compreensão humana.',
    icon: `<svg viewBox="0 0 64 64" fill="none" stroke="currentColor" stroke-width="1.4" stroke-linejoin="round">
      <path d="M32 5 L37 25 L55 12 L39 29 L59 33 L38 36 L48 53 L34 40 L26 58 L28 39 L9 43 L25 30 L7 19 L26 23 Z" />
    </svg>`,
  },
  {
    numero: '04',
    nome: 'Nyarlathotep',
    descricao:
      'O Caos Rastejante, mensageiro e manifestação dos deuses exteriores.',
    icon: `<svg viewBox="0 0 64 64" fill="none" stroke="currentColor" stroke-width="1.4" stroke-linecap="round">
      <path d="M32 7 L45 19 L45 39 Q45 52 32 57 Q19 52 19 39 L19 19 Z" />
      <line x1="24" y1="27" x2="40" y2="27" />
      <path d="M25 35 Q32 40 39 35" />
    </svg>`,
  },
]
</script>

<template>
  <div
    class="site"
    :class="{ 'light-mode': isLightMode }"
  >

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

      <div class="nav-actions">

        <button
          class="theme-toggle"
          @click="isLightMode = !isLightMode"
          :aria-label="
            isLightMode
              ? 'Ativar modo escuro'
              : 'Ativar modo claro'
          "
        >
          <span v-if="!isLightMode">☀</span>
          <span v-else>☾</span>

          <span class="theme-text">
            {{ isLightMode ? 'MODO ESCURO' : 'MODO CLARO' }}
          </span>
        </button>

        <div class="nav-status">
          <span></span>
          THE UNKNOWN AWAITS
        </div>

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

        <!-- SÍMBOLO CÓSMICO -->

        <div class="cosmic-symbol" role="img" aria-label="Ilustração de uma entidade tentacular cósmica adormecida">

          <div class="symbol-orbit orbit-one"></div>
          <div class="symbol-orbit orbit-two"></div>
          <div class="symbol-orbit orbit-three"></div>

          <div class="symbol-inner">

            <svg class="entity-svg" viewBox="0 0 300 260" fill="none" aria-hidden="true">

              <!-- tentáculos externos -->
              <g class="entity-tentacles" stroke-linecap="round">
                <path d="M118 168 Q95 196 82 236" />
                <path d="M132 182 Q116 212 108 250" />
                <path d="M150 190 Q147 222 150 256" />
                <path d="M168 182 Q176 212 184 250" />
                <path d="M182 168 Q205 196 218 236" />
                <path d="M100 150 Q65 168 34 186" />
                <path d="M200 150 Q235 168 266 186" />
              </g>

              <!-- chifres -->
              <path class="entity-line" d="M120 108 Q92 60 52 42 Q86 74 102 122" />
              <path class="entity-line" d="M180 108 Q208 60 248 42 Q214 74 198 122" />

              <!-- cabeça -->
              <path class="entity-line" d="M104 150 Q150 96 196 150 Q202 194 150 210 Q98 194 104 150 Z" />

              <!-- olho -->
              <ellipse class="entity-eye" cx="150" cy="150" rx="15" ry="9.5" />
              <circle class="entity-pupil" cx="150" cy="150" r="4.2" />

            </svg>

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

            <span class="section-number">
              01 / AUTOR
            </span>

            <h2>
              O homem que
              <em>olhou para o abismo.</em>
            </h2>

          </div>

          <span class="section-mark">
            HPL
          </span>

        </div>

        <div class="author-layout">

          <div class="author-card">

            <div class="portrait-placeholder">

              <svg class="portrait-art" viewBox="0 0 400 500" preserveAspectRatio="xMidYMax slice" aria-hidden="true">
                <g class="portrait-waves" fill="none" stroke-linecap="round">
                  <path d="M-10 432 Q40 415 90 432 T190 432 T290 432 T390 432" />
                  <path d="M-10 452 Q40 436 90 452 T190 452 T290 452 T390 452" />
                  <path d="M-10 472 Q40 456 90 472 T190 472 T290 472 T390 472" />
                </g>
                <g class="portrait-tentacles" fill="none" stroke-linecap="round">
                  <path d="M232 434 Q248 344 220 262 Q202 322 214 384 Q186 330 198 268" />
                  <path d="M186 434 Q164 352 196 280" />
                </g>
              </svg>

              <span>H.P.L</span>

              <small>
                1890 — 1937
              </small>

            </div>

            <div class="card-caption">

              <span>
                HOWARD PHILLIPS LOVECRAFT
              </span>

              <span>
                PROVIDENCE, RHODE ISLAND
              </span>

            </div>

          </div>

          <div class="author-text">

            <p class="lead">
              H. P. Lovecraft transformou o medo do desconhecido
              em uma visão de mundo.
            </p>

            <p>
              Nascido em Providence, Rhode Island, Lovecraft tornou-se
              uma das figuras mais influentes da literatura de horror
              do século XX.
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

        <div class="quote-symbol">
          “
        </div>

        <blockquote>
          O medo mais antigo e mais forte da humanidade
          <span>é o medo do desconhecido.</span>
        </blockquote>

        <svg class="quote-divider" viewBox="0 0 220 16" aria-hidden="true">
          <path d="M0 8 Q27 -2 55 8 T110 8 T165 8 T220 8" fill="none" stroke-linecap="round" />
        </svg>

        <div class="quote-author">
          — H. P. LOVECRAFT
        </div>

      </section>

      <!-- ================= OBRAS ================= -->

      <section id="obras" class="works section">

        <div class="section-header">

          <div>

            <span class="section-number">
              02 / BIBLIOTECA
            </span>

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

            <div class="work-top">

              <span>
                0{{ index + 1 }}
              </span>

              <span>
                {{ obra.ano }}
              </span>

            </div>

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

            <div class="work-bottom">

              <span>
                ARQUIVO HPL
              </span>

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

            <strong>
              MYTHOS
            </strong>

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

            <div
              class="entity-symbol"
              v-html="entidade.icon"
            ></div>

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

        <svg class="final-sign" viewBox="0 0 200 200" aria-hidden="true">
          <circle cx="100" cy="100" r="92" fill="none" />
          <path
            fill="none"
            d="M100 12 L118 78 L182 60 L128 100 L182 140 L118 122 L100 188 L82 122 L18 140 L72 100 L18 60 L82 78 Z"
          />
        </svg>

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

        <span>
          H.P.L
        </span>

        <small>
          ARCHIVES
        </small>

      </div>

      <div class="footer-center">
        THE UNKNOWN AWAITS
      </div>

      <div class="footer-right">

        <span>
          1890 — 1937
        </span>

        <span>
          PROVIDENCE
        </span>

      </div>

    </footer>

  </div>
</template>

<style>
@import url('https://fonts.googleapis.com/css2?family=Cinzel:wght@400;500;600;700;800&family=Inter:wght@300;400;500;600&display=swap');

/* ================= VARIÁVEIS ================= */

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

@media (prefers-reduced-motion: reduce) {
  html {
    scroll-behavior: auto;
  }

  *,
  *::before,
  *::after {
    animation-duration: 0.001ms !important;
    animation-iteration-count: 1 !important;
    transition-duration: 0.001ms !important;
  }
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

  transition:
    background 0.5s ease,
    color 0.5s ease;
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

  transition:
    background 0.4s ease,
    border-color 0.4s ease;
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

/* ================= NAV ACTIONS ================= */

.nav-actions {
  display: flex;
  align-items: center;
  gap: 25px;
}

.theme-toggle {
  display: flex;
  align-items: center;

  gap: 8px;

  padding: 8px 12px;

  background: transparent;

  border: 1px solid var(--border);

  color: var(--green-light);

  font-family: 'Inter', sans-serif;

  font-size: 8px;

  letter-spacing: 2px;

  cursor: pointer;

  transition:
    background 0.3s ease,
    border-color 0.3s ease,
    color 0.3s ease,
    transform 0.3s ease;
}

.theme-toggle:focus-visible {
  outline: 1px solid var(--green-light);
  outline-offset: 3px;
}

.theme-toggle span:first-child {
  font-size: 15px;
}

.theme-toggle:hover {
  background: var(--green);

  border-color: var(--green);

  color: var(--black);

  transform: translateY(-2px);
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

  box-shadow:
    0 0 12px var(--green);
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

.primary-button:focus-visible,
.secondary-button:focus-visible {
  outline: 1px solid var(--green-light);
  outline-offset: 4px;
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

  width: 62%;
  height: 62%;

  border: 1px solid rgba(158, 184, 164, 0.4);

  border-radius: 50%;

  display: grid;
  place-items: center;

  box-shadow:
    0 0 80px rgba(88, 128, 98, 0.12),
    inset 0 0 50px rgba(88, 128, 98, 0.08);
}

.entity-svg {
  width: 78%;
  height: 78%;

  overflow: visible;

  animation: entityBreathe 7s ease-in-out infinite;
}

@keyframes entityBreathe {
  0%, 100% {
    transform: scale(1);
  }
  50% {
    transform: scale(1.02);
  }
}

.entity-line,
.entity-tentacles path {
  stroke: var(--green-light);
  stroke-width: 1.6;
  fill: none;
}

.entity-tentacles path {
  stroke: var(--green);
  opacity: 0.8;
}

.entity-eye {
  fill: none;
  stroke: var(--green-light);
  stroke-width: 2;
}

.entity-pupil {
  fill: var(--green-light);
  filter: drop-shadow(0 0 6px rgba(171, 207, 181, 0.8));
}

.tentacle {
  position: absolute;

  width: 2px;
  height: 90px;

  background:
    linear-gradient(
      transparent,
      var(--green)
    );

  transform-origin: top;
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

  display: flex;
  flex-direction: column;

  justify-content: end;

  padding: 35px;

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

.portrait-placeholder::before {
  content: 'H';

  position: absolute;

  top: 35px;
  left: 50%;

  transform: translateX(-50%);

  font-family: 'Cinzel', serif;

  font-size: 320px;

  line-height: 1;

  color: rgba(158, 184, 164, 0.025);
}

.portrait-placeholder::after {
  content: '';

  position: absolute;

  inset: 20px;

  border: 1px solid rgba(158, 184, 164, 0.08);

  pointer-events: none;
}

.portrait-art {
  position: absolute;

  inset: 0;

  width: 100%;
  height: 100%;

  pointer-events: none;
}

.portrait-waves path {
  stroke: var(--green-light);
  stroke-width: 1;
  opacity: 0.3;
}

.portrait-tentacles path {
  stroke: var(--green-light);
  stroke-width: 1.2;
  opacity: 0.4;
}

.portrait-placeholder span {
  position: relative;

  z-index: 2;

  font-family: 'Cinzel', serif;

  font-size: 55px;

  color: var(--green-light);

  letter-spacing: 5px;
}

.portrait-placeholder small {
  position: relative;

  z-index: 2;

  margin-top: 10px;

  color: var(--muted);

  font-size: 9px;

  letter-spacing: 3px;
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

.quote-divider {
  width: 140px;
  height: 12px;

  margin: 35px auto 0;
}

.quote-divider path {
  stroke: var(--green);
}

.quote-author {
  margin-top: 20px;

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

.work-card {
  position: relative;

  min-height: 390px;

  padding: 28px;

  display: flex;
  flex-direction: column;

  border-right: 1px solid var(--border);

  border-bottom: 1px solid var(--border);

  background:
    linear-gradient(
      145deg,
      rgba(22, 31, 25, 0.5),
      rgba(6, 9, 7, 0.4)
    );

  transition:
    transform 0.4s ease,
    background 0.4s ease;
}

.work-card::before {
  content: '';

  position: absolute;

  inset: 0;

  opacity: 0;

  background:
    radial-gradient(
      circle at 50% 30%,
      rgba(93, 130, 101, 0.14),
      transparent 55%
    );

  transition: opacity 0.4s;
}

.work-card:hover {
  transform: translateY(-5px);

  background: #0e1510;
}

.work-card:hover::before {
  opacity: 1;
}

.work-top,
.work-bottom,
.work-content {
  position: relative;

  z-index: 2;
}

.work-top {
  display: flex;

  justify-content: space-between;

  color: #59625b;

  font-size: 9px;

  letter-spacing: 2px;
}

.work-content {
  margin-top: auto;

  margin-bottom: auto;
}

.work-category {
  color: var(--green);

  font-size: 8px;

  letter-spacing: 3px;
}

.work-card h3 {
  max-width: 300px;

  margin: 18px 0;

  font-family: 'Cinzel', serif;

  font-size: 28px;

  font-weight: 500;

  line-height: 1.15;

  color: var(--green-light);
}

.work-card p {
  max-width: 330px;

  color: var(--muted);

  font-size: 12px;

  line-height: 1.8;
}

.work-bottom {
  display: flex;

  justify-content: space-between;

  align-items: center;

  padding-top: 18px;

  border-top: 1px solid var(--border);

  color: #535b55;

  font-size: 8px;

  letter-spacing: 2px;
}

.arrow {
  font-size: 18px;

  color: var(--green);

  transition: transform 0.3s;
}

.work-card:hover .arrow {
  transform: translate(4px, -4px);
}

/* ================= MYTHOS ================= */

.mythos {
  position: relative;

  overflow: hidden;

  background:
    radial-gradient(
      ellipse at 80% 20%,
      rgba(45, 75, 54, 0.2),
      transparent 40%
    );
}

.mythos::before {
  content: '☿';

  position: absolute;

  right: -100px;
  top: 50%;

  transform: translateY(-50%);

  font-size: 600px;

  color: rgba(158, 184, 164, 0.025);
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

  transition:
    background 0.4s,
    transform 0.4s;
}

.entity:hover {
  background: rgba(89, 123, 97, 0.06);

  transform: translateY(-5px);
}

.entity-number {
  color: var(--green);

  font-size: 9px;

  letter-spacing: 2px;
}

.entity-symbol {
  width: 46px;
  height: 46px;

  margin-top: 50px;

  color: rgba(158, 184, 164, 0.55);

  transition:
    color 0.4s,
    transform 0.4s;
}

.entity-symbol svg {
  width: 100%;
  height: 100%;
}

.entity:hover .entity-symbol {
  color: var(--green-light);
  transform: scale(1.08);
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

.final-sign {
  position: absolute;

  width: clamp(320px, 40vw, 560px);
  height: clamp(320px, 40vw, 560px);

  opacity: 0.06;

  animation: signSpin 90s linear infinite;
}

.final-sign circle,
.final-sign path {
  stroke: var(--green-light);
  stroke-width: 1;
}

@keyframes signSpin {
  from {
    transform: rotate(0deg);
  }
  to {
    transform: rotate(360deg);
  }
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

  padding:
    30px
    clamp(24px, 7vw, 100px);

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

/* ================================================= */
/* ================= MODO CLARO ==================== */
/* ================================================= */

.light-mode {

  --black: #eeeae0;
  --black-soft: #e5e1d6;
  --black-card: #f5f2e9;

  --green: #405b47;
  --green-light: #304a38;
  --green-bright: #253d2d;

  --cream: #252923;
  --muted: #626961;

  --gold: #75683c;

  --border: rgba(55, 75, 61, 0.18);
}

.light-mode {
  background:
    radial-gradient(
      ellipse at 50% -20%,
      rgba(91, 119, 98, 0.14),
      transparent 50%
    ),
    var(--black);

  color: var(--cream);
}

.light-mode .navbar {
  background: rgba(238, 234, 224, 0.88);
}

.light-mode .hero-grid {
  opacity: 0.09;

  background-image:
    linear-gradient(
      rgba(64, 91, 71, 0.3) 1px,
      transparent 1px
    ),
    linear-gradient(
      90deg,
      rgba(64, 91, 71, 0.3) 1px,
      transparent 1px
    );
}

.light-mode .stars {
  opacity: 0.25;

  background-image:
    radial-gradient(circle, #405b47 1px, transparent 1px),
    radial-gradient(circle, #5b705f 1px, transparent 1px),
    radial-gradient(circle, #687b6c 1px, transparent 1px);
}

.light-mode .symbol-orbit {
  border-color: rgba(64, 91, 71, 0.2);
}

.light-mode .symbol-inner {
  border-color: rgba(64, 91, 71, 0.35);

  box-shadow:
    0 0 80px rgba(64, 91, 71, 0.08),
    inset 0 0 50px rgba(64, 91, 71, 0.05);
}

.light-mode .entity-pupil {
  filter: drop-shadow(0 0 6px rgba(48, 74, 56, 0.4));
}

.light-mode .author {
  background:
    linear-gradient(
      90deg,
      rgba(196, 202, 191, 0.4),
      transparent
    );
}

.light-mode .author-card {
  background: var(--black-card);

  box-shadow:
    20px 20px 0 rgba(64, 91, 71, 0.04);
}

.light-mode .portrait-placeholder {
  background:
    radial-gradient(
      ellipse at 50% 40%,
      rgba(80, 110, 88, 0.2),
      transparent 45%
    ),
    linear-gradient(
      145deg,
      #d9d7cc,
      #ece9df
    );
}

.light-mode .portrait-placeholder::before {
  color: rgba(48, 74, 56, 0.05);
}

.light-mode .quote-section {
  background:
    radial-gradient(
      ellipse at center,
      rgba(79, 110, 87, 0.12),
      transparent 55%
    );
}

.light-mode .quote-symbol {
  color: rgba(64, 91, 71, 0.1);
}

.light-mode .works {
  background: var(--black-soft);
}

.light-mode .work-card {
  background:
    linear-gradient(
      145deg,
      rgba(255, 255, 255, 0.35),
      rgba(218, 220, 210, 0.2)
    );
}

.light-mode .work-card:hover {
  background: #eeece3;
}

.light-mode .work-card::before {
  background:
    radial-gradient(
      circle at 50% 30%,
      rgba(83, 117, 91, 0.12),
      transparent 55%
    );
}

.light-mode .mythos {
  background:
    radial-gradient(
      ellipse at 80% 20%,
      rgba(78, 110, 86, 0.12),
      transparent 40%
    );
}

.light-mode .mythos::before {
  color: rgba(64, 91, 71, 0.04);
}

.light-mode .entity:hover {
  background: rgba(64, 91, 71, 0.05);
}

.light-mode .final-section {
  background:
    radial-gradient(
      ellipse at center,
      rgba(78, 110, 86, 0.08),
      transparent 55%
    );
}

.light-mode .final-glow {
  background:
    radial-gradient(
      circle,
      rgba(75, 113, 84, 0.12),
      transparent 65%
    );
}

.light-mode .final-sign {
  opacity: 0.1;
}

.light-mode footer {
  background: #dfdcd1;
}

.light-mode .theme-toggle:hover {
  color: #f4f1e8;
}

/* ================= RESPONSIVE ================= */

@media (max-width: 1100px) {

  .nav-status {
    display: none;
  }

  .nav-actions {
    gap: 15px;
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

  .theme-text {
    display: none;
  }

  .theme-toggle {
    width: 38px;
    height: 38px;

    padding: 0;

    justify-content: center;
  }

  .theme-toggle span:first-child {
    font-size: 18px;
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