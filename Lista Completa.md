Para cobrir um projeto de TI de ponta a ponta, eu não começaria perguntando “quantos documentos precisamos produzir?”, mas sim:

> **Quais decisões, requisitos, riscos, entregas e evidências precisamos conseguir entender, rastrear e manter ao longo da vida do produto?**

Um projeto completo pode reunir dezenas de artefatos, mas eles **não precisam ser dezenas de arquivos separados**. Um backlog pode conter requisitos e critérios de aceite; um repositório pode conter arquitetura e decisões técnicas; um pipeline pode gerar evidências de testes e segurança.

A seguir, apresento um catálogo abrangente, com finalidade, conteúdo e responsável sugerido para cada artefato.

**Referência temporal:** pesquisa consultada até novembro de 2026. A lista abaixo é uma **proposta prática consolidada**, baseada nas fontes citadas — não uma lista oficial de documentos obrigatórios publicada pelo Gartner.

---

# 1. O que mudou na documentação moderna de projetos de TI?

As referências recentes apontam para uma documentação mais integrada ao trabalho real das equipes.

O Gartner destaca, em suas pesquisas de 2026, o uso de IA ao longo do SDLC, a importância da engenharia de plataforma, da segurança e da organização do contexto necessário para ferramentas e agentes de IA. Isso torna ainda mais valiosos requisitos claros, decisões arquiteturais registradas, contratos de integração e informações confiáveis sobre o produto. ([gartner.com](https://www.gartner.com/en/documents/6988266?utm_source=openai))

Na prática, recomendo cinco princípios:

1. **Documentação viva:** atualizada quando o produto ou a decisão muda.
2. **Uma fonte principal por informação:** evitar versões divergentes em vários arquivos.
3. **Rastreabilidade:** conectar objetivo, requisito, implementação, teste e operação.
4. **Automação quando possível:** gerar evidências de testes, implantação e dependências por ferramentas.
5. **Profundidade proporcional ao risco:** um sistema financeiro crítico exige mais formalidade que um protótipo interno.

O NIST também reforça que práticas de segurança devem ser integradas ao SDLC, independentemente de o projeto usar abordagem ágil, tradicional ou DevOps. ([nist.gov](https://www.nist.gov/publications/secure-software-development-framework-ssdf-version-11-recommendations-mitigating-risk?utm_source=openai))

## Como ler o catálogo

- **Essencial:** recomendo para praticamente todo projeto, mesmo que em formato simples.
- **Condicional:** necessário quando o contexto, risco, contrato ou arquitetura justificar.
- **Dono sugerido:** papel que coordena a manutenção; não significa que trabalha sozinho.

**Importante:** “essencial” nesta resposta é uma recomendação de gestão. Obrigações legais, regulatórias e contratuais precisam ser avaliadas especificamente para a organização e a jurisdição.

---

# 2. Negócio e justificativa do investimento

## 2.1. Documento de visão e justificativa do negócio

**Classificação:** essencial  
**Dono sugerido:** patrocinador, responsável de negócio ou gestor de produto  
**Quando criar:** na concepção; revisar quando as premissas mudarem.

É o documento que explica **por que o projeto existe** e qual resultado se espera alcançar.

### Conteúdo recomendado

- Problema ou oportunidade.
- Contexto do negócio.
- Público e áreas afetadas.
- Situação atual e principais dificuldades.
- Objetivos estratégicos.
- Alternativas consideradas, inclusive não executar o projeto.
- Benefícios esperados e como serão medidos.
- Estimativa de custos, investimentos e ganhos.
- Premissas, restrições e principais riscos.
- Decisão solicitada e responsáveis.

### Exemplo

> Reduzir o tempo médio de aprovação de crédito de 48 para 12 horas, mantendo os controles de risco existentes.

Esse documento pode reunir o **business case** e a visão inicial do projeto. Para iniciativas pequenas, uma ou duas páginas podem ser suficientes.

---

## 2.2. Mapeamento de processos de negócio: situação atual e futura

**Classificação:** essencial quando o sistema altera ou suporta um processo de negócio  
**Dono sugerido:** analista de negócios ou responsável pelo processo  
**Quando criar:** durante a descoberta; revisar após mudanças relevantes.

Descreve como o trabalho acontece hoje e como deverá acontecer após a solução.

### Conteúdo recomendado

- Fluxo atual e fluxo desejado.
- Participantes e responsabilidades.
- Entradas, saídas e pontos de decisão.
- Sistemas utilizados.
- Regras de negócio.
- Exceções e tratamentos manuais.
- Gargalos, retrabalho e controles.
- Indicadores atuais e esperados.

### Formatos possíveis

- Fluxogramas.
- BPMN, quando a organização usar essa notação.
- Tabelas de etapas e responsáveis.
- Jornadas operacionais.

**Atenção:** o processo futuro deve mostrar também como serão tratadas falhas, exceções e atividades humanas — não apenas o caminho ideal.

---

## 2.3. Catálogo de regras de negócio e glossário

**Classificação:** essencial  
**Dono sugerido:** analista de negócios, com validação do responsável pelo negócio  
**Quando criar:** durante a análise; manter ao longo da evolução.

Registra conceitos e regras que precisam permanecer consistentes em telas, APIs, cálculos, integrações e relatórios.

### Conteúdo recomendado

Para cada regra:

- Identificador.
- Nome e descrição clara.
- Condições de aplicação.
- Resultado esperado.
- Exceções.
- Exemplos.
- Origem da regra.
- Responsável pela validação.
- Requisitos e testes relacionados.

Para o glossário:

- Termo.
- Definição.
- Sinônimos ou termos que devem ser evitados.
- Responsável pela definição.

### Exemplo

| Campo | Exemplo |
|---|---|
| Identificador | RN-014 |
| Regra | Uma proposta expirada não pode ser aprovada |
| Condição | Data atual posterior à data de validade |
| Exceção | Nenhuma |
| Validador | Área de crédito |
| Testes relacionados | CT-031 e CT-032 |

---

## 2.4. Análise de impacto organizacional

**Classificação:** condicional; fortemente recomendada quando há mudança de processos ou equipes  
**Dono sugerido:** negócio, gestão de mudanças ou responsável pela implantação  
**Quando criar:** antes da implantação.

### Conteúdo recomendado

- Áreas, cargos e usuários afetados.
- Atividades que mudam, deixam de existir ou surgem.
- Alterações em controles e responsabilidades.
- Necessidade de treinamento.
- Impactos em fornecedores e clientes.
- Riscos de adoção.
- Plano de comunicação e transição.

---

# 3. Produto, usuários e experiência

## 3.1. Visão do produto e estratégia

**Classificação:** essencial  
**Dono sugerido:** gestor de produto  
**Quando criar:** na descoberta; revisar periodicamente.

Explica **para quem o produto existe, qual valor entrega e como será avaliado**.

### Conteúdo recomendado

- Público-alvo.
- Necessidades e problemas prioritários.
- Proposta de valor.
- Objetivos do produto.
- Diferenciais ou capacidades esperadas.
- Indicadores de resultado.
- Limites iniciais do produto.
- Dependências estratégicas.
- Principais hipóteses a validar.

### Diferença para o documento de negócio

- **Negócio:** por que investir.
- **Produto:** o que será oferecido, para quem e com qual resultado.

Em projetos menores, ambos podem estar no mesmo documento, com seções distintas.

---

## 3.2. Pesquisa de usuários, personas e jornadas

**Classificação:** essencial quando há usuários humanos; proporcional à complexidade  
**Dono sugerido:** pesquisa de experiência, design ou produto  
**Quando criar:** durante a descoberta e sempre que surgirem dúvidas relevantes.

### Conteúdo recomendado

- Perfis de usuários e necessidades.
- Pesquisas e fontes utilizadas.
- Tarefas que os usuários precisam realizar.
- Dores, barreiras e expectativas.
- Jornada atual e futura.
- Hipóteses ainda não validadas.
- Resultados de entrevistas, observações ou testes.
- Requisitos de acessibilidade identificados.

**Boa prática:** separar o que foi observado em pesquisa do que ainda é hipótese da equipe.

---

## 3.3. Documento de requisitos do produto — PRD

**Classificação:** essencial  
**Dono sugerido:** gestor de produto ou analista de produto  
**Quando criar:** antes de detalhar e construir uma capacidade relevante.

O PRD conecta o problema do usuário à solução proposta e aos resultados esperados.

### Conteúdo recomendado

- Problema a resolver.
- Público afetado.
- Objetivo e resultado esperado.
- Escopo e itens fora do escopo.
- Fluxo principal.
- Capacidades e funcionalidades.
- Regras de negócio relacionadas.
- Critérios de aceite.
- Requisitos de acessibilidade e segurança pertinentes.
- Dependências.
- Métricas e plano de validação.
- Questões em aberto.

**Formato moderno:** pode ser uma página por iniciativa, com links para backlog, protótipos, regras e arquitetura. Não precisa ser um documento extenso para cada entrega.

---

## 3.4. Roadmap e estratégia de entregas

**Classificação:** essencial  
**Dono sugerido:** produto, com tecnologia e negócio  
**Quando criar:** após definir objetivos e prioridades; revisar continuamente.

### Conteúdo recomendado

- Objetivos e resultados esperados por período.
- Iniciativas e entregas previstas.
- Dependências.
- Marcos relevantes.
- Prioridades.
- Grau de confiança das datas.
- Critérios que podem alterar a sequência.

**Cuidado:** diferencie uma **previsão de roadmap** de uma **data contratualmente comprometida**.

---

## 3.5. Backlog de produto e critérios de aceite

**Classificação:** essencial  
**Dono sugerido:** gestor de produto; detalhamento compartilhado com análise, desenvolvimento e qualidade  
**Quando criar:** desde o planejamento; manter continuamente.

É o registro priorizado do trabalho a ser realizado e do resultado esperado.

### Cada item relevante deve conter

- Identificador e descrição.
- Problema ou objetivo relacionado.
- Valor esperado.
- Regras de negócio.
- Critérios de aceite verificáveis.
- Dependências.
- Requisitos não funcionais pertinentes.
- Protótipos, contratos ou documentos associados.
- Testes relacionados.
- Situação e prioridade.

### Exemplo de critério de aceite

> Dado que uma proposta está expirada, quando o usuário tentar aprová-la, o sistema deve impedir a aprovação e apresentar o motivo.

---

## 3.6. Protótipos, especificações de interface e conteúdo

**Classificação:** condicional, conforme a existência de interface  
**Dono sugerido:** design de produto  
**Quando criar:** antes da construção das interfaces mais relevantes.

### Conteúdo recomendado

- Fluxos de navegação.
- Telas e componentes.
- Estados de carregamento, vazio, erro e sucesso.
- Validações de formulário.
- Mensagens e textos.
- Comportamento em diferentes dispositivos.
- Regras de acessibilidade.
- Interações excepcionais.
- Referências ao sistema de design, se existir.

---

# 4. Requisitos e rastreabilidade

## 4.1. Especificação de requisitos funcionais

**Classificação:** essencial  
**Dono sugerido:** análise de sistemas ou de negócios, em conjunto com produto  
**Quando criar:** antes da implementação de cada capacidade.

Descreve **o que a solução precisa fazer**. Pode existir em uma especificação formal ou estar distribuída entre PRD, backlog, fluxos e contratos.

### Conteúdo recomendado

- Identificador.
- Descrição objetiva.
- Ator ou sistema envolvido.
- Pré-condições.
- Fluxo principal.
- Fluxos alternativos e exceções.
- Entradas e saídas.
- Regras de negócio.
- Critérios de aceite.
- Prioridade.
- Dependências.
- Fonte e responsável pela aprovação.

A ISO/IEC/IEEE 29148 trata de processos e informações de engenharia de requisitos. Na consulta realizada, a edição publicada de 2018 seguia vigente, enquanto uma nova edição estava em desenvolvimento; portanto, o rascunho não deve ser apresentado como norma já publicada. ([iso.org](https://www.iso.org/cms/%20render/live/en/sites/isoorg/contents/data/standard/07/20/72089.html?utm_source=openai))

---

## 4.2. Catálogo de requisitos não funcionais

**Classificação:** essencial  
**Dono sugerido:** arquitetura e engenharia, com segurança, operações e negócio  
**Quando criar:** antes das decisões técnicas relevantes.

Descreve **como a solução deve se comportar** e quais restrições deve respeitar.

### Categorias a considerar

- Desempenho e tempo de resposta.
- Disponibilidade.
- Capacidade e crescimento.
- Segurança.
- Privacidade.
- Acessibilidade.
- Observabilidade.
- Recuperação e continuidade.
- Manutenibilidade.
- Interoperabilidade.
- Compatibilidade.
- Retenção e exclusão de dados.
- Custos operacionais.
- Restrições tecnológicas.

### Exemplo verificável

> Em condições normais e com até 500 usuários simultâneos, 95% das consultas de proposta devem responder em até dois segundos.

Esse número é apenas **ilustrativo**. Os limites reais devem vir de necessidades de negócio, capacidade e acordos do projeto.

---

## 4.3. Matriz de rastreabilidade

**Classificação:** essencial em alguma forma; maior formalidade em projetos críticos  
**Dono sugerido:** análise, qualidade ou gestão do projeto  
**Quando criar:** conforme os requisitos são detalhados.

Conecta objetivos e requisitos às entregas e evidências.

| Objetivo | Requisito | Regra | Implementação | Teste | Evidência |
|---|---|---|---|---|---|
| Reduzir tempo de aprovação | RF-012 | RN-014 | Serviço de propostas | CT-031 | Resultado da execução |

### O que deve permitir responder

- Qual requisito atende a determinado objetivo?
- Onde uma regra foi implementada?
- Qual teste comprova o comportamento?
- Quais itens serão afetados por uma mudança?
- Quais requisitos ainda não possuem validação?

Em ferramentas modernas, essa matriz pode ser montada a partir de **links entre itens**, sem necessariamente manter uma planilha manual.

---

# 5. Arquitetura e desenho da solução

## 5.1. Documento de arquitetura da solução

**Classificação:** essencial  
**Dono sugerido:** arquiteto de solução ou liderança técnica  
**Quando criar:** antes das principais decisões de construção; atualizar conforme a solução evolui.

Descreve a estrutura da solução e explica como ela atende aos requisitos e restrições.

### Conteúdo recomendado

- Contexto e objetivos da solução.
- Sistemas internos e externos envolvidos.
- Componentes e suas responsabilidades.
- Fluxos principais.
- Integrações.
- Dados e armazenamento.
- Ambientes e infraestrutura.
- Segurança e limites de confiança.
- Estratégia de implantação.
- Requisitos não funcionais e como serão atendidos.
- Dependências e riscos.
- Premissas e decisões arquiteturais.
- Questões em aberto.

### Visões úteis

1. **Contexto:** solução, usuários e sistemas externos.
2. **Componentes:** principais serviços e responsabilidades.
3. **Fluxos:** sequências importantes, inclusive falhas.
4. **Implantação:** ambientes e infraestrutura.
5. **Dados:** onde são produzidos, armazenados e compartilhados.

---

## 5.2. Registros de decisão arquitetural — ADRs

**Classificação:** essencial para decisões relevantes  
**Dono sugerido:** liderança técnica ou arquitetura  
**Quando criar:** quando uma decisão importante for tomada ou alterada.

Um ADR registra não apenas a escolha, mas também **por que ela foi feita**.

### Estrutura recomendada

- Identificador e título.
- Data e situação.
- Contexto.
- Problema.
- Alternativas consideradas.
- Decisão.
- Justificativa.
- Consequências e compromissos.
- Responsáveis.
- Relação com outros ADRs.

### Exemplo de tema

> Utilizar mensageria assíncrona para processar notificações de aprovação.

O ADR deve registrar, por exemplo, os efeitos sobre confiabilidade, reprocessamento, custo e complexidade.

---

## 5.3. Especificação técnica detalhada

**Classificação:** condicional, conforme complexidade ou risco  
**Dono sugerido:** liderança técnica ou equipe responsável pela implementação  
**Quando criar:** antes da construção de componentes complexos.

### Conteúdo recomendado

- Objetivo do componente.
- Responsabilidades e limites.
- Fluxos e sequências.
- Algoritmos ou cálculos críticos.
- Estruturas de dados.
- Tratamento de erros.
- Concorrência, idempotência e reprocessamento.
- Dependências.
- Requisitos de segurança e desempenho.
- Estratégia de testes.
- Observabilidade.
- Pontos de extensão e restrições.

Não é necessário produzir uma especificação extensa para toda alteração simples. Para componentes críticos, ela ajuda a reduzir ambiguidades.

---

## 5.4. Contratos de APIs, eventos e integrações

**Classificação:** essencial quando houver integração  
**Dono sugerido:** equipe proprietária da interface  
**Quando criar:** antes ou em conjunto com o desenvolvimento da integração.

### Conteúdo recomendado

- Objetivo e responsável.
- Consumidores e produtores.
- Operações disponíveis.
- Formatos de entrada e saída.
- Campos obrigatórios e opcionais.
- Regras de validação.
- Autenticação e autorização.
- Códigos e tratamento de erros.
- Limites de uso.
- Versionamento e compatibilidade.
- Tempo limite, tentativas e idempotência.
- Exemplos.
- Política de descontinuação.
- Eventos publicados e garantias esperadas, quando aplicável.

Para APIs, a especificação pode ser mantida em formato legível por máquina, como **OpenAPI**, além de documentação explicativa.

---

## 5.5. Arquitetura de infraestrutura e plataforma

**Classificação:** essencial; pode ser incorporada ao documento de arquitetura  
**Dono sugerido:** infraestrutura, plataforma ou arquitetura  
**Quando criar:** antes da preparação dos ambientes.

### Conteúdo recomendado

- Ambientes e finalidade de cada um.
- Serviços de infraestrutura utilizados.
- Redes e conectividade.
- Identidades e permissões.
- Gestão de segredos.
- Configuração e provisionamento.
- Escalabilidade.
- Backup e recuperação.
- Monitoramento.
- Dependências de fornecedores.
- Estimativa e controle de custos.
- Responsabilidades entre equipes.

---

# 6. Dados, privacidade e governança

## 6.1. Modelo de dados e dicionário

**Classificação:** essencial quando houver dados persistidos ou compartilhados  
**Dono sugerido:** arquitetura de dados ou equipe técnica  
**Quando criar:** durante o desenho; manter conforme o modelo evolui.

### Conteúdo recomendado

- Entidades e relacionamentos.
- Definição de campos.
- Tipos e formatos.
- Obrigatoriedade.
- Regras de validação.
- Chaves e identificadores.
- Origem e destino.
- Classificação de sensibilidade.
- Responsável pelo dado.
- Retenção e descarte.
- Restrições de uso.

**Atenção:** o dicionário deve explicar o **significado de negócio** dos dados, não apenas o tipo técnico da coluna.

---

## 6.2. Mapeamento do fluxo e tratamento de dados

**Classificação:** essencial para sistemas que tratam dados relevantes; especialmente importante para dados pessoais  
**Dono sugerido:** responsável por dados ou privacidade, com apoio técnico  
**Quando criar:** antes de definir integrações e controles de tratamento.

### Conteúdo recomendado

- Dados coletados ou recebidos.
- Origem e finalidade.
- Sistemas e fornecedores envolvidos.
- Armazenamento e compartilhamento.
- Acessos e perfis autorizados.
- Transferências entre ambientes ou organizações.
- Retenção e exclusão.
- Medidas de proteção.
- Responsáveis pelo tratamento.
- Riscos identificados.

---

## 6.3. Avaliação de privacidade e RIPD

**Classificação:** condicional, conforme tratamento, risco e exigências aplicáveis  
**Dono sugerido:** controlador e área responsável por privacidade, com participação do encarregado e das equipes técnicas  
**Quando criar:** preferencialmente antes do tratamento de maior risco.

### Conteúdo recomendado

- Descrição e finalidade do tratamento.
- Tipos de dados e titulares envolvidos.
- Operações realizadas.
- Necessidade e proporcionalidade.
- Riscos para direitos e liberdades dos titulares.
- Medidas de segurança e mitigação.
- Risco residual.
- Responsáveis e decisões.
- Revisões e aprovação.

**Se a LGPD brasileira se aplicar:** a ANPD recomenda elaborar o RIPD antes de tratamentos que possam gerar alto risco e informa que ele deve ser elaborado quando solicitado pela autoridade. Isso **não significa que todo projeto de TI precise automaticamente de um RIPD**. A aplicabilidade deve ser analisada com a área de privacidade e jurídica. ([gov.br](https://www.gov.br/anpd/pt-br/canais_atendimento/agente-de-tratamento/relatorio-de-impacto-a-protecao-de-dados-pessoais-ripd?trk=article-ssr-frontend-pulse_x-social-details_comments-action_comment-text&utm_source=openai))

---

## 6.4. Plano de migração e qualidade de dados

**Classificação:** condicional, quando houver migração, carga inicial ou consolidação de dados  
**Dono sugerido:** equipe de dados e responsável pelo sistema de origem  
**Quando criar:** antes da implantação e dos ensaios de migração.

### Conteúdo recomendado

- Sistemas e bases de origem e destino.
- Mapeamento de campos.
- Transformações.
- Regras de saneamento.
- Critérios de qualidade.
- Volumetria.
- Sequência de cargas.
- Validação e reconciliação.
- Tratamento de registros rejeitados.
- Plano de retorno.
- Responsáveis e janela de execução.
- Evidências de ensaio.

---

# 7. Segurança e conformidade

## 7.1. Requisitos e plano de segurança

**Classificação:** essencial  
**Dono sugerido:** segurança da informação, com arquitetura e engenharia  
**Quando criar:** desde a concepção.

### Conteúdo recomendado

- Classificação da solução e dos dados.
- Requisitos de autenticação e autorização.
- Proteção de dados em trânsito e armazenamento.
- Gestão de segredos e credenciais.
- Registros de auditoria.
- Gestão de vulnerabilidades.
- Segurança de dependências.
- Proteção dos ambientes de desenvolvimento.
- Requisitos para fornecedores.
- Testes de segurança.
- Exceções aprovadas e responsáveis.
- Critérios para entrada em produção.

O NIST SSDF recomenda integrar práticas de desenvolvimento seguro ao ciclo de vida e manter rastreáveis requisitos, riscos e decisões de segurança. ([csrc.nist.gov](https://csrc.nist.gov/projects/ssdf?utm_source=openai))

---

## 7.2. Modelo de ameaças

**Classificação:** essencial para soluções expostas, sensíveis ou críticas; versão simplificada nos demais casos  
**Dono sugerido:** segurança e arquitetura  
**Quando criar:** antes de consolidar o desenho técnico; revisar após mudanças relevantes.

### Conteúdo recomendado

- Ativos que precisam de proteção.
- Componentes e fluxos.
- Pontos de entrada.
- Limites de confiança.
- Ameaças e cenários de abuso.
- Impacto e probabilidade estimados.
- Controles existentes e planejados.
- Riscos residuais.
- Responsáveis e prazos.

### Exemplo de ameaça

> Um usuário autenticado tenta acessar propostas de outro cliente alterando um identificador na requisição.

---

## 7.3. Registro de vulnerabilidades, riscos e exceções

**Classificação:** essencial  
**Dono sugerido:** segurança e equipes proprietárias dos componentes  
**Quando criar:** durante o desenvolvimento e manter na operação.

### Conteúdo recomendado

- Vulnerabilidade ou risco.
- Componente afetado.
- Origem da identificação.
- Severidade e contexto de exploração.
- Impacto.
- Responsável.
- Prazo de correção.
- Medida temporária.
- Decisão de aceite, quando aplicável.
- Data de revisão e evidência de resolução.

---

## 7.4. Inventário de componentes de software — SBOM

**Classificação:** recomendado para aplicações distribuídas ou com dependências relevantes; pode ser exigido por contrato ou norma aplicável  
**Dono sugerido:** engenharia, plataforma ou segurança  
**Quando criar:** nas compilações ou versões relevantes; atualizar automaticamente quando possível.

O SBOM é um inventário estruturado de componentes de software e suas dependências.

### Conteúdo recomendado

- Componentes e versões.
- Identificadores.
- Produtores ou fornecedores.
- Relações entre dependências.
- Autor e data de geração do inventário.
- Informações adicionais úteis para análise de vulnerabilidades e licenças.

A CISA descreve elementos mínimos para um SBOM processável por máquina, incluindo dados para identificação dos componentes e suas relações. ([cisa.gov](https://www.cisa.gov/sites/default/files/2025-08/2025_CISA_SBOM_Minimum_Elements.pdf?utm_source=openai))

---

## 7.5. Matriz de conformidade

**Classificação:** condicional; essencial em ambientes regulados ou com obrigações contratuais relevantes  
**Dono sugerido:** conformidade, jurídico e segurança  
**Quando criar:** na descoberta; revisar até a operação.

### Conteúdo recomendado

- Exigência aplicável.
- Fonte da exigência.
- Avaliação de aplicabilidade.
- Controle necessário.
- Responsável.
- Evidência.
- Situação.
- Lacunas e plano de ação.
- Data da última revisão.

---

# 8. Construção, qualidade e testes

## 8.1. Guia de desenvolvimento e contribuição

**Classificação:** essencial; pode ser compartilhado por vários projetos  
**Dono sugerido:** liderança técnica ou engenharia de plataforma  
**Quando criar:** antes ou no início da construção.

### Conteúdo recomendado

- Como configurar o ambiente local.
- Como executar a aplicação.
- Organização do repositório.
- Padrões de código.
- Estratégia de branches ou fluxo de alterações.
- Revisão de código.
- Execução de testes.
- Padrões de segurança.
- Gestão de dependências.
- Como propor mudanças.
- Responsáveis e canais de suporte.

Esse conteúdo costuma ficar próximo ao código, por exemplo, no `README` e em guias do repositório.

---

## 8.2. Estratégia e plano de testes

**Classificação:** essencial  
**Dono sugerido:** qualidade e engenharia  
**Quando criar:** antes da construção das capacidades críticas.

### Conteúdo recomendado

- Objetivos e riscos de qualidade.
- Escopo e itens fora do escopo.
- Tipos e níveis de teste.
- Responsabilidades.
- Ambientes e dados de teste.
- Critérios de entrada e saída.
- Automação prevista.
- Gestão de defeitos.
- Evidências.
- Testes de regressão.
- Tratamento de riscos residuais.

### Tipos que podem ser necessários

- Unitários.
- Integração e contrato.
- Funcionais.
- Ponta a ponta.
- Aceitação do usuário.
- Segurança.
- Desempenho e carga.
- Acessibilidade.
- Recuperação e continuidade.
- Migração e reconciliação.

A profundidade depende dos riscos. Não é necessário executar todos os tipos para toda alteração.

---

## 8.3. Casos de teste, resultados e defeitos

**Classificação:** essencial para comportamentos críticos; proporcional para os demais  
**Dono sugerido:** qualidade, engenharia e negócio  
**Quando criar:** junto com os requisitos e a implementação.

### Conteúdo recomendado para cada cenário

- Identificador.
- Requisito ou risco relacionado.
- Pré-condições.
- Dados de entrada.
- Passos ou ação executada.
- Resultado esperado.
- Resultado obtido.
- Evidência.
- Situação.
- Defeito associado, quando houver.

**Formato:** casos automatizados podem ser registrados no próprio código; testes manuais e de aceitação podem estar em ferramenta de gestão ou outro repositório adequado.

---

## 8.4. Registro de aceite de negócio e aceite técnico

**Classificação:** essencial antes de marcos relevantes de entrada em produção  
**Dono sugerido:** negócio para aceite funcional; tecnologia e segurança para prontidão técnica  
**Quando criar:** após as validações previstas.

### Conteúdo recomendado

- Entrega ou versão avaliada.
- Critérios de aceite.
- Testes executados e resultados.
- Pendências conhecidas.
- Riscos residuais.
- Decisão: aprovado, aprovado com ressalvas ou não aprovado.
- Responsáveis pela decisão.
- Data.
- Condições para implantação ou correção posterior.

O aceite **não deve ocultar defeitos conhecidos**: eles precisam estar registrados com responsáveis e prazos.

---

# 9. Implantação, operação e continuidade

## 9.1. Plano de implantação e retorno

**Classificação:** essencial  
**Dono sugerido:** engenharia, operações ou responsável pela implantação  
**Quando criar:** antes de cada implantação relevante.

### Conteúdo recomendado

- Versão e itens incluídos.
- Pré-requisitos.
- Janela e responsáveis.
- Sequência de implantação.
- Configurações necessárias.
- Migração de dados.
- Validações antes e depois da implantação.
- Comunicação às áreas afetadas.
- Critérios para interromper a implantação.
- Estratégia de retorno ou correção.
- Tempo estimado e dependências.
- Contatos de apoio.

**Ponto importante:** nem toda mudança permite retorno simples, sobretudo após migração de dados. Essa limitação precisa ser registrada e ensaiada.

---

## 9.2. Evidências de entrega e implantação

**Classificação:** essencial; preferencialmente automatizada  
**Dono sugerido:** equipe de engenharia ou plataforma  
**Quando criar:** a cada versão relevante.

### Conteúdo recomendado

- Código ou alteração incluída.
- Versão ou artefato implantado.
- Resultado dos testes e verificações.
- Aprovações necessárias.
- Ambiente de destino.
- Data e responsável ou mecanismo de implantação.
- Resultado da implantação.
- Exceções e falhas.
- Referência ao SBOM e outras evidências, quando aplicável.

---

## 9.3. Manual operacional e runbooks

**Classificação:** essencial para produção  
**Dono sugerido:** equipe proprietária do serviço, operações ou confiabilidade  
**Quando criar:** antes da transferência para operação.

O manual explica **como operar e manter**; os runbooks detalham **como agir em situações específicas**.

### Conteúdo recomendado

- Visão do serviço e seus componentes.
- Dono técnico e contatos.
- Dependências.
- Como iniciar, parar e verificar o serviço.
- Painéis e alertas.
- Procedimentos de manutenção.
- Problemas conhecidos.
- Diagnóstico de falhas.
- Reprocessamento.
- Gestão de acesso.
- Escalonamento.
- Links para arquitetura, contratos e procedimentos de recuperação.

---

## 9.4. Plano de observabilidade e níveis de serviço

**Classificação:** essencial para serviços em produção  
**Dono sugerido:** engenharia e operações, com validação do negócio  
**Quando criar:** antes da entrada em produção.

### Conteúdo recomendado

- Indicadores de funcionamento e experiência.
- Métricas, logs e rastreamento necessários.
- Eventos de negócio relevantes.
- Painéis.
- Alertas e responsáveis.
- Limites de alerta.
- Objetivos de nível de serviço.
- Procedimentos de resposta.
- Proteção e retenção de registros.
- Como identificar impactos em dependências.

### Exemplo

> Medir a proporção de propostas que concluem o processamento dentro do tempo acordado.

Defina metas e fórmulas de medição específicas para o contexto, em vez de adotar percentuais genéricos.

---

## 9.5. Plano de resposta a incidentes e comunicação

**Classificação:** essencial para produção  
**Dono sugerido:** operações e segurança, com participação das áreas de negócio  
**Quando criar:** antes da entrada em produção.

### Conteúdo recomendado

- Como identificar e classificar incidentes.
- Papéis e responsabilidades.
- Critérios de acionamento e escalonamento.
- Contatos.
- Procedimentos de contenção e recuperação.
- Comunicação interna e externa.
- Preservação de evidências.
- Tratamento de incidentes de segurança e privacidade.
- Registro de decisões.
- Análise posterior e ações corretivas.

---

## 9.6. Plano de continuidade, backup e recuperação

**Classificação:** essencial para serviços relevantes; profundidade proporcional à criticidade  
**Dono sugerido:** operações, infraestrutura e negócio  
**Quando criar:** antes da entrada em produção; testar periodicamente.

### Conteúdo recomendado

- Cenários de indisponibilidade.
- Impactos de negócio.
- Dependências críticas.
- Objetivo de tempo de recuperação — **RTO**.
- Objetivo de perda máxima de dados — **RPO**.
- Estratégia de backup.
- Procedimento de restauração.
- Alternativas operacionais.
- Responsáveis e contatos.
- Ensaios, resultados e melhorias.

**Backup sem teste de restauração não é evidência suficiente de recuperação.**

---

## 9.7. Materiais de suporte, treinamento e adoção

**Classificação:** essencial quando o produto altera a rotina dos usuários  
**Dono sugerido:** negócio, suporte e gestão de mudanças  
**Quando criar:** antes da implantação.

### Conteúdo recomendado

- Guias por perfil de usuário.
- Perguntas frequentes.
- Fluxos principais e exceções.
- Orientações de acesso.
- Materiais de treinamento.
- Canais de suporte.
- Procedimento de abertura de chamados.
- Comunicação de mudanças.
- Plano de acompanhamento da adoção.

---

## 9.8. Plano de descontinuação e encerramento

**Classificação:** condicional no início; necessário quando houver substituição ou retirada de serviço  
**Dono sugerido:** responsável pelo produto e operação  
**Quando criar:** quando houver decisão de desativação.

### Conteúdo recomendado

- Sistemas, usuários e contratos afetados.
- Comunicação e prazos.
- Migração ou exportação de dados.
- Retenção e descarte aplicáveis.
- Desativação de acessos e integrações.
- Encerramento de infraestrutura e custos.
- Evidências de conclusão.
- Responsáveis e riscos residuais.

---

# 10. Gestão e governança do projeto

## 10.1. Termo de abertura e governança

**Classificação:** essencial; pode ser simples  
**Dono sugerido:** patrocinador e gestor do projeto  
**Quando criar:** no início.

### Conteúdo recomendado

- Objetivo.
- Escopo inicial.
- Patrocinador.
- Responsáveis.
- Limites de orçamento e prazo.
- Premissas e restrições.
- Principais riscos.
- Fóruns de decisão.
- Critérios de sucesso.
- Autoridade para aprovar mudanças.

---

## 10.2. Matriz de responsabilidades e partes interessadas

**Classificação:** essencial  
**Dono sugerido:** gestor do projeto ou produto  
**Quando criar:** no início; revisar quando a equipe mudar.

### Conteúdo recomendado

- Partes interessadas.
- Responsabilidades de cada papel.
- Responsáveis por aprovar requisitos, arquitetura, segurança e implantação.
- Canais de comunicação.
- Frequência de acompanhamento.
- Caminho de escalonamento.

Uma matriz RACI pode ajudar, mas o importante é que não haja dúvidas sobre **quem decide e quem executa**.

---

## 10.3. Registro de riscos, premissas, problemas e dependências

**Classificação:** essencial  
**Dono sugerido:** gestão do projeto ou produto  
**Quando criar:** no início; revisar continuamente.

### Conteúdo recomendado

- Descrição.
- Categoria: risco, premissa, problema ou dependência.
- Impacto.
- Probabilidade, quando for risco.
- Responsável.
- Plano de resposta.
- Data necessária.
- Situação.
- Decisões relacionadas.

---

## 10.4. Plano de orçamento, fornecedores e contratos

**Classificação:** essencial quando houver investimento ou contratação relevante  
**Dono sugerido:** gestor do projeto, compras e responsável financeiro  
**Quando criar:** antes dos compromissos financeiros.

### Conteúdo recomendado

- Custos de construção.
- Custos recorrentes de infraestrutura, licenças e suporte.
- Premissas de consumo.
- Fornecedores e responsabilidades.
- Entregáveis contratuais.
- Níveis de serviço acordados.
- Obrigações de segurança e dados.
- Critérios de aceite.
- Dependências e riscos.
- Estratégia de saída ou substituição do fornecedor.

---

## 10.5. Registro de decisões e mudanças de escopo

**Classificação:** essencial  
**Dono sugerido:** gestão do projeto, produto ou responsável pela decisão  
**Quando criar:** continuamente.

### Conteúdo recomendado

- Decisão ou mudança proposta.
- Motivo.
- Alternativas consideradas.
- Impactos em prazo, custo, risco e escopo.
- Responsáveis consultados.
- Aprovador.
- Data.
- Artefatos que precisam ser atualizados.

Decisões arquiteturais importantes podem ser registradas em ADRs e referenciadas aqui, sem duplicar o conteúdo.

---

# 11. Documentação adicional quando houver IA

É importante separar dois cenários:

1. **IA usada pela equipe para desenvolver:** por exemplo, assistentes de código ou agentes de engenharia.
2. **IA como parte do produto:** por exemplo, um agente que responde clientes ou recomenda decisões.

Os dois exigem controles, mas o segundo normalmente requer documentação adicional sobre o comportamento entregue ao usuário.

## 11.1. Política de uso de IA no desenvolvimento

**Classificação:** condicional; recomendada quando a equipe utiliza IA  
**Dono sugerido:** engenharia, segurança e governança  
**Quando criar:** antes de ampliar o uso de ferramentas de IA.

### Conteúdo recomendado

- Ferramentas autorizadas.
- Tipos de dados e código que podem ou não ser enviados.
- Requisitos de revisão humana.
- Cuidados com credenciais e dados pessoais.
- Verificação de código, dependências e licenças.
- Registro de uso em atividades sensíveis.
- Permissões concedidas a agentes.
- Limites para alterações automáticas e implantação.
- Procedimentos para incidentes.

O Gartner aponta a expansão de ferramentas e agentes de IA por diferentes etapas do SDLC. Já a pesquisa DORA de 2025 apresenta a IA como um amplificador das condições existentes na organização — o que reforça a necessidade de fundamentos, controles e medição, não apenas adoção de ferramentas. ([gartner.com](https://www.gartner.com/en/documents/7361230?utm_source=openai))

---

## 11.2. Ficha do componente ou funcionalidade de IA

**Classificação:** condicional, quando o produto incorpora IA  
**Dono sugerido:** responsável pelo produto de IA e equipe técnica  
**Quando criar:** antes da liberação da funcionalidade.

### Conteúdo recomendado

- Finalidade e usuários.
- Modelo ou serviço utilizado e sua versão.
- Entradas e saídas.
- Fontes de conhecimento e dados utilizados.
- Integrações e ferramentas disponíveis ao agente.
- Limitações conhecidas.
- Riscos de respostas incorretas ou inadequadas.
- Permissões e ações permitidas.
- Necessidade de supervisão humana.
- Proteção de dados.
- Custos e limites de consumo.
- Responsável pelo componente.

---

## 11.3. Plano de avaliação e monitoramento de IA

**Classificação:** condicional, quando o produto incorpora IA  
**Dono sugerido:** equipe de IA, produto, qualidade e segurança  
**Quando criar:** antes da liberação; manter durante a operação.

### Conteúdo recomendado

- Casos de uso e cenários de falha.
- Conjunto de exemplos de avaliação.
- Critérios de qualidade e segurança.
- Testes para instruções maliciosas e uso indevido, quando pertinentes.
- Avaliação de respostas incorretas.
- Monitoramento de comportamento e custo.
- Critérios para revisão humana.
- Procedimento para alterar modelo, instruções ou fontes.
- Gestão de incidentes.
- Evidências das avaliações.

O NIST também disponibiliza um perfil do SSDF voltado a práticas de desenvolvimento seguro para IA generativa e modelos de base. ([csrc.nist.gov](https://csrc.nist.gov/projects/ssdf?utm_source=openai))

---

# 12. Qual é o pacote mínimo que eu exigiria?

Para um projeto de complexidade média, com sistema em produção, eu começaria com os seguintes **12 conjuntos**. Eles podem ser arquivos, páginas, itens de ferramenta ou registros automatizados.

| Nº | Conjunto mínimo | Pode reunir |
|---:|---|---|
| 1 | Visão e justificativa | Problema, objetivos, benefícios e decisão de investimento |
| 2 | Processos, regras e glossário | Fluxos atual/futuro e regras de negócio |
| 3 | Visão de produto e roadmap | Público, proposta de valor, métricas e entregas |
| 4 | Backlog e requisitos | Requisitos funcionais, critérios de aceite e prioridades |
| 5 | Requisitos não funcionais | Segurança, desempenho, disponibilidade e demais atributos |
| 6 | Arquitetura e decisões | Diagramas, integrações, infraestrutura e ADRs |
| 7 | Dados e privacidade | Modelo, dicionário, fluxos e avaliação de privacidade aplicável |
| 8 | Segurança e riscos | Ameaças, controles, vulnerabilidades e exceções |
| 9 | Estratégia e evidências de testes | Testes, defeitos, resultados e aceite |
| 10 | Implantação | Plano de implantação, validação e retorno |
| 11 | Operação e continuidade | Manual, monitoramento, incidentes, backup e recuperação |
| 12 | Governança e rastreabilidade | Responsáveis, riscos, decisões, dependências e vínculos |

**Acrescente conforme o contexto:** contratos de integração, migração, conformidade regulatória, SBOM, treinamento, fornecedores e documentação de IA.

---

# 13. Exemplo de rastreabilidade de ponta a ponta

Imagine um projeto para automatizar a aprovação de crédito:

```text
Objetivo de negócio
Reduzir o tempo de aprovação de 48 para 12 horas
        ↓
Processo futuro
Receber proposta, consultar dados, avaliar e comunicar decisão
        ↓
Regra de negócio
Propostas expiradas não podem ser aprovadas
        ↓
Requisito funcional
RF-012 — Impedir aprovação de proposta expirada
        ↓
Critério de aceite
Bloquear a ação e apresentar o motivo ao usuário
        ↓
Arquitetura e contrato
Serviço de propostas + API de aprovação
        ↓
Implementação e teste
Alteração no serviço + CT-031
        ↓
Implantação
Versão identificada, validação e plano de retorno
        ↓
Operação
Monitorar falhas de aprovação e tempo de processamento
        ↓
Resultado
Medir se o tempo médio de aprovação diminuiu
```

O benefício dessa estrutura é que uma mudança na regra pode ser rastreada até telas, APIs, testes, materiais de treinamento e operação.

---

# 14. Estrutura sugerida para organizar tudo

Uma estrutura possível em repositório ou plataforma de documentação seria:

```text
projeto/
├── 01-negocio/
│   ├── visao-e-justificativa
│   ├── processos
│   ├── regras-de-negocio
│   └── glossario
├── 02-produto/
│   ├── visao-do-produto
│   ├── pesquisas-e-jornadas
│   ├── roadmap
│   └── requisitos
├── 03-arquitetura/
│   ├── arquitetura-da-solucao
│   ├── decisoes-arquiteturais
│   ├── integracoes
│   └── infraestrutura
├── 04-dados-e-privacidade/
│   ├── modelo-e-dicionario
│   ├── fluxos-de-dados
│   └── avaliacoes-de-privacidade
├── 05-seguranca/
│   ├── requisitos
│   ├── modelo-de-ameacas
│   └── riscos-e-vulnerabilidades
├── 06-qualidade/
│   ├── estrategia-de-testes
│   ├── evidencias
│   └── aceites
├── 07-implantacao-e-operacao/
│   ├── implantacao-e-retorno
│   ├── manual-operacional
│   ├── incidentes
│   └── continuidade
└── 08-governanca/
    ├── responsabilidades
    ├── riscos-e-dependencias
    └── decisoes
```

Essa é uma **organização lógica**, não uma exigência de pastas. Backlog, testes, riscos e evidências podem estar em ferramentas diferentes, desde que sejam localizáveis e vinculados.

## Metadados mínimos para cada artefato

- Nome e objetivo.
- Responsável.
- Situação: rascunho, aprovado, substituído ou obsoleto.
- Data da última revisão.
- Versão ou histórico de alterações.
- Aprovador, quando necessário.
- Links para artefatos relacionados.
- Classificação de acesso, quando houver informação sensível.

---

# 15. Como decidir o nível de documentação

| Contexto | Abordagem recomendada |
|---|---|
| **Protótipo ou prova de conceito** | Visão, hipóteses, escopo limitado, riscos principais e decisão sobre continuidade. |
| **Produto interno simples** | Pacote mínimo simplificado; critérios de aceite, arquitetura básica, testes e operação. |
| **Sistema corporativo com integrações** | Pacote mínimo completo, contratos de integração, dados, segurança e plano de implantação. |
| **Sistema crítico ou regulado** | Maior formalidade, rastreabilidade, evidências de testes, conformidade, continuidade e aprovações. |
| **Produto com IA ou agentes** | Pacote aplicável acima, mais limites de uso, avaliações, monitoramento, segurança e supervisão humana. |

A documentação deve acompanhar o risco: **mais crítica a decisão ou maior seu impacto, mais importante registrar contexto, evidência, responsável e aprovação**.

---

# 16. Principais fontes utilizadas

- **Gartner — planejamento de engenharia de software para 2026:** fundamentos de engenharia, segurança, IA e plataformas. ([gartner.com](https://www.gartner.com/en/documents/6988266?utm_source=openai))
- **Gartner — IA ao longo do SDLC:** evolução de assistentes para ferramentas e agentes aplicados às etapas do ciclo de desenvolvimento. ([gartner.com](https://www.gartner.com/en/documents/7361230?utm_source=openai))
- **Gartner — camada de contexto para agentes de SDLC:** integração de intenção, dependências e informações de engenharia. ([gartner.com](https://www.gartner.com/en/documents/8349217?utm_source=openai))
- **NIST — Secure Software Development Framework:** práticas de desenvolvimento seguro integráveis a diferentes modelos de SDLC. ([nist.gov](https://www.nist.gov/publications/secure-software-development-framework-ssdf-version-11-recommendations-mitigating-risk?utm_source=openai))
- **ISO/IEC/IEEE 29148:** referência para engenharia e informações de requisitos. ([iso.org](https://www.iso.org/cms/%20render/live/en/sites/isoorg/contents/data/standard/07/20/72089.html?utm_source=openai))
- **DORA — pesquisa sobre desenvolvimento assistido por IA:** relação entre adoção de IA e condições organizacionais. ([dora.dev](https://dora.dev/research/2025/dora-report/?utm_source=openai))
- **CISA — elementos mínimos de SBOM:** transparência e identificação de componentes de software. ([cisa.gov](https://www.cisa.gov/sites/default/files/2025-08/2025_CISA_SBOM_Minimum_Elements.pdf?utm_source=openai))
- **ANPD — orientação sobre RIPD:** avaliação e documentação de riscos do tratamento de dados pessoais no contexto brasileiro. ([gov.br](https://www.gov.br/anpd/pt-br/canais_atendimento/agente-de-tratamento/relatorio-de-impacto-a-protecao-de-dados-pessoais-ripd?trk=article-ssr-frontend-pulse_x-social-details_comments-action_comment-text&utm_source=openai))

**Observação sobre as fontes:** parte das pesquisas do Gartner é paga; utilizei as descrições e resumos públicos disponíveis. Normas e guias são referências de boas práticas ou requisitos em seus respectivos contextos — **consultá-los não significa, por si só, que o projeto esteja certificado ou em conformidade**.