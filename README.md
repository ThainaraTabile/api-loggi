# Loggi API Mock

Utilizando as bibliotecas [json-server](https://github.com/typicode/json-server) 
e [json-server-auth](https://github.com/jeremyben/json-server-auth) 
foi criado um mock para simular rastreamento de pedidos.

## Execução

1. Clone o repositório
2. Instale as dependências
    ```bash
    npm install
    ```
3. Execute o Mock
    ```bash
    npm start
    ```
4. Agora você pode acessar os endpoints da API descritos abaixo:

#### Listar todos os pedidos
```bash
curl --request GET \
  --url http://localhost:8080/pedidos
```
#### Buscar um pedido através do `id`

```bash
curl --request GET \
  --url http://localhost:8080/pedidos/1
```

*Resposta de sucesso:*
Status HTTP 200
```json
{
	"id": 1,
	"mensageiro": "Luigi",
	"cliente": "Renner",
	"dataPedido": "30-06-2023 08:40:10",
	"localEntrega": {
		"logradouro": "Rua Teste",
		"numero": "23",
		"bairro": "Centro",
		"complemento": "prédio cinza",
		"cep": "78455000",
		"cidade": "Florianópolis",
		"estado": "Santa Catarina"
	},
	"localOrigem": {
		"logradouro": "Rua Teste",
		"numero": "23",
		"bairro": "Centro",
		"complemento": "prédio cinza",
		"cep": "78455000",
		"cidade": "Florianópolis",
		"estado": "Santa Catarina"
	},
	"dataEntrega": "30-06-2023 12:40:10",
	"status": "Finalizado",
	"historicoStatus": [
		{
			"status": "Pedido recebido",
			"dataStatus": "30-06-2023 08:40:10"
		},
		{
			"status": "Em rota de entrega",
			"dataStatus": "30-06-2023 09:15:00",
			"dataPrevistaEntrega": "30-06-2023 12:30:00"
		},
		{
			"status": "Finalizado",
			"dataStatus": "30-06-2023 12:40:10"
		}
	]
}
```

*Resposta de erro:*
Status HTTP 404
```json
{}
```
