# 📦 ms-rabittmq

![Java](https://img.shields.io/badge/Java-17-blue)
![Docker](https://img.shields.io/badge/Docker-Enabled-blue)
![RabbitMQ](https://img.shields.io/badge/RabbitMQ-Messaging-orange)
![Microservices](https://img.shields.io/badge/Architecture-Microservices-green)

Sistema baseado em arquitetura de microservices com comunicação assíncrona via mensageria, utilizando Docker para orquestração de serviços.

---

#  Arquitetura

Este sistema é composto por múltiplos serviços independentes que se comunicam via eventos.

RabbitMQ atua como broker central de mensagens.

Docker Compose é responsável por orquestrar toda a infraestrutura do sistema.

---

##  Componentes

- banking-service → processamento principal de operações
- banking-validation → validação de regras de negócio
- banking-audit → auditoria e rastreabilidade de eventos
- RabbitMQ → mensageria entre serviços
- PostgreSQL → persistência de dados

---

#  Fluxo da aplicação

1. banking-service processa uma operação
2. Evento é publicado no RabbitMQ
3. banking-validation consome e valida regras
4. banking-audit registra o evento
5. Dados são persistidos no PostgreSQL

---

#  Como executar o projeto

## 1. Clonar o repositório

```bash
git clone https://github.com/miqueelino/ms-rabittmq.git
cd ms-rabittmq
