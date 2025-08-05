# Lista de Tarefas (To-Do List)

**Desenvolvida com:** Vue.js + Tailwind CSS

## 📋 Descrição

Este é um site simples de lista de tarefas (To-Do List) criado com Vue.js e estilizado com Tailwind CSS. Ele permite que você adicione, marque como concluída e remova tarefas, mantendo os dados salvos no armazenamento local do navegador.

## ✨ Funcionalidades

* **Adicionar Tarefas:** Insira novas atividades na lista.
* **Marcar/Desmarcar Tarefas:** Clique para alternar o status de conclusão de cada tarefa.
* **Remover Tarefas:** Exclua tarefas concluídas ou não.
* **Armazenamento Local:** As tarefas são salvas no `localStorage`, permitindo persistência entre sessões.

## 🚀 Tecnologias Utilizadas

* [Vue.js](https://vuejs.org/) (versão 3.x)
* [Tailwind CSS](https://tailwindcss.com/) (versão 3.x)
* JavaScript (ES6+)
* HTML5
* CSS3

## 🛠️ Pré-requisitos

* **Node.js** (>= 14.x)
* **npm** (>= 6.x) ou **yarn** (>= 1.x)

## 💻 Instalação

1. **Clone este repositório:**

   ```bash
   git clone https://github.com/SEU_USUARIO/nome-do-repositorio.git
   cd nome-do-repositorio
   ```

2. **Instale as dependências:**

   ```bash
   npm install
   # ou
   yarn install
   ```

3. **Inicie o servidor de desenvolvimento:**

   ```bash
   npm run serve
   # ou
   yarn serve
   ```

4. **Abra o app no navegador:**

   Acesse `http://localhost:8080` (ou a porta indicada no terminal).

## ⚙️ Scripts Disponíveis

| Comando         | Descrição                             |
| --------------- | ------------------------------------- |
| `npm run serve` | Inicia o servidor de desenvolvimento  |
| `npm run build` | Gera a versão otimizada para produção |
| `npm run lint`  | Executa o linter (ESLint)             |

## 🗂️ Estrutura de Pastas

```
├── public/              # Arquivos estáticos (index.html, favicon etc.)
├── src/
│   ├── assets/          # Imagens e estilos globais
│   ├── components/      # Componentes Vue reutilizáveis
│   ├── views/           # Páginas principais
│   ├── App.vue          # Componente raiz
│   └── main.js          # Ponto de entrada da aplicação
├── .eslintrc.js         # Configuração do ESLint
├── tailwind.config.js   # Configuração do Tailwind CSS
└── package.json         # Dependências e scripts
```

## 🤝 Contribuição

Contribuições são bem-vindas! Caso queira colaborar com melhorias ou correções, siga estes passos:

1. Fork este repositório.
2. Crie uma branch para sua feature: `git checkout -b feature/nome-da-feature`.
3. Faça commit das suas alterações: `git commit -m 'Adiciona nova feature'`.
4. Faça push para a branch remota: `git push origin feature/nome-da-feature`.
5. Abra um Pull Request neste repositório.

## 📄 Licença

Este projeto está licenciado sob a [MIT License](LICENSE).

---

> Desenvolvido com carinho 💜
