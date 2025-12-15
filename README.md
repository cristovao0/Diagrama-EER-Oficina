# Diagrama EER Oficina

Sistema de Controle de Ordens de Serviço – Oficina Mecânica
Visão Geral

Este projeto apresenta o modelo conceitual de um sistema de controle e gerenciamento de Ordens de Serviço (OS) para uma oficina mecânica.
O objetivo do sistema é organizar o fluxo de atendimento de veículos, desde a entrada do cliente na oficina até a conclusão dos serviços executados, garantindo rastreabilidade, clareza e consistência das informações.

O diagrama foi construído com base em uma narrativa fornecida no desafio, buscando representar fielmente as regras de negócio descritas, ao mesmo tempo em que mantém uma modelagem limpa e sem redundâncias.

Contexto do Sistema

No contexto da oficina mecânica:

Clientes levam seus veículos para conserto ou revisões periódicas.

Cada atendimento gera uma Ordem de Serviço, que registra todas as informações do trabalho.

Uma equipe de mecânicos é responsável por avaliar e executar os serviços da OS.

A OS pode conter um ou mais serviços, que representam os trabalhos efetivamente realizados.

O cliente deve autorizar a execução dos serviços antes da conclusão.

Ao final, a OS possui status, datas relevantes e o valor total calculado.

Principais Entidades e Responsabilidades
Proprietário

Representa o cliente da oficina.
Um proprietário pode possuir um ou mais veículos.

Principais informações:

Nome

Endereço

Veículo

Representa o veículo levado à oficina para atendimento.
Cada veículo pertence a um único proprietário, mas pode ter várias Ordens de Serviço ao longo do tempo.

Principais informações:

Marca

Modelo

Quilometragem

Ordem de Serviço

É a entidade central do sistema e representa cada atendimento realizado pela oficina.

A Ordem de Serviço:

Está associada a um veículo

É atribuída a uma equipe de mecânicos

Possui um ou mais serviços executados

Registra informações essenciais do processo

Principais informações:

Data de emissão

Data de entrega/conclusão

Status da OS

Valor total do serviço

Autorização do cliente para execução

Equipe de Mecânicos

Representa um grupo de mecânicos que atua em conjunto na execução das Ordens de Serviço.

Uma equipe:

Pode atender várias Ordens de Serviço ao longo do tempo

É composta por um ou mais mecânicos

Mecânico

Representa o profissional que executa os serviços na oficina.
Cada mecânico pertence a uma equipe.

Principais informações:

Nome

Endereço

Especialidade

Serviços da OS

Representa os serviços efetivamente incluídos em uma Ordem de Serviço.
Essa entidade não funciona como um catálogo genérico de serviços, mas sim como o registro dos serviços executados dentro de uma OS específica.

Cada serviço está sempre associado a uma única Ordem de Serviço.

Principais informações:

Descrição do serviço executado

Decisões de Modelagem

Algumas decisões importantes foram tomadas durante a construção do modelo:

A Equipe de Mecânicos foi associada diretamente à Ordem de Serviço, e não ao veículo, permitindo que um mesmo veículo seja atendido por equipes diferentes em visitas distintas.

Foram evitadas chaves estrangeiras redundantes, garantindo que cada entidade conheça apenas seus relacionamentos diretos.

A autorização do cliente foi modelada como um atributo da Ordem de Serviço, por se tratar de uma decisão vinculada à execução daquele atendimento específico.

A cardinalidade mínima entre Ordem de Serviço e Serviços pode ser zero no início do processo (fase de triagem), apesar de o diagrama indicar 1..*, devido a limitações da ferramenta de modelagem. Essa regra é tratada como uma decisão de negócio.

Considerações Finais

Este modelo conceitual busca refletir de forma clara e organizada o funcionamento de uma oficina mecânica, priorizando consistência, simplicidade e aderência à narrativa proposta no desafio.

O diagrama serve como base sólida para futuras etapas do projeto, como a modelagem lógica e a implementação do banco de dados.
