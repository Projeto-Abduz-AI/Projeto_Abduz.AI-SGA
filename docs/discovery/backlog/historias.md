# Histórias de usuário

Etapa 03 — Backlog. Todas as histórias são propostas para validação. Os comportamentos vêm dos requisitos citados; as lacunas permanecem em [pendências](pendencias.md).

**Pré-condição transversal:** funcionário autenticado e com permissão para a operação, exceto o próprio fluxo de autenticação e a solicitação por esquecimento de senha, cujo canal está pendente. Automações dependem do evento/estado indicado em seus critérios. As dependências abaixo indicam relação de domínio, não sequência obrigatória de programação.

**Qualidade transversal:** observar [NFR-001 a NFR-005](qualidade.md). Auditoria depende de US-033 a US-035; esta relação transversal não deve ser interpretada como ciclo de execução entre histórias.

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
**Dependências de domínio:** [US-001](historias.md#us-001)

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
**Dependências de domínio:** [US-001](historias.md#us-001)

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
**Dependências de domínio:** [US-003](historias.md#us-003)

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
**Dependências de domínio:** [US-004](historias.md#us-004)

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
**Dependências de domínio:** [US-001](historias.md#us-001), [US-003](historias.md#us-003)

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
**Dependências de domínio:** [US-003](historias.md#us-003)

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
**Dependências de domínio:** [US-008](historias.md#us-008)

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
**Dependências de domínio:** [US-008](historias.md#us-008)

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
**Dependências de domínio:** [US-011](historias.md#us-011)

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
**Dependências de domínio:** [US-012](historias.md#us-012)

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
**Dependências de domínio:** [US-001](historias.md#us-001), [US-008](historias.md#us-008), [US-011](historias.md#us-011), [US-013](historias.md#us-013)

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
**Dependências de domínio:** [US-014](historias.md#us-014)

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
**Dependências de domínio:** [US-014](historias.md#us-014), [US-008](historias.md#us-008)

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
**Dependências de domínio:** [US-015](historias.md#us-015), [US-016](historias.md#us-016), [US-010](historias.md#us-010)

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
**Dependências de domínio:** [US-017](historias.md#us-017)

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
**Dependências de domínio:** [US-014](historias.md#us-014)

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
**Dependências de domínio:** [US-014](historias.md#us-014)

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
**Dependências de domínio:** [US-014](historias.md#us-014)

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
**Dependências de domínio:** [US-017](historias.md#us-017)

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
**Dependências de domínio:** [US-022](historias.md#us-022)

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
**Dependências de domínio:** [US-023](historias.md#us-023)

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
**Dependências de domínio:** [US-017](historias.md#us-017)

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
**Dependências de domínio:** [US-025](historias.md#us-025), [US-023](historias.md#us-023)

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
**Dependências de domínio:** [US-025](historias.md#us-025)

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
**Dependências de domínio:** [US-011](historias.md#us-011), [US-017](historias.md#us-017)

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
**Dependências de domínio:** [US-028](historias.md#us-028)

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
**Dependências de domínio:** [US-028](historias.md#us-028)

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
**Dependências de domínio:** [US-014](historias.md#us-014)

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
**Dependências de domínio:** [US-031](historias.md#us-031)

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
**Dependências de domínio:** [US-003](historias.md#us-003)

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
**Dependências de domínio:** [US-001](historias.md#us-001), [US-008](historias.md#us-008), [US-014](historias.md#us-014), [US-028](historias.md#us-028)

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
**Dependências de domínio:** [US-034](historias.md#us-034)

**Critérios de aceitação:**

- **CA-01:** Dado Gestor ou Supervisor, quando consultar registros de alteração, então a consulta é permitida; para os demais perfis é impedida.
- **CA-02:** Dado qualquer perfil, quando tentar editar ou excluir um registro de alteração, então a operação não é permitida.
- **CA-03:** Dada consulta de auditoria, então se registra quem consultou, data/hora e qual registro foi consultado.

**Pendências vinculadas:** OPEN-031
**Limites e observações:** FR-018 e FR-088 são tratados em uma história. Retenção do registro de consulta e expiração administrada versus exclusão por usuário precisam ser esclarecidas.

**Situação de refinamento:** Requer refinamento nas questões vinculadas; critérios já definidos podem ser avaliados separadamente.
