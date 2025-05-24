# 🚗 ParkingAPI

API REST para gerenciamento de um sistema de estacionamento, desenvolvida em **ASP.NET Core 8**, com autenticação via **JWT**, persistência de dados em banco **Oracle** e mapeamento de objetos com **AutoMapper**.

## 👨‍💻 Desenvolvido por

- Celso Canaveze Teixeira Pinto: **RM556118**
- Sofia Domingues Gonçalves: **RM554920**
- Thiago Moreno Matheus: **RM554507**

## 📑 Sumário

- [Sobre o Projeto](#-sobre-o-projeto)
- [Tecnologias Utilizadas](#-tecnologias-utilizadas)
- [Pré-requisitos](#-pré-requisitos)
- [Configurações do Projeto](#-configurações-do-projeto)
- [Rodando a Aplicação](#-rodando-a-aplicação)
- [Estrutura dos Endpoints](#-estrutura-dos-endpoints)
- [Autenticação](#-autenticação)
- [Banco de Dados](#-banco-de-dados)
- [Licença](#-licença)

## 🚀 Sobre o Projeto

O **ParkingAPI** permite realizar o cadastro, consulta, atualização e exclusão de:

- 🏍️ Motos
- 👤 Clientes
- 🅿️ Pátios
- 👨‍💻 Usuários

Inclui autenticação segura com **JWT**, onde apenas usuários autenticados podem acessar os endpoints protegidos.

## 🛠️ Tecnologias Utilizadas

- ✅ ASP.NET Core 8
- ✅ Entity Framework Core (com provider Oracle)
- ✅ Oracle Database
- ✅ AutoMapper
- ✅ JWT Authentication
- ✅ Swagger (documentação)
- ✅ C#

## ⚙️ Pré-requisitos

- [.NET 8 SDK](https://dotnet.microsoft.com/en-us/download/dotnet/8.0)
- Oracle Database (local ou cloud)
- [Visual Studio 2022](https://visualstudio.microsoft.com/) ou qualquer IDE compatível com .NET 8
- Docker (opcional, se quiser subir o Oracle via container)

## 🔧 Configurações do Projeto

Edite o arquivo `appsettings.json` com seus dados de conexão:

```json
{
  "ConnectionStrings": {
    "DefaultConnection": "User Id=USUARIO;Password=SENHA;Data Source=//localhost:1521/XEPDB1"
  },
  "Jwt": {
    "Secret": "sua_chave_super_secreta_aqui"
  },
  "Logging": {
    "LogLevel": {
      "Default": "Information",
      "Microsoft.AspNetCore": "Warning"
    }
  },
  "AllowedHosts": "*"
}
```

## ▶️ Rodando a Aplicação

### ✔️ Pelo Visual Studio

1. Abra `ParkingAPI.sln`.
2. Configure como projeto de inicialização o `ParkingAPI`.
3. Pressione `F5` ou clique em **Run**.

### ✔️ Pelo terminal

```bash
cd ParkingAPI
dotnet restore
dotnet run
```

🔗 Acesse: https://localhost:5001/swagger

## 🌐 Estrutura dos Endpoints

### 🔑 Autenticação

| Método | Endpoint     | Descrição      |
|--------|--------------|----------------|
| POST   | /api/login   | Gera Token JWT |

### 🏍️ Motos

| Método | Endpoint          | Descrição            |
|--------|-------------------|----------------------|
| GET    | /api/motos        | Lista todas as motos |
| GET    | /api/motos/{id}   | Busca moto por ID    |
| POST   | /api/motos        | Cria uma moto        |
| PUT    | /api/motos/{id}   | Atualiza uma moto    |
| DELETE | /api/motos/{id}   | Remove uma moto      |

### 👤 Clientes

| Método | Endpoint             | Descrição              |
|--------|----------------------|------------------------|
| GET    | /api/clientes        | Lista todos os clientes|
| GET    | /api/clientes/{id}   | Busca cliente por ID   |
| POST   | /api/clientes        | Cria um cliente        |
| PUT    | /api/clientes/{id}   | Atualiza um cliente    |
| DELETE | /api/clientes/{id}   | Remove um cliente      |

### 🅿️ Pátios

| Método | Endpoint           | Descrição             |
|--------|--------------------|-----------------------|
| GET    | /api/patios        | Lista todos os pátios |
| GET    | /api/patios/{id}   | Busca pátio por ID    |
| POST   | /api/patios        | Cria um pátio         |
| PUT    | /api/patios/{id}   | Atualiza um pátio     |
| DELETE | /api/patios/{id}   | Remove um pátio       |

### 👨‍💻 Usuários

| Método | Endpoint              | Descrição               |
|--------|-----------------------|-------------------------|
| GET    | /api/usuarios         | Lista todos os usuários |
| GET    | /api/usuarios/{id}    | Busca usuário por ID    |
| POST   | /api/usuarios         | Cria um usuário         |
| PUT    | /api/usuarios/{id}    | Atualiza um usuário     |
| DELETE | /api/usuarios/{id}    | Remove um usuário       |

## 🔐 Autenticação

- Faça login via `/api/login` com usuário e senha.
- Use o token retornado no Swagger (**Authorize**) ou no cabeçalho:

```
Authorization: Bearer {seu_token}
```

## 🗄️ Banco de Dados

- Conecte-se ao Oracle Database configurado.
- As tabelas podem ser geradas automaticamente pelo Entity Framework ou manualmente.

## 📜 Licença

Projeto acadêmico e livre para fins educacionais.
