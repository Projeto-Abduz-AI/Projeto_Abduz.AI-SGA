# Abduz.AI — Sistema de Gestão de Abduções Alienígenas

Trabalho acadêmico de Engenharia de Software — FATEC Sorocaba. Documentação consolidada e planejamento inicial, atualizados em **22/10/2026**.

## Links para avaliação

- **[Repositório](https://github.com/Projeto-Abduz-AI/Projeto_Abduz.AI-SGA)**
- **[Project — quadro do backlog](https://github.com/orgs/Projeto-Abduz-AI/projects/4/views/1)**
- **[Sprint 1 — Funcionários e acesso](https://github.com/Projeto-Abduz-AI/Projeto_Abduz.AI-SGA/milestone/1)**

Repositório e Project são públicos: a consulta do professor não depende de convite.

## Conferência da atividade

| Pedido do professor | Organização da entrega |
|---|---|
| Criar board | Project Abduz.AI, com backlog, Todo, In Progress, Team Help, Review e Done. |
| Criar branches main e develop | Ambas existentes. main contém a referência de entrega; develop é a branch de integração do desenvolvimento. |
| Criar itens do backlog | 35 User Stories, US-001 a US-035, nas Issues #1 a #35 e no Project. |
| Planejar a primeira Sprint | Milestone Sprint 1 com US-001, US-002 e US-003; objetivo, período, tarefas, estimativas e conclusão definidos abaixo. |
| Documentação gerada pela IA no README.md | Conteúdo dos cinco documentos Markdown do Discovery/backlog reunido integralmente nas seções expansíveis abaixo, além deste plano. |
| Acesso do professor quando privado | Não se aplica: repositório e Project públicos. |

O prazo da **atividade de entrega dos links é 29/10/2026 às 23h59**, conforme o enunciado fornecido. Esse prazo é diferente do encerramento planejado da Sprint. O enunciado solicita o planejamento, não a conclusão da implementação.

## Contexto e escopo

O SGA centraliza funcionários, naves, humanos, pesquisa pré-missão, agendamento, execução, retornos, dados científicos, histórico e auditoria. Seus usuários são Gestor, Supervisor, Piloto, Abduzidor, Pesquisador e Cientista; humanos abduzidos são participantes do domínio.

O levantamento preserva 7 objetivos, 88 requisitos funcionais, 5 requisitos não funcionais, 23 regras de negócio e 7 decisões consolidadas. O backlog organiza esse conteúdo em **9 Epics, 17 Features e 35 User Stories**. As questões OPEN permanecem visíveis e não são tratadas como decisões confirmadas.

Decisões centrais: login e senha; login único; credenciais administradas por Gestor/Supervisor; bloqueio após cinco falhas por 15 minutos ou liberação administrativa; cancelamento definitivo; remarcação somente de missão Adiada; impedimento de sobreposição; autonomia para ida e volta ao Estacionamento Alien. Área 51 e relatório separado de missão estão fora do escopo.

## Sprint 1 — Funcionários e acesso

**Objetivo:** disponibilizar a base de funcionários e acesso, permitindo cadastro administrativo, autenticação e controle de funcionários ativos/inativos.

**Período planejado:** 22/10/2026 a 04/11/2026, 14 dias corridos. Datas e estimativas são decisões de planejamento propostas nesta preparação da entrega, não registros de execução passada ou de aprovação já ocorrida do grupo.

**Capacidade inicial proposta:** 13 pontos relativos de esforço. Os pontos não equivalem a horas e serão recalibrados pelo grupo. Responsáveis individuais serão registrados nas Issues ao assumir o trabalho; não foram atribuídas pessoas sem informação de disponibilidade.

| Ordem | Item | Prioridade na Sprint | Estimativa inicial | Dependências e entrega esperada |
|---|---|---|---|---|
| 1 | [US-001 — Cadastrar e atualizar funcionários](https://github.com/Projeto-Abduz-AI/Projeto_Abduz.AI-SGA/issues/1) | Alta | 5 pontos | Cadastro e atualização administrativa, dados definidos e login único. Integração com US-003 para controle de acesso. |
| 2 | [US-003 — Acessar o SGA](https://github.com/Projeto-Abduz-AI/Projeto_Abduz.AI-SGA/issues/3) | Alta | 3 pontos | Conta cadastrada em US-001; aceitar credenciais válidas e negar inválidas/acesso sem autenticação. |
| 3 | [US-002 — Inativar e reativar funcionários](https://github.com/Projeto-Abduz-AI/Projeto_Abduz.AI-SGA/issues/2) | Alta | 5 pontos | US-001 e US-003; preservar cadastro, bloquear acesso inativo e reativar conforme DEC-006. |

### Tarefas previstas

- [ ] **S1-T01 — Refinamento:** confirmar validações de funcionários (OPEN-023), permissões administrativas aplicáveis e tratamento de OPEN-019; registrar decisões sem alterar regras silenciosamente.
- [ ] **S1-T02 — Cadastro:** preparar o fluxo de cadastro e edição com nome, matrícula/registro, função, cargo, situação e credenciais; verificar login duplicado (US-001).
- [ ] **S1-T03 — Autenticação:** realizar acesso com credenciais válidas, rejeitar inválidas e impedir consulta protegida sem autenticação (US-003).
- [ ] **S1-T04 — Situação:** inativar sem excluir o cadastro e reativar com novas credenciais; conferir bloqueio de acesso e inelegibilidade para nova missão (US-002).
- [ ] **S1-T05 — Integração e testes:** executar os critérios de aceitação das três histórias, com cenários positivos e negativos, e registrar evidências.
- [ ] **S1-T06 — Revisão:** revisar mudanças por outro integrante, integrar em develop e atualizar documentação.
- [ ] **S1-T07 — Encerramento:** demonstrar o incremento, revisar o objetivo e registrar o que ficou concluído ou voltou ao backlog.

### Sequência e acompanhamento

1. **22–23/10:** refinamento, divisão das tarefas e preparação dos cenários de teste.
2. **24–29/10:** cadastro e autenticação, com integração progressiva.
3. **30/10–02/11:** situação de funcionários e testes de integração.
4. **03–04/11:** revisão, correções e demonstração do incremento.

Atualizar o quadro a cada avanço real. Os estados existentes foram preservados: US-001 e US-002 estavam em In Progress; US-003 estava em Todo na conferência. Isso não comprova implementação nem substitui testes. Os demais itens continuam no backlog geral, mesmo que já estejam priorizados na coluna Todo; pertencimento à Sprint é definido pelo milestone.

### Riscos e limites

- OPEN-023 afeta validações do cadastro; resolver a parte necessária antes da aceitação de US-001.
- OPEN-019 afeta inativação com missões já agendadas. Enquanto não resolvido, não presumir cancelamento automático nem marcar US-002 integralmente pronta.
- O critério de US-002 sobre seleção para nova missão depende do fluxo de missões, previsto para incrementos posteriores. Preparar o teste e a regra de elegibilidade nesta Sprint; se a verificação completa continuar impossível, manter a história aberta ou registrar uma divisão explícita aprovada pelo grupo.
- Bloqueio por tentativas, alertas, troca de senha, encerramento de expediente, naves e missões continuam no backlog; não estão incluídos implicitamente nesta Sprint.
- Critérios de auditoria e qualidade continuam transversais. Não declarar o SGA completo ou pronto para produção ao concluir esta Sprint.
- Se as pendências impedirem o objetivo, ajustar o escopo no planejamento e registrar o motivo; não inventar decisões de negócio para fechar uma Issue.

### Definição de pronto

Uma história somente vai para **Done** quando seus critérios de aceitação aplicáveis tiverem evidência, não houver pendência que impeça sua validação, as permissões tiverem sido conferidas, outro integrante tiver revisado a entrega, a integração em develop estiver concluída e a documentação estiver atualizada. Critérios bloqueados mantêm a história aberta. A aprovação da Sprint deve ser registrada pelo grupo após a demonstração.

## Uso das branches e do board

- **main:** documentação e referência estável apresentada na entrega.
- **develop:** integração das próximas alterações de desenvolvimento.
- Alterações de funcionalidade devem ser revisadas antes de integrar; o fechamento de Issues acompanha a evidência de conclusão.
- **backlog → Todo → In Progress → Review → Done**, com **Team Help** para impedimentos.
- A Sprint 1 agrupa Issues existentes pelo milestone; não duplica histórias.
- Os estados de missão do SGA (Pendente, Em andamento, Adiada, Concluída e Cancelada) são regras do produto, diferentes das colunas do trabalho no GitHub.

## Documentação integral de referência

Os blocos abaixo reproduzem os documentos Markdown existentes no repositório em 22/10/2026. As referências a ausência de Sprint nos textos originais descrevem a etapa de 29/09; o planejamento desta Sprint, acima, é a atualização vigente. As pendências de Discovery não foram declaradas resolvidas por esta organização da entrega.

<details>
<summary><strong>Organização, fontes e hierarquia do backlog</strong></summary>

# Backlog do SGA — Abduz.AI

Etapa 03 — Backlog | Versão 1.0 | 29/09/2026

Este backlog organiza o Discovery em **9 épicos, 17 features e 35 histórias de usuário**. Os **88 FR** possuem associação principal a uma história; os **5 NFR** são tratados transversalmente. Estado: **proposta para validação do grupo**, com questões abertas explícitas. Cobertura documental não significa prontidão integral para implementação.

## Como ler

- [Histórias detalhadas](docs/discovery/backlog/historias.md): necessidade, benefício, dados, dependências, critérios e pendências.
- [Requisitos transversais e critérios de qualidade](docs/discovery/backlog/qualidade.md).
- [Questões abertas e revisão de consistência](docs/discovery/backlog/pendencias.md).
- [Rastreabilidade e catálogo de requisitos de origem](docs/discovery/backlog/rastreabilidade.md).

## Fontes e limites

1. `SGA_Especificacao_Formal_Requisitos_Discovery_v1.1.docx`, versão 1.1, datada de 28/09/2026.
2. `SGA_Documento_Consolidado_de_Requisitos_Discovery.docx`, versão 1.0, datada de 28/09/2026.
3. Histórico fornecido pelo grupo nesta conversa, incluindo decisões posteriores e orientações copiadas de “03 — Organização dos Chats”.
4. `image(8).png`: índice da página “Estruturando o projeto com ChatGPT”; não contém critérios adicionais do backlog.

Página indicada pelo grupo: [Engenharia de Software — professor Glauco Todesco](https://glaucotodesco.notion.site/Engenharia-de-Software-3c25d52a81f580ccbca7ffc98c5a4f8a?pvs=73). O conteúdo integral não ficou acessível na consulta. A conformidade com instruções adicionais dessa página precisa ser conferida pelo grupo.

Os documentos-base e registros de 105 perguntas são citados pelos DOCX, mas não foram fornecidos integralmente nesta etapa. Não se declara revisão direta dessas fontes. O histórico colado contém trechos repetidos: eles não foram contados como decisões adicionais.

## Critérios de organização

- IDs FR, NFR, BR, DEC e OPEN existentes foram preservados. EPIC, FEAT e US são novos identificadores deste backlog.
- Agrupamento, critérios de teste derivados e ordem de trabalho são propostas de organização, não novas decisões de negócio.
- Exemplos numéricos de aceitação são dados de teste e não limites do sistema.
- Critérios dependentes de OPEN são condicionais e não devem ser marcados como aprovados antes da decisão.
- Nenhuma estimativa, prazo, sprint ou responsável individual foi inventado.
- Os atores das histórias representam quem obtém valor; o sistema executa automações e o humano abduzido é participante, não usuário.
- Arquitetura e implementação estão fora desta entrega. Área 51, relatório separado e integração com folha salarial não foram incluídos.

## Hierarquia Epic → Feature → User Story

### EPIC-001 — Funcionários e acesso

**Objetivos:** OBJ-001, OBJ-007. **Resultado:** Administrar funcionários e permitir acesso controlado.

**FEAT-001 — Ciclo cadastral de funcionários**

- [US-001 — Cadastrar e atualizar funcionários](docs/discovery/backlog/historias.md#us-001)
- [US-002 — Inativar e reativar funcionários](docs/discovery/backlog/historias.md#us-002)

**FEAT-002 — Autenticação e credenciais**

- [US-003 — Acessar o SGA](docs/discovery/backlog/historias.md#us-003)
- [US-004 — Bloquear e desbloquear uma conta](docs/discovery/backlog/historias.md#us-004)
- [US-005 — Receber alerta de bloqueio](docs/discovery/backlog/historias.md#us-005)
- [US-006 — Solicitar alteração ou recuperação de senha](docs/discovery/backlog/historias.md#us-006)
- [US-007 — Encerrar a sessão ao final do expediente](docs/discovery/backlog/historias.md#us-007)

### EPIC-002 — Naves e percurso

**Objetivos:** OBJ-001, OBJ-003. **Resultado:** Manter naves e validar condições de uso.

**FEAT-003 — Cadastro e manutenção de naves**

- [US-008 — Cadastrar e atualizar naves](docs/discovery/backlog/historias.md#us-008)
- [US-009 — Controlar manutenção de naves](docs/discovery/backlog/historias.md#us-009)

**FEAT-004 — Autonomia e percurso**

- [US-010 — Validar autonomia de ida e retorno](docs/discovery/backlog/historias.md#us-010)

### EPIC-003 — Humanos e pesquisa pré-missão

**Objetivos:** OBJ-001, OBJ-002, OBJ-004. **Resultado:** Preparar informações para a decisão humana.

**FEAT-005 — Cadastro de humanos**

- [US-011 — Cadastrar e consultar humanos](docs/discovery/backlog/historias.md#us-011)

**FEAT-006 — Pesquisa e avaliação pré-missão**

- [US-012 — Registrar pesquisa pré-missão](docs/discovery/backlog/historias.md#us-012)
- [US-013 — Avaliar pesquisa e decidir prosseguimento](docs/discovery/backlog/historias.md#us-013)

### EPIC-004 — Planejamento e ciclo de missões

**Objetivos:** OBJ-002, OBJ-003, OBJ-004. **Resultado:** Agendar e acompanhar missões sem conflitos conhecidos.

**FEAT-007 — Definição e validação de agendamento**

- [US-014 — Definir uma missão](docs/discovery/backlog/historias.md#us-014)
- [US-015 — Validar conflitos de agendamento](docs/discovery/backlog/historias.md#us-015)
- [US-016 — Validar lotação com vários humanos](docs/discovery/backlog/historias.md#us-016)

**FEAT-008 — Estados e movimentação da missão**

- [US-017 — Iniciar missão e registrar saída](docs/discovery/backlog/historias.md#us-017)
- [US-018 — Concluir missão e registrar entrada](docs/discovery/backlog/historias.md#us-018)
- [US-019 — Adiar e remarcar missão](docs/discovery/backlog/historias.md#us-019)
- [US-020 — Cancelar definitivamente uma missão](docs/discovery/backlog/historias.md#us-020)

**FEAT-009 — Notificações de missão**

- [US-021 — Notificar mudanças da missão](docs/discovery/backlog/historias.md#us-021)

### EPIC-005 — Retorno e advertências

**Objetivos:** OBJ-005. **Resultado:** Registrar retornos e acompanhar ocorrências e advertências.

**FEAT-010 — Retornos e ocorrências**

- [US-022 — Registrar retorno normal ou inadequado](docs/discovery/backlog/historias.md#us-022)

**FEAT-011 — Advertências e correção**

- [US-023 — Manter advertências e punição por reincidência](docs/discovery/backlog/historias.md#us-023)
- [US-024 — Acompanhar correção e reincidência não corrigida](docs/discovery/backlog/historias.md#us-024)

### EPIC-006 — Ocorrências de morte

**Objetivos:** OBJ-005. **Resultado:** Registrar análise e encerramento dos casos.

**FEAT-012 — Análise e encerramento de morte**

- [US-025 — Registrar morte e análise do caso](docs/discovery/backlog/historias.md#us-025)
- [US-026 — Tratar morte natural e encerrar o caso](docs/discovery/backlog/historias.md#us-026)
- [US-027 — Registrar punição por falha atribuível](docs/discovery/backlog/historias.md#us-027)

### EPIC-007 — Dados científicos

**Objetivos:** OBJ-006. **Resultado:** Registrar, restringir consulta e tratar obsolescência.

**FEAT-013 — Registro, alteração e consulta científica**

- [US-028 — Registrar e manter dados científicos](docs/discovery/backlog/historias.md#us-028)
- [US-029 — Consultar dados científicos com restrição](docs/discovery/backlog/historias.md#us-029)

**FEAT-014 — Obsolescência científica**

- [US-030 — Excluir dados científicos obsoletos](docs/discovery/backlog/historias.md#us-030)

### EPIC-008 — Histórico de missões

**Objetivos:** OBJ-005. **Resultado:** Consultar e corrigir o histórico conforme permissões.

**FEAT-015 — Consulta e manutenção do histórico**

- [US-031 — Consultar histórico de missões](docs/discovery/backlog/historias.md#us-031)
- [US-032 — Corrigir histórico com permissão administrativa](docs/discovery/backlog/historias.md#us-032)

### EPIC-009 — Auditoria

**Objetivos:** OBJ-007. **Resultado:** Rastrear acessos, alterações e consultas administrativas.

**FEAT-016 — Registros de acesso e alteração**

- [US-033 — Registrar e reter acessos](docs/discovery/backlog/historias.md#us-033)
- [US-034 — Registrar alterações e seus valores](docs/discovery/backlog/historias.md#us-034)

**FEAT-017 — Consulta e proteção da auditoria**

- [US-035 — Consultar auditoria imutável e registrar consultas](docs/discovery/backlog/historias.md#us-035)

## Ordem sugerida de refinamento — a validar

| Ordem | Foco | Razão |
|---|---|---|
| 1 | Funcionários, acesso e cadastros de naves/humanos | Base dos demais fluxos; definir permissões e dados essenciais. |
| 2 | Pesquisa, decisão, agendamento, capacidade e autonomia | Caminho principal e prevenção dos conflitos centrais do problema. |
| 3 | Início, retorno, conclusão, adiamento e cancelamento | Completar o ciclo operacional e esclarecer suas transições. |
| 4 | Advertências, morte e dados científicos | Refinar regras de exceção e dados restritos. |
| Contínuo | Histórico, auditoria e NFR | Critérios transversais a acompanhar desde as primeiras histórias. |

Essa sequência não define MVP nem reduz o escopo. O grupo ainda deve aprovar prioridades; as pendências de severidade alta devem ser tratadas antes de considerar prontas as histórias afetadas.

## Checklist para validar uma história

- [ ] Ator e permissão conferidos pelo grupo.
- [ ] Critérios positivos, negativos e limites aplicáveis compreendidos.
- [ ] OPEN que impede o teste resolvido ou história dividida com escopo explícito.
- [ ] Dependências e critérios transversais revisados.
- [ ] Prioridade e estimativa discutidas pelo grupo quando houver planejamento.


</details>

<details>
<summary><strong>35 histórias de usuário e critérios de aceitação</strong></summary>

# Histórias de usuário

Etapa 03 — Backlog. Todas as histórias são propostas para validação. Os comportamentos vêm dos requisitos citados; as lacunas permanecem em [pendências](docs/discovery/backlog/pendencias.md).

**Pré-condição transversal:** funcionário autenticado e com permissão para a operação, exceto o próprio fluxo de autenticação e a solicitação por esquecimento de senha, cujo canal está pendente. Automações dependem do evento/estado indicado em seus critérios. As dependências abaixo indicam relação de domínio, não sequência obrigatória de programação.

**Qualidade transversal:** observar [NFR-001 a NFR-005](docs/discovery/backlog/qualidade.md). Auditoria depende de US-033 a US-035; esta relação transversal não deve ser interpretada como ciclo de execução entre histórias.

<a id="us-001"></a>
## US-001 — Cadastrar e atualizar funcionários

**Hierarquia:** EPIC-001 → FEAT-001 → US-001.
**História:** Como Gestor ou Supervisor, quero manter os funcionários e suas credenciais, para administrar quem trabalha no SGA.

**Origem:** FR-001, FR-006.
**Regras relacionadas:** BR-001
**Dados e condições específicas:** Nome, matrícula/registro, função, cargo, situação e login; senha inicial definida por Gestor/Supervisor.
**Dependências de domínio:** Nenhuma outra história predecessora identificada; aplicam-se acesso e permissões transversais.

**Critérios de aceitação:**

- **CA-01:** Dado um Gestor ou Supervisor autenticado, quando cadastrar um funcionário com os dados definidos, então o funcionário e suas credenciais ficam disponíveis no cadastro.
- **CA-02:** Dado um login já cadastrado, quando tentar atribuí-lo a outro funcionário, então o cadastro não aceita a duplicação.
- **CA-03:** Dado um funcionário existente, quando Gestor/Supervisor alterar seus dados, então o cadastro apresenta os valores atualizados.

**Pendências vinculadas:** Nenhuma pendência específica vinculada; validação do grupo e requisitos transversais continuam necessários.
**Limites e observações:** Unicidade de matrícula, campos obrigatórios e normalização de login não estão definidos.

**Situação de refinamento:** Critérios específicos elaborados; aguarda validação do grupo.

<a id="us-002"></a>
## US-002 — Inativar e reativar funcionários

**Hierarquia:** EPIC-001 → FEAT-001 → US-002.
**História:** Como Gestor ou Supervisor, quero alterar a situação do funcionário sem excluí-lo, para preservar seus registros e controlar o acesso.

**Origem:** FR-002, FR-003, FR-004, FR-012.
**Regras relacionadas:** BR-001, BR-002, BR-003
**Dados e condições específicas:** Funcionário, situação e novas credenciais na reativação (DEC-006).
**Dependências de domínio:** [US-001](docs/discovery/backlog/historias.md#us-001)

**Critérios de aceitação:**

- **CA-01:** Dado um funcionário ativo, quando for inativado, então seu cadastro permanece e seu acesso é bloqueado.
- **CA-02:** Dado um funcionário inativo, quando forem selecionados participantes de nova missão, então ele não pode ser selecionado.
- **CA-03:** Dado um funcionário inativo, quando Gestor/Supervisor reativá-lo, então não se exige justificativa adicional e são criadas novas credenciais conforme DEC-006.

**Pendências vinculadas:** OPEN-019
**Limites e observações:** O efeito da inativação sobre missões já agendadas depende de decisão.

**Situação de refinamento:** Requer refinamento nas questões vinculadas; critérios já definidos podem ser avaliados separadamente.

<a id="us-003"></a>
## US-003 — Acessar o SGA

**Hierarquia:** EPIC-001 → FEAT-002 → US-003.
**História:** Como funcionário, quero entrar usando login e senha, para acessar as informações permitidas ao meu perfil.

**Origem:** FR-005.
**Regras relacionadas:** Condições expressas nos FR de origem e permissões transversais.
**Dados e condições específicas:** Login, senha e situação da conta. Pré-condição: conta ativa e não bloqueada.
**Dependências de domínio:** [US-001](docs/discovery/backlog/historias.md#us-001)

**Critérios de aceitação:**

- **CA-01:** Dada uma conta ativa e não bloqueada, quando fornecer login e senha válidos, então a autenticação é aceita.
- **CA-02:** Dadas credenciais inválidas, quando tentar entrar, então o acesso não é concedido.
- **CA-03:** Dado um usuário não autenticado, quando tentar consultar informações de missão, então o acesso é impedido (NFR-002).

**Pendências vinculadas:** Nenhuma pendência específica vinculada; validação do grupo e requisitos transversais continuam necessários.
**Limites e observações:** O ator é o funcionário, inclusive perfis operacionais; a tabela de FR-005 lista apenas administradores, embora a autenticação seja comum aos usuários.

**Situação de refinamento:** Critérios específicos elaborados; aguarda validação do grupo.

<a id="us-004"></a>
## US-004 — Bloquear e desbloquear uma conta

**Hierarquia:** EPIC-001 → FEAT-002 → US-004.
**História:** Como Gestor ou Supervisor, quero controlar bloqueios por falhas de autenticação, para limitar novas tentativas após cinco erros consecutivos.

**Origem:** FR-007, FR-008.
**Regras relacionadas:** Condições expressas nos FR de origem e permissões transversais.
**Dados e condições específicas:** Conta, tentativas consecutivas, instante do bloqueio e aprovação de desbloqueio.
**Dependências de domínio:** [US-003](docs/discovery/backlog/historias.md#us-003)

**Critérios de aceitação:**

- **CA-01:** Dada uma conta sem falhas anteriores na sequência, quando ocorrerem quatro senhas incorretas consecutivas, então ainda não se aplica o bloqueio de cinco tentativas.
- **CA-02:** Quando ocorrer a quinta senha incorreta consecutiva, então a conta fica bloqueada.
- **CA-03:** Dada uma conta bloqueada, quando completar 15 minutos, então pode tentar autenticar novamente.
- **CA-04:** Dada uma conta bloqueada há menos de 15 minutos, quando Gestor/Supervisor aprovar o desbloqueio, então novas tentativas são permitidas antes do prazo.

**Pendências vinculadas:** OPEN-020
**Limites e observações:** Janela de contagem, reinício do contador e resultado de tentativas durante o bloqueio permanecem pendentes.

**Situação de refinamento:** Requer refinamento nas questões vinculadas; critérios já definidos podem ser avaliados separadamente.

<a id="us-005"></a>
## US-005 — Receber alerta de bloqueio

**Hierarquia:** EPIC-001 → FEAT-002 → US-005.
**História:** Como Gestor ou Supervisor, quero receber alerta de uma conta bloqueada, para identificar possível risco de intrusão.

**Origem:** FR-009.
**Regras relacionadas:** Condições expressas nos FR de origem e permissões transversais.
**Dados e condições específicas:** Conta bloqueada, destinatários administrativos e indicação de criticidade.
**Dependências de domínio:** [US-004](docs/discovery/backlog/historias.md#us-004)

**Critérios de aceitação:**

- **CA-01:** Quando uma conta for bloqueada por tentativas incorretas, então o alerta é destinado a Gestor e Supervisor.
- **CA-02:** Então o alerta ocorre dentro do SGA e por e-mail, conforme FR-009.
- **CA-03:** Então a mensagem indica caráter crítico ou possível risco de intrusão.

**Pendências vinculadas:** OPEN-021
**Limites e observações:** O prazo mensurável de envio, endereços dos destinatários e tratamento de falhas de e-mail não foram definidos. Não confundir com notificações internas de missão.

**Situação de refinamento:** Requer refinamento nas questões vinculadas; critérios já definidos podem ser avaliados separadamente.

<a id="us-006"></a>
## US-006 — Solicitar alteração ou recuperação de senha

**Hierarquia:** EPIC-001 → FEAT-002 → US-006.
**História:** Como funcionário, quero solicitar uma nova senha ao Gestor ou Supervisor, para recuperar ou atualizar meu acesso mediante aprovação.

**Origem:** FR-010, FR-011.
**Regras relacionadas:** Condições expressas nos FR de origem e permissões transversais.
**Dados e condições específicas:** Funcionário, solicitação e aprovação administrativa.
**Dependências de domínio:** [US-001](docs/discovery/backlog/historias.md#us-001), [US-003](docs/discovery/backlog/historias.md#us-003)

**Critérios de aceitação:**

- **CA-01:** Dado um funcionário que deseja alterar sua senha, quando não houver aprovação, então a alteração não é permitida.
- **CA-02:** Dada uma solicitação aprovada por Gestor/Supervisor, então a alteração de senha é permitida.
- **CA-03:** Dado esquecimento de senha, então se aplica o mesmo procedimento de solicitação e aprovação.

**Pendências vinculadas:** OPEN-022
**Limites e observações:** Canal da solicitação, executor da alteração após aprovação e entrega da nova senha estão pendentes; não presumir autoatendimento.

**Situação de refinamento:** Requer refinamento nas questões vinculadas; critérios já definidos podem ser avaliados separadamente.

<a id="us-007"></a>
## US-007 — Encerrar a sessão ao final do expediente

**Hierarquia:** EPIC-001 → FEAT-002 → US-007.
**História:** Como funcionário, quero ter a sessão encerrada ao final do dia de trabalho, para exigir nova autenticação no próximo acesso.

**Origem:** FR-013.
**Regras relacionadas:** Condições expressas nos FR de origem e permissões transversais.
**Dados e condições específicas:** Sessão e referência de final do dia de trabalho ainda não definida.
**Dependências de domínio:** [US-003](docs/discovery/backlog/historias.md#us-003)

**Critérios de aceitação:**

- **CA-01:** Dado o marco de fim do expediente definido pelo grupo, quando ele ocorrer, então a sessão é encerrada automaticamente.
- **CA-02:** Dada a sessão encerrada, quando houver novo acesso, então são exigidas credenciais novamente.

**Pendências vinculadas:** OPEN-005
**Limites e observações:** Critérios condicionados à definição do horário/regra em OPEN-005.

**Situação de refinamento:** Requer refinamento nas questões vinculadas; critérios já definidos podem ser avaliados separadamente.

<a id="us-008"></a>
## US-008 — Cadastrar e atualizar naves

**Hierarquia:** EPIC-002 → FEAT-003 → US-008.
**História:** Como Gestor ou Supervisor, quero manter os dados das naves, para dispor de informações para planejar missões.

**Origem:** FR-019, FR-020.
**Regras relacionadas:** BR-001
**Dados e condições específicas:** Nave, capacidade total, quilômetros que pode voar e status operacional.
**Dependências de domínio:** Nenhuma outra história predecessora identificada; aplicam-se acesso e permissões transversais.

**Critérios de aceitação:**

- **CA-01:** Quando Gestor/Supervisor cadastrar uma nave, então o cadastro mantém capacidade total, quilômetros disponíveis e status operacional.
- **CA-02:** Dada uma nave cadastrada, quando seus dados forem alterados, então os valores atualizados são apresentados para planejamento.

**Pendências vinculadas:** OPEN-023
**Limites e observações:** Identificador, obrigatoriedade e limites numéricos dos campos não estão definidos.

**Situação de refinamento:** Requer refinamento nas questões vinculadas; critérios já definidos podem ser avaliados separadamente.

<a id="us-009"></a>
## US-009 — Controlar manutenção de naves

**Hierarquia:** EPIC-002 → FEAT-003 → US-009.
**História:** Como Gestor ou Supervisor, quero alterar a disponibilidade operacional da nave, para impedir o uso de nave em manutenção.

**Origem:** FR-021, FR-022.
**Regras relacionadas:** BR-004
**Dados e condições específicas:** Nave e status disponível/manutenção.
**Dependências de domínio:** [US-008](docs/discovery/backlog/historias.md#us-008)

**Critérios de aceitação:**

- **CA-01:** Dada uma nave, quando Gestor/Supervisor alterar o status, então ele pode assumir disponível ou manutenção.
- **CA-02:** Dada uma nave em manutenção, quando for utilizada na definição/agendamento de missão, então o uso é impedido.

**Pendências vinculadas:** OPEN-019
**Limites e observações:** Tratamento das missões já agendadas quando a nave entra em manutenção não está definido.

**Situação de refinamento:** Requer refinamento nas questões vinculadas; critérios já definidos podem ser avaliados separadamente.

<a id="us-010"></a>
## US-010 — Validar autonomia de ida e retorno

**Hierarquia:** EPIC-002 → FEAT-004 → US-010.
**História:** Como Gestor, quero verificar a autonomia para todo o percurso, para planejar uma missão com retorno ao Estacionamento Alien.

**Origem:** FR-025, FR-026, FR-027.
**Regras relacionadas:** BR-016, BR-017
**Dados e condições específicas:** Autonomia em quilômetros, distância total, origem e retorno no Estacionamento Alien.
**Dependências de domínio:** [US-008](docs/discovery/backlog/historias.md#us-008)

**Critérios de aceitação:**

- **CA-01:** Dado um percurso de missão, então sua origem e seu destino de retorno são o Estacionamento Alien.
- **CA-02:** Dadas distância total e autonomia conhecidas, quando validar o percurso, então a comparação considera ida e retorno.
- **CA-03:** Dada autonomia inferior à distância total, então a validação aponta insuficiência; a regra para satisfazer todas as validações do agendamento permanece aplicável.

**Pendências vinculadas:** OPEN-009, OPEN-024
**Limites e observações:** O percurso está decidido (DEC-005); origem da distância, medição e fronteira de autonomia exatamente igual dependem de refinamento.

**Situação de refinamento:** Requer refinamento nas questões vinculadas; critérios já definidos podem ser avaliados separadamente.

<a id="us-011"></a>
## US-011 — Cadastrar e consultar humanos

**Hierarquia:** EPIC-003 → FEAT-005 → US-011.
**História:** Como Gestor ou Supervisor, quero manter o cadastro de humanos, para identificar os participantes das missões.

**Origem:** FR-028, FR-029.
**Regras relacionadas:** Condições expressas nos FR de origem e permissões transversais.
**Dados e condições específicas:** Humano, nome, localização, idade e popularidade.
**Dependências de domínio:** Nenhuma outra história predecessora identificada; aplicam-se acesso e permissões transversais.

**Critérios de aceitação:**

- **CA-01:** Quando um humano for cadastrado, então nome, localização, idade e popularidade são mantidos no cadastro.
- **CA-02:** Dado um humano cadastrado, quando consultá-lo, então seus dados cadastrados são apresentados.

**Pendências vinculadas:** OPEN-023
**Limites e observações:** Identificador único, obrigatoriedade e escalas de popularidade dependem de definição. Humano é participante do domínio, não usuário do SGA.

**Situação de refinamento:** Requer refinamento nas questões vinculadas; critérios já definidos podem ser avaliados separadamente.

<a id="us-012"></a>
## US-012 — Registrar pesquisa pré-missão

**Hierarquia:** EPIC-003 → FEAT-006 → US-012.
**História:** Como Pesquisador, quero registrar informações de vida e de localização, para fornecer dados à avaliação da missão.

**Origem:** FR-031, FR-032, FR-033.
**Regras relacionadas:** BR-009
**Dados e condições específicas:** Idade, patrimônio/riqueza, emprego, fonte de renda, popularidade, interações sociais, informações gerais e locais pesquisados.
**Dependências de domínio:** [US-011](docs/discovery/backlog/historias.md#us-011)

**Critérios de aceitação:**

- **CA-01:** Quando o Pesquisador registrar a pesquisa, então pode registrar todos os grupos de informações previstos em FR-032.
- **CA-02:** Quando registrar informações de localização, então elas ficam disponíveis para identificar locais mais calmos na avaliação humana.
- **CA-03:** Dada uma missão sem pesquisa pré-missão, quando tentar agendá-la, então o agendamento é impedido.

**Pendências vinculadas:** OPEN-011, OPEN-025
**Limites e observações:** Não criar pontuação automática de tranquilidade nem estados adicionais da pesquisa. Completude por humano em missão coletiva depende de OPEN-025.

**Situação de refinamento:** Requer refinamento nas questões vinculadas; critérios já definidos podem ser avaliados separadamente.

<a id="us-013"></a>
## US-013 — Avaliar pesquisa e decidir prosseguimento

**Hierarquia:** EPIC-003 → FEAT-006 → US-013.
**História:** Como Gestor, quero avaliar a pesquisa com o Supervisor, para decidir se a missão pode prosseguir.

**Origem:** FR-034, FR-035, FR-036, FR-037.
**Regras relacionadas:** BR-010, BR-011
**Dados e condições específicas:** Pesquisa, avaliação humana, relevância global e decisão. DEC-002 distingue ocorrências durante/depois da missão.
**Dependências de domínio:** [US-012](docs/discovery/backlog/historias.md#us-012)

**Critérios de aceitação:**

- **CA-01:** Dada uma pesquisa registrada, então Gestor e Supervisor podem avaliar suas informações.
- **CA-02:** Quando uma exceção for classificada, então a identificação decorre da avaliação humana, não de classificação automática do SGA.
- **CA-03:** Dada relevância global identificada, então a missão não prossegue e seu cancelamento é definitivo.
- **CA-04:** Dada ausência de impedimento relevante, então o Gestor pode decidir pelo prosseguimento.

**Pendências vinculadas:** OPEN-026
**Limites e observações:** O momento de criação do registro cancelável e o efeito de um humano com relevância global em missão com vários humanos estão pendentes.

**Situação de refinamento:** Requer refinamento nas questões vinculadas; critérios já definidos podem ser avaliados separadamente.

<a id="us-014"></a>
## US-014 — Definir uma missão

**Hierarquia:** EPIC-004 → FEAT-007 → US-014.
**História:** Como Gestor, quero registrar a solicitação e os participantes da missão, para preparar seu agendamento.

**Origem:** FR-038, FR-039, FR-043, FR-044.
**Regras relacionadas:** BR-002, BR-006
**Dados e condições específicas:** Humano(s), nave, tripulação, local, data, horário e intervalo da missão.
**Dependências de domínio:** [US-001](docs/discovery/backlog/historias.md#us-001), [US-008](docs/discovery/backlog/historias.md#us-008), [US-011](docs/discovery/backlog/historias.md#us-011), [US-013](docs/discovery/backlog/historias.md#us-013)

**Critérios de aceitação:**

- **CA-01:** Quando o Gestor definir a missão, então registra humano(s), nave, tripulação, local, data e horário.
- **CA-02:** Dada tripulação sem Piloto ou sem Abduzidor, então a composição não satisfaz a exigência mínima.
- **CA-03:** Dada seleção da tripulação, então apenas funcionários ativos e disponíveis podem compô-la.

**Pendências vinculadas:** OPEN-007, OPEN-017, OPEN-023
**Limites e observações:** BR-001 concede poderes iguais ao Supervisor, enquanto vários FR citam só o Gestor; a matriz final precisa explicitar a abrangência.

**Situação de refinamento:** Requer refinamento nas questões vinculadas; critérios já definidos podem ser avaliados separadamente.

<a id="us-015"></a>
## US-015 — Validar conflitos de agendamento

**Hierarquia:** EPIC-004 → FEAT-007 → US-015.
**História:** Como Gestor, quero verificar disponibilidade e sobreposição, para evitar alocar os mesmos recursos em missões incompatíveis.

**Origem:** FR-030, FR-040, FR-041, FR-042.
**Regras relacionadas:** BR-007, BR-008
**Dados e condições específicas:** Nave, funcionários, humanos e intervalos de missão.
**Dependências de domínio:** [US-014](docs/discovery/backlog/historias.md#us-014)

**Critérios de aceitação:**

- **CA-01:** Dado o mesmo funcionário em dois intervalos com sobreposição, quando tentar agendar a segunda missão, então o agendamento é bloqueado.
- **CA-02:** Dado um humano participante de missão simultânea, quando tentar incluí-lo em outra, então o conflito é impedido.
- **CA-03:** Dada nave ou funcionário indisponível, quando tentar agendar, então o agendamento é bloqueado.
- **CA-04:** Dadas todas as validações satisfeitas, então a missão pode ficar Pendente, conforme o fluxo consolidado.

**Pendências vinculadas:** OPEN-007, OPEN-008, OPEN-024
**Limites e observações:** DEC-004 define início e término como base. Falta esclarecer término previsto versus término real, fronteiras entre intervalos e disponibilidade além da situação cadastral.

**Situação de refinamento:** Requer refinamento nas questões vinculadas; critérios já definidos podem ser avaliados separadamente.

<a id="us-016"></a>
## US-016 — Validar lotação com vários humanos

**Hierarquia:** EPIC-004 → FEAT-007 → US-016.
**História:** Como Gestor, quero verificar a quantidade de ocupantes, para respeitar a capacidade da nave.

**Origem:** FR-045, FR-046, FR-047.
**Regras relacionadas:** BR-005
**Dados e condições específicas:** Capacidade total, quantidade de tripulantes e humanos.
**Dependências de domínio:** [US-014](docs/discovery/backlog/historias.md#us-014), [US-008](docs/discovery/backlog/historias.md#us-008)

**Critérios de aceitação:**

- **CA-01:** Dada uma nave de capacidade 4, com 2 tripulantes e 2 humanos, então a capacidade não bloqueia a missão.
- **CA-02:** Dada a mesma nave com 2 tripulantes e 3 humanos, então o agendamento é bloqueado por exceder a capacidade.
- **CA-03:** Então a contagem inclui todos os tripulantes e humanos, permitindo mais de um humano quando couber.

**Pendências vinculadas:** Nenhuma pendência específica vinculada; validação do grupo e requisitos transversais continuam necessários.
**Limites e observações:** Os números são dados de teste, não limites do produto. Demais validações continuam necessárias.

**Situação de refinamento:** Critérios específicos elaborados; aguarda validação do grupo.

<a id="us-017"></a>
## US-017 — Iniciar missão e registrar saída

**Hierarquia:** EPIC-004 → FEAT-008 → US-017.
**História:** Como Gestor, quero acompanhar o início automático da missão, para manter o estado da missão e a saída da nave registrados.

**Origem:** FR-023, FR-048, FR-049.
**Regras relacionadas:** BR-012
**Dados e condições específicas:** Missão Pendente, horário agendado, nave e saída. Pré-condição: agendamento validado.
**Dependências de domínio:** [US-015](docs/discovery/backlog/historias.md#us-015), [US-016](docs/discovery/backlog/historias.md#us-016), [US-010](docs/discovery/backlog/historias.md#us-010)

**Critérios de aceitação:**

- **CA-01:** Dada uma missão Pendente, quando chegar o horário agendado, então seu estado muda automaticamente para Em andamento.
- **CA-02:** Quando a missão entrar em Em andamento, então a saída da nave é registrada automaticamente.
- **CA-03:** Então os estados utilizados são Pendente, Em andamento, Adiada, Concluída e Cancelada.

**Pendências vinculadas:** OPEN-019, OPEN-027
**Limites e observações:** Fuso horário, recuperação após indisponibilidade do SGA e revalidação no instante da partida estão pendentes.

**Situação de refinamento:** Requer refinamento nas questões vinculadas; critérios já definidos podem ser avaliados separadamente.

<a id="us-018"></a>
## US-018 — Concluir missão e registrar entrada

**Hierarquia:** EPIC-004 → FEAT-008 → US-018.
**História:** Como Gestor, quero informar o término da missão, para concluir seu registro e registrar a entrada da nave.

**Origem:** FR-024, FR-050.
**Regras relacionadas:** BR-013
**Dados e condições específicas:** Missão, término informado e entrada da nave.
**Dependências de domínio:** [US-017](docs/discovery/backlog/historias.md#us-017)

**Critérios de aceitação:**

- **CA-01:** Dada uma missão Em andamento com conclusão normal, quando o Gestor informar o término, então ela passa para Concluída.
- **CA-02:** Quando a missão passar para Concluída, então a entrada da nave é registrada automaticamente.
- **CA-03:** Dada missão Concluída, então o estado é definitivo.

**Pendências vinculadas:** OPEN-001, OPEN-018
**Limites e observações:** Conclusão com morte ou retornos mistos e possibilidade de nave retornada antes do fechamento administrativo não estão resolvidas.

**Situação de refinamento:** Requer refinamento nas questões vinculadas; critérios já definidos podem ser avaliados separadamente.

<a id="us-019"></a>
## US-019 — Adiar e remarcar missão

**Hierarquia:** EPIC-004 → FEAT-008 → US-019.
**História:** Como Gestor ou Supervisor, quero postergar uma missão e definir nova data, para reorganizar o planejamento mantendo o registro.

**Origem:** FR-051, FR-052, FR-053, FR-057.
**Regras relacionadas:** BR-014
**Dados e condições específicas:** Missão, estado Adiada e nova data.
**Dependências de domínio:** [US-014](docs/discovery/backlog/historias.md#us-014)

**Critérios de aceitação:**

- **CA-01:** Quando uma missão for postergada, então ela permanece em Adiada enquanto não receber nova data.
- **CA-02:** Dada missão Adiada, quando Gestor/Supervisor definir nova data, então ela retorna para Pendente mantendo o mesmo registro.
- **CA-03:** Então não se cria o estado Reagendada.

**Pendências vinculadas:** OPEN-028
**Limites e observações:** Estados de origem permitidos e revalidações na remarcação precisam ser confirmados; não tratar cancelamento como adiamento.

**Situação de refinamento:** Requer refinamento nas questões vinculadas; critérios já definidos podem ser avaliados separadamente.

<a id="us-020"></a>
## US-020 — Cancelar definitivamente uma missão

**Hierarquia:** EPIC-004 → FEAT-008 → US-020.
**História:** Como Gestor ou Supervisor, quero registrar cancelamento e motivo, para encerrar uma missão que não pode prosseguir.

**Origem:** FR-054, FR-055, FR-056.
**Regras relacionadas:** BR-011, BR-013, BR-015
**Dados e condições específicas:** Missão, responsável, motivo de indisponibilidade ou exceção.
**Dependências de domínio:** [US-014](docs/discovery/backlog/historias.md#us-014)

**Critérios de aceitação:**

- **CA-01:** Quando cancelar a missão, então o registro identifica quem cancelou e o motivo.
- **CA-02:** Dada missão Cancelada, quando tentar reativá-la ou reagendá-la, então a operação não é permitida.
- **CA-03:** Então cancelamento por indisponibilidade também é definitivo (DEC-001).

**Pendências vinculadas:** OPEN-026, OPEN-028
**Limites e observações:** Estados a partir dos quais se pode cancelar dependem de decisão. Retorno inadequado e morte não são impedimentos da pesquisa pré-missão.

**Situação de refinamento:** Requer refinamento nas questões vinculadas; critérios já definidos podem ser avaliados separadamente.

<a id="us-021"></a>
## US-021 — Notificar mudanças da missão

**Hierarquia:** EPIC-004 → FEAT-009 → US-021.
**História:** Como funcionário envolvido, quero receber notificações internas sobre mudanças relevantes, para acompanhar as missões de que participo.

**Origem:** FR-058.
**Regras relacionadas:** Condições expressas nos FR de origem e permissões transversais.
**Dados e condições específicas:** Missão, mudança e funcionários envolvidos.
**Dependências de domínio:** [US-014](docs/discovery/backlog/historias.md#us-014)

**Critérios de aceitação:**

- **CA-01:** Dada uma mudança classificada como relevante, quando ela ocorrer, então os funcionários envolvidos recebem notificação dentro do SGA.
- **CA-02:** Então a regra desta história usa o canal interno definido em DEC-003; e-mail de bloqueio pertence à US-005.

**Pendências vinculadas:** OPEN-012
**Limites e observações:** A lista de eventos relevantes, destinatários após troca de tripulação e prazo de entrega estão pendentes.

**Situação de refinamento:** Requer refinamento nas questões vinculadas; critérios já definidos podem ser avaliados separadamente.

<a id="us-022"></a>
## US-022 — Registrar retorno normal ou inadequado

**Hierarquia:** EPIC-005 → FEAT-010 → US-022.
**História:** Como Gestor, quero registrar o resultado do retorno, para manter o desfecho da missão e suas ocorrências.

**Origem:** FR-059, FR-060, FR-061, FR-084.
**Regras relacionadas:** BR-023
**Dados e condições específicas:** Humano, local de abdução, local de devolução, condição de retorno e relato.
**Dependências de domínio:** [US-017](docs/discovery/backlog/historias.md#us-017)

**Critérios de aceitação:**

- **CA-01:** Dado retorno normal, quando registrá-lo, então o resultado consta como retornado com vida.
- **CA-02:** Dado humano devolvido a local diferente do local de abdução, então o retorno é registrado como inadequado.
- **CA-03:** Dada consequência de saúde classificada como retorno inadequado, então a ocorrência é registrada; a classificação objetiva depende de OPEN-014.
- **CA-04:** Dada ocorrência fora do padrão, quando o Gestor relatá-la, então o relato narrativo fica no histórico da missão.

**Pendências vinculadas:** OPEN-014, OPEN-018
**Limites e observações:** Retornos diferentes de humanos na mesma missão e critérios de saúde dependem de refinamento.

**Situação de refinamento:** Requer refinamento nas questões vinculadas; critérios já definidos podem ser avaliados separadamente.

<a id="us-023"></a>
## US-023 — Manter advertências e punição por reincidência

**Hierarquia:** EPIC-005 → FEAT-011 → US-023.
**História:** Como Gestor, quero registrar advertências por funcionário, para acompanhar o tratamento de retornos inadequados.

**Origem:** FR-062, FR-063.
**Regras relacionadas:** BR-018
**Dados e condições específicas:** Funcionário, histórico de advertências, contador normal e punição salarial.
**Dependências de domínio:** [US-022](docs/discovery/backlog/historias.md#us-022)

**Critérios de aceitação:**

- **CA-01:** Dado um funcionário, quando registrar advertências, então seu histórico mantém os registros associados a ele.
- **CA-02:** Dada a sequência normal de advertências por retorno inadequado, então as três primeiras são advertências e a quarta está associada à punição salarial definida no levantamento.

**Pendências vinculadas:** OPEN-029
**Limites e observações:** Valor/tipo da punição, contagem por ocorrência, responsáveis e eventual reinício do contador não estão definidos; não assumir desconto automático em folha.

**Situação de refinamento:** Requer refinamento nas questões vinculadas; critérios já definidos podem ser avaliados separadamente.

<a id="us-024"></a>
## US-024 — Acompanhar correção e reincidência não corrigida

**Hierarquia:** EPIC-005 → FEAT-011 → US-024.
**História:** Como Supervisor, quero acompanhar a correção do problema, para tratar reincidências conforme a regra de advertência.

**Origem:** FR-064, FR-065.
**Regras relacionadas:** BR-018
**Dados e condições específicas:** Problema, situação de correção e advertência anterior.
**Dependências de domínio:** [US-023](docs/discovery/backlog/historias.md#us-023)

**Critérios de aceitação:**

- **CA-01:** Dado um problema registrado, então o Supervisor pode acompanhar sua correção.
- **CA-02:** Dado problema não corrigido, então a regra de negócio exige nova advertência em dobro da anterior; o teste numérico depende da fórmula a definir em OPEN-002.

**Pendências vinculadas:** OPEN-002, OPEN-029
**Limites e observações:** Não interpretar em dobro como duas advertências, dobro de salário ou dobro de pontos sem decisão.

**Situação de refinamento:** Requer refinamento nas questões vinculadas; critérios já definidos podem ser avaliados separadamente.

<a id="us-025"></a>
## US-025 — Registrar morte e análise do caso

**Hierarquia:** EPIC-006 → FEAT-012 → US-025.
**História:** Como Supervisor, quero analisar a ocorrência de morte, para subsidiar o registro do resultado pelo Gestor.

**Origem:** FR-067, FR-068, FR-069.
**Regras relacionadas:** BR-020
**Dados e condições específicas:** Humano, devolução do corpo, procedimento, envolvidos, causa e resultado.
**Dependências de domínio:** [US-017](docs/discovery/backlog/historias.md#us-017)

**Critérios de aceitação:**

- **CA-01:** Dada morte durante a missão, então o registro contempla devolução do corpo ao local da abdução.
- **CA-02:** Então o Supervisor pode analisar procedimento, humano, envolvidos e causa da morte.
- **CA-03:** Dada a análise realizada, então o Gestor pode registrar seu resultado.

**Pendências vinculadas:** OPEN-001, OPEN-018
**Limites e observações:** Não criar estado adicional da missão; não incluir ocultação ou falsificação da causa da morte.

**Situação de refinamento:** Requer refinamento nas questões vinculadas; critérios já definidos podem ser avaliados separadamente.

<a id="us-026"></a>
## US-026 — Tratar morte natural e encerrar o caso

**Hierarquia:** EPIC-006 → FEAT-012 → US-026.
**História:** Como Gestor, quero registrar advertência de cuidado após morte natural, para encerrar a análise sem alterar o contador normal.

**Origem:** FR-066, FR-070, FR-072.
**Regras relacionadas:** BR-019, BR-020
**Dados e condições específicas:** Causa natural, advertência de cuidado, resultado e encerramento do caso.
**Dependências de domínio:** [US-025](docs/discovery/backlog/historias.md#us-025), [US-023](docs/discovery/backlog/historias.md#us-023)

**Critérios de aceitação:**

- **CA-01:** Dada análise com causa natural, então a advertência específica de cuidado não integra o contador normal.
- **CA-02:** Dado resultado da análise registrado, então o caso é encerrado definitivamente.
- **CA-03:** Dado resultado ainda não registrado, então a pré-condição de encerramento do caso não está satisfeita.

**Pendências vinculadas:** OPEN-001
**Limites e observações:** Encerrar o caso não define automaticamente um novo estado nem resolve o estado da missão.

**Situação de refinamento:** Requer refinamento nas questões vinculadas; critérios já definidos podem ser avaliados separadamente.

<a id="us-027"></a>
## US-027 — Registrar punição por falha atribuível

**Hierarquia:** EPIC-006 → FEAT-012 → US-027.
**História:** Como Gestor, quero registrar a punição decorrente da análise, para documentar a responsabilização definida no caso.

**Origem:** FR-071.
**Regras relacionadas:** BR-020
**Dados e condições específicas:** Resultado da análise, envolvidos e punição aplicável.
**Dependências de domínio:** [US-025](docs/discovery/backlog/historias.md#us-025)

**Critérios de aceitação:**

- **CA-01:** Dada análise que atribua falha aos envolvidos e punição definida, quando o Gestor registrar o resultado, então a punição aplicável é registrada junto ao caso.

**Pendências vinculadas:** OPEN-013, OPEN-029
**Limites e observações:** Critérios de julgamento e punições não definidos impedem testar a escolha da punição; não presumir cálculo automático.

**Situação de refinamento:** Requer refinamento nas questões vinculadas; critérios já definidos podem ser avaliados separadamente.

<a id="us-028"></a>
## US-028 — Registrar e manter dados científicos

**Hierarquia:** EPIC-007 → FEAT-013 → US-028.
**História:** Como Cientista, quero registrar dados científicos após a abdução, para manter informações para necessidades futuras.

**Origem:** FR-073, FR-074, FR-075, FR-077.
**Regras relacionadas:** BR-021
**Dados e condições específicas:** Humano, altura, peso, cor, etnia, DNA e tipo sanguíneo.
**Dependências de domínio:** [US-011](docs/discovery/backlog/historias.md#us-011), [US-017](docs/discovery/backlog/historias.md#us-017)

**Critérios de aceitação:**

- **CA-01:** Dada abdução realizada, quando o Cientista registrar dados científicos, então os campos previstos em FR-074 podem ser mantidos para consulta futura.
- **CA-02:** Dado Cientista autenticado, quando alterar dados científicos, então a alteração é permitida.
- **CA-03:** Dado usuário que não seja Cientista, inclusive Gestor ou Supervisor, quando tentar alterar esses dados, então a alteração é impedida por BR-021.

**Pendências vinculadas:** OPEN-010, OPEN-023
**Limites e observações:** Unidades, formatos e obrigatoriedade dos campos não estão definidos. Não inventar workflow de progresso científico para OPEN-010.

**Situação de refinamento:** Requer refinamento nas questões vinculadas; critérios já definidos podem ser avaliados separadamente.

<a id="us-029"></a>
## US-029 — Consultar dados científicos com restrição

**Hierarquia:** EPIC-007 → FEAT-013 → US-029.
**História:** Como Cientista, Gestor ou Supervisor, quero consultar dados científicos, para acessar informações compatíveis com minhas atribuições.

**Origem:** FR-076.
**Regras relacionadas:** Condições expressas nos FR de origem e permissões transversais.
**Dados e condições específicas:** Dados científicos e perfil do funcionário.
**Dependências de domínio:** [US-028](docs/discovery/backlog/historias.md#us-028)

**Critérios de aceitação:**

- **CA-01:** Dado Cientista, Gestor ou Supervisor autenticado, quando consultar dados científicos existentes, então a consulta é permitida.
- **CA-02:** Dado Piloto, Abduzidor ou Pesquisador, quando tentar consultar os dados científicos, então a consulta é impedida.

**Pendências vinculadas:** OPEN-016
**Limites e observações:** Evitar ampliar acesso por meio do histórico geral; a delimitação do conteúdo depende de OPEN-016.

**Situação de refinamento:** Requer refinamento nas questões vinculadas; critérios já definidos podem ser avaliados separadamente.

<a id="us-030"></a>
## US-030 — Excluir dados científicos obsoletos

**Hierarquia:** EPIC-007 → FEAT-014 → US-030.
**História:** Como Gestor ou Supervisor, quero determinar a obsolescência dos dados, para retirar informações consideradas obsoletas.

**Origem:** FR-078, FR-079, FR-080.
**Regras relacionadas:** BR-022
**Dados e condições específicas:** Dados científicos e decisão de obsolescência.
**Dependências de domínio:** [US-028](docs/discovery/backlog/historias.md#us-028)

**Critérios de aceitação:**

- **CA-01:** Dado Gestor ou Supervisor, então pode determinar que dados científicos são obsoletos.
- **CA-02:** Dada a decisão de obsolescência, então os dados são excluídos; o prazo de imediatamente depende de OPEN-006.
- **CA-03:** Então não se mantém registro específico dessa exclusão, conforme FR-080; a relação com a auditoria exige delimitação em OPEN-003.

**Pendências vinculadas:** OPEN-003, OPEN-006, OPEN-030
**Limites e observações:** Granularidade da exclusão e relação com valores preservados na auditoria não estão definidas.

**Situação de refinamento:** Requer refinamento nas questões vinculadas; critérios já definidos podem ser avaliados separadamente.

<a id="us-031"></a>
## US-031 — Consultar histórico de missões

**Hierarquia:** EPIC-008 → FEAT-015 → US-031.
**História:** Como funcionário, quero consultar o histórico das missões, para acompanhar operações e ocorrências.

**Origem:** FR-081, FR-082.
**Regras relacionadas:** BR-023
**Dados e condições específicas:** Histórico de missões e ocorrências. Pré-condição: funcionário autenticado.
**Dependências de domínio:** [US-014](docs/discovery/backlog/historias.md#us-014)

**Critérios de aceitação:**

- **CA-01:** Dado qualquer perfil de funcionário autenticado, quando consultar o histórico, então a consulta é permitida.
- **CA-02:** Então o histórico contém os registros de missões e ocorrências previstas no Discovery.
- **CA-03:** Então o histórico satisfaz o registro da missão sem exigir relatório separado.

**Pendências vinculadas:** OPEN-016
**Limites e observações:** Histórico completo deve ser delimitado perante dados científicos restritos e auditoria administrativa.

**Situação de refinamento:** Requer refinamento nas questões vinculadas; critérios já definidos podem ser avaliados separadamente.

<a id="us-032"></a>
## US-032 — Corrigir histórico com permissão administrativa

**Hierarquia:** EPIC-008 → FEAT-015 → US-032.
**História:** Como Gestor ou Supervisor, quero alterar o histórico das missões, para corrigir seus registros conforme minha permissão.

**Origem:** FR-083.
**Regras relacionadas:** BR-023
**Dados e condições específicas:** Histórico e dados alterados.
**Dependências de domínio:** [US-031](docs/discovery/backlog/historias.md#us-031)

**Critérios de aceitação:**

- **CA-01:** Dado Gestor ou Supervisor, quando alterar o histórico, então a alteração é permitida.
- **CA-02:** Dado outro perfil de funcionário, quando tentar alterar o histórico, então a alteração é impedida.
- **CA-03:** Então alteração de histórico não concede permissão para alterar registros imutáveis de auditoria (US-035).

**Pendências vinculadas:** Nenhuma pendência específica vinculada; validação do grupo e requisitos transversais continuam necessários.
**Limites e observações:** Eventos de alteração do histórico abrangidos pela auditoria devem constar no catálogo de alterações relevantes.

**Situação de refinamento:** Critérios específicos elaborados; aguarda validação do grupo.

<a id="us-033"></a>
## US-033 — Registrar e reter acessos

**Hierarquia:** EPIC-009 → FEAT-016 → US-033.
**História:** Como Gestor ou Supervisor, quero dispor dos registros de tentativas de acesso, para acompanhar a autenticação no período definido.

**Origem:** FR-014, FR-085.
**Regras relacionadas:** Condições expressas nos FR de origem e permissões transversais.
**Dados e condições específicas:** Usuário, data/hora e resultado da tentativa.
**Dependências de domínio:** [US-003](docs/discovery/backlog/historias.md#us-003)

**Critérios de aceitação:**

- **CA-01:** Dada tentativa bem-sucedida, então se registra usuário, data/hora e resultado.
- **CA-02:** Dada tentativa malsucedida, então também se registra o resultado e os dados de identificação disponíveis.
- **CA-03:** Então os registros de acesso têm retenção de 2 meses; cálculo do prazo e tratamento após seu término dependem de OPEN-031.

**Pendências vinculadas:** OPEN-031
**Limites e observações:** Acesso administrativo a esses registros e login inexistente precisam de detalhamento; não inventar retenção permanente.

**Situação de refinamento:** Requer refinamento nas questões vinculadas; critérios já definidos podem ser avaliados separadamente.

<a id="us-034"></a>
## US-034 — Registrar alterações e seus valores

**Hierarquia:** EPIC-009 → FEAT-016 → US-034.
**História:** Como Gestor ou Supervisor, quero dispor de trilha das alterações relevantes, para identificar autoria e mudanças nos dados.

**Origem:** FR-015, FR-086, FR-087.
**Regras relacionadas:** Condições expressas nos FR de origem e permissões transversais.
**Dados e condições específicas:** Usuário, data/hora, registro/dado, valor anterior e novo valor.
**Dependências de domínio:** [US-001](docs/discovery/backlog/historias.md#us-001), [US-008](docs/discovery/backlog/historias.md#us-008), [US-014](docs/discovery/backlog/historias.md#us-014), [US-028](docs/discovery/backlog/historias.md#us-028)

**Critérios de aceitação:**

- **CA-01:** Dada alteração classificada como relevante em funcionário, nave, missão ou dados científicos, então a auditoria registra usuário, data/hora, registro/dado, valor anterior e novo valor.
- **CA-02:** Então os registros de alteração têm retenção de 6 meses.

**Pendências vinculadas:** OPEN-003, OPEN-030, OPEN-031, OPEN-032
**Limites e observações:** Catálogo de eventos, tratamento de credenciais e dados sensíveis e convivência com exclusão científica dependem de refinamento.

**Situação de refinamento:** Requer refinamento nas questões vinculadas; critérios já definidos podem ser avaliados separadamente.

<a id="us-035"></a>
## US-035 — Consultar auditoria imutável e registrar consultas

**Hierarquia:** EPIC-009 → FEAT-017 → US-035.
**História:** Como Gestor ou Supervisor, quero consultar a auditoria com rastreamento, para fiscalizar alterações sem modificar suas evidências.

**Origem:** FR-016, FR-017, FR-018, FR-088.
**Regras relacionadas:** Condições expressas nos FR de origem e permissões transversais.
**Dados e condições específicas:** Registro de auditoria, usuário consultante, data/hora e registro consultado.
**Dependências de domínio:** [US-034](docs/discovery/backlog/historias.md#us-034)

**Critérios de aceitação:**

- **CA-01:** Dado Gestor ou Supervisor, quando consultar registros de alteração, então a consulta é permitida; para os demais perfis é impedida.
- **CA-02:** Dado qualquer perfil, quando tentar editar ou excluir um registro de alteração, então a operação não é permitida.
- **CA-03:** Dada consulta de auditoria, então se registra quem consultou, data/hora e qual registro foi consultado.

**Pendências vinculadas:** OPEN-031
**Limites e observações:** FR-018 e FR-088 são tratados em uma história. Retenção do registro de consulta e expiração administrada versus exclusão por usuário precisam ser esclarecidas.

**Situação de refinamento:** Requer refinamento nas questões vinculadas; critérios já definidos podem ser avaliados separadamente.


</details>

<details>
<summary><strong>Requisitos não funcionais e permissões</strong></summary>

# Requisitos transversais e critérios de qualidade

Etapa 03 — Backlog. Os IDs NFR originais foram preservados. Não há arquitetura, tecnologia ou infraestrutura definida aqui.

| ID | Compromisso da fonte | Critério verificável no backlog | Pendência / aplicação |
|---|---|---|---|
| NFR-001 | Disponibilidade 24 horas por dia, 7 dias por semana. | A cobertura operacional requerida abrange todos os dias e horários. Medição de conformidade ainda não pode ser concluída. | OPEN-033: janela de medição, tolerância e manutenção. Nenhum percentual foi inventado. Aplica-se ao sistema inteiro. |
| NFR-002 | Autenticação para acesso às informações de missões. | Tentar consultar missão sem sessão autenticada deve impedir acesso; credenciais válidas de conta habilitada permitem autenticação. | US-003; aplicar também aos fluxos de missão e histórico. |
| NFR-003 | Prevenção contra perda ou alteração indevida. | Requisito ainda não possui critério integral de aceitação: faltam metas de perda e recuperação. Testes de permissão cobrem apenas parte da intenção. | OPEN-004; não declarar atendido por existir auditoria ou bloqueio de acesso. |
| NFR-004 | Respeito às permissões definidas. | Executar cada operação com perfil autorizado e não autorizado; conferir concessão/negação. Cientistas alteram dados científicos; demais perfis não. Auditoria de alteração é restrita a Gestor/Supervisor. | OPEN-016/017 delimitam ambiguidades; US-002, US-028, US-029, US-031, US-032, US-035. |
| NFR-005 | Acessos e alterações registrados e retidos. | Registrar acesso aceito/negado; verificar autoria, data/hora e resultado. Para alteração relevante, verificar dado, valor anterior e novo. Retenção declarada: 2 meses para acesso e 6 meses para alteração. | US-033 a US-035; OPEN-003/030/031/032 impedem fechar todos os testes de retenção, exclusão e cobertura. |

## Matriz de permissões explicitamente consolidada

| Operação | Permitido na fonte | Limite / observação |
|---|---|---|
| Cadastrar/alterar funcionários e credenciais iniciais | Gestor e Supervisor | Login único. Validações restantes em OPEN-023. |
| Inativar/reativar funcionário | Gestor e Supervisor | Sem excluir cadastro; novas credenciais na reativação. |
| Autenticar | Funcionário habilitado | Abrange os perfis operacionais; conta inativa/bloqueada não acessa. |
| Alterar/recuperar senha | Mediante solicitação e aprovação de Gestor/Supervisor | Executor e canal não definidos; OPEN-022. |
| Cadastrar/alterar naves e manutenção | Gestor e Supervisor | Naves em manutenção não podem ser usadas. |
| Cadastrar/consultar humanos | Gestor e Supervisor na especificação | Não ampliar a outros perfis sem validação. |
| Registrar pesquisa pré-missão | Pesquisador | Avaliação por Gestor/Supervisor; decisão de prosseguimento atribuída ao Gestor. |
| Definir missão e informar término | Gestor explicitamente citado | Alcance equivalente do Supervisor a confirmar em OPEN-017. |
| Definir nova data de missão Adiada | Gestor e Supervisor | Retorna a Pendente com mesmo registro. |
| Analisar morte / registrar resultado | Supervisor / Gestor | Atribuições específicas e equivalência administrativa em OPEN-017. |
| Registrar/alterar dados científicos | Cientista | BR-021 restringe alteração mesmo diante de BR-001. |
| Consultar dados científicos | Cientista, Gestor e Supervisor | Demais perfis não consultam. |
| Determinar obsolescência científica | Gestor e Supervisor | Exclusão segue decisão; escopo e prazo pendentes. |
| Consultar histórico de missões | Todos os funcionários | Conteúdo diante de dados restritos em OPEN-016. |
| Alterar histórico | Gestor e Supervisor | Não significa alterar auditoria. |
| Consultar auditoria de alterações | Gestor e Supervisor | Registrar a consulta; ninguém edita/exclui manualmente a trilha. |

## Orientação para revisão dos critérios

- Critérios derivados dos FR são cenários de aceitação, não resultados de testes executados em um sistema.
- Critérios numéricos já decididos: cinco falhas consecutivas, bloqueio de quinze minutos, ocupação igual/maior que capacidade e retenções declaradas.
- Critérios que citam uma classificação, fórmula ou horário ainda aberto não estão prontos para aprovação integral.
- Não incluir métricas inventadas de tempo de resposta, número de usuários, disponibilidade percentual ou recuperação.
- O início automático e a entrada/saída automáticas de nave mantêm o comportamento definido; não especificam mecanismo de execução.


</details>

<details>
<summary><strong>Questões abertas, revisão e decisões</strong></summary>

# Questões abertas e revisão do backlog

Etapa 03 — revisão de consistência necessária à organização das histórias. Não substitui a auditoria completa da etapa 04.

Os IDs OPEN-001 a OPEN-015 vêm da especificação v1.1 e não foram renumerados. OPEN-016 a OPEN-033 são lacunas identificadas na elaboração do backlog, ainda sem decisão do grupo. Severidade representa impacto no refinamento, não prioridade aprovada de produto.

## Pendências herdadas

| ID | Texto da fonte | Tratamento nesta etapa |
|---|---|---|
| OPEN-001 | Não foi definido um estado específico da missão durante a análise de morte. Não criar novo status sem decisão. | Aberta. Não inventar estado da missão durante análise de morte. |
| OPEN-002 | “Nova advertência em dobro” não possui fórmula numérica detalhada. | Aberta; bloqueia critério numérico da regra em dobro. |
| OPEN-003 | Auditoria de exclusão de dados científicos não foi detalhada; permanece a decisão explícita de não manter registro específico da exclusão. | Decisão FR-080 preservada; falta delimitar relação com auditoria de alterações. |
| OPEN-004 | NFR-003 não possui métrica verificável para “prevenção contra perda ou alteração indevida”. Definir critério mensurável antes de considerar o NFR plenamente especificado. | Aberta; NFR-003 ainda não é plenamente testável. |
| OPEN-005 | FR-013 usa “final do dia de trabalho”, mas não define horário ou regra objetiva para encerramento automático da sessão. | Aberta; impede determinar o instante do encerramento de sessão. |
| OPEN-006 | FR-079 usa “imediatamente” para exclusão de dados obsoletos, sem limite temporal verificável. | Aberta; exclusão definida, prazo verificável pendente. |
| OPEN-007 | O levantamento não definiu claramente a duração de uma missão, embora o conflito de funcionários use o intervalo entre início e término. | Parcialmente esclarecida por DEC-004 e conversa: início/término delimitam conflitos. Resta término previsto no agendamento versus término real informado pelo Gestor. |
| OPEN-008 | O levantamento não definiu regra operacional para determinar disponibilidade de funcionário além da condição de ativo/inativo. | Aberta quanto à disponibilidade além de ativo/inativo e sobreposição. |
| OPEN-009 | O levantamento não definiu como medir quilometragem/autonomia da nave nem a unidade/critério operacional além do valor cadastrado. | Parcialmente esclarecida por DEC-005: quilômetros e percurso completo definidos; origem da distância/medição ainda pendente. Não reabrir a decisão de ida e volta. |
| OPEN-010 | O levantamento não definiu fluxo formal de etapas/status para o progresso da pesquisa científica. | Nenhum workflow de progresso definido; manter fora das histórias até necessidade confirmada, sem criar novos estados. |
| OPEN-011 | O levantamento não definiu fórmula/critério para calcular “locais mais calmos” na pesquisa pré-missão. | Pesquisa humana de localização confirmada; critério de seleção ainda não detalhado. Não criar fórmula automática. |
| OPEN-012 | O levantamento não detalhou quais mudanças de missão são “relevantes” para disparo de notificações internas. | Canal interno e envolvidos definidos; eventos relevantes ainda pendentes. |
| OPEN-013 | O tratamento de punições por falha atribuível em caso de morte não define critérios objetivos de julgamento. | Aberta; não inventar julgamento ou punição. |
| OPEN-014 | O termo “consequência de saúde” no retorno inadequado não foi operacionalizado em critérios de classificação. | Aberta para classificação; local incorreto já é critério verificável. |
| OPEN-015 | O levantamento contém terminologia variável para a função operacional: “Abduzidor” no levantamento consolidado e “Abdutor” no Documento Base. A terminologia vigente do consolidado é “Abduzidor”. | Terminologia resolvida na própria fonte: adotar Abduzidor. Manter ID por rastreabilidade, sem repetir pergunta. |

## Pendências identificadas na transformação em backlog

| ID | Lacuna | Origem | Decisão ainda necessária | Severidade |
|---|---|---|---|---|
| OPEN-016 | Delimitar o histórico geral diante dos dados científicos e da auditoria restritos. | FR-076, FR-082, FR-016 | Definir quais informações constam no histórico visível a todos sem ampliar as permissões de consulta. | Alta |
| OPEN-017 | Explicitar a abrangência dos poderes iguais de Gestor e Supervisor. | BR-001, FR-038, FR-050, FR-069, BR-021 | Confirmar a matriz administrativa; manter a exceção explícita de que somente Cientistas alteram dados científicos. | Alta |
| OPEN-018 | Definir retorno e encerramento em missões com vários humanos. | FR-046, FR-059 a FR-072 | Distinguir resultado por humano, retorno da nave, fechamento da missão e encerramento do caso de morte. | Alta |
| OPEN-019 | Tratar indisponibilidade surgida depois do agendamento. | FR-003, FR-012, FR-022, FR-049 | Definir efeito de inativação ou manutenção sobre missões pendentes/em andamento e revalidação da partida. | Alta |
| OPEN-020 | Detalhar a sequência de tentativas de autenticação. | FR-007, FR-008 | Definir reinício do contador, efeito de sucesso e efeito de tentativas durante bloqueio. | Média |
| OPEN-021 | Detalhar alerta crítico por e-mail e dentro do SGA. | FR-009 | Definir destinatários, origem dos e-mails, prazo verificável e tratamento de falha; o canal e-mail já consta na fonte. | Média |
| OPEN-022 | Completar o procedimento de troca e recuperação de senha. | FR-010, FR-011 | Definir canal de solicitação, executor após aprovação e forma de entrega da nova credencial. | Média |
| OPEN-023 | Definir validações dos dados cadastrais e científicos. | FR-001, FR-019, FR-028, FR-038, FR-074 | Definir identificadores, campos obrigatórios, formatos e limites necessários aos testes, sem inventar escalas ou unidades. | Média |
| OPEN-024 | Definir fronteiras temporais e numéricas do agendamento. | FR-027, FR-030, FR-040, FR-042 | Esclarecer missão que inicia no exato término da anterior, autonomia igual ao percurso e conflitos de nave. | Alta |
| OPEN-025 | Definir suficiência da pesquisa em missões com vários humanos. | FR-031, FR-032, FR-046 | Esclarecer cobertura por humano, conclusão da pesquisa e possibilidade de reutilização. | Alta |
| OPEN-026 | Definir cancelamento por relevância global antes do agendamento. | FR-036, FR-039, FR-046 | Esclarecer qual registro é cancelado antes de agendar e efeito sobre uma missão com vários humanos. | Alta |
| OPEN-027 | Definir referência temporal e início automático após interrupção. | FR-049 | Esclarecer fuso/referência de horário e comportamento se o SGA não estiver disponível no instante previsto. | Média |
| OPEN-028 | Completar transições permitidas e remarcação. | FR-048, FR-051 a FR-057 | Definir estados de origem de adiamento/cancelamento e validações ao informar nova data. Cancelamento definitivo permanece decidido. | Alta |
| OPEN-029 | Completar contagem de advertências e punição salarial. | FR-062 a FR-065, FR-071 | Definir atribuição aos envolvidos, contagem, reinício e natureza/valor da punição. Não presumir integração com folha. | Alta |
| OPEN-030 | Delimitar exclusão científica e dados preservados em auditoria. | FR-075, FR-079, FR-080, FR-087 | Definir granularidade da exclusão e tratamento dos valores científicos/credenciais na trilha de alteração. | Alta |
| OPEN-031 | Detalhar retenção e expiração de auditoria. | FR-017, FR-018, FR-085, FR-086, FR-088 | Definir cálculo de meses, tratamento após prazo, retenção das consultas, acesso a tentativas e distinção entre expiração e exclusão por usuário. | Média |
| OPEN-032 | Definir quais alterações são relevantes para auditoria. | FR-015, FR-087 | Enumerar os eventos abrangidos, inclusive alterações no histórico e credenciais, sem registrar valores sensíveis por inferência. | Média |
| OPEN-033 | Tornar verificável a disponibilidade 24×7. | NFR-001 | Definir janela de medição, tolerância e manutenção; não inventar percentual. | Média |

## Duplicidades agrupadas sem apagar requisitos

| Requisitos | Organização adotada |
|---|---|
| FR-018 e FR-088 | US-035 reúne o registro de consulta à auditoria; ambos os IDs permanecem rastreáveis. |
| FR-061 e FR-084 | US-022 reúne o relato narrativo e sua presença no histórico. |
| FR-066 e FR-070 | US-026 reúne advertência de cuidado por morte natural, fora do contador normal. |
| FR-025 e FR-026 | US-010 reúne origem e retorno ao Estacionamento Alien. |
| FR-052, FR-053 e FR-057 | US-019 reúne remarcação da missão Adiada, sem criar estado Reagendada. |
| FR-015 e FR-087; FR-007 e FR-008 | Detalhes complementares agrupados, respectivamente, em US-034 e US-004. |

## Conflitos e ambiguidades relevantes

- **Cancelamento × reagendamento:** resolvido por DEC-001. Missão Cancelada não pode voltar a Pendente; missão Adiada pode.
- **Exceções antes e depois da missão:** DEC-002 diferencia relevância global de retorno inadequado/morte. Não cancelar preventivamente por uma ocorrência futura.
- **Notificação interna × e-mail:** não são regras mutuamente exclusivas. DEC-003/FR-058 tratam da missão; FR-009 exige os dois canais para bloqueio de acesso. O catálogo de integrações do DOCX não descreve esse envio de e-mail; OPEN-021 registra o detalhamento necessário.
- **Supervisor com poderes iguais × atribuições específicas:** BR-001 convive com FR que citam somente Gestor e com BR-021, que reserva alterações científicas aos Cientistas. OPEN-017 pede delimitação sem remover a restrição explícita.
- **Histórico completo × dados restritos:** OPEN-016 impede inferir que qualquer funcionário pode acessar DNA ou auditoria pelo histórico.
- **Dados científicos excluídos × valores anteriores auditados:** OPEN-003/OPEN-030 preservam a decisão de não manter registro específico de exclusão, mas exigem esclarecer quais dados permanecem na auditoria.
- **Auditoria imutável × retenção finita:** OPEN-031 distingue proibição de exclusão por usuário do tratamento após a retenção, que ainda não foi definido.
- **Atores/dados genéricos da especificação:** por exemplo, FR-005 lista apenas Gestor/Supervisor, e FR-038 lista dados de nave apesar de tratar da missão. As histórias usam os atores e dados descritos no próprio comportamento e no contexto consolidado; não concedem novas permissões.
- **Critérios genéricos:** vários FR dizem apenas verificar o comportamento. As histórias explicitam cenários observáveis; onde falta decisão, o critério continua condicionado ao OPEN.
- **Mais de um humano:** FR-046 torna necessário diferenciar pesquisa, relevância global e resultado de retorno por participante (OPEN-018, OPEN-025, OPEN-026).

## Decisões preservadas

| ID | Decisão da especificação v1.1 |
|---|---|
| DEC-001 | Cancelamento é definitivo e não permite reativação/reagendamento, substituindo a regra anterior que permitia reagendamento após cancelamento por indisponibilidade. |
| DEC-002 | Retorno inadequado e morte são ocorrências/exceções operacionais durante/depois da execução; não equivalem à relevância global na avaliação pré-missão. |
| DEC-003 | Notificações de missão são internas ao SGA no escopo acadêmico. |
| DEC-004 | Conflito de funcionários é definido pelo intervalo entre início e término da missão. |
| DEC-005 | A nave parte e retorna ao Estacionamento Alien; autonomia considera o percurso completo. |
| DEC-006 | Na reativação de funcionário são criadas novas credenciais; credenciais iniciais podem ser definidas por Gestor/Supervisor. |
| DEC-007 | A consolidação mantém apenas requisitos definidos; decisões técnicas de implementação ficam fora do Discovery. |

## Limites da prontidão

Não há metas definidas de desempenho, volume de usuários/missões ou privacidade/retensão dos dados de negócio além dos pontos descritos. Esta ausência não autoriza criar números ou funcionalidades. Na etapa 04, o grupo pode avaliar sua relevância proporcional ao trabalho acadêmico.

Não é necessário responder a todas as lacunas em uma sessão. A entrevista deve seguir uma pergunta por vez, priorizando decisões que mudam permissões, agendamento ou critérios de aceitação. Não reabrir escolhas já consolidadas.


</details>

<details>
<summary><strong>Catálogo de requisitos, regras e rastreabilidade</strong></summary>

# Rastreabilidade do backlog

Esta matriz associa cada FR a uma história principal. O catálogo preserva o texto de origem, incluindo termos ainda abertos. Agrupar FR não elimina seus identificadores.

## Requisitos funcionais → histórias

| ID | Requisito da especificação v1.1 | História principal |
|---|---|---|
| FR-001 | Permitir o cadastro e alteração de funcionários pelo Gestor ou Supervisor. | [US-001](docs/discovery/backlog/historias.md#us-001) |
| FR-002 | Manter funcionário desligado/inativo sem excluí-lo do sistema. | [US-002](docs/discovery/backlog/historias.md#us-002) |
| FR-003 | Impedir a seleção de funcionário inativo para novas missões. | [US-002](docs/discovery/backlog/historias.md#us-002) |
| FR-004 | Permitir a reativação de funcionário inativo pelo Gestor ou Supervisor, sem condição ou justificativa adicional. | [US-002](docs/discovery/backlog/historias.md#us-002) |
| FR-005 | Permitir autenticação por login/usuário e senha. | [US-003](docs/discovery/backlog/historias.md#us-003) |
| FR-006 | Garantir que o login seja único no SGA. | [US-001](docs/discovery/backlog/historias.md#us-001) |
| FR-007 | Bloquear temporariamente a conta após 5 tentativas consecutivas de senha incorreta. | [US-004](docs/discovery/backlog/historias.md#us-004) |
| FR-008 | Manter o bloqueio por 15 minutos ou até aprovação do Gestor/Supervisor, o que ocorrer primeiro. | [US-004](docs/discovery/backlog/historias.md#us-004) |
| FR-009 | Alertar imediatamente Gestor e Supervisor sobre o bloqueio por tentativas incorretas, dentro do SGA e por e-mail, indicando caráter crítico/possível risco de intrusão. | [US-005](docs/discovery/backlog/historias.md#us-005) |
| FR-010 | Permitir alteração de senha somente mediante solicitação do funcionário e aprovação do Gestor ou Supervisor. | [US-006](docs/discovery/backlog/historias.md#us-006) |
| FR-011 | Aplicar o mesmo procedimento de aprovação para esquecimento de senha. | [US-006](docs/discovery/backlog/historias.md#us-006) |
| FR-012 | Bloquear imediatamente o acesso de funcionário inativo/desligado. | [US-002](docs/discovery/backlog/historias.md#us-002) |
| FR-013 | Encerrar automaticamente a sessão ao final do dia de trabalho; as credenciais são exigidas novamente no próximo acesso. | [US-007](docs/discovery/backlog/historias.md#us-007) |
| FR-014 | Registrar tentativas de acesso bem-sucedidas e malsucedidas. | [US-033](docs/discovery/backlog/historias.md#us-033) |
| FR-015 | Registrar alterações relevantes de dados de funcionários, naves, missões e dados científicos. | [US-034](docs/discovery/backlog/historias.md#us-034) |
| FR-016 | Permitir consulta dos registros de alteração somente ao Gestor e Supervisor. | [US-035](docs/discovery/backlog/historias.md#us-035) |
| FR-017 | Manter registros de alteração somente para leitura, sem permitir sua alteração ou exclusão. | [US-035](docs/discovery/backlog/historias.md#us-035) |
| FR-018 | Registrar quem consultou registros de auditoria, data/hora e qual registro foi consultado. | [US-035](docs/discovery/backlog/historias.md#us-035) |
| FR-019 | Permitir cadastrar e alterar dados de naves. | [US-008](docs/discovery/backlog/historias.md#us-008) |
| FR-020 | Manter para a nave os dados definidos: capacidade total, quilômetros que pode voar e status operacional. | [US-008](docs/discovery/backlog/historias.md#us-008) |
| FR-021 | Permitir alterar o status operacional entre disponível e manutenção pelo Gestor ou Supervisor. | [US-009](docs/discovery/backlog/historias.md#us-009) |
| FR-022 | Impedir a utilização de nave em manutenção em uma missão. | [US-009](docs/discovery/backlog/historias.md#us-009) |
| FR-023 | Registrar automaticamente a saída da nave quando a missão entrar em Em andamento. | [US-017](docs/discovery/backlog/historias.md#us-017) |
| FR-024 | Registrar automaticamente a entrada da nave quando a missão passar para Concluída. | [US-018](docs/discovery/backlog/historias.md#us-018) |
| FR-025 | Considerar o Estacionamento Alien como ponto de partida das naves. | [US-010](docs/discovery/backlog/historias.md#us-010) |
| FR-026 | Considerar o Estacionamento Alien como destino de retorno das naves. | [US-010](docs/discovery/backlog/historias.md#us-010) |
| FR-027 | Verificar a autonomia da nave para o percurso completo da missão, incluindo ida e retorno. | [US-010](docs/discovery/backlog/historias.md#us-010) |
| FR-028 | Permitir cadastrar e consultar humanos. | [US-011](docs/discovery/backlog/historias.md#us-011) |
| FR-029 | Manter no cadastro do humano nome, localização, idade e popularidade. | [US-011](docs/discovery/backlog/historias.md#us-011) |
| FR-030 | Impedir que um mesmo humano participe de mais de uma missão simultaneamente. | [US-015](docs/discovery/backlog/historias.md#us-015) |
| FR-031 | Exigir pesquisa pré-missão antes do agendamento de toda missão. | [US-012](docs/discovery/backlog/historias.md#us-012) |
| FR-032 | Permitir ao Pesquisador registrar pesquisa sobre idade, patrimônio/riqueza, emprego, fonte de renda, popularidade, interações sociais e informações gerais da vida. | [US-012](docs/discovery/backlog/historias.md#us-012) |
| FR-033 | Permitir ao Pesquisador registrar pesquisa de localização para identificar locais mais calmos. | [US-012](docs/discovery/backlog/historias.md#us-012) |
| FR-034 | Permitir que Gestor e Supervisor avaliem as informações da pesquisa. | [US-013](docs/discovery/backlog/historias.md#us-013) |
| FR-035 | Não realizar automaticamente a classificação de exceções; a identificação cabe à avaliação humana de Gestor/Supervisor. | [US-013](docs/discovery/backlog/historias.md#us-013) |
| FR-036 | Impedir a prossecução da missão quando for identificada relevância em escala global, resultando em cancelamento definitivo. | [US-013](docs/discovery/backlog/historias.md#us-013) |
| FR-037 | Quando não houver exceção relevante para impedir a missão, permitir que o Gestor decida se a abdução prosseguirá. | [US-013](docs/discovery/backlog/historias.md#us-013) |
| FR-038 | Permitir ao Gestor definir humano, nave, tripulação, local, data e horário da missão. | [US-014](docs/discovery/backlog/historias.md#us-014) |
| FR-039 | Permitir ao Gestor iniciar/registrar a solicitação da missão. | [US-014](docs/discovery/backlog/historias.md#us-014) |
| FR-040 | Verificar disponibilidade de nave e funcionários antes do agendamento. | [US-015](docs/discovery/backlog/historias.md#us-015) |
| FR-041 | Bloquear o agendamento quando houver conflito ou indisponibilidade. | [US-015](docs/discovery/backlog/historias.md#us-015) |
| FR-042 | Impedir que funcionário participe de duas missões com horários sobrepostos. | [US-015](docs/discovery/backlog/historias.md#us-015) |
| FR-043 | Exigir pelo menos um Piloto e um Abduzidor na tripulação. | [US-014](docs/discovery/backlog/historias.md#us-014) |
| FR-044 | Considerar apenas funcionários ativos e disponíveis na seleção da tripulação. | [US-014](docs/discovery/backlog/historias.md#us-014) |
| FR-045 | Considerar tripulação e humanos no cálculo da capacidade da nave. | [US-016](docs/discovery/backlog/historias.md#us-016) |
| FR-046 | Permitir mais de um humano na mesma missão, desde que respeitada a capacidade da nave. | [US-016](docs/discovery/backlog/historias.md#us-016) |
| FR-047 | Bloquear agendamento quando a capacidade da nave for excedida. | [US-016](docs/discovery/backlog/historias.md#us-016) |
| FR-048 | Manter os estados de missão: Pendente, Em andamento, Adiada, Concluída e Cancelada. | [US-017](docs/discovery/backlog/historias.md#us-017) |
| FR-049 | Alterar automaticamente Pendente para Em andamento no horário agendado. | [US-017](docs/discovery/backlog/historias.md#us-017) |
| FR-050 | Permitir ao Gestor informar o término da missão, levando-a para Concluída. | [US-018](docs/discovery/backlog/historias.md#us-018) |
| FR-051 | Permitir postergar uma missão. | [US-019](docs/discovery/backlog/historias.md#us-019) |
| FR-052 | Manter missão Adiada até que Gestor ou Supervisor defina nova data. | [US-019](docs/discovery/backlog/historias.md#us-019) |
| FR-053 | Retornar a missão Adiada para Pendente quando nova data for definida. | [US-019](docs/discovery/backlog/historias.md#us-019) |
| FR-054 | Permitir cancelamento por indisponibilidade ou exceção. | [US-020](docs/discovery/backlog/historias.md#us-020) |
| FR-055 | Registrar quem cancelou e o motivo do cancelamento. | [US-020](docs/discovery/backlog/historias.md#us-020) |
| FR-056 | Considerar cancelamento definitivo, sem reativação ou reagendamento. | [US-020](docs/discovery/backlog/historias.md#us-020) |
| FR-057 | Não criar um status chamado Reagendada; uma nova data de missão postergada mantém o mesmo registro e retorna a Pendente. | [US-019](docs/discovery/backlog/historias.md#us-019) |
| FR-058 | Enviar notificações internas aos funcionários envolvidos quando houver mudanças relevantes da missão. | [US-021](docs/discovery/backlog/historias.md#us-021) |
| FR-059 | Registrar retorno normal como 'retornado com vida'. | [US-022](docs/discovery/backlog/historias.md#us-022) |
| FR-060 | Registrar retorno inadequado quando o humano não for devolvido ao local da abdução ou sofrer consequência de saúde no retorno. | [US-022](docs/discovery/backlog/historias.md#us-022) |
| FR-061 | Registrar ocorrências fora do padrão no histórico da missão por meio de relato narrativo do Gestor. | [US-022](docs/discovery/backlog/historias.md#us-022) |
| FR-062 | Manter histórico de advertências por funcionário. | [US-023](docs/discovery/backlog/historias.md#us-023) |
| FR-063 | Aplicar três advertências para retorno inadequado e punição salarial na quarta advertência. | [US-023](docs/discovery/backlog/historias.md#us-023) |
| FR-064 | Permitir ao Supervisor acompanhar a correção do problema. | [US-024](docs/discovery/backlog/historias.md#us-024) |
| FR-065 | Quando o problema não for corrigido, considerar a nova advertência em dobro em relação à anterior. | [US-024](docs/discovery/backlog/historias.md#us-024) |
| FR-066 | Não incluir advertência relacionada a morte natural no contador normal de advertências. | [US-026](docs/discovery/backlog/historias.md#us-026) |
| FR-067 | Registrar a devolução do corpo ao local da abdução em caso de morte. | [US-025](docs/discovery/backlog/historias.md#us-025) |
| FR-068 | Permitir ao Supervisor analisar o procedimento, o humano, as pessoas envolvidas e a causa da morte. | [US-025](docs/discovery/backlog/historias.md#us-025) |
| FR-069 | Permitir ao Gestor registrar o resultado da análise. | [US-025](docs/discovery/backlog/historias.md#us-025) |
| FR-070 | Registrar advertência específica relacionada ao cuidado quando a causa for natural, sem incluí-la no contador normal. | [US-026](docs/discovery/backlog/historias.md#us-026) |
| FR-071 | Registrar a punição aplicável quando houver falha atribuível aos envolvidos. | [US-027](docs/discovery/backlog/historias.md#us-027) |
| FR-072 | Encerrar definitivamente o caso após o registro do resultado da análise. | [US-026](docs/discovery/backlog/historias.md#us-026) |
| FR-073 | Permitir ao Cientista coletar e registrar dados científicos após a abdução. | [US-028](docs/discovery/backlog/historias.md#us-028) |
| FR-074 | Manter os dados científicos definidos: altura, peso, cor, etnia, DNA e tipo sanguíneo. | [US-028](docs/discovery/backlog/historias.md#us-028) |
| FR-075 | Armazenar os dados científicos para necessidades futuras. | [US-028](docs/discovery/backlog/historias.md#us-028) |
| FR-076 | Permitir consulta dos dados científicos somente por Cientistas, Gestor e Supervisor. | [US-029](docs/discovery/backlog/historias.md#us-029) |
| FR-077 | Permitir alteração dos dados científicos somente por Cientistas. | [US-028](docs/discovery/backlog/historias.md#us-028) |
| FR-078 | Permitir ao Gestor ou Supervisor decidir que dados científicos são obsoletos. | [US-030](docs/discovery/backlog/historias.md#us-030) |
| FR-079 | Excluir imediatamente os dados científicos considerados obsoletos. | [US-030](docs/discovery/backlog/historias.md#us-030) |
| FR-080 | Não manter registro específico da exclusão de dados científicos. | [US-030](docs/discovery/backlog/historias.md#us-030) |
| FR-081 | Manter o histórico das missões como registro suficiente, sem relatório separado de missão. | [US-031](docs/discovery/backlog/historias.md#us-031) |
| FR-082 | Permitir consulta do histórico completo a todos os funcionários. | [US-031](docs/discovery/backlog/historias.md#us-031) |
| FR-083 | Permitir alteração do histórico somente ao Gestor e Supervisor. | [US-032](docs/discovery/backlog/historias.md#us-032) |
| FR-084 | Registrar no histórico as ocorrências fora do padrão. | [US-022](docs/discovery/backlog/historias.md#us-022) |
| FR-085 | Reter auditoria de acessos por 2 meses. | [US-033](docs/discovery/backlog/historias.md#us-033) |
| FR-086 | Reter auditoria de alterações por 6 meses. | [US-034](docs/discovery/backlog/historias.md#us-034) |
| FR-087 | Registrar em auditoria de alteração: usuário, data/hora, registro/dado alterado, valor anterior e novo valor. | [US-034](docs/discovery/backlog/historias.md#us-034) |
| FR-088 | Registrar em auditoria de consulta de auditoria: usuário, data/hora e registro de auditoria consultado. | [US-035](docs/discovery/backlog/historias.md#us-035) |

## Regras de negócio preservadas

| ID | Regra da fonte |
|---|---|
| BR-001 | Gestor e Supervisor possuem poderes iguais no sistema. |
| BR-002 | Funcionário inativo não pode ser selecionado para nova missão. |
| BR-003 | Funcionário inativo não é excluído do sistema e pode ser reativado pelo Gestor ou Supervisor. |
| BR-004 | Nave em manutenção não pode participar de missão. |
| BR-005 | Capacidade da nave inclui tripulação e humanos. |
| BR-006 | Uma missão exige pelo menos um Piloto e um Abduzidor. |
| BR-007 | Um funcionário não pode participar de missões com sobreposição de horários. |
| BR-008 | Um humano não pode participar de mais de uma missão simultaneamente. |
| BR-009 | Pesquisa pré-missão é obrigatória antes do agendamento. |
| BR-010 | A avaliação de exceções é humana, realizada por Gestor e Supervisor. |
| BR-011 | Relevância global impede a prossecução da missão e resulta em cancelamento definitivo. |
| BR-012 | Os estados de missão são Pendente, Em andamento, Adiada, Concluída e Cancelada. |
| BR-013 | Concluída e Cancelada são estados definitivos. |
| BR-014 | Missão Adiada retorna a Pendente quando recebe nova data. |
| BR-015 | Cancelamento exige motivo: indisponibilidade ou exceção. |
| BR-016 | Nave parte e retorna ao Estacionamento Alien. |
| BR-017 | Autonomia considera o percurso completo de ida e retorno. |
| BR-018 | Retorno inadequado gera tratamento de advertências conforme regra definida. |
| BR-019 | Morte natural gera advertência de cuidado fora do contador normal. |
| BR-020 | Em caso de morte, o resultado da análise deve ser registrado antes do encerramento definitivo do caso. |
| BR-021 | Somente Cientistas alteram dados científicos. |
| BR-022 | Gestor/Supervisor podem determinar obsolescência dos dados científicos. |
| BR-023 | Todos os funcionários consultam o histórico; alteração é restrita a Gestor/Supervisor. |

## Objetivos → épicos

| Objetivo | Texto da fonte | Épicos relacionados |
|---|---|---|
| OBJ-001 | Centralizar o controle das abduções, naves, funcionários, humanos e missões. | EPIC-001, EPIC-002, EPIC-003 |
| OBJ-002 | Reduzir conflitos de agendamento de missões. | EPIC-003, EPIC-004 |
| OBJ-003 | Impedir o uso de naves indisponíveis ou em manutenção. | EPIC-002, EPIC-004 |
| OBJ-004 | Impedir conflitos de participação de funcionários e de humanos em missões. | EPIC-003, EPIC-004 |
| OBJ-005 | Manter o histórico das missões e das ocorrências fora do padrão. | EPIC-005, EPIC-006, EPIC-008 |
| OBJ-006 | Controlar informações e dados científicos relacionados aos humanos. | EPIC-007 |
| OBJ-007 | Controlar o acesso ao sistema e registrar atividades relevantes de usuários. | EPIC-001, EPIC-009 |

## Cobertura não funcional

| NFR | Tratamento |
|---|---|
| NFR-001 | Sistema inteiro; OPEN-033. |
| NFR-002 | US-003 e todas as consultas a missões. |
| NFR-003 | Sistema inteiro; OPEN-004. |
| NFR-004 | Matriz em qualidade.md; testes por perfil nas histórias. |
| NFR-005 | US-033, US-034, US-035 e operações auditáveis. |

## Resultado da conferência documental

- 88 de 88 FR possuem associação principal; nenhum FR foi descartado.
- 5 de 5 NFR tratados transversalmente; os incompletos permanecem sinalizados.
- 23 BR e 7 DEC preservadas para rastreabilidade.
- 15 OPEN originais preservadas; 18 novas questões registradas (OPEN-016 a OPEN-033). OPEN-015 já tem terminologia resolvida.
- 9 épicos, 17 features e 35 histórias com critérios específicos e dependências.
- Nenhum requisito de Área 51, relatório separado, arquitetura ou integração salarial foi acrescentado.
- A conferência valida a organização dos documentos; não equivale à aprovação do grupo nem a testes de software.


</details>

