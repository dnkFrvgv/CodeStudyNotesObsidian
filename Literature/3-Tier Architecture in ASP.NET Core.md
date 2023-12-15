# 3 Tier Architecture in ASP.NET Core
[[3-Tier Architecture]] | [[ASP.NET Core]] | [article](https://www.c-sharpcorner.com/article/three-tier-architecture-in-asp-net-core-6-web-api/) | #literature 

---
# Configuração das camadas

- Crie um novo projeto para a [[3-Tier Architecture#Tier Apresentação|camada de apresentação]], pode ser [[ASP.NET Web API]], ou [[ASP.NET Core MVC]].
- Adicionar projeto [[Class Library - Csharp|Class Library]]  para a [[3-Tier Architecture#Tier Dados|camada de dados]].
- Adicionar projeto [[Class Library - Csharp|Class Library]]  para a [[3-Tier Architecture#Tier Aplicação|camada de aplicação]].

## Adicionar referências

- Na camada de apresentação, adicione referência as camadas de dados e de aplicação.
- Na camada de aplicação, adicione referência a camada de dados.

---
# Camada de dados - Data Access Layer

A camada de dados é responsável por ser uma interface entre o banco de dados e a camada de aplicação.

## Diretórios:

- Data - Contém a [[Entity Framework#Implementando o `DbContext`|Classe DB Context]].
- Interfaces - Contém a interface [[Generic Repositories|genéricas do banco de dados]]:

```c#
public interface IRepository < T > {
	public Task < T > Create(T _object);
	public void Delete(T _object);
	public void Update(T _object);
	public IEnumerable < T > GetAll();
	public T GetById(int Id);
}
```

- Migrations - Contém informações de todas as migrações do projeto.
- Models - Contém os models/entities essenciais para a lógica do projeto, seus atributos e métodos.
- Repositories - Contém os [[Repository Pattern|repositórios]] de cada model para as operações CRUD. 

---
# Camada de aplicação - Business Access Layer

A camada de aplicação se comunica com a camada de dados e a camada de apresentação. 

## Diretórios

- Services - Contém os [[Services BL|services]] que interagem com a camada apresentação e a de dados.

---
# Camada de apresentação - Presentation Layer

Responsável a entregar os resultados das requisições [[HTTP]] do usuário.

## Diretórios

- Controllers - Gerencia as requisições.