# API de Gerenciamento de Tarefas (ToDo List) - SDD

Projeto desenvolvido para o curso de ADS utilizando o fluxo Spec-Driven Development (SDD), automacao por agentes de IA e empacotamento em containers.

## Tecnologias Utilizadas
- Node.js / TypeScript
- Express
- GitHub Projects & Issues
- Jest & Harness de Testes SDD
- Docker & Docker Compose

---

## Como Executar o Projeto

Execucao via Docker:
docker-compose up --build

A API estara acessivel em http://localhost:3000.

---

## Registro de Decisoes Arquiteturais (ADRs)

### ADR 001: Adocao do Fluxo SDD (Spec-Driven Development)
- Decisao: A especificacao tecnica em docs/spec.md e a fonte unica da verdade para desenvolvimento e contexto da IA.
- Consequencia: Garante previsibilidade e evita divergencias de escopo na geracao de codigo por agentes de IA.

### ADR 002: Armazenamento em Memoria
- Decisao: Utilizacao de estrutura de dados em memoria para a versao inicial.
- Consequencia: Facilita a reprodutibilidade nos ambientes de teste e container sem dependencias externas.

---

## Evidencias da Suite de Testes (Test Harness)
Os testes cobrem os cenarios principais (Happy Path) e cenarios de borda (Edge Cases) das regras de negocio RN01 a RN05.

Evidencia registrada no arquivo docs/test-results.txt.
