# 🐤 Flappy Bird

### ▶️ [**JOGAR AGORA**](https://coimbradouglas.github.io/flappy-bird/) &nbsp;·&nbsp; `https://coimbradouglas.github.io/flappy-bird/`

[![Jogar online](https://img.shields.io/badge/%F0%9F%8E%AE_Jogar_online-GitHub_Pages-4ec0ca?style=for-the-badge)](https://coimbradouglas.github.io/flappy-bird/)

Um clone do **Flappy Bird** feito em **HTML5 Canvas**, num **único arquivo** (`index.html`), **100% offline** e **sem dependências**. É só abrir no navegador e jogar.

O jogo evolui conforme você pontua: o **céu muda de hora** (dia → noite), os **canos enferrujam**, surgem **meteoros** e **habilidades especiais** — tudo com **sons sintetizados** em tempo real (nenhum arquivo de áudio).

---

## 📱 QR Code para jogar online

Aponte a câmera do celular para o QR Code e jogue direto no navegador:

<p align="center">
  <img src="coimbradouglas-github-io-flappy-bird.png" alt="QR Code — https://coimbradouglas.github.io/flappy-bird/" width="240">
</p>

<p align="center">
  <a href="https://coimbradouglas.github.io/flappy-bird/">https://coimbradouglas.github.io/flappy-bird/</a>
</p>

---

## ▶️ Como jogar

1. Abra o arquivo **`index.html`** no navegador (duplo clique ou arraste pra janela do navegador).
2. Clique em **JOGAR** e toque/clique para voar.

Não precisa instalar nada, nem servidor, nem internet.

### Controles

| Ação | Como |
|------|------|
| Voar (flap) | Clique · Toque · `Espaço` · `↑` · `Enter` |
| Menu principal | `Enter`/`Espaço` = Jogar |
| Voltar ao menu | `Esc` (a qualquer momento) · botão **MENU** no Game Over |
| Tela cheia | Botão **⛶** no canto superior direito |

---

## 📱 Resumo prático (celular)

Ao abrir a URL no navegador do celular, o jogo já se ajusta pra ocupar quase toda a tela, **mas a barra de endereço/sistema continua aparecendo**. Para tela cheia de verdade:

- **Android (Chrome/Edge):** toque no botão **⛶** (canto superior direito) → entra em **tela cheia real** e tenta **travar em retrato**. Jogabilidade ideal. ✅
- **iPhone (Safari):** o Safari **não** permite tela cheia para páginas comuns, então o botão **⛶ se esconde sozinho**. Use **Compartilhar → Adicionar à Tela de Início** e abra pelo ícone criado — aí roda **sem as barras**, como um app. ✅

> O canvas é responsivo: mantém a proporção 9:16, renderiza em alta resolução (`devicePixelRatio`) e se reajusta ao redimensionar/rotacionar ou entrar/sair da tela cheia.

---

## ✨ Funcionalidades

- **Física** de gravidade + pulo, com o pássaro rotacionando conforme sobe/cai.

- **Moedas bônus** em três tipos, que somam pontos:
  - 🥉 **Bronze** — `+1`
  - 🥈 **Prata** — `+2`
  - 🥇 **Ouro** — `+3`
  
- **Visual dinâmico** 
- **Habilidades especiais** (veja abaixo).
- **Sons** sintetizados via Web Audio para todas as ações (pulo, ponto, moeda, morte, poderes, cliques…).
- **Menu inicial** com fundo do jogo desfocado e telas de **Recordes** e **Opções**.
- **Recorde** salvo no navegador (`localStorage`).

### Habilidades (power-ups)

Aparecem como itens flutuantes coletáveis, com timer no HUD e efeito visual.

| Item | Efeito | Quando aparece |
|------|--------|----------------|
| ⭐ **Estrela** | Invencível por **13s**: **destrói os canos** que tocar (com estilhaços e tremor de tela) | 
| 🐌 **Câmera lenta** | Tudo a **50%** da velocidade por **13s** (estilo bullet-time) | 
| 🌀 **Espaço (warp)** | **Teletransporta** de uma vez, com flash roxo, portal e partículas | 

---

## ⚙️ Opções (no menu)

- **Som:** liga/desliga todos os efeitos sonoros.
- **Tremor:** liga/desliga o tremor de tela do impacto da Estrela.
- **Zerar Recorde:** apaga a melhor pontuação salva.

As preferências ficam salvas no navegador.

---

## 🛠️ Personalização

Tudo é ajustável no topo do `<script>` em `index.html`:

| Constante | O que controla |
|-----------|----------------|
| `GRAVITY`, `FLAP` | Física do pulo/queda |
| `PIPE_GAP`, `PIPE_SPACING`, `PIPE_SPEED` | Dificuldade dos canos |
| `COIN_TYPES` | Valor, cor e chance das moedas |
| `SKY_STOPS` / `SKY_THEMES` | Pontos e cores da progressão do céu |
| `nightFactor()` | Faixa em que estrelas/lua/noite surgem |
| `RUST_FULL` | Ponto em que os canos ficam totalmente enferrujados |
| `METEOR_SCORE` | A partir de quando surgem meteoros |
| `POWER_SCORE` | A partir de quando surgem Estrela/Câmera lenta |
| `INV_TIME`, `SLOW_TIME` | Duração dos poderes (em frames, 60 = 1s) |
| `SLOW_MUL` | Intensidade da câmera lenta |
| `WARP_GAIN` | Pontos ganhos com o Espaço |

---

## 🧩 Tecnologia

- **HTML5 Canvas 2D** para todo o render (nada de imagens externas — tudo desenhado por código).
- **Web Audio API** para sons sintetizados (osciladores + ruído filtrado).
- **localStorage** para recorde e preferências.
- **Fullscreen API** + `screen.orientation.lock` para tela cheia no celular.
- **Zero dependências**, zero build, um único arquivo.

## 📁 Estrutura

```
FlappyBird/
├── index.html   ← o jogo inteiro (HTML + CSS + JS)
└── README.md
```

### Dados salvos no navegador (`localStorage`)

| Chave | Valor |
|-------|-------|
| `flappy_best` | Melhor pontuação |
| `flappy_shake` | Tremor de tela ligado (`1`) / desligado (`0`) |
| `flappy_sound` | Som ligado (`1`) / desligado (`0`) |

---

Feito para rodar em qualquer navegador moderno, no computador ou no celular. 🎮
Obs: Eu percebi jogando em alguns navegadores que no modo on-line pode acontecer da calibragem da gravidade/ velocidade fique desregular. Se for o seu caso, recomendo baixar o projeto e jogar localmente para ter uma experiência melhor.
