# GitHub Actions Demo

Este repositório é uma **demonstração prática do GitHub Actions**, criado para ajudar desenvolvedores a entender como funcionam os workflows, jobs e actions, além de fornecer exemplos reais para estudo e prática.

---

## Comece agora
Para começar a aprender sobre GitHub Actions, leia primeiro a [Introdução ao GitHub Actions](github-actions-intro.md) e entenda os conceitos básicos.

---

## Estrutura do projeto

- `github-actions-intro.md` – Introdução ao GitHub Actions.  
- `important-concepts-github-actions.md` – Conceitos essenciais do GitHub Actions.  
- `workflow-structure.md` – Estrutura detalhada de um workflow com exemplos YAML.  
- `nostr-demo-ts/` – Projeto em **Next.js + TypeScript** demonstrando um feed Nostr em tempo real.  
- `package.json` – Dependências do projeto Next.js.  
- `LICENSE` – Licença do repositório.

---

## Objetivo

Este repositório serve para:  

1. **Aprender conceitos chave do GitHub Actions**, incluindo workflows, jobs, steps, actions e runners.  
2. **Praticar a criação de workflows** automatizados para repositórios GitHub.  
3. **Explorar exemplos práticos** integrando automação com projetos reais, como o feed Nostr.  
4. Servir como **material de referência e sandbox** para experimentar triggers, actions e pipelines.

---

## Como usar
### 1. Clonar o repositório
```bash
git clone https://github.com/CUSTcoding/github-actions.git
cd github-actions
```
### 2. Ler a documentação
- Comece pelo `github-actions-intro.md` para visão geral.  
- Continue com `important-concepts-github-actions.md` e `workflow-structure.md` para entender detalhadamente.

### 3. Executar o demo Next.js (opcional)
```bash
cd nostr-demo-ts
npm install
npm run dev