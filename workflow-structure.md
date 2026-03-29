# Estrutura de um workflow

Um workflow organiza a automação de forma hierárquica:

```bash
Workflow
├─ Evento (gatilho)
├─ Job 1
│ ├─ Step 1 (Action ou comando)
│ ├─ Step 2 (Action ou comando)
│ └─ ...
├─ Job 2
│ ├─ Step 1
│ └─ ...
└─ Job N
└─ ...
```

## Por que .github/workflows/?
```bash
.github/
 └─ workflows/
      ├─ ci.yml
      ├─ deploy.yml
      └─ tests.yml
```
Qualquer arquivo YAML fora desta pasta não será detectado.

É uma convenção obrigatória, criada pelo GitHub, para organizar as automações de forma padronizada.

A pasta `.github/` já existe como espaço para configurações do repositório (ex.: templates, issues, actions).

A subpasta `workflows` é exclusiva para arquivos de workflow.

O GitHub Actions procura automaticamente por workflows apenas nessa pasta específica:

## O que vai dentro de cada arquivo YAML

Cada arquivo dentro da pasta workflows é um workflow independente e deve conter:

```yaml
name: CI Demo  # ❗ Nome do workflow, para identificar no GitHub. Relaciona-se ao "Workflow".

on:             # ❗ Evento que dispara o workflow.
  push:         # Este workflow será executado quando houver um push.
    branches:
      - main    # Apenas quando o push acontecer na branch "main".

jobs:           # ❗ Início da seção de jobs. Aqui definimos os conjuntos de tarefas.
  build:        # Nome do job. Pode haver múltiplos jobs em um workflow.
    runs-on: ubuntu-latest  # ❗ Runner: define o ambiente onde o job será executado.
    
    steps:      # ❗ Steps: tarefas individuais dentro do job.
      - name: Checkout repository      # Nome do step (legível na interface do GitHub)
        uses: actions/checkout@v3      # ❗ Action: faz checkout do código do repositório.

      - name: Setup Node.js
        uses: actions/setup-node@v3   # ❗ Action: prepara o ambiente Node.js
        with:
          node-version: 18            # Parâmetro da action: define a versão do Node.js.

      - name: Install dependencies
        run: npm install              # ❗ Step executando comando shell: instala dependências do projeto.

      - name: Run tests
        run: npm test                 # ❗ Step executando comando shell: roda os testes do projeto.
```

[Exemplo Prático](.github/workflows/workflow.yaml)