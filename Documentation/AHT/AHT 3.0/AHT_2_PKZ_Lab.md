# Análise Hierárquica de Tarefas (AHT) – PKZ Lab

## 1. Introdução

Este documento faz parte da AHT do portal institucional da Holding Esportiva (PKZ Lab e One to One) e descreve a tarefa de explorar a landing page do PKZ Lab (Tarefa 2). A numeração das tarefas segue a AHT completa; a meta principal (Meta 0), os usuários e a conclusão geral estão no documento do Hub.

Escopo do projeto:

- Somente front-end, com React e Vite (seção 6.1).

Notação:

- 0 = meta principal.
- 1, 2, 3 = tarefas; 1.1, 1.2 = subtarefas.
- Plano = ordem e condições em que o usuário realiza as subtarefas.
- Cada plano é acompanhado do seu diagrama de atividade, escrito em PlantUML.

## 2. Tarefas

### Tarefa 2 – Explorar o PKZ Lab

- 2.1 Acessar a landing page do PKZ Lab a partir do Hub
- 2.2 Ler a apresentação institucional
- 2.3 Ver os conteúdos direcionados ao seu público (jovens, atletas de base e Pais/Responsáveis)
- 2.4 Ver os serviços (avaliação física, planejamento de treino, evolução do desempenho, desenvolvimento esportivo e alta performance)
- 2.5 Ver o portfólio de treinamentos (imagens e vídeos)
- 2.6 Clicar no CTA de contato, no CTA de agendamento ou retornar ao Hub

Plano 2: O usuário entra na página do PKZ Lab e lê a apresentação. Depois vê o conteúdo para o seu público, os serviços e o portfólio, na ordem que quiser. No fim, clica no botão de contato (vai para a Tarefa 4), no botão de agendamento (vai para a Tarefa 5) ou volta ao Hub (Tarefa 1).

Diagrama de atividade do Plano 2:

```plantuml
@startuml 2_explorar_pkz_lab
skin rose
title Tarefa 2 - Explorar o PKZ Lab
start
:Acessar a landing page do PKZ Lab;
:Ler a apresentação institucional;
:Ver os conteúdos do seu público;
:Ver os serviços;
:Ver o portfólio de treinamentos;
if (Deseja entrar em contato?) then (sim)
  :Clicar no CTA de contato;
  :Ir para a página de Contato;
elseif (Deseja agendar uma aula?) then (sim)
  :Clicar no CTA de agendamento;
  :Ir para a página de Agendamento;
else (não)
  :Retornar ao Hub;
endif
stop
@enduml
```

## 3. Rastreabilidade: tarefas × requisitos (seção 5.1)

- Tarefa 2: Página Institucional do PKZ Lab; Navegação entre as Empresas; Conteúdo Visual; Chamadas para Ação.
