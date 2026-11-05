A seguir está uma **versão enxuta**, organizada por fase do **SDLC — ciclo de vida de desenvolvimento de software**.



A proposta reúne os principais conteúdos em **12 documentos ou conjuntos de registros**. Eles não precisam ser 12 arquivos separados: podem estar distribuídos entre a ferramenta de gestão, o repositório de código e a plataforma de documentação.



> As fases são uma forma de organização. Em projetos ágeis, elas se repetem a cada iniciativa ou entrega, e vários documentos evoluem em paralelo.



# Visão geral por fase



| Fase do SDLC | Objetivo | Principais documentos |

|---|---|---|

| 1. Concepção e planejamento | Entender o problema e justificar o investimento | Visão do projeto; governança e riscos |

| 2. Descoberta e análise de negócio | Entender processos, usuários e regras | Processos e regras; visão do produto e backlog |

| 3. Requisitos | Definir o que será construído e como validar | Backlog e critérios de aceite; requisitos não funcionais |

| 4. Arquitetura e desenho | Definir como a solução será estruturada | Arquitetura; dados e privacidade; segurança |

| 5. Desenvolvimento | Construir a solução de forma consistente | Guia de desenvolvimento; registros técnicos atualizados |

| 6. Testes e validação | Comprovar que a solução atende ao esperado | Estratégia de testes, evidências e aceite |

| 7. Implantação | Colocar a solução em produção com controle | Plano de implantação e retorno |

| 8. Operação e evolução | Sustentar, monitorar e melhorar a solução | Manual operacional e continuidade; backlog atualizado |



---



# 1. Concepção e planejamento



## Documento 1 — Visão e justificativa do projeto



**Objetivo:** explicar por que o projeto existe e o que se espera alcançar.



**Responsável sugerido:** patrocinador ou responsável pelo negócio, com apoio de produto e gestão do projeto.



### Conteúdo mínimo



- Problema ou oportunidade.

- Objetivos de negócio.

- Público e áreas afetadas.

- Benefícios esperados.

- Indicadores de sucesso.

- Escopo inicial e o que está fora dele.

- Estimativa inicial de prazo e investimento.

- Principais premissas e restrições.



**Exemplo de objetivo:** reduzir o tempo médio de aprovação de propostas de 48 para 12 horas.



---



## Documento 2 — Governança, riscos e decisões



**Objetivo:** deixar claro quem decide, quais são os riscos e quais dependências podem afetar a entrega.



**Responsável sugerido:** gestor do projeto ou produto.



### Conteúdo mínimo



- Patrocinador e responsáveis por negócio, produto, tecnologia e segurança.

- Responsáveis por aprovar requisitos e implantação.

- Principais riscos e respectivos planos de ação.

- Dependências internas e externas.

- Decisões importantes, responsáveis e datas.

- Mudanças relevantes de escopo, prazo ou custo.



**Quando atualizar:** durante todo o projeto.



---



# 2. Descoberta e análise de negócio



## Documento 3 — Processos e regras de negócio



**Objetivo:** registrar como o trabalho acontece e quais regras a solução deve respeitar.



**Responsável sugerido:** analista de negócios, com validação da área responsável pelo processo.



### Conteúdo mínimo



- Processo atual e principais dificuldades.

- Processo futuro esperado.

- Participantes e responsabilidades.

- Etapas, decisões e exceções.

- Sistemas envolvidos.

- Regras de negócio.

- Glossário dos termos importantes.



### Exemplo de regra



> Uma proposta expirada não pode ser aprovada.



Essa regra deve estar ligada ao requisito e aos testes correspondentes.



---



## Documento 4 — Visão do produto e backlog



**Objetivo:** definir para quem a solução será construída, qual valor deve gerar e quais entregas serão priorizadas.



**Responsável sugerido:** gestor de produto, com apoio de negócio e tecnologia.



### Conteúdo mínimo



- Usuários ou públicos atendidos.

- Necessidades e problemas prioritários.

- Proposta de valor.

- Objetivos e métricas do produto.

- Principais funcionalidades.

- Prioridades e dependências.

- Planejamento inicial das entregas.

- Hipóteses que ainda precisam ser validadas.



O backlog será detalhado na fase seguinte. Para um projeto pequeno, visão e backlog podem ficar na mesma ferramenta ou página.



---



# 3. Requisitos



## Complemento do documento 4 — Requisitos e critérios de aceite



**Objetivo:** tornar claro o que cada entrega precisa fazer e como será validada.



**Responsáveis sugeridos:** produto, análise de negócios, engenharia e qualidade.



### Para cada requisito ou item relevante do backlog, registrar



- Identificador e descrição.

- Problema ou objetivo atendido.

- Usuário ou sistema envolvido.

- Regras de negócio relacionadas.

- Fluxo principal e exceções.

- Critérios de aceite verificáveis.

- Prioridade e dependências.

- Referências para telas, integrações ou testes.



### Exemplo de critério de aceite



> Dada uma proposta expirada, quando o usuário tentar aprová-la, o sistema deve impedir a aprovação e informar o motivo.



---



## Documento 5 — Requisitos não funcionais



**Objetivo:** definir os atributos de qualidade e as restrições da solução.



**Responsável sugerido:** arquitetura ou liderança técnica, com participação de negócio, segurança e operações.



### Conteúdo mínimo



- Desempenho esperado.

- Disponibilidade necessária.

- Volume de usuários e transações.

- Segurança e controle de acesso.

- Privacidade e retenção de dados.

- Acessibilidade, quando houver interface.

- Monitoramento e registros.

- Backup e recuperação.

- Restrições técnicas ou de fornecedores.



**Boa prática:** sempre que possível, escreva requisitos mensuráveis. Por exemplo, prefira “95% das consultas em até dois segundos” a “a tela deve ser rápida”.



---



# 4. Arquitetura e desenho



## Documento 6 — Arquitetura da solução e decisões técnicas



**Objetivo:** explicar como a solução será estruturada e por que as principais decisões foram tomadas.



**Responsável sugerido:** arquiteto de solução ou liderança técnica.



### Conteúdo mínimo



- Diagrama de contexto: usuários, solução e sistemas externos.

- Componentes e responsabilidades.

- Principais fluxos.

- Integrações e contratos de APIs ou eventos.

- Ambientes e infraestrutura.

- Dependências técnicas.

- Como a solução atende aos requisitos não funcionais.

- Decisões técnicas relevantes, alternativas e consequências.

- Riscos e pontos ainda em aberto.



As decisões podem ser registradas em pequenos **registros de decisão arquitetural**, vinculados ao documento principal.



---



## Documento 7 — Dados e privacidade



**Objetivo:** registrar quais dados serão tratados, onde estarão e como serão protegidos.



**Responsável sugerido:** equipe de dados ou liderança técnica, com participação de privacidade quando aplicável.



### Conteúdo mínimo



- Principais entidades e dados.

- Significado dos campos relevantes.

- Origem e destino dos dados.

- Sistemas e fornecedores que recebem informações.

- Dados pessoais ou sensíveis, quando houver.

- Responsáveis pelo acesso e tratamento.

- Retenção e exclusão.

- Necessidade de migração e validação dos dados.



**Quando aplicável:** avaliações de privacidade mais detalhadas, incluindo RIPD, devem ser tratadas conforme o risco e as exigências pertinentes.



---



## Documento 8 — Segurança e modelo de ameaças



**Objetivo:** identificar os principais riscos de segurança antes e durante a construção.



**Responsável sugerido:** segurança da informação e arquitetura.



### Conteúdo mínimo



- Ativos e dados que precisam de proteção.

- Pontos de entrada e integrações.

- Principais ameaças e cenários de abuso.

- Requisitos de autenticação e autorização.

- Proteção de dados e credenciais.

- Controles previstos.

- Vulnerabilidades identificadas.

- Riscos aceitos, responsáveis e prazos.

- Testes de segurança necessários.



**Exemplo de ameaça:** um usuário tenta acessar informações de outro cliente alterando um identificador na requisição.



---



# 5. Desenvolvimento



## Documento 9 — Guia de desenvolvimento



**Objetivo:** permitir que a equipe construa e mantenha a solução de maneira consistente.



**Responsável sugerido:** liderança técnica ou equipe de engenharia.



### Conteúdo mínimo



- Como configurar o ambiente.

- Como executar a aplicação.

- Organização do código.

- Padrões de desenvolvimento.

- Processo de revisão de código.

- Como executar testes.

- Gestão de dependências e segredos.

- Processo de construção e implantação.

- Responsáveis pelo repositório e canais de suporte.



Esse guia pode ficar no próprio repositório, próximo ao código. Um guia comum da organização pode ser reutilizado, desde que indique as particularidades do projeto.



### Durante a construção, também manter atualizados



- Backlog e critérios de aceite.

- Arquitetura e decisões técnicas.

- Contratos de integração.

- Registro de riscos e vulnerabilidades.

- Testes automatizados e suas evidências.



---



# 6. Testes e validação



## Documento 10 — Estratégia de testes, evidências e aceite



**Objetivo:** demonstrar que a solução atende aos requisitos e que os riscos conhecidos foram considerados.



**Responsável sugerido:** qualidade e engenharia, com aceite da área de negócio.



### Conteúdo mínimo



- Escopo e responsabilidades dos testes.

- Critérios de entrada e saída.

- Cenários e comportamentos críticos.

- Tipos de teste necessários.

- Ambiente e dados de teste.

- Resultados e evidências.

- Defeitos e pendências.

- Riscos residuais.

- Decisão de aceite e responsáveis.



### Tipos de teste a avaliar



- Funcionais e de integração.

- Segurança.

- Desempenho.

- Acessibilidade.

- Migração de dados.

- Recuperação.

- Aceitação do usuário.



**Importante:** o aceite deve registrar também as pendências conhecidas, com responsáveis e prazos.



---



# 7. Implantação



## Documento 11 — Plano de implantação e retorno



**Objetivo:** orientar a entrada em produção e reduzir o impacto de falhas.



**Responsável sugerido:** engenharia ou responsável pela implantação, com operações e negócio.



### Conteúdo mínimo



- Versão e funcionalidades incluídas.

- Data, janela e responsáveis.

- Pré-requisitos.

- Passos de implantação.

- Configurações e migrações necessárias.

- Validações antes e depois da implantação.

- Comunicação aos usuários e áreas afetadas.

- Critérios para interromper a implantação.

- Plano de retorno ou correção.

- Contatos de apoio.

- Resultado da implantação.



**Atenção:** se a mudança envolver migração de dados, documente se o retorno é realmente possível e como será feito.



---



# 8. Operação e evolução



## Documento 12 — Manual operacional e continuidade



**Objetivo:** garantir que a solução possa ser monitorada, sustentada e recuperada após a implantação.



**Responsável sugerido:** equipe proprietária do serviço ou operações.



### Conteúdo mínimo



- Responsável pelo serviço e contatos.

- Visão dos componentes e dependências.

- Procedimentos operacionais mais comuns.

- Painéis, métricas e alertas.

- Tratamento e escalonamento de incidentes.

- Problemas conhecidos.

- Procedimentos de backup e restauração.

- Objetivos de recuperação acordados.

- Procedimentos para falhas críticas.

- Links para arquitetura e documentação técnica.



Para situações recorrentes ou críticas, inclua instruções específicas de diagnóstico e resolução — os chamados **runbooks**.



---



# Resumo: os 12 documentos essenciais



| Nº | Documento ou conjunto | Fase principal |

|---:|---|---|

| 1 | Visão e justificativa do projeto | Concepção |

| 2 | Governança, riscos e decisões | Planejamento e acompanhamento |

| 3 | Processos e regras de negócio | Análise de negócio |

| 4 | Visão do produto, backlog e requisitos | Produto e requisitos |

| 5 | Requisitos não funcionais | Requisitos |

| 6 | Arquitetura e decisões técnicas | Arquitetura e desenho |

| 7 | Dados e privacidade | Arquitetura e desenho |

| 8 | Segurança e modelo de ameaças | Arquitetura e construção |

| 9 | Guia de desenvolvimento | Desenvolvimento |

| 10 | Testes, evidências e aceite | Testes e validação |

| 11 | Implantação e retorno | Implantação |

| 12 | Manual operacional e continuidade | Operação |



## Documentos adicionais, somente quando aplicáveis



| Situação | Documento adicional recomendado |

|---|---|

| Migração de sistemas ou bases | Plano de migração e reconciliação de dados |

| Mudança significativa para usuários | Plano de comunicação, treinamento e adoção |

| Exigências regulatórias ou contratuais relevantes | Matriz de conformidade e evidências |

| Componentes e dependências relevantes | Inventário de componentes de software — SBOM |

| Funcionalidades com IA | Ficha da funcionalidade, avaliação de riscos e plano de testes e monitoramento |

| Substituição ou retirada de um sistema | Plano de descontinuação e descarte ou migração de dados |



## Regra prática



Se for necessário reduzir ainda mais a quantidade de arquivos, **agrupe documentos, mas não elimine seus conteúdos essenciais**. Por exemplo:



- Visão do projeto + governança.

- Processos + regras de negócio.

- Backlog + requisitos + critérios de aceite.

- Arquitetura + dados + segurança.

- Testes + evidências + aceite.

- Implantação + operação + continuidade.



O resultado pode ser um pacote de **seis conjuntos**, desde que cada informação tenha responsável, esteja atualizada e possa ser encontrada facilmente.

