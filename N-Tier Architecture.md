# N-Tier Architecture
[[Layered Architecture]]

---

Uma forma de [[Layered Architecture|arquitetura em camadas]] organizada em múltiplas tiers, geralmente 3 ou mais.

![](https://www.baeldung.com/wp-content/uploads/sites/4/2022/01/ntier_usecase.drawio.svg)

## O que é uma Tier

Representa a separação física dos componentes da aplicação. A comunicação entre as tiers é Top-Down, cada tier geralmente só interage com a que está abaixo.

## Quando usar a arquitetura N-Tier

- Aplicações web pequenas ou de medio porte.
- Em cenários em que a testabilidade é uma prioridade e é desejável testar cada camada de maneira isolada.
- Quando você precisa escalar diferentes partes do sistema de maneira independente.

## Considerações

É possível desenvolver uma aplicação com uma arquitetura N-Tier mas fazer o deploy com uma arquitetura [[Monolithic Architecture|monolítica]]. Para evitar isso é preciso fazer o deploy de cada tier separadamente.

## Vantagens

- Seguro
- Simplicidade
- Fácil de gerenciar
- Escalável
- Flexível

---

[[3-Tier Architecture]] | [[N-Tier Architecture in ASP.NET MVC]]