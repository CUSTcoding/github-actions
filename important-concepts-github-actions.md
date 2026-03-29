# Conceitos Importantes do GitHub Actions

O GitHub Actions é uma ferramenta poderosa de **automação de CI/CD**, mas para utilizá-la corretamente é fundamental entender seus principais conceitos.  

---

## **1. Workflow**

- Um **workflow** é o conjunto de processos automatizados que você deseja executar no seu repositório.  
- Define **quando** e **como** suas tarefas devem ser executadas.  
- É configurado em arquivos YAML dentro da pasta `.github/workflows/`.  
- Pode ser disparado por eventos como `push`, `pull_request`, `workflow_dispatch` (manual) ou `schedule` (CRON).  

**Resumo:** Workflow = pipeline completo de automação.

---

## **2. Job**

- Um **job** é uma unidade dentro de um workflow.  
- Contém um conjunto de **steps** que são executados juntos em um **runner**.  
- Jobs podem rodar em paralelo ou em sequência usando `needs:` para definir dependências.  
- Cada job roda em um ambiente isolado, garantindo que não haja interferência entre eles.

**Resumo:** Job = conjunto de tarefas isoladas dentro de um workflow.

---

## **3. Step**

- Um **step** é uma **tarefa individual** dentro de um job.  
- Pode ser um comando shell, um script ou a execução de uma **action** pronta.  
- Steps são executados na ordem em que aparecem no job.

**Resumo:** Step = ação ou comando específico dentro de um job.

---

## **4. Action**

- Uma **action** é uma unidade reutilizável de código que realiza uma tarefa específica.  
- Pode ser oficial do GitHub, criada pela comunidade ou personalizada por você.  
- Actions permitem reduzir código repetitivo e padronizar tarefas.  

**Resumo:** Action = bloco de automação reutilizável.

---

## **5. Runner**

- O **runner** é o ambiente onde os jobs são executados.  
- Pode ser **GitHub-hosted** (Linux, Windows, macOS) ou **self-hosted** (seu próprio servidor).  
- Cada job é executado em um runner separado, garantindo isolamento e consistência.

**Resumo:** Runner = máquina ou ambiente que executa os jobs.

---

## **6. Event (Evento)**

- Um **evento** é o que dispara o workflow.  
- Exemplos de eventos:
  - `push` → quando há commits em uma branch.
  - `pull_request` → quando um PR é aberto ou atualizado.
  - `workflow_dispatch` → disparo manual.
  - `schedule` → disparo programado via CRON.
- Você pode combinar múltiplos eventos para disparar o mesmo workflow.

**Resumo:** Event = gatilho que inicia o workflow.

---

## **7. Artifact**

- Um **artifact** é um arquivo ou conjunto de arquivos gerados durante a execução do workflow que você deseja salvar ou compartilhar.  
- Pode ser usado para logs, relatórios de testes, pacotes compilados ou builds.  
- Artifacts podem ser baixados diretamente do GitHub após a execução.

**Resumo:** Artifact = arquivo ou pacote produzido e armazenado pelo workflow.

---

## **8. Secrets**

- **Secrets** são variáveis sensíveis, como tokens, senhas ou chaves API, usadas em workflows sem expor informações confidenciais.  
- Devem ser configurados em **Settings → Secrets** do repositório.  
- São acessados dentro do workflow usando a sintaxe `${{ secrets.NOME_DO_SECRET }}`.  

**Resumo:** Secret = variável segura para dados confidenciais.

---

## **Resumo geral**

| Conceito   | Definição rápida |
|------------|----------------|
| Workflow   | Pipeline completo de automação |
| Job        | Conjunto de steps executados em um runner |
| Step       | Tarefa individual dentro de um job |
| Action     | Bloco reutilizável de automação |
| Runner     | Ambiente que executa os jobs |
| Event      | Gatilho que dispara o workflow |
| Artifact   | Arquivo gerado e armazenado pelo workflow |
| Secret     | Variável segura para informações confidenciais |

> **Dica:** Compreender cada conceito é essencial para criar workflows eficientes, seguros e escaláveis.

Next: [Estrutura do Workflow](workflow-structure.md)