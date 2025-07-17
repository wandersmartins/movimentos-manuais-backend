# 🛠️ MovimentosManuais.Backend

API desenvolvida em **.NET Core 8** com arquitetura em camadas (Domain, Application e Infrastructure) para gerenciamento de movimentos contábeis manuais.

---

## 📸 Visão Geral

Esta API faz parte do sistema Movimentos Manuais, consumida por uma aplicação Angular 16. Oferece endpoints RESTful para:

- Consultar movimentos manuais por mês e ano
- Cadastrar novos movimentos
- Listar produtos e produtos COSIF

---

## 🧰 Tecnologias Utilizadas

- ASP.NET Core 6
- Dapper (micro ORM)
- SQL Server
- Entity Framework Core (somente para controle de migrações, se necessário)
- Injeção de Dependência nativa
- Swagger (para documentação da API)

---

## 🗂️ Estrutura de Pastas

<img width="366" height="489" alt="image" src="https://github.com/user-attachments/assets/614560bc-e837-4a15-873c-e971a26d5450" />


---

## 🎯 Funcionalidades

- ✅ **GET /api/movimentomanual/{mes}/{ano}**  
  Lista os movimentos de um mês/ano específico.

- ✅ **POST /api/movimentomanual**  
  Cadastra um novo movimento.

- ✅ **GET /api/produto**  
  Lista todos os produtos.

- ✅ **GET /api/produtocosif**  
  Lista todos os produtos COSIF.

---

## 🗃️ Banco de Dados

- Estrutura relacional contendo as tabelas:
  - `PRODUTO`
  - `PRODUTO_COSIF`
  - `MOVIMENTO_MANUAL`

- Procedures utilizadas:
  - `Pr_ListarMovimentos`
  - `Pr_ListarProdutos`
  - `Pr_ListarProdutoCosif`

> As constraints de chave estrangeira garantem integridade entre `MOVIMENTO_MANUAL` e as tabelas de domínio.

---

## ▶️ Como Executar

1. Clone o repositório:

```bash
git clone https://github.com/seu-usuario/MovimentosManuais.Backend.git
cd MovimentosManuais.Backend

2. Configure a connectionString no appsettings.json:
"ConnectionStrings": {
  "DefaultConnection": "Server=SEU_SERVIDOR;Database=MovimentosManuais;User Id=USUARIO;Password=SENHA;"
}

3.Execute a aplicação:
dotnet run --project MovimentosManuais.Api

4.Acesse a documentação Swagger:
http://localhost:5000/swagger
