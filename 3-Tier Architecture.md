# 3-Tier Architecture
[[N-Tier Architecture]]

---

A arquitetura [[N-Tier Architecture|N-Tier]] mais comum e composta por 3 tiers: tier de apresentação, tier de aplicação e tier de persistência.

![](https://docs.aws.amazon.com/images/whitepapers/latest/serverless-multi-tier-architectures-api-gateway-lambda/images/image2.png)

## Tier Apresentação

Também conhecida por Front-end. 
Lida com as requisições dos usuários, com a interface de usuário e como os dados serão apresentados.

## Tier Aplicação

Lida com a lógica de negócio da aplicação, operações CRUD.  Essa camada não foca em como as informações serão apresentadas nem em como os dados são armazenados.

## Tier Dados

Foca em como os dados serão armazenados e fornece uma interface para que a [[#Tier Aplicação]] receba esses dados.

---
## Vantagens da arquitetura 3-Tier

- Cada tier é independente.
- Fácil de manter
- Client não tem acesso direto ao banco de dados

## Desvantagens da arquitetura 3-Tier

- Leva mais tempo para desenvolver uma aplicação pequena
- Requer bom entendimento de [[Programação Orientada a Objetos - OOP|OOP]]
