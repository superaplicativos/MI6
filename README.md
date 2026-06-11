# 🕵️‍♂️ MI-X: Operação Eclipse (MI6 Game)

[![Claude Fable V1.0](https://img.shields.io/badge/Developed%20with-Claude%20Fable-blueviolet?style=for-the-badge)](https://anthropic.com)
[![Version 1.0](https://img.shields.io/badge/Version-1.0-green?style=for-the-badge)](./)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg?style=for-the-badge)](LICENSE)

> Um clone espiritual web do clássico **007 contra GoldenEye (N64)**, construído puramente com tecnologias web modernas (`HTML5`, `CSS3`, `Vanilla JavaScript` e `Three.js`). Desenvolvido em parceria com a inteligência artificial **Claude Fable**.

O projeto encontra-se em sua **versão 1.0**, entregando uma base jogável em primeira pessoa (FPS) retro, leve, sem necessidade de emuladores ou downloads, rodando direto no navegador a 60 FPS com baixa resolução proposital para replicar a estética marcante dos anos 90.

---

## 🎮 Demonstração / Como Jogar

Como o jogo é composto por um único arquivo estático de vanguarda, basta abrir o `index.html` em qualquer navegador moderno.

### 🕹️ Controles
*   **WASD**: Movimentação do Agente 09.
*   **MOUSE**: Mirar (Trava de ponteiro inclusa).
*   **CLIQUE ESQUERDO**: Atirar (Segure para disparo automático com o Fuzil).
*   **R**: Recarregar arma.
*   **1 / 2**: Trocar entre Pistola Silenciada e Fuzil de Assalto.
*   **E (Segurar)**: Interagir com objetos (Hackear terminais, Plantar explosivos, Abrir cofres).
*   **TAB / ESC**: Pausar / Abrir o Relógio de Missão clássico.
*   **M**: Ligar/Desligar a trilha sonora adaptativa.

---

## 🛠️ Recursos Atuais (v1.0)

O motor do jogo foi construído do zero (`Custom Single-File Engine`) e já conta com as seguintes mecânicas prontas:

*   **Renderização Retrô**: Filtro pixelado simulando a resolução original do Nintendo 64 usando técnicas de downsampling no canvas do `Three.js`.
*   **Texturas Dinâmicas**: Geradas via código (`HTML5 Canvas Context 2D`) em tempo real, evitando requisições HTTP externas de imagens e mantendo o código ultraleve.
*   **Áudio Procedural**: Sons de tiros (silenciados e pesados), passos, alarmes e explosões gerados nativamente através da `Web Audio API` (Osciladores e Nós de Ganho).
*   **Trilha Sonora Adaptativa**: Sistema de áudio que muda o padrão da música de fundo caso os inimigos entrem em estado de alerta.
*   **Miras Assistidas**: Sistema de auxílio de mira sutil para simular a jogabilidade fluida de consoles antigos no PC.
*   **Duas Missões Completas**:
    1.  **Complexo Vektra**: Infiltração noturna tática baseada em furtividade e sabotagem de geradores.
    2.  **Represa Krava**: Mapa longo diurno, com portões trancados, coleta de armas do cenário, galeria técnica interna com emissão de vapor e fuga por rapel.
*   **5 Classes de Inimigos**: Comum, Guarda de Campo, Oficial, Sniper de longa distância e Soldado de Elite.

---

## 🚀 Próximos Passos & O que estamos buscando (Contribua!)

O core do jogo está sólido, mas queremos levar o **MI-X** para o próximo nível. Se você é desenvolvedor JavaScript, artista técnico Three.js, ou entusiasta de Web Audio, **sua contribuição é muito bem-vinda!**

### 🎯 Roadmap de Melhorias:
*   [ ] **Sistema de Inteligência Artificial Avançado**: Adicionar caminhos de patrulha mais complexos e reações a corpos caídos.
*   [ ] **Novas Armas**: Implementação de minas de proximidade (Proximity Mines), lançadores de foguetes e a icônica faca de arremesso.
*   [ ] **Modelos 3D de Baixo Polígono (Low-Poly)**: Substituir as caixas de colisão dos guardas e armas por meshes texturizados retrô (formato `.gltf` ou `.obj`).
*   [ ] **Efeitos Visuais**: Sprites de sangue 2D (estilo outdoor), estilhaços físicos ao atirar nas paredes e animações de recarregamento mais detalhadas.
*   [ ] **Otimização de Colisão**: Migrar o array de colisores retangulares simples para um sistema de octree ou bounding boxes nativas mais escalável.

---

## 🤝 Como Contribuir

1. Faça um **Fork** do projeto.
2. Crie uma branch para sua feature: `git checkout -b feature/minha-melhoria`.
3. Faça o commit de suas alterações: `git commit -m 'Adiciona novos efeitos visuais retrô'`.
4. Envie para a branch original: `git push origin feature/minha-melhoria`.
5. Abra um **Pull Request**.

*Sinta-se livre para abrir Issues para relatar bugs ou sugerir novas ideias de missões!*

---

## 📄 Licença

Este projeto está sob a licença MIT. Veja o arquivo [LICENSE](LICENSE) para mais detalhes.

---
Developed with 💚 by the community & Claude Fable.
