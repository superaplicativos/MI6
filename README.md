# 🕵️‍♂️ MI-X: Operação Eclipse (Web Retro FPS Engine)

[![Claude Fable V1.0](https://img.shields.io/badge/Developed%20with-Claude%20Fable-blueviolet?style=for-the-badge)](#)
[![Three.js](https://img.shields.io/badge/Engine-Three.js-black?style=for-the-badge)](#)
[![Status](https://img.shields.io/badge/Status-Procurando%20Contribuidores-success?style=for-the-badge)](#)

> Um FPS furtivo de espionagem focado na estética e nas mecânicas da era 64-bits (especialmente *007 GoldenEye*). Desenvolvido inteiramente como uma **Single-File Engine**, rodando direto no navegador sem necessidade de emuladores, downloads ou requisições de assets externos.

## 🎯 Visão do Produto

O **MI-X: Operação Eclipse** não é apenas um jogo, é um experimento arquitetural e de produto. O objetivo foi provar que é possível entregar uma experiência 3D completa, com inteligência artificial, física simplificada, áudio dinâmico e múltiplas missões, tudo encapsulado dentro de um único arquivo `index.html`. 

Todo o desenvolvimento foi assistido pela IA **Claude Fable**, resultando em um código vanilla altamente otimizado que gera seus próprios assets proceduralmente no momento da execução.

---

## ⚙️ Arquitetura Técnica & Engine

Para manter a filosofia de *Zero Network Requests* (além da biblioteca base), o jogo utiliza técnicas avançadas de geração procedural[cite: 1]:

### 🎨 Texturização Procedural (Canvas 2D)
Nenhum arquivo `.png` ou `.jpg` é carregado. Todas as texturas são desenhadas pixel a pixel em tempo de execução usando a API do Canvas do HTML5 e convertidas para `THREE.CanvasTexture`[cite: 1].
*   **Geradores de Ruído:** Algoritmos customizados (`ruido()`, `manchas()`) criam imperfeições realistas em concreto, asfalto, terra e metal[cite: 1].
*   **Materiais Dinâmicos:** Painéis de LED, telas de CRT com *scanlines* e água com animação de fluxo (offset dinâmico)[cite: 1].

### 🎵 Sistema de Áudio (Web Audio API)
Sintetizadores nativos do navegador substituem arquivos `.mp3` ou `.wav`[cite: 1].
*   **SFX Baseado em Ruído:** Tiros, passos e explosões são criados injetando *White Noise* em buffers de áudio filtrados por `BiquadFilters` e controlados por envelopes de decaimento exponencial (`exponentialRampToValueAtTime`)[cite: 1].
*   **Trilha Sonora Adaptativa:** Uma rotina de step-sequencer lê arrays de frequências (`padraoCalmo` e `padraoAlerta`) e muda a música dinamicamente se algum inimigo no mapa entrar em estado de alerta[cite: 1].

### 🧠 Inteligência Artificial (State Machine)
Os NPCs (Guardas) operam através de uma máquina de estados finita:
*   **Patrulha:** Seguem *waypoints* predefinidos.
*   **Visão e Audição:** Utilizam Raycasting (`THREE.Raycaster`) para linha de visão (LOS) atrelado a um cone de visão e reagem a ruídos de tiros não silenciados[cite: 1].
*   **Alerta:** Ao detectarem o Agente 09, disparam alarmes locais que encadeiam o estado de alerta para outros guardas próximos[cite: 1].

---

## 🔫 Arsenal & Combate

O jogo implementa balística via *Raycasting* instantâneo (Hitscan) com mecânicas de *cooldown*, recuo da câmera (recoil) e dispersão[cite: 1].

| Arma | Tipo | Munição | Ruído | Dano (Headshot) | Características |
| :--- | :--- | :---: | :---: | :---: | :--- |
| **PX-7 Silenciada** | Pistola | 7 / 35 | Baixo (8m) | Hit-Kill | A arma primária do espião. Discreta, letal em distâncias curtas e não aciona alarmes ao redor[cite: 1]. |
| **RV-9 Fuzil** | Automático | 30 / 60 | Alto (30m) | Hit-Kill | Encontrada no cenário. Alta cadência e dispersão. Um disparo atrai toda a base[cite: 1]. |

> **Dica de Design:** O jogo conta com um sistema de **Aim Assist** suave no eixo central (indicado por um anel vermelho no HUD) que ajuda na aquisição de alvos, replicando o "feeling" da mira solta dos controles analógicos antigos[cite: 1].

---

## 🗺️ Missões Disponíveis (v1.0)

O nível de design foca em múltiplas rotas e objetivos que devem ser concluídos antes da extração[cite: 1].

### MISSÃO 01: Complexo Vektra (Noturna)
Infiltração furtiva em uma área industrial sob forte esquema de segurança.
*   **Estética:** Iluminação azulada (HemisphereLight), neblina densa, lua geradora de sombras dramáticas[cite: 1].
*   **Objetivos:**
    1. Localizar e hackear o terminal de dados na ala leste[cite: 1].
    2. Plantar explosivos no núcleo do gerador principal na ala oeste[cite: 1].
    3. Alcançar o ponto de extração seguro[cite: 1].

### MISSÃO 02: Represa Krava (Diurna / Longa)
Uma jornada épica pelas montanhas até uma colossal obra de engenharia militar.
*   **Estética:** Céu nublado, abismos, paredões de rocha e um rio correndo no fundo de um canyon de 70 metros de profundidade[cite: 1].
*   **Objetivos:**
    1. Invadir a guarita de segurança para destravar o portão principal do checkpoint[cite: 1].
    2. Encontrar a entrada leste da galeria técnica para sabotar a rede de transformadores[cite: 1].
    3. Infiltrar-se no prédio administrativo e arrombar o cofre do comandante para roubar projetos secretos[cite: 1].

---

## 🚀 Como Rodar o Jogo

Como a engine é puramente Client-Side e contida, a execução é imediata:

1. Clone o repositório:
```bash
   git clone [https://github.com/seu-usuario/mi-x-eclipse.git](https://github.com/seu-usuario/mi-x-eclipse.git)
