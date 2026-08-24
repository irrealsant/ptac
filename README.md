# atividades-ptac4
Atividades 

API de tarefas desenvolvida com o módulo nativo `node:http`, sem dependências externas.

## Requisitos

- Node.js 18 ou superior

## Como executar

1. Clone o repositório e entre na pasta do projeto.
2. Inicie o servidor:

```bash
npm run dev
```

O servidor ficará disponível em `http://localhost:3000`.

## Endpoints

### Listar tarefas

```bash
curl http://localhost:3000/tarefas
```

Resposta:

```json
[
	{ "id": 1, "titulo": "Estudar HTTP do NodeJS" },
	{ "id": 2, "titulo": "Lavar louças" }
]
```

### Criar tarefa

```bash
curl -X POST http://localhost:3000/tarefas \
	-H "Content-Type: application/json" \
	-d '{"titulo":"Ler a documentação do Node.js"}'
```

Resposta com status `201`:

```json
{ "id": 3, "titulo": "Ler a documentação do Node.js" }
```

O campo `titulo` é obrigatório. Requisições com JSON inválido ou sem esse campo retornam status `400`.

## Observação

As tarefas são armazenadas apenas em memória. Ao reiniciar o servidor, os dados criados são perdidos.