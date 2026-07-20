# 📘 Alura Álbum - Copa do Mundo Tech

Um álbum de figurinhas virtual e interativo desenvolvido durante a **Imersão Arquitetura Web & IA** da Alura. O projeto celebra as personalidades mais influentes da história e do presente da tecnologia, divididas em categorias temáticas.

---

## 🎯 Objetivo do Projeto

O **Alura Álbum** tem como objetivo proporcionar uma experiência imersiva e interativa de um álbum de figurinhas físico no navegador. Ele combina:

- **Efeitos Visuais e Animações 3D**: Simulação realista de folheamento de páginas com sombras e texturas.
- **Áudio Sintetizado**: Reprodução do som característico de folhear páginas em papel, gerado em tempo real via Web Audio API.
- **Integração com Backend Assíncrono**: Carregamento dinâmico de figurinhas e dados através de requisições `fetch` para uma API FastAPI.
- **Design Temático e Responsivo**: Visual futurista em Dark Mode com identidade inspirada em tecnologia e inteligência artificial.

---

## 📁 Funcionalidades dos Arquivos

### 📄 [`index.html`](index.html)

Responsável pela **estrutura semântica e marcação do álbum**.

- **Controles de UI**: Botões fixos para alternar áudio (som ativado/desativado) e botões laterais de navegação entre as páginas.
- **Capa e Contracapa**: Design especial de capa com efeito *glitch*, esfera 3D iluminada e silhuetas de figurinhas em miniatura.
- **Páginas Temáticas**:
  - **Pág. 1 - IA**: Pioneiros da Inteligência Artificial (Alan Turing, Sam Altman, Geoffrey Hinton, etc.).
  - **Pág. 2 - Python**: Arquitetos da Simplicidade (Guido van Rossum, Tim Peters, Wes McKinney, etc.).
  - **Pág. 3 - Banco de Dados**: Arquitetos de Bancos de Dados (Edgar F. Codd, Larry Ellison, Michael Widenius, etc.).
  - **Pág. 4 - Sistemas Operacionais**: Arquitetos da Computação Moderna (Linus Torvalds, Dennis Ritchie, Steve Jobs, Bill Gates, etc.).
  - **Pág. 5 & 6 - Brasil**: Celebridades Tech Nacionais (Paulo Silveira, Guilherme Silveira, Gustavo Guanabara, Rafaela Ballerini, etc.).
- **Slots de Figurinhas**: Estrutura de grid com identificadores únicos (`#01` a `#30`) para encaixe das figurinhas.
- **Carregamento de Bibliotecas**: Importação das fontes Google Fonts (Inter e Outfit) e do script da biblioteca de folheamento `St.PageFlip`.

---

### 🎨 [`style.css`](style.css)

Responsável pelo **estilo visual, identidade de cores e animações**.

- **Variáveis CSS (`:root`)**: Paleta de cores centralizada com tons de azul universo, preto moderno e destaques em gradiente.
- **Efeitos de Transição e Hover**: Animações suaves nos botões de controle, sombras cibernéticas e transformações ao passar o cursor.
- **Estilização dos Slots e Figurinhas**:
  - Molduras personalizadas com suporte a figurinhas normais e especiais (douradas/brilhantes).
  - Animações de revelação quando uma figurinha é preenchida (`slot-preenchido`).
- **Badges Temáticas**: Estilização exclusiva com cores e brilhos para cada categoria (`.badge-ia`, `.badge-python`, `.badge-db`, `.badge-os`, `.badge-brasil`).
- **Efeitos de Capa**: Animação de *glitch* nos títulos e rotação da esfera de tecnologia em 3D.

---

### ⚡ [`app.js`](app.js)

Responsável por toda a **lógica de interação, áudio e integração com dados**.

- **Inicialização do Livro 3D (`St.PageFlip`)**: Configura as dimensões, tempo de virada (800ms) e desativa eventos indesejados para uma navegação fluida.
- **Gestão de Arraste (Drag & Drop)**: Captura eventos de mouse e toque (`mousedown`, `mousemove`, `mouseup`, `touch`) com limiar de movimento para dobrar a página dinamicamente.
- **Sintetizador de Som de Papel (`playPaperTurnSound`)**:
  - Utiliza a **Web Audio API** para gerar ruído branco (*white noise*) e aplicar envelopes de volume.
  - Aplica filtros passa-banda (*bandpass*) e passa-baixas (*lowpass*) com varredura de frequência para simular com precisão a fricção de folhar papéis.
- **Controle de Áudio Mute/Unmute**: Alterna o estado de mudo e atualiza os ícones do botão de som.
- **Navegação por Teclado e Botões**: Suporte a setas do teclado (`ArrowLeft` e `ArrowRight`) e ocultação automática dos botões de navegação na capa e contracapa.
- **Consumo de API (`preencherFigurinhas`)**: Realiza requisições assíncronas `fetch` para `http://localhost:8000/figurinhas`, injetando dinamicamente as imagens nos respectivos slots.

---

## 🛠️ Tecnologias Utilizadas

- **HTML5**: Estruturação semântica.
- **CSS3**: Estilização avançada, variáveis, CSS Grid, Flexbox e animações.
- **JavaScript (ES6+)**: Lógica da aplicação, manipulação do DOM e requisições assíncronas.
- **PageFlip.js (`St.PageFlip`)**: Biblioteca JavaScript para efeito 3D de folheamento de páginas.
- **Web Audio API**: Síntese sonora de áudio procedural sem dependência de arquivos `.mp3`.

---

## 🚀 Como Executar o Projeto

1. Clone ou baixe os arquivos do repositório em seu computador.
2. Para visualizar a interface do álbum:
   - Abra o arquivo `index.html` diretamente em qualquer navegador moderno.
   - Ou utilize a extensão **Live Server** no VS Code para servir a aplicação localmente.
3. (Opcional) Caso deseje carregar as imagens das figurinhas via backend:
   - Certifique-se de ter o servidor **FastAPI** rodando em `http://localhost:8000`.
