# Documentação

Esta documentação tem como objetivo listar, descrever e exemplificar os endpoints de todas as APIs do projeto de forma a facilitar o consumo da API pelos clientes.

### **Índice**
👨 [Cliente](#-api-de-clientes) \
🌎 [Endereços](#-api-de-enderecos) \
🚗 [Veiculos](#-api-de-veiculos) \
🎌 [Parquimetro](#-api-de-parquimetro)
<br />

## 🌎 API de Clientes
A API de clientes consiste em um conjunto de endpoints para gerenciar os clientes. Ela dispõe de métodos para criação, edição, busca e listagem de clientes. <br /><br />

📌
### 🔵 **POST** http://localhost:81/cliente
\
Cria um cliente através dos dados recebidos via JSON no corpo da requisição.

#### *Exemplo de inserção* <br /><br />
````
        {
            "nome": "Ed Carlos",
            "nascimento": "2023-11-03",
            "sexo":"Masculino",
            "email":"edcarlos.1@java.com"
        }
````
```
        {
            "nome": "Priscila ",
            "nascimento": "2023-10-02",
            "sexo":"Feminino",
            "email":"priscila.1@java.com"
        }
```
<br />

📌
### 🔵 **GET** http://localhost:81/cliente
\
Lista todos os endereços contidos na base de dados.

#### *Exemplo de requisição* <br /><br />

```
        {
            "id_cliente": 2,
            "nome": "Priscila ",
            "dtcriacao": "2023-11-15T15:54:39.025836Z",
            "nascimento": "2023-10-02",
            "sexo": "Feminino",
            "email": "priscila.1@java.com",
            "endereco": []
        },
        {
            "id_cliente": 1,
            "nome": "Ed Carlos",
            "dtcriacao": "2023-11-15T12:48:34.151570Z",
            "nascimento": "2023-11-03",
            "sexo": "Masculino",
            "email": "edcarlos.1@java.com",
            "endereco": []
        }
```
<br />


📌
### 🔵 **GET** http://localhost:81/cliente/1
\
Lista um cliente especifico passando o seu ID.

#### *Exemplo de requisição por ID* <br /><br />

```
            {
            "id_cliente": 1,
            "nome": "Ed Carlos",
            "dtcriacao": "2023-11-15T12:48:34.151570Z",
            "nascimento": "2023-11-03",
            "sexo": "Masculino",
            "email": "edcarlos.1@java.com",
            "endereco": []
            }
```
<br />


















📌
### 🔵 **GET** http://localhost:8080/endereco/1
\
Busca um endereço através do código recebido via parâmetro de URL


#### *Exemplo resposta* <br /><br />

		 {  "id": 1,
			"rua": "Rua Concordia",
			"numero": 12,
			"bairro": "Santana",
			"cidade": "São Paulo",
			"estado": "SP"
		}
<br />

📌
### 🟢 **POST** http://localhost:8080/endereco
\
Cria um endereço através dos dados recebidos via JSON no corpo da requisição 


#### *Exemplo de requisição* <br /><br />

    {
        "rua": "Rua Clementina",
        "numero": 12,
        "bairro": "Penha",
        "cidade": "Minas Gerais",
        "estado": "MG"
 }
<br />

#### *Exemplo de resposta* <br /><br />

       {   
	    "id": 6,
        "rua": "Rua Clementina",
        "numero": 12,
        "bairro": "Penha",
        "cidade": "Minas Gerais",
        "estado": "MG"
       }
<br />

📌
### 🟠 **PUT** http://localhost:8080/endereco/5
\
Altera um endereço através do código recebido via parâmetro de URL e dos dados recebidos via JSON no corpo da requisição


#### *Exemplo de  requisição* <br /><br />

       {
	    "rua": "Rua Concordia",
	    "numero": "12",
	    "bairro": "Bairro teste",
	    "cidade": "Cidade teste",
	    "estado": "SP"
       }
<br />

#### *Exemplo de resposta* <br /><br />

    
	{
    "id": 5,
    "rua": "Rua Concordia Damasceno",
    "numero": 122,
    "bairro": "Santana",
    "cidade": "São Paulo",
    "estado": "SP"
    }

<br />

📌
## 📺 API de Eletrodomésticos

A API de eletrodomésticos consiste em um conjunto de endpoints para gerenciar os eletrodomésticos da aplicação. Ela dispõe de métodos para criação, edição, busca e listagem de eletrodomésticos. <br /><br />

📌
### 🟢 **POST** http://localhost:8080/eletro
\
Cadastra um eletrodoméstico através dos dados recebidos via JSON no corpo da requisição.


#### *Exemplo de requisição* <br /><br />

  
    {
    "modelo": "LAVA LOUÇAS",
    "potencia": 4.9,
    "tempo": 1,
    "consumo": 17.0
    }

<br />

#### *Exemplo de payload da requisição* <br /><br />

    {
        "id": "6",
        "modelo": "LAVA LOUÇAS",
		"potencia": 4.9,
		"tempo": 1,
		"consumo": 17.0
    }
<br />

📌
### 🔵 **GET** http://localhost:8080/eletro/2
\
Busca um eletrodomestico através do código recebido via parâmetro de URL


#### *Exemplo de payload da resposta* <br /><br />

    {
    "id": 2,
    "modelo": "TELEVISAO",
    "potencia": 4.2,
    "tempo": 1,
    "consumo": 12.0,
    "cliente": {
        "id": 1,
        "nome": "Cristina Torres",
        "nascimento": "23/12/1987",
        "sexo": "Feminino",
        "parentesco": "Titular",
        "endereco": {
            "id": 1,
            "rua": "Rua Concordia",
            "numero": 12,
            "bairro": "Santana",
            "cidade": "São Paulo",
            "estado": "SP"
        }
    }
}
<br />

📌
### 🟠 **PUT** http://localhost:8080/eletro/3
\
Altera os dados do eletrodoméstico através do código recebido via parâmetro de URL e dos dados recebidos via JSON no corpo da requisição


#### *Exemplo de payload da requisição* <br /><br />

	{
		"id": 3,
		"modelo": "COMPUTADOR",
		"potencia": 4.5,
		"tempo": 1,
		"consumo": 11.0,
	}
<br />

#### *Exemplo de payload da resposta* <br /><br />

	{
		"id": 3,
		"modelo": "NOTEBOOK",
		"potencia": 4.5,
		"tempo": 1,
		"consumo": 11.0,
	}
<br />


## 👤 API de Cliente

A API de pessoas consiste em um conjunto de endpoints para gerenciar os usuários que representam os clientes da aplicação. Ela dispõe de métodos para criação, edição, busca e listagem de pessoas. <br /><br />


📌
### 🟢 **POST** http://localhost:8080/cliente
\
Cadastra uma pessoa através dos dados recebidos via JSON no corpo da requisição.


#### *Exemplo de requisição* <br /><br />

	 
    {
        "nome": "João Bosco",
        "nascimento": "03/05/1997",
        "sexo": "Masculino",
        "parentesco": "Filho",
        "endereco": {
            "id": 3,
            "rua": "Rua Santo Elias",
            "numero": 567,
            "bairro": "Tatuape",
            "cidade": "São Paulo",
            "estado": "SP"
        }
    }
<br />

#### *Exemplo de resposta* <br /><br />

	{
    "id": 6,
    "nome": "João Bosco",
    "nascimento": "03/05/1997",
    "sexo": "Masculino",
    "parentesco": "Filho",
    "endereco": {
        "id": 3,
        "rua": "Rua Santo Elias",
        "numero": 567,
        "bairro": "Tatuape",
        "cidade": "São Paulo",
        "estado": "SP"
    }
}
<br />

📌
### 🔵 **GET** http://localhost:8080/cliente/5
\
Busca uma pessoa através do código recebido via parâmetro de URL


#### *Exemplo de resposta* <br /><br />
	
	{
    "id": 5,
    "nome": "Angelo Amorim",
    "nascimento": "10/03/1959",
    "sexo": "Masculino",
    "parentesco": "Titular",
    "endereco": {
        "id": 3,
        "rua": "Rua Santo Elias",
        "numero": 567,
        "bairro": "Tatuape",
        "cidade": "São Paulo",
        "estado": "SP"
    }
}
<br />

📌
### 🟠 **PUT** http://localhost:8080/cliente
\
Altera o cadastro da pessoa através do código recebido via parâmetro de URL e dos dados recebidos via JSON no corpo da requisição

Status de retorno esperado: **200 - SUCCESS**

#### *Exemplo de requisição* <br /><br />

	{
    "nome": "ED ",
    "nascimento": "24/05/1984",
    "sexo": null,
    "parentesco": null,
    "endereco": {
        "id": 1,
        "rua": "Rua Concordia",
        "numero": 12,
        "bairro": "Santana",
        "cidade": "São Paulo",
        "estado": "SP"
    }
}
<br />

#### *Exemplo de resposta* <br /><br />

	{
    "id": 3,
    "nome": "ED CARLOS",
    "nascimento": "24/05/1984",
    "sexo": null,
    "parentesco": null,
    "endereco": {
        "id": 1,
        "rua": "Rua Concordia",
        "numero": 12,
        "bairro": "Santana",
        "cidade": "São Paulo",
        "estado": "SP"
    }
}
<br />



