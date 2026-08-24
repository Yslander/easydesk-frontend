# EasyDesk (ConnectHub) - Frontend 🖥️

O **EasyDesk Frontend** é a interface de usuário do sistema de gestão de chamados. Nesta fase do projeto (ConnectHub), a aplicação evoluiu de um sistema estático que utilizava `LocalStorage` para uma aplicação real e dinâmica, totalmente integrada a uma API RESTful com banco de dados relacional e autenticação protegida por JWT.

## 🎯 Principais Funcionalidades

* **Integração com API REST:** Comunicação assíncrona utilizando a `Fetch API` para realizar operações de CRUD diretamente no servidor.
* **Autenticação e Login:** Telas dedicadas de login e registro, com captura e armazenamento seguro do Token JWT no navegador para controle de acesso ao `painel.html`.
* **Tratamento de Erros e UX:** Exibição de estados de carregamento (*loading*) e mensagens de erro amigáveis baseadas nos status HTTP da API (ex: "Senha incorreta", "Acesso não autorizado").
* **Renderização Dinâmica:** Atualização instantânea do DOM (cards de chamados, mudança de cores por status e contadores) alimentada exclusivamente pelos dados vindos do banco de dados na nuvem.
* **Design Responsivo:** Interface fluida adaptada para uso em computadores e celulares, garantindo usabilidade em qualquer dispositivo.

## 💻 Tecnologias Utilizadas

* **HTML5:** Estruturação das páginas de acesso e do painel de controle.
* **CSS3:** Estilização pura, customizada e livre de frameworks externos (sem Bootstrap ou Tailwind).
* **JavaScript (Vanilla):** Motor da aplicação responsável pelo controle de rotas privadas, injeção de Headers de Autorização (Bearer Token), manipulação de Objetos/Arrays e Eventos do DOM.
* **Deploy/Hospedagem:** Vercel.

## ⚙️ Como Executar Localmente

**1. Clone o repositório:**
```bash
git clone [https://github.com/Yslander/easydesk-frontend.git](https://github.com/Yslander/easydesk-frontend.git)
cd easydesk-frontend

```

**2. Aponte para a API:**
Certifique-se de que as requisições `fetch` dentro dos arquivos JavaScript (como o arquivo principal e o de autenticação) estejam apontando para a URL correta do seu back-end (ex: `http://localhost:3000/api` para testes locais ou a URL da API hospedada).

**3. Execute o projeto:**
Por ser uma aplicação baseada em Vanilla JS, não é necessária a instalação de dependências como o Node.js no front-end. Basta abrir o projeto utilizando a extensão **Live Server** do VS Code ou abrir o arquivo `index.html` diretamente em seu navegador.

---

## 👨‍💻 Autores

Desenvolvido por **Yslander Martins de Souza** em parceria com **Lucas Satoshi Cipriano Oikawa**.