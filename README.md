# Sistema de Controle de Ordens de Serviço – Oficina Mecânica

## Visão Geral

Este projeto apresenta o **modelo conceitual de um sistema de controle e gerenciamento de Ordens de Serviço (OS)** para uma oficina mecânica.  
O objetivo do sistema é organizar o fluxo de atendimento de veículos, desde a entrada do cliente na oficina até a conclusão dos serviços executados, garantindo rastreabilidade, clareza e consistência das informações.

O diagrama foi construído com base em uma narrativa fornecida no desafio, buscando representar fielmente as regras de negócio descritas, ao mesmo tempo em que mantém uma modelagem limpa e sem redundâncias.

---

## Contexto do Sistema

No contexto da oficina mecânica:

- Clientes levam seus veículos para conserto ou revisões periódicas
- Cada atendimento gera uma **Ordem de Serviço**
- Uma **equipe de mecânicos** é responsável por avaliar e executar os serviços
- Uma OS pode conter **um ou mais serviços**
- O cliente deve **autorizar a execução** dos serviços
- Ao final, a OS possui status, datas relevantes e valor total calculado

---

## Principais Entidades

### Proprietário

Representa o cliente da oficina.  
Um proprietário pode possuir um ou mais veículos.

**Principais informações:**
- Nome
- Endereço

---

### Veículo

Representa o veículo levado à oficina para atendimento.  
Cada veículo pertence a um único proprietário, mas pode ter várias Ordens de Serviço ao longo do tempo.

**Principais informações:**
- Marca
- Modelo
- Quilometragem

---

### Ordem de Serviço

Entidade central do sistema, representando cada atendimento realizado pela oficina.

A Ordem de Serviço:
- Está associada a **um veículo**
- É atribuída a **uma equipe de mecânicos**
- Possui **um ou mais serviços executados**
- Registra informações essenciais do processo

**Principais informações:**
- Data de emissão
- Data de entrega ou conclusão
- Status da OS
- Valor total
- Autorização do cliente

---

### Equipe de Mecânicos

Representa um grupo de mecânicos que atua em conjunto na execução das Ordens de Serviço.

Uma equipe:
- Pode atender várias Ordens de Serviço
- É composta por um ou mais mecânicos

---

### Mecânico

Representa o profissional responsável pela execução dos serviços na oficina.  
Cada mecânico pertence a uma equipe.

**Principais informações:**
- Nome
- Endereço
- Especialidade

---

### Serviços da OS

Representa os **serviços efetivamente incluídos em uma Ordem de Serviço**.  
Não funciona como um catálogo genérico de serviços, mas como o registro dos serviços executados em uma OS específica.

Cada serviço está sempre associado a uma única Ordem de Serviço.

**Principais informações:**
- Descrição do serviço executado

---

## Decisões de Modelagem

Durante a construção do modelo, foram adotadas as seguintes decisões:

- A **Equipe de Mecânicos foi associada diretamente à Ordem de Serviço**, permitindo que um mesmo veículo seja atendido por equipes diferentes em visitas distintas
- Foram evitadas **chaves estrangeiras redundantes**, garantindo um modelo mais limpo e consistente
- A autorização do cliente foi modelada como um atributo da Ordem de Serviço
- A cardinalidade mínima entre Ordem de Serviço e Serviços pode ser zero no início do processo (fase de triagem), embora o diagrama indique 1..*, devido a limitações da ferramenta de modelagem

---

## Considerações Finais

Este modelo conceitual busca representar de forma clara e organizada o funcionamento de uma oficina mecânica, respeitando as regras de negócio propostas no desafio.

O diagrama serve como base para futuras etapas do projeto, como a modelagem lógica e a implementação do banco de dados.
