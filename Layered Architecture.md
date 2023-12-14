# Layered Architecture
[[Architectural Patterns]]

---

A arquitetura em camadas organiza sistemas em camadas.

## O que são camadas?

Camadas separam a aplicação. Cada camada tem uma responsabilidade especifica como lidar com as requisições ou lógica de negócio. Essa separação torna as camadas independentes das outras (modulares) promovendo [[Separation of concerns]].

Quando uma camada é **fechada** ela só pode usar os serviços da camada diretamente abaixo. Quando uma camada é **aberta** qualquer camada pode requisitar seus serviços ou ela pode ser ignorada. É importante identificar quais camadas devem ser abertas.

![](https://user.oc-static.com/upload/2020/05/05/15886650000516_Layered_High_Level.png)

## Vantagens

- Abstração
- Reusabilidade
- Testabilidade
- Separation of concerns
- Mudanças são isoladas a uma só camada reduzindo risco e erros
- Código mais gerenciável

---
[[N-Tier Architecture]]