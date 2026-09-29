# Backlog do SGA — Abduz.AI

Etapa 03 — Backlog | Versão 1.0 | 29/09/2026

Este backlog organiza o Discovery em **9 épicos, 17 features e 35 histórias de usuário**. Os **88 FR** possuem associação principal a uma história; os **5 NFR** são tratados transversalmente. Estado: **proposta para validação do grupo**, com questões abertas explícitas. Cobertura documental não significa prontidão integral para implementação.

## Como ler

- [Histórias detalhadas](historias.md): necessidade, benefício, dados, dependências, critérios e pendências.
- [Requisitos transversais e critérios de qualidade](qualidade.md).
- [Questões abertas e revisão de consistência](pendencias.md).
- [Rastreabilidade e catálogo de requisitos de origem](rastreabilidade.md).

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

- [US-001 — Cadastrar e atualizar funcionários](historias.md#us-001)
- [US-002 — Inativar e reativar funcionários](historias.md#us-002)

**FEAT-002 — Autenticação e credenciais**

- [US-003 — Acessar o SGA](historias.md#us-003)
- [US-004 — Bloquear e desbloquear uma conta](historias.md#us-004)
- [US-005 — Receber alerta de bloqueio](historias.md#us-005)
- [US-006 — Solicitar alteração ou recuperação de senha](historias.md#us-006)
- [US-007 — Encerrar a sessão ao final do expediente](historias.md#us-007)

### EPIC-002 — Naves e percurso

**Objetivos:** OBJ-001, OBJ-003. **Resultado:** Manter naves e validar condições de uso.

**FEAT-003 — Cadastro e manutenção de naves**

- [US-008 — Cadastrar e atualizar naves](historias.md#us-008)
- [US-009 — Controlar manutenção de naves](historias.md#us-009)

**FEAT-004 — Autonomia e percurso**

- [US-010 — Validar autonomia de ida e retorno](historias.md#us-010)

### EPIC-003 — Humanos e pesquisa pré-missão

**Objetivos:** OBJ-001, OBJ-002, OBJ-004. **Resultado:** Preparar informações para a decisão humana.

**FEAT-005 — Cadastro de humanos**

- [US-011 — Cadastrar e consultar humanos](historias.md#us-011)

**FEAT-006 — Pesquisa e avaliação pré-missão**

- [US-012 — Registrar pesquisa pré-missão](historias.md#us-012)
- [US-013 — Avaliar pesquisa e decidir prosseguimento](historias.md#us-013)

### EPIC-004 — Planejamento e ciclo de missões

**Objetivos:** OBJ-002, OBJ-003, OBJ-004. **Resultado:** Agendar e acompanhar missões sem conflitos conhecidos.

**FEAT-007 — Definição e validação de agendamento**

- [US-014 — Definir uma missão](historias.md#us-014)
- [US-015 — Validar conflitos de agendamento](historias.md#us-015)
- [US-016 — Validar lotação com vários humanos](historias.md#us-016)

**FEAT-008 — Estados e movimentação da missão**

- [US-017 — Iniciar missão e registrar saída](historias.md#us-017)
- [US-018 — Concluir missão e registrar entrada](historias.md#us-018)
- [US-019 — Adiar e remarcar missão](historias.md#us-019)
- [US-020 — Cancelar definitivamente uma missão](historias.md#us-020)

**FEAT-009 — Notificações de missão**

- [US-021 — Notificar mudanças da missão](historias.md#us-021)

### EPIC-005 — Retorno e advertências

**Objetivos:** OBJ-005. **Resultado:** Registrar retornos e acompanhar ocorrências e advertências.

**FEAT-010 — Retornos e ocorrências**

- [US-022 — Registrar retorno normal ou inadequado](historias.md#us-022)

**FEAT-011 — Advertências e correção**

- [US-023 — Manter advertências e punição por reincidência](historias.md#us-023)
- [US-024 — Acompanhar correção e reincidência não corrigida](historias.md#us-024)

### EPIC-006 — Ocorrências de morte

**Objetivos:** OBJ-005. **Resultado:** Registrar análise e encerramento dos casos.

**FEAT-012 — Análise e encerramento de morte**

- [US-025 — Registrar morte e análise do caso](historias.md#us-025)
- [US-026 — Tratar morte natural e encerrar o caso](historias.md#us-026)
- [US-027 — Registrar punição por falha atribuível](historias.md#us-027)

### EPIC-007 — Dados científicos

**Objetivos:** OBJ-006. **Resultado:** Registrar, restringir consulta e tratar obsolescência.

**FEAT-013 — Registro, alteração e consulta científica**

- [US-028 — Registrar e manter dados científicos](historias.md#us-028)
- [US-029 — Consultar dados científicos com restrição](historias.md#us-029)

**FEAT-014 — Obsolescência científica**

- [US-030 — Excluir dados científicos obsoletos](historias.md#us-030)

### EPIC-008 — Histórico de missões

**Objetivos:** OBJ-005. **Resultado:** Consultar e corrigir o histórico conforme permissões.

**FEAT-015 — Consulta e manutenção do histórico**

- [US-031 — Consultar histórico de missões](historias.md#us-031)
- [US-032 — Corrigir histórico com permissão administrativa](historias.md#us-032)

### EPIC-009 — Auditoria

**Objetivos:** OBJ-007. **Resultado:** Rastrear acessos, alterações e consultas administrativas.

**FEAT-016 — Registros de acesso e alteração**

- [US-033 — Registrar e reter acessos](historias.md#us-033)
- [US-034 — Registrar alterações e seus valores](historias.md#us-034)

**FEAT-017 — Consulta e proteção da auditoria**

- [US-035 — Consultar auditoria imutável e registrar consultas](historias.md#us-035)

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
