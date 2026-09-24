# Análise Hierárquica de Tarefas (AHT) – Contato e Agendamento

## 1. Introdução

Este documento faz parte da AHT do portal institucional da Holding Esportiva (PKZ Lab e One to One) e descreve as tarefas de entrar em contato (Tarefa 4) e agendar uma aula (Tarefa 5). A numeração das tarefas segue a AHT completa; a meta principal (Meta 0), os usuários e a conclusão geral estão no documento do Hub.

Escopo do projeto:

- Somente front-end, com React e Vite (seção 6.1).
- Necessidades que exijam back-end, banco de dados ou autenticação real não serão atendidas no projeto (seção 6.1).
- A página de agendamento de aula faz parte da plataforma (seções 1.2 e 5.1). Na Tarefa 5 é desenvolvida a interface; a verificação real dos horários disponíveis, o registro do agendamento e a consulta dos agendamentos dependem de back-end (seção 6.1).

Notação:

- 0 = meta principal.
- 1, 2, 3 = tarefas; 1.1, 1.2 = subtarefas.
- Plano = ordem e condições em que o usuário realiza as subtarefas.
- Cada plano é acompanhado do seu diagrama de atividade, escrito em PlantUML.

## 2. Tarefas

### Tarefa 4 – Entrar em contato

- 4.1 Acessar a página de Contato
- 4.2 Escolher entre o formulário ou os canais oficiais
- 4.3 Preencher os dados de identificação e comunicação
- 4.4 Indicar a empresa desejada (quando aplicável)
- 4.5 Escrever e enviar a mensagem
- 4.6 Ver a confirmação de envio
- 4.7 Clicar no link ou botão do canal oficial (WhatsApp ou redes sociais)

Plano 4: O usuário entra na página de Contato e escolhe como quer falar com a empresa. Se escolher o formulário, preenche seus dados, indica a empresa, escreve e envia a mensagem, e vê a confirmação de envio. Se preferir um canal oficial, clica no link do WhatsApp ou das redes sociais.

Diagrama de atividade do Plano 4:

```plantuml
@startuml 4_entrar_em_contato
skin rose
title Tarefa 4 - Entrar em contato
start
:Acessar a página de Contato;
if (Como deseja falar com a empresa?) then (formulário)
  :Preencher os dados de identificação e comunicação;
  :Indicar a empresa desejada;
  :Escrever a mensagem;
  :Enviar a mensagem;
  :Ver a confirmação de envio;
else (canal oficial)
  :Clicar no link do WhatsApp ou das redes sociais;
endif
stop
@enduml
```

### Tarefa 5 – Agendar uma aula

- 5.1 Acessar a página de Agendamento pelo CTA
- 5.2 Ver as opções de aulas ou modalidades disponíveis
- 5.3 Selecionar a empresa desejada (quando aplicável)
- 5.4 Selecionar o serviço ou modalidade
- 5.5 Selecionar a data e o horário disponíveis
- 5.6 Ver o aviso e escolher outra data, horário ou modalidade, se não houver horários disponíveis
- 5.7 Preencher as informações necessárias para o agendamento
- 5.8 Confirmar a solicitação de agendamento
- 5.9 Ver a confirmação do agendamento
- 5.10 Consultar seus agendamentos (usuários autenticados, quando essa funcionalidade estiver disponível)

Plano 5: O usuário abre a página de Agendamento pelo CTA e vê as aulas ou modalidades disponíveis. Se a empresa ainda não estiver definida (quando o acesso não vem da página de uma empresa), escolhe a empresa. Depois escolhe o serviço ou modalidade, a data e o horário. Se não houver horários disponíveis, vê o aviso e escolhe outra data, horário ou modalidade, até encontrar uma opção disponível. Com o horário definido, preenche suas informações, confirma a solicitação e vê a confirmação do agendamento. Se estiver autenticado, pode consultar seus agendamentos, quando essa funcionalidade estiver disponível.

Diagrama de atividade do Plano 5:

```plantuml
@startuml 5_agendar_aula
skin rose
title Tarefa 5 - Agendar uma aula
start
:Acessar a página de Agendamento pelo CTA;
:Ver as opções de aulas ou modalidades disponíveis;
if (Empresa já selecionada?) then (sim)
else (não)
  :Selecionar a empresa desejada;
endif
:Selecionar o serviço ou modalidade;
:Selecionar a data e o horário;
while (Há horários disponíveis?) is (não)
  :Ver o aviso de horários indisponíveis;
  :Escolher outra data, horário ou modalidade;
endwhile (sim)
:Preencher as informações para o agendamento;
:Confirmar a solicitação de agendamento;
:Ver a confirmação do agendamento;
if (Usuário autenticado?) then (sim)
  :Consultar seus agendamentos;
else (não)
endif
stop
@enduml
```

Observação sobre a Tarefa 5: é desenvolvida a página de agendamento. A verificação real dos horários disponíveis, o registro do agendamento e a consulta dos agendamentos pelo usuário autenticado exigem back-end, banco de dados e autenticação real, que não serão atendidos no projeto (seção 6.1).

## 3. Rastreabilidade: tarefas × requisitos (seção 5.1)

- Tarefa 4: Contato; Chamadas para Ação.
- Tarefa 5: Agendamento de Aula (somente a tela); Chamadas para Ação.
