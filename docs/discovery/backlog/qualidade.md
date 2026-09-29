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
