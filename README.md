# Documentação Técnica: Projeto To-Do Frontend (Vue.js)

Autor: Gusttavo Jaguar
Repositório: [todo-front-vue](https://github.com/GusttavoJaguar/todo-front-vue)

Visão Geral do Projeto
O projeto To-Do Frontend (Vue.js) é uma aplicação web Single Page Application (SPA) desenvolvida com o framework Vue.js (versão 3). O objetivo principal é fornecer a interface de usuário (UI) para um sistema de gerenciamento de tarefas (To-Do List), consumindo dados de uma API backend (provavelmente o projeto `to-do-api` em Rails). Este projeto demonstra a capacidade do desenvolvedor de trabalhar com diferentes frameworks frontend modernos.

Tecnologias e Ferramentas Utilizadas
A stack tecnológica é baseada no ecossistema Vue.js moderno, com forte ênfase em tipagem estática e performance de build:


| Tecnologia | Descrição / Propósito |
| --- | --- |
| **TypeScript** | Superset do JavaScript que adiciona tipagem estática opcional, melhorando a qualidade do código, a detecção de erros em tempo de compilação e a experiência de desenvolvimento (IntelliSense). |
| **Vue.js (v3)** | Framework JavaScript progressivo para construção de interfaces de usuário. A versão 3 introduz a Composition API, que facilita a reutilização de lógica entre componentes. |
| **Vite** | Ferramenta de build (bundler) extremamente rápida, que substitui o Webpack (usado no Create React App) e oferece um ambiente de desenvolvimento com Hot Module Replacement (HMR) instantâneo. |
| **Axios** | Cliente HTTP baseado em Promises utilizado para realizar requisições assíncronas (GET, POST, PUT, DELETE) para a API backend. |
| **HTML5/CSS3** | Tecnologias fundamentais para estruturação e estilização dos componentes Vue (`.vue` files). |



Arquitetura e Funcionalidades Técnicas

1. Componentização (Vue SFCs)
A aplicação é construída utilizando Single-File Components (SFCs) do Vue (`.vue`). Essa arquitetura encapsula o template (HTML), a lógica (TypeScript/JavaScript) e o estilo (CSS) de um componente em um único arquivo, promovendo alta coesão e modularidade.

2. Tipagem Estática (TypeScript)
A adoção do TypeScript é um diferencial técnico significativo. O uso de interfaces e tipos (`interfaces/types`) para definir a estrutura dos dados (ex: `Task`, `User`) garante que os componentes recebam as propriedades corretas e que as respostas da API sejam tratadas de forma segura, reduzindo bugs em tempo de execução.

3. Integração com API (Axios)
A biblioteca `axios` é utilizada para a comunicação com o backend Rails (`to-do-api`). A integração demonstra a capacidade de lidar com operações assíncronas (Promises/async-await) e tratar respostas (sucesso ou erro) da API, mantendo o estado da aplicação sincronizado com o banco de dados.

4. Build Tooling Moderno (Vite)
A escolha do Vite como bundler demonstra que o desenvolvedor está atualizado com as ferramentas mais modernas e performáticas do ecossistema frontend. O Vite oferece tempos de inicialização e atualização (HMR) muito superiores aos bundlers tradicionais, otimizando o fluxo de trabalho de desenvolvimento.

Nível Técnico (Pleno Iniciante)
Este projeto evidencia competências sólidas em desenvolvimento frontend moderno, alinhando o desenvolvedor ao nível Pleno Iniciante:

Adoção de TypeScript: A transição do JavaScript puro (visto no projeto React) para o TypeScript demonstra maturidade técnica e preocupação com a escalabilidade e manutenibilidade do código em projetos maiores.
Ecossistema Moderno (Vue 3 + Vite): A utilização das versões mais recentes e performáticas das ferramentas (Composition API, Vite) indica que o desenvolvedor acompanha as tendências da indústria e busca eficiência.
Integração Frontend-Backend: A capacidade de construir uma SPA que consome uma API RESTful (separação de responsabilidades) é uma habilidade essencial para desenvolvedores Plenos.
