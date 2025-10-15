# API de Livraria com Node.js

![Node.js](https://img.shields.io/badge/Node.js-43853D?style=for-the-badge&logo=node.js&logoColor=white)
![Express.js](https://img.shields.io/badge/Express.js-000000?style=for-the-badge&logo=express&logoColor=white)

Este projeto é uma API RESTful básica para o gerenciamento de uma livraria, desenvolvida com Node.js e Express. Ela permite realizar operações de CRUD (Criar, Ler, Atualizar e Deletar) para livros.

## 👨‍💻 Funcionalidades

-   **Listar** todos os livros.
-   **Buscar** um livro específico por seu ID.
-   **Adicionar** um novo livro à coleção.
-   **Atualizar** as informações de um livro existente.
-   **Remover** um livro.

## 🛠️ Tecnologias Utilizadas

-   **[Node.js](https://nodejs.org/)**: Ambiente de execução JavaScript no servidor.
-   **[Express.js](https://expressjs.com/pt-br/)**: Framework para construção de APIs web.
-   **[Dotenv](https://www.npmjs.com/package/dotenv)**: Para gerenciamento de variáveis de ambiente.
-   **[Morgan](https://www.npmjs.com/package/morgan)**: Middleware para logging de requisições HTTP.

## 🚀 Começando

Siga as instruções abaixo para configurar e executar o projeto em seu ambiente local.

### Pré-requisitos

-   [Node.js](https://nodejs.org/en/download/) (versão 14 ou superior recomendada)
-   [npm](https://www.npmjs.com/get-npm) ou [Yarn](https://classic.yarnpkg.com/en/docs/install/)

### Instalação

1.  Clone o repositório para sua máquina local:
    ```bash
    git clone https://github.com/seu-usuario/APILivrariaNode.git
    ```

2.  Navegue até o diretório do projeto:
    ```bash
    cd APILivrariaNode
    ```

3.  Instale as dependências do projeto:
    ```bash
    npm install
    ```

4.  Crie um arquivo `.env` na raiz do projeto e adicione as variáveis de ambiente necessárias. Para este projeto, você pode definir a porta do servidor:
    ```env
    # .env
    PORT=3000
    NODE_ENV=development
    ```

### Executando a Aplicação

Para iniciar o servidor, execute o seguinte comando:

```bash
npm start
```

Ou, se não tiver um script `start` configurado no `package.json`:

```bash
node server.js
```

O servidor estará rodando em `http://localhost:3000`.

## 📖 Documentação da API

A seguir estão os endpoints disponíveis na API.

### Status da API

-   **`GET /api/`**: Verifica a mensagem de boas-vindas da API para confirmar que ela está online.

### Livros (CRUD)

-   **`GET /api/livros/`**: Retorna uma lista com todos os livros cadastrados.
-   **`GET /api/livros/:id`**: Busca e retorna um livro específico pelo seu ID.
-   **`POST /api/livros/`**: Adiciona um novo livro à coleção.
    -   **Corpo da Requisição (JSON):**
        ```json
        {
            "titulo": "O Hobbit",
            "autor": "J.R.R. Tolkien",
            "categoria": "Fantasia",
            "ano": 1937
        }
        ```
-   **`PUT /api/livros/:id`**: Atualiza os dados de um livro existente a partir do seu ID.
    -   **Corpo da Requisição (JSON):**
        ```json
        {
            "titulo": "Clean Code (Edição Revisada)",
            "autor": "Robert C. Martin"
        }
        ```
-   **`DELETE /api/livros/:id`**: Remove um livro da coleção a partir do seu ID.

### Coleção do Postman

Você pode importar a coleção completa do Postman para testar os endpoints facilmente. Cole o conteúdo do arquivo `docsAPI.json` abaixo:

```json
{
	"info": {
		"_postman_id": "a1b2c3d4-e5f6-4a7b-8c9d-0e1f2a3b4c5d",
		"name": "API de Livraria (TesteNodeServer)",
		"description": "Coleção de endpoints para a API de gerenciamento de livros, baseada no projeto TesteNodeServer.",
		"schema": "https://schema.getpostman.com/json/collection/v2.1.0/collection.json"
	},
	"item": [
		{
			"name": "Status da API",
			"request": {
				"method": "GET",
				"header": [],
				"url": {
					"raw": "{{baseUrl}}/api/",
					"host": [
						"{{baseUrl}}"
					],
					"path": [
						"api",
						""
					]
				},
				"description": "Verifica a mensagem de boas-vindas da API para confirmar que ela está online."
			},
			"response": []
		},
		{
			"name": "Livros",
			"item": [
				{
					"name": "Listar todos os livros",
					"request": {
						"method": "GET",
						"header": [],
						"url": {
							"raw": "{{baseUrl}}/api/livros/",
							"host": [
								"{{baseUrl}}"
							],
							"path": [
								"api",
								"livros",
								""
							]
						},
						"description": "Retorna uma lista com todos os livros cadastrados."
					},
					"response": []
				},
				{
					"name": "Buscar livro por ID",
					"request": {
						"method": "GET",
						"header": [],
						"url": {
							"raw": "{{baseUrl}}/api/livros/1",
							"host": [
								"{{baseUrl}}"
							],
							"path": [
								"api",
								"livros",
								"1"
							]
						},
						"description": "Busca e retorna um livro específico pelo seu ID."
					},
					"response": []
				},
				{
					"name": "Criar novo livro",
					"request": {
						"method": "POST",
						"header": [
							{
								"key": "Content-Type",
								"value": "application/json",
								"type": "text"
							}
						],
						"body": {
							"mode": "raw",
							"raw": "{\n    \"titulo\": \"O Hobbit\",\n    \"autor\": \"J.R.R. Tolkien\",\n    \"categoria\": \"Fantasia\",\n    \"ano\": 1937\n}",
							"options": {
								"raw": {
									"language": "json"
								}
							}
						},
						"url": {
							"raw": "{{baseUrl}}/api/livros/",
							"host": [
								"{{baseUrl}}"
							],
							"path": [
								"api",
								"livros",
								""
							]
						},
						"description": "Adiciona um novo livro à coleção."
					},
					"response": []
				},
				{
					"name": "Atualizar livro por ID",
					"request": {
						"method": "PUT",
						"header": [
							{
								"key": "Content-Type",
								"value": "application/json",
								"type": "text"
							}
						],
						"body": {
							"mode": "raw",
							"raw": "{\n    \"titulo\": \"Clean Code (Edição Revisada)\",\n    \"autor\": \"Robert C. Martin\",\n    \"categoria\": \"Desenvolvimento de Software\",\n    \"ano\": 2009\n}",
							"options": {
								"raw": {
									"language": "json"
								}
							}
						},
						"url": {
							"raw": "{{baseUrl}}/api/livros/1",
							"host": [
								"{{baseUrl}}"
							],
							"path": [
								"api",
								"livros",
								"1"
							]
						},
						"description": "Atualiza os dados de um livro existente a partir do seu ID."
					},
					"response": []
				},
				{
					"name": "Remover livro por ID",
					"request": {
						"method": "DELETE",
						"header": [],
						"url": {
							"raw": "{{baseUrl}}/api/livros/2",
							"host": [
								"{{baseUrl}}"
							],
							"path": [
								"api",
								"livros",
								"2"
							]
						},
						"description": "Remove um livro da coleção a partir do seu ID. (Use um ID de um livro que você criou para testar)."
					},
					"response": []
				}
			],
			"description": "Endpoints para o gerenciamento de livros (CRUD)."
		}
	],
	"variable": [
		{
			"key": "baseUrl",
			"value": "http://localhost:3000",
			"type": "string"
		}
	]
}

```

---

