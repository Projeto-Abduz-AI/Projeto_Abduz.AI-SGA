# Rastreabilidade do backlog

Esta matriz associa cada FR a uma história principal. O catálogo preserva o texto de origem, incluindo termos ainda abertos. Agrupar FR não elimina seus identificadores.

## Requisitos funcionais → histórias

| ID | Requisito da especificação v1.1 | História principal |
|---|---|---|
| FR-001 | Permitir o cadastro e alteração de funcionários pelo Gestor ou Supervisor. | [US-001](historias.md#us-001) |
| FR-002 | Manter funcionário desligado/inativo sem excluí-lo do sistema. | [US-002](historias.md#us-002) |
| FR-003 | Impedir a seleção de funcionário inativo para novas missões. | [US-002](historias.md#us-002) |
| FR-004 | Permitir a reativação de funcionário inativo pelo Gestor ou Supervisor, sem condição ou justificativa adicional. | [US-002](historias.md#us-002) |
| FR-005 | Permitir autenticação por login/usuário e senha. | [US-003](historias.md#us-003) |
| FR-006 | Garantir que o login seja único no SGA. | [US-001](historias.md#us-001) |
| FR-007 | Bloquear temporariamente a conta após 5 tentativas consecutivas de senha incorreta. | [US-004](historias.md#us-004) |
| FR-008 | Manter o bloqueio por 15 minutos ou até aprovação do Gestor/Supervisor, o que ocorrer primeiro. | [US-004](historias.md#us-004) |
| FR-009 | Alertar imediatamente Gestor e Supervisor sobre o bloqueio por tentativas incorretas, dentro do SGA e por e-mail, indicando caráter crítico/possível risco de intrusão. | [US-005](historias.md#us-005) |
| FR-010 | Permitir alteração de senha somente mediante solicitação do funcionário e aprovação do Gestor ou Supervisor. | [US-006](historias.md#us-006) |
| FR-011 | Aplicar o mesmo procedimento de aprovação para esquecimento de senha. | [US-006](historias.md#us-006) |
| FR-012 | Bloquear imediatamente o acesso de funcionário inativo/desligado. | [US-002](historias.md#us-002) |
| FR-013 | Encerrar automaticamente a sessão ao final do dia de trabalho; as credenciais são exigidas novamente no próximo acesso. | [US-007](historias.md#us-007) |
| FR-014 | Registrar tentativas de acesso bem-sucedidas e malsucedidas. | [US-033](historias.md#us-033) |
| FR-015 | Registrar alterações relevantes de dados de funcionários, naves, missões e dados científicos. | [US-034](historias.md#us-034) |
| FR-016 | Permitir consulta dos registros de alteração somente ao Gestor e Supervisor. | [US-035](historias.md#us-035) |
| FR-017 | Manter registros de alteração somente para leitura, sem permitir sua alteração ou exclusão. | [US-035](historias.md#us-035) |
| FR-018 | Registrar quem consultou registros de auditoria, data/hora e qual registro foi consultado. | [US-035](historias.md#us-035) |
| FR-019 | Permitir cadastrar e alterar dados de naves. | [US-008](historias.md#us-008) |
| FR-020 | Manter para a nave os dados definidos: capacidade total, quilômetros que pode voar e status operacional. | [US-008](historias.md#us-008) |
| FR-021 | Permitir alterar o status operacional entre disponível e manutenção pelo Gestor ou Supervisor. | [US-009](historias.md#us-009) |
| FR-022 | Impedir a utilização de nave em manutenção em uma missão. | [US-009](historias.md#us-009) |
| FR-023 | Registrar automaticamente a saída da nave quando a missão entrar em Em andamento. | [US-017](historias.md#us-017) |
| FR-024 | Registrar automaticamente a entrada da nave quando a missão passar para Concluída. | [US-018](historias.md#us-018) |
| FR-025 | Considerar o Estacionamento Alien como ponto de partida das naves. | [US-010](historias.md#us-010) |
| FR-026 | Considerar o Estacionamento Alien como destino de retorno das naves. | [US-010](historias.md#us-010) |
| FR-027 | Verificar a autonomia da nave para o percurso completo da missão, incluindo ida e retorno. | [US-010](historias.md#us-010) |
| FR-028 | Permitir cadastrar e consultar humanos. | [US-011](historias.md#us-011) |
| FR-029 | Manter no cadastro do humano nome, localização, idade e popularidade. | [US-011](historias.md#us-011) |
| FR-030 | Impedir que um mesmo humano participe de mais de uma missão simultaneamente. | [US-015](historias.md#us-015) |
| FR-031 | Exigir pesquisa pré-missão antes do agendamento de toda missão. | [US-012](historias.md#us-012) |
| FR-032 | Permitir ao Pesquisador registrar pesquisa sobre idade, patrimônio/riqueza, emprego, fonte de renda, popularidade, interações sociais e informações gerais da vida. | [US-012](historias.md#us-012) |
| FR-033 | Permitir ao Pesquisador registrar pesquisa de localização para identificar locais mais calmos. | [US-012](historias.md#us-012) |
| FR-034 | Permitir que Gestor e Supervisor avaliem as informações da pesquisa. | [US-013](historias.md#us-013) |
| FR-035 | Não realizar automaticamente a classificação de exceções; a identificação cabe à avaliação humana de Gestor/Supervisor. | [US-013](historias.md#us-013) |
| FR-036 | Impedir a prossecução da missão quando for identificada relevância em escala global, resultando em cancelamento definitivo. | [US-013](historias.md#us-013) |
| FR-037 | Quando não houver exceção relevante para impedir a missão, permitir que o Gestor decida se a abdução prosseguirá. | [US-013](historias.md#us-013) |
| FR-038 | Permitir ao Gestor definir humano, nave, tripulação, local, data e horário da missão. | [US-014](historias.md#us-014) |
| FR-039 | Permitir ao Gestor iniciar/registrar a solicitação da missão. | [US-014](historias.md#us-014) |
| FR-040 | Verificar disponibilidade de nave e funcionários antes do agendamento. | [US-015](historias.md#us-015) |
| FR-041 | Bloquear o agendamento quando houver conflito ou indisponibilidade. | [US-015](historias.md#us-015) |
| FR-042 | Impedir que funcionário participe de duas missões com horários sobrepostos. | [US-015](historias.md#us-015) |
| FR-043 | Exigir pelo menos um Piloto e um Abduzidor na tripulação. | [US-014](historias.md#us-014) |
| FR-044 | Considerar apenas funcionários ativos e disponíveis na seleção da tripulação. | [US-014](historias.md#us-014) |
| FR-045 | Considerar tripulação e humanos no cálculo da capacidade da nave. | [US-016](historias.md#us-016) |
| FR-046 | Permitir mais de um humano na mesma missão, desde que respeitada a capacidade da nave. | [US-016](historias.md#us-016) |
| FR-047 | Bloquear agendamento quando a capacidade da nave for excedida. | [US-016](historias.md#us-016) |
| FR-048 | Manter os estados de missão: Pendente, Em andamento, Adiada, Concluída e Cancelada. | [US-017](historias.md#us-017) |
| FR-049 | Alterar automaticamente Pendente para Em andamento no horário agendado. | [US-017](historias.md#us-017) |
| FR-050 | Permitir ao Gestor informar o término da missão, levando-a para Concluída. | [US-018](historias.md#us-018) |
| FR-051 | Permitir postergar uma missão. | [US-019](historias.md#us-019) |
| FR-052 | Manter missão Adiada até que Gestor ou Supervisor defina nova data. | [US-019](historias.md#us-019) |
| FR-053 | Retornar a missão Adiada para Pendente quando nova data for definida. | [US-019](historias.md#us-019) |
| FR-054 | Permitir cancelamento por indisponibilidade ou exceção. | [US-020](historias.md#us-020) |
| FR-055 | Registrar quem cancelou e o motivo do cancelamento. | [US-020](historias.md#us-020) |
| FR-056 | Considerar cancelamento definitivo, sem reativação ou reagendamento. | [US-020](historias.md#us-020) |
| FR-057 | Não criar um status chamado Reagendada; uma nova data de missão postergada mantém o mesmo registro e retorna a Pendente. | [US-019](historias.md#us-019) |
| FR-058 | Enviar notificações internas aos funcionários envolvidos quando houver mudanças relevantes da missão. | [US-021](historias.md#us-021) |
| FR-059 | Registrar retorno normal como 'retornado com vida'. | [US-022](historias.md#us-022) |
| FR-060 | Registrar retorno inadequado quando o humano não for devolvido ao local da abdução ou sofrer consequência de saúde no retorno. | [US-022](historias.md#us-022) |
| FR-061 | Registrar ocorrências fora do padrão no histórico da missão por meio de relato narrativo do Gestor. | [US-022](historias.md#us-022) |
| FR-062 | Manter histórico de advertências por funcionário. | [US-023](historias.md#us-023) |
| FR-063 | Aplicar três advertências para retorno inadequado e punição salarial na quarta advertência. | [US-023](historias.md#us-023) |
| FR-064 | Permitir ao Supervisor acompanhar a correção do problema. | [US-024](historias.md#us-024) |
| FR-065 | Quando o problema não for corrigido, considerar a nova advertência em dobro em relação à anterior. | [US-024](historias.md#us-024) |
| FR-066 | Não incluir advertência relacionada a morte natural no contador normal de advertências. | [US-026](historias.md#us-026) |
| FR-067 | Registrar a devolução do corpo ao local da abdução em caso de morte. | [US-025](historias.md#us-025) |
| FR-068 | Permitir ao Supervisor analisar o procedimento, o humano, as pessoas envolvidas e a causa da morte. | [US-025](historias.md#us-025) |
| FR-069 | Permitir ao Gestor registrar o resultado da análise. | [US-025](historias.md#us-025) |
| FR-070 | Registrar advertência específica relacionada ao cuidado quando a causa for natural, sem incluí-la no contador normal. | [US-026](historias.md#us-026) |
| FR-071 | Registrar a punição aplicável quando houver falha atribuível aos envolvidos. | [US-027](historias.md#us-027) |
| FR-072 | Encerrar definitivamente o caso após o registro do resultado da análise. | [US-026](historias.md#us-026) |
| FR-073 | Permitir ao Cientista coletar e registrar dados científicos após a abdução. | [US-028](historias.md#us-028) |
| FR-074 | Manter os dados científicos definidos: altura, peso, cor, etnia, DNA e tipo sanguíneo. | [US-028](historias.md#us-028) |
| FR-075 | Armazenar os dados científicos para necessidades futuras. | [US-028](historias.md#us-028) |
| FR-076 | Permitir consulta dos dados científicos somente por Cientistas, Gestor e Supervisor. | [US-029](historias.md#us-029) |
| FR-077 | Permitir alteração dos dados científicos somente por Cientistas. | [US-028](historias.md#us-028) |
| FR-078 | Permitir ao Gestor ou Supervisor decidir que dados científicos são obsoletos. | [US-030](historias.md#us-030) |
| FR-079 | Excluir imediatamente os dados científicos considerados obsoletos. | [US-030](historias.md#us-030) |
| FR-080 | Não manter registro específico da exclusão de dados científicos. | [US-030](historias.md#us-030) |
| FR-081 | Manter o histórico das missões como registro suficiente, sem relatório separado de missão. | [US-031](historias.md#us-031) |
| FR-082 | Permitir consulta do histórico completo a todos os funcionários. | [US-031](historias.md#us-031) |
| FR-083 | Permitir alteração do histórico somente ao Gestor e Supervisor. | [US-032](historias.md#us-032) |
| FR-084 | Registrar no histórico as ocorrências fora do padrão. | [US-022](historias.md#us-022) |
| FR-085 | Reter auditoria de acessos por 2 meses. | [US-033](historias.md#us-033) |
| FR-086 | Reter auditoria de alterações por 6 meses. | [US-034](historias.md#us-034) |
| FR-087 | Registrar em auditoria de alteração: usuário, data/hora, registro/dado alterado, valor anterior e novo valor. | [US-034](historias.md#us-034) |
| FR-088 | Registrar em auditoria de consulta de auditoria: usuário, data/hora e registro de auditoria consultado. | [US-035](historias.md#us-035) |

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
