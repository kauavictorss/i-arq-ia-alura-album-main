# 📘 Alura Álbum - Copa do Mundo Tech

Um álbum de figurinhas virtual e interativo desenvolvido durante a **Imersão Arquitetura Web com IA** da Alura. O projeto celebra as personalidades mais influentes da história e do presente da tecnologia, divididas em categorias temáticas.

---

## 🛠️ Stacks Utilizadas

### **Frontend**

![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge&logo=html5&logoColor=white)
![CSS3](https://img.shields.io/badge/CSS3-1572B6?style=for-the-badge&logo=css3&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black)

### **Backend**

![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)
![FastAPI](https://img.shields.io/badge/FastAPI-009688?style=for-the-badge&logo=fastapi&logoColor=white)
![Uvicorn](https://img.shields.io/badge/Uvicorn-4053D6?style=for-the-badge&logo=uvicorn&logoColor=white)

---

## 🧠 Inteligência Artificial Aplicada no Projeto

A Inteligência Artificial desempenhou um papel central na concepção e execução do projeto:

- 🎨 **Geração de Imagens & Assets Visuais**: As figurinhas e elementos gráficos dos ícones da tecnologia foram concebidos e refinados utilizando ferramentas de **IA Generativa de Imagens**, proporcionando um visual coeso em estilo *dark futurista*.
- 🤖 **Pair Programming & Assistência de Código**: IAs generativas de código (LLMs) foram empregadas no suporte ao desenvolvimento da lógica de síntese sonora com **Web Audio API**, estruturação de endpoints no **FastAPI** e estilização CSS responsiva.
- 💡 **Curadoria Temática**: O álbum reserva sua primeira seção para homenagear os grandes nomes da história e evolução da IA (Alan Turing, Sam Altman, Geoffrey Hinton, Yann LeCun, John McCarthy).

---

## ⚡ Recursos & Diferenciais Técnicos

- 📖 **St.PageFlip (Efeito 3D)**: Biblioteca especializada para simular o efeito realista de folheamento de páginas em um álbum físico, com sombras dinâmicas, dobra de papel e física de interatividade ao arrastar com o mouse ou toque.
- 🔊 **Web Audio API (Síntese Sonora Procedural)**: Áudio procedural gerado dinamicamente via código (filtros *bandpass*, *lowpass* e varredura de frequências). Simula a fricção física de folhas de papel sem a necessidade de carregar arquivos de áudio externos (`.mp3` ou `.wav`).
- ⚡ **Backend Assíncrono com FastAPI**: API de alta performance responsável pelo gerenciamento de dados das figurinhas e entrega otimizada de imagens.

---

## 🎯 Objetivo do Projeto

O **Alura Álbum** tem como objetivo proporcionar uma experiência imersiva e interativa de um álbum de figurinhas físico no navegador. Ele combina:

- **Efeitos Visuais e Animações 3D**: Simulação realista de folheamento de páginas com sombras e texturas.
- **Áudio Sintetizado**: Reprodução do som característico de folhear páginas em papel, gerado em tempo real via Web Audio API.
- **Integração Backend-Frontend**: Carregamento dinâmico de figurinhas e dados através de requisições `fetch` para uma API FastAPI.
- **Design Temático e Responsivo**: Visual futurista em Dark Mode com identidade inspirada em tecnologia e inteligência artificial.

---

## 📋 Pré-requisitos

Antes de iniciar, você precisará ter instalado em sua máquina:

- [Python 3.10+](https://www.python.org/)
- Um navegador web moderno (Google Chrome, Firefox, Edge, Safari)
- (Opcional) Extensão **Live Server** para o VS Code

---

## 📁 Estrutura e Funcionalidades dos Arquivos

```text
├── backend/
│   ├── figurinhas/        # Imagens das figurinhas (.jpg, .png, etc.)
│   └── main.py            # Servidor FastAPI com rotas da API
├── frontend/
│   ├── index.html         # Estrutura semântica e páginas do álbum
│   ├── style.css          # Estilização visual, grid e temas das categorias
│   └── app.js             # Lógica do álbum 3D, síntese de áudio e fetch da API
└── README.md              # Documentação principal do projeto
```

### 📄 Frontend

- **[`frontend/index.html`](frontend/index.html)**:
  - **Controles de UI**: Botões fixos para alternar áudio (som ativado/desativado) e botões laterais de navegação entre as páginas.
  - **Capa e Contracapa**: Design especial de capa com efeito *glitch*, esfera 3D iluminada e silhuetas de figurinhas em miniatura.
  - **Páginas Temáticas**:
    - **Pág. 1 - IA**: Pioneiros da Inteligência Artificial (Alan Turing, Sam Altman, Geoffrey Hinton, etc.).
    - **Pág. 2 - Python**: Arquitetos da Simplicidade (Guido van Rossum, Tim Peters, Wes McKinney, etc.).
    - **Pág. 3 - Banco de Dados**: Arquitetos de Bancos de Dados (Edgar F. Codd, Larry Ellison, Michael Widenius, etc.).
    - **Pág. 4 - Sistemas Operacionais**: Arquitetos da Computação Moderna (Linus Torvalds, Dennis Ritchie, Steve Jobs, Bill Gates, etc.).
    - **Pág. 5 & 6 - Brasil**: Celebridades Tech Nacionais (Paulo Silveira, Guilherme Silveira, Gustavo Guanabara, Rafaela Ballerini, etc.).
  - **Slots de Figurinhas**: Estrutura de grid com identificadores únicos (`#01` a `#30`) para encaixe das figurinhas.
- **[`frontend/style.css`](frontend/style.css)**:
  - **Variáveis CSS (`:root`)**: Paleta de cores centralizada com tons de azul universo, preto moderno e destaques em gradiente.
  - **Efeitos de Transição e Hover**: Animações suaves nos botões de controle, sombras cibernéticas e transformações ao passar o cursor.
  - **Estilização dos Slots e Figurinhas**: Molduras personalizadas e suporte a figurinhas com revelação animada (`slot-preenchido`).
  - **Badges Temáticas**: Estilização exclusiva para cada categoria (`.badge-ia`, `.badge-python`, `.badge-db`, `.badge-os`, `.badge-brasil`).
- **[`frontend/app.js`](frontend/app.js)**:
  - **Inicialização do Livro 3D (`St.PageFlip`)**: Configuração de navegação e efeito realista de folhear páginas.
  - **Sintetizador de Som (`playPaperTurnSound`)**: Síntese sonora procedural via **Web Audio API** (sem arquivos `.mp3`).
  - **Consumo de API (`preencherFigurinhas`)**: Requisições `fetch` para `http://localhost:8000/figurinhas` injetando imagens dinamicamente.

### ⚙️ Backend

- **[`backend/main.py`](backend/main.py)**:
  - API desenvolvida em **FastAPI** responsável por disponibilizar os metadados das figurinhas e servir os arquivos de imagens correspondentes da pasta `figurinhas/`.
  - Rotas principais:
    - `GET /figurinhas`: Retorna a lista de figurinhas ativas em formato JSON.
    - `GET /figurinhas/{id}/imagem`: Serve o arquivo de imagem correspondente ao ID informado.

---

## 🚀 Como Executar o Projeto

### 1️⃣ Inicializar o Backend (API FastAPI)

1. Navegue até a pasta do backend:

   ```bash
   cd backend
   ```

2. Crie e ative o ambiente virtual (opcional, mas recomendado):

   ```bash
   python -m venv .venv
   # Windows (PowerShell):
   .\.venv\Scripts\Activate.ps1
   # Linux/macOS:
   source .venv/bin/activate
   ```

3. Instale as dependências necessárias:

   ```bash
   pip install fastapi uvicorn
   ```

4. Inicie o servidor da API:

   ```bash
   uvicorn main:app --reload
   ```

   A API estará rodando em `http://localhost:8000`.

---

### 2️⃣ Executar o Frontend

1. Com o backend em execução, abra o arquivo `frontend/index.html`:
   - Diretamente no seu navegador de preferência;
   - Ou utilizando a extensão **Live Server** no VS Code para servir a aplicação web.
2. Interaja com o álbum: folheie as páginas, ligue/desligue o som e veja as figurinhas sendo carregadas dinamicamente da API!

---

## 📜 Licença & Agradecimentos

Projeto desenvolvido com fins educativos durante a **Imersão Arquitetura Web & IA** promovida pela [Alura](https://www.alura.com.br/).

Distribuído sob a licença MIT.
