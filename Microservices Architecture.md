# Microservices Architecture
[[Architectural Patterns]]

---

# O que é arquitetura de microsserviço?

É uma arquitetura em que uma aplicação é estruturada em um grupo de serviço pequenos que rodam em [[Processos|processos]] separados. Em vez de criar uma aplicação [[Monolithic Architecture|monolítica]], onde todas as funcionalidade rodam em um só [[Processos|processo]], na arquitetura de microsserviço as funcionalidades são separadas em serviços independentes que focam em uma função específica do sistema.

![](https://miro.medium.com/v2/resize:fit:770/0*Cecp_Eh4bFm2Pe7c.png)

---
# Características

- **Comunicação via API:** A comunicação entre os microsserviços de uma aplicação é feita por chamadas de [[API]]s
- **Dados descentralizados:** Cada serviço tem seu próprio [[Database|banco de dados]].
- **Independência de tecnologia:** Cada microsserviço pode ser implementado usando a tecnologia mais adequada para sua função, assim, diferentes partes da aplicação podem usar linguagens de programação, frameworks e banco de dados diferentes.

---
# [[API Gateway]]

Quando o cliente deseja receber dados que estão armazenados em diferentes serviços de uma aplicação com arquitetura de microsserviços, a API Gateway atua como interface para esse request, reunindo informações de vários microsserviços e retornando uma única resposta para o cliente. Assim ao invés do cliente se comunicar diretamente com vários microsserviços, ele interage apenas com [[API Gateway]].

---
[[Microservices Scalability]]
