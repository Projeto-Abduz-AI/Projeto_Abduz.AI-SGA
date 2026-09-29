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
