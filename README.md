# EasyDesk Frontend — Interface Central de Suporte

O EasyDesk Frontend é a interface web do sistema EasyDesk, projetada para oferecer uma experiência de utilizador fluida, responsiva e intuitiva na abertura, monitorização e gestão de chamados de suporte técnico. A aplicação funciona como uma IHM (Interface Homem-Máquina) moderna, comunicando de forma totalmente assíncrona com a EasyDesk API para o processamento de dados em tempo real.

## 🔗 Links do Projeto
* **Deploy da Aplicação:** [EasyDesk Live Demo](https://easydesk-frontend.vercel.app/index.html)
* **Painel de Desenvolvimento (GitHub Projects):** [EasyDesk Frontend Kanban](https://github.com/users/Yslander/projects/4)

## 🛠️ Tecnologias e Recursos Utilizados
O desenvolvimento do frontend priorizou a performance, a leveza e a ausência de dependências complexas (zero frameworks), utilizando a base nativa da web:
* **HTML5:** Estruturação semântica da interface, tabelas de dados e formulários dinâmicos.
* **CSS3:** Design moderno com foco em usabilidade corporativa, transições suaves, estilização de estados de prioridade e janelas modais flutuantes.
* **JavaScript Vanilla (ES6+):** Manipulação dinâmica do DOM, controlo de eventos, gestão de estados de visualização e execução de requisições assíncronas através da *Fetch API*.
* **Hospedagem e Distribuição:** Vercel (Integração contínua e entrega de alta velocidade).

## 🛡️ Arquitetura de Segurança na Interface (Vigia de Rotas)
* **Gestão de Sessão Stateless:** Após a validação das credenciais na interface de login, o token JWT retornado pela API é armazenado de forma segura no `localStorage` do navegador do utilizador.
* **Proteção Ativa de Páginas:** Foi implementado um script de verificação imediata (Vigia) no carregamento do painel principal. Caso o utilizador tente aceder diretamente ao ficheiro `painel.html` sem possuir o token válido no navegador, o sistema bloqueia o acesso, exibe um alerta de segurança e redireciona o intruso para o ecrã de login (`index.html`).
* **Headers de Autorização:** Todas as requisições operacionais de leitura ou alteração de dados incluem automaticamente o cabeçalho `Authorization: Bearer <token>`, assegurando a legitimidade da comunicação com o servidor.

## 💻 Funcionalidades Implementadas

### 1. Ecrã de Autenticação (`index.html`)
* Formulário seguro para captura de e-mail e palavra-passe.
* Disparo assíncrono via método `POST` para validação de acesso.
* Redirecionamento automático após confirmação de credenciais válidas.

### 2. Painel de Controlo (`painel.html`)
* **Leitura Dinâmica (READ):** Consome a rota `GET` da API para listar todos os chamados ativos numa tabela organizada, aplicando cores específicas conforme o nível de criticidade (Baixa, Média, Alta).
* **Abertura de Chamados (CREATE):** Construção de uma janela modal flutuante moderna que recolhe os dados do problema e realiza o envio via `POST` diretamente para a nuvem.
* **Atualização Dinâmica (UPDATE):** Botão inteligente que permite ao operador marcar um chamado pendente como "Concluído" através de uma requisição `PUT`.
* **Eliminação de Registos (DELETE):** Controlo operacional protegido por confirmação de segurança para remover chamados de forma definitiva do ecossistema.

## 📁 Estrutura de Ficheiros do Projeto
```gantt
easydesk-frontend/
├── index.html        # Interface de login e gestão do token JWT inicial
├── painel.html       # Painel de controlo principal, tabela de chamados e modal
└── README.md         # Documentação oficial do repositório frontend

## 🚀 Como Executar o Projeto Localmente

Para testar ou expandir a interface no seu computador, certifique-se de que a [EasyDesk API](https://github.com/Yslander/easydesk-api.git) está ativa e siga os passos abaixo:

1. Clone este repositório para a sua máquina local executando o comando no terminal:
```bash
git clone [https://github.com/Yslander/easydesk-frontend.git](https://github.com/Yslander/easydesk-frontend.git)
```
2. Abra a pasta do projeto clonado no seu **Visual Studio Code**.
3. Certifique-se de que possui a extensão **Live Server** instalada no seu VS Code.
4. Abra o arquivo `index.html` no editor.
5. Clique no botão **"Go Live"** localizado no canto inferior direito da tela.
6. A aplicação será inicializada automaticamente no seu navegador através do endereço local seguro `http://127.0.0.1:5500/index.html`.