# Especificação Técnica: API de Gerenciamento de Tarefas (ToDo List)
**Fluxo de Desenvolvimento:** Spec-Driven Development (SDD)
**Versão:** 1.1.0
**Status:** Aprovado

---

## 1. Visão Geral do Problema
O objetivo desta aplicação é fornecer uma API RESTful para o gerenciamento básico de tarefas diárias (ToDo List). A API deve permitir criar, listar, atualizar o status e remover tarefas, garantindo a integridade dos dados e tratamento apropriado de erros.

---

## 2. Requisitos da Aplicação

### 2.1. Requisitos Funcionais (RF)
- **RF01:** O sistema deve permitir o cadastro de novas tarefas informando `title` (obrigatório) e `description` (opcional).
- **RF02:** O sistema deve permitir a listagem de todas as tarefas cadastradas.
- **RF03:** O sistema deve permitir consultar uma tarefa específica por seu `id`.
- **RF04:** O sistema deve permitir a atualização do status de uma tarefa (`pending` ou `completed`).
- **RF05:** O sistema deve permitir a exclusão de uma tarefa cadastrada utilizando seu `id`.

### 2.2. Requisitos Não-Funcionais (RNF)
- **RNF01:** A API deve ser desenvolvida em Node.js com Express e TypeScript.
- **RNF02:** Os dados serão mantidos em memória (array) para facilitar a execução sem dependência de banco de dados externo.
- **RNF03:** O tempo de resposta das requisições deve ser inferior a 200ms em ambiente local.
- **RNF04:** As entradas e saídas de dados devem ser estritamente formatadas em JSON.

---

## 3. Regras de Negócio (RN)
- **RN01:** Toda nova tarefa deve ser criada com o status inicial `pending`.
- **RN02:** O campo `title` não pode ser vazio ou conter apenas espaços em branco.
- **RN03:** O campo `title` deve ter no mínimo 3 caracteres e no máximo 100 caracteres.
- **RN04:** O status de uma tarefa só pode assumir os valores `'pending'` ou `'completed'`.
- **RN05:** Caso uma busca, atualização ou exclusão receba um `id` inexistente, o sistema deve retornar HTTP 404 (Not Found) com mensagem de erro amigável.

---

## 4. Contrato da API REST (Endpoints e Schemas)

### Modelo de Dados (`Task`)
```json
{
  "id": "string (UUID v4)",
  "title": "string",
  "description": "string | null",
  "status": "pending | completed",
  "createdAt": "string (ISO 8601)"
}