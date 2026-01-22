# Sistemas monolíticos - Criação de API

API Express em TypeScript com SQLite em memória para cadastro de produtos, clientes, checkout e consulta de faturas.

## Pré-requisitos
- Node.js >= 18
- npm

## Instalação
1. Instale as dependências:
	 ```bash
	 npm install
	 ```

## Testes
- Executa checagem de tipos e toda a suíte (unitária + end-to-end com supertest):
	```bash
	npm test
	```

## Execução da API
- Inicie o servidor em modo desenvolvimento (porta `PORT` no `.env` ou 3000 por padrão):
	```bash
	npm run dev
	```
- O banco é SQLite em memória, portanto os dados são reinicializados a cada execução.

## Endpoints principais
- `POST /products`
	```json
	{
		"name": "Product 1",
		"description": "Some Product",
		"purchasePrice": 30,
		"salesPrice": 50,
		"stock": 10
	}
	```
- `POST /clients`
	```json
	{
		"name": "Client 1",
		"email": "client@client.com",
		"document": "123",
		"street": "Main St",
		"number": "100",
		"complement": "Apt 1",
		"city": "São Paulo",
		"state": "SP",
		"zipCode": "01000-000"
	}
	```
- `POST /checkout`
	```json
	{
		"clientId": "<client-id>",
		"products": [
			{"productId": "<product-id-1>"},
			{"productId": "<product-id-2>"}
		]
	}
	```
- `GET /invoice/{id}`
	- Retorna os dados da fatura gerada no checkout.

