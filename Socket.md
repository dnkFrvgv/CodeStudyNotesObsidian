# Socket
[[Computer Network]]

---

# O que é um Socket ?

É uma interface da comunicação entre dois [[Processos|processos]] rodando em uma rede. Esses processos podem estar na mesma maquina ou em maquinas diferentes.

Quando você tem um servidor e um cliente se comunicando, cada lado cria um socket. Esses sockets são usadas para enviar e receber dados entre cliente e servidor.

Um socket permite que seja possível identificar o destino de um [[pacote]] vindo da rede. Cada socket é identificada pelo [[endereço IP]], o número da porta, e o protocolo usado ([[Protocolo TCP|TCP]]/[[Protocolo UDP|UDP]]).  O endereço IP identifica a máquina e a porta identifica um processo específico rodando em uma máquina. 

A função de uma socket também envolve definir qual protocolo está sendo usado na camada de transporte.

---
# Como funciona

## Socket Client

O cliente criar uma socket para iniciar uma conexão com servidor.

## Socket Listener

O servidor criar um socket que fica em modo de escuta, aguardando por novas conexões. Quando uma conexão é aceita, ele criar uma nova socket para aquela conexão em especifico, podendo assim trocar dados com o cliente conectado.

---
# Tipos de Sockets

## Stream Sockets

São sockets que implementam o [[Protocolo TCP]]. Garantem que os dados sejam recebidos em ordem e sem erro. Utilizados para a comunicação confiável.

## Datagram Sockets

São sockets que implementam o [[Protocolo UDP]]. [[datagramas]] são enviados independentemente. Dados podem ser perdidos, recebidos fora de ordem ou duplicados

---
