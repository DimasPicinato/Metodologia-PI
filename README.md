<!-- markdownlint-disable-file MD025 -->

# Metodologia

Esta documentação detalha a proposta de metodologia de desenvolvimento para o Projeto Integrador do curso de Análise e Desenvolvimento de Sistemas da Fatec Lins - Professor Antonio Seabra. Através de um framework estruturado que integra papéis estratégicos, fluxos de trabalho Kanban e uma infraestrutura de ambientes, este documento responde de forma clara e objetiva: **Quem faz?**, **Como faz?** e **Quando faz?**, garantindo a excelência técnica, a transparência nos processos e a rastreabilidade em todo o ciclo de vida do software.

> Elaborado por **Dimas Picinato**.  
> Data da última atualização: **04/03/2026**.

## Resumo

Esta metodologia estabelece as diretrizes estruturais para o desenvolvimento do projeto integrador, consolidando a organização da equipe por meio de responsabilidades claras para os papéis de Product Owner, Tech Lead, Analista, Designer, DevOps e Desenvolvedores (Seção 2). A gestão ágil é fundamentada em um Kanban Estruturado, que padroniza a tipologia e a estrutura acadêmica dos tickets, além de definir a cronologia técnica exata dos fluxos Operational, Architectural, DevOps, Execution e Development (Seção 3).

O ciclo de vida do software é gerido através de ambientes segregados de Desenvolvimento, Staging, Beta e Produção (Seção 4), integrados a uma estratégia de versionamento via Git e GitHub. Esta estratégia utiliza padrões como Conventional Commits e Semantic Versioning (SemVer), com fluxos de branches sincronizados diretamente aos ambientes e ao quadro Kanban (Seção 5). Por fim, a cadência operacional é mantida por ritos de comunicação que incluem reuniões semanais, a manutenção de um Diário de Bordo para registro histórico e alinhamentos pontuais para garantir a agilidade técnica da equipe (Seção 6).

# Sumário

- [Metodologia](#metodologia)
  - [Resumo](#resumo)
- [Sumário](#sumário)
- [1. Ferramentas](#1-ferramentas)
  - [1.1. Jira](#11-jira)
  - [1.2. GitHub](#12-github)
- [2. Equipe](#2-equipe)
  - [2.1. Product Owner (PO)](#21-product-owner-po)
  - [2.2. Tech Lead](#22-tech-lead)
  - [2.3. Analista](#23-analista)
  - [2.4. Designer](#24-designer)
  - [2.5. DevOps](#25-devops)
  - [2.6. Desenvolvedor (Dev)](#26-desenvolvedor-dev)
- [3. Kanban](#3-kanban)
  - [3.1. Tickets](#31-tickets)
    - [3.1.1. Tipos](#311-tipos)
    - [3.1.2. Estrutura](#312-estrutura)
    - [3.1.3. Atributos e Metadados](#313-atributos-e-metadados)
  - [3.2. Fluxos](#32-fluxos)
    - [3.2.1. Operational](#321-operational)
    - [3.2.2. Architectural](#322-architectural)
    - [3.2.3. DevOps](#323-devops)
    - [3.2.4. Execution](#324-execution)
    - [3.2.5. Development](#325-development)
- [4. Ambientes](#4-ambientes)
  - [4.1. Desenvolvimento](#41-desenvolvimento)
  - [4.2. Staging](#42-staging)
  - [4.3. Beta](#43-beta)
  - [4.4. Produção](#44-produção)
- [5. Versionamento](#5-versionamento)
  - [5.1. Padrão de Commits](#51-padrão-de-commits)
  - [5.2. Versionamento Semântico (SemVer)](#52-versionamento-semântico-semver)
  - [5.3. Fluxo de Branches](#53-fluxo-de-branches)
  - [5.4. Integração CI/CD e Infraestrutura](#54-integração-cicd-e-infraestrutura)
  - [5.5. Integração GitHub x Kanban](#55-integração-github-x-kanban)
- [6. Ritos e Comunicação](#6-ritos-e-comunicação)
  - [6.1. Reunião Semanal de Alinhamento](#61-reunião-semanal-de-alinhamento)
  - [6.2. Diário de Bordo](#62-diário-de-bordo)
  - [6.3. Alinhamentos Pontuais](#63-alinhamentos-pontuais)

# 1. Ferramentas

Nesta seção são descritas as ferramentas utilizadas para organização, controle e execução do processo de desenvolvimento. A adoção de ferramentas padronizadas visa garantir rastreabilidade, colaboração estruturada e controle de qualidade ao longo do ciclo de vida do projeto.

## 1.1. Jira

O [Jira](https://www.atlassian.com/software/jira) é a ferramenta adotada para gestão de tarefas e acompanhamento do fluxo de trabalho do projeto. Nele são registrados requisitos, histórias de usuário, tarefas técnicas, correções de bugs e demais atividades relacionadas ao desenvolvimento.

Sua utilização deve estar estruturada no modelo Kanban, permitindo a visualização do estado das atividades em quadros organizados por etapas do processo. A ferramenta também possibilita definição de responsáveis, prazos, prioridades e critérios de aceite, garantindo rastreabilidade, transparência e controle do andamento do projeto.

## 1.2. GitHub

O [GitHub](https://github.com) é a plataforma utilizada para controle de versão e hospedagem do código-fonte do projeto, baseada no sistema Git. Por meio dela é mantido o repositório central da aplicação, assegurando histórico e integridade das alterações realizadas.

A ferramenta é empregada para gerenciamento de branches, submissão e revisão de pull requests, além de permitir integração com processos de integração contínua (CI). Dessa forma, promove colaboração estruturada, controle de qualidade do código e padronização do processo de entrega.

# 2. Equipe

Nesta seção, são detalhadas as atribuições e responsabilidades de cada função desempenhada pelos membros da equipe durante o ciclo de vida do projeto. A definição clara dos papéis visa otimizar a colaboração, mitigar conflitos de escopo e assegurar que todos os aspectos técnicos, de design e de negócio sejam devidamente atendidos.

![Equipe](<imgs/modelagem de processos-Equipe.jpg>)

## 2.1. Product Owner (PO)

O Product Owner é o responsável pela definição, consolidação e priorização das regras de negócio do sistema. Atua como principal representante das partes interessadas, assegurando que os requisitos funcionais e não funcionais estejam alinhados às necessidades institucionais e aos objetivos do projeto. Compete ao PO validar os artefatos desenvolvidos pela equipe, garantindo aderência às regras estabelecidas, bem como aprovar as entregas parciais e finais. Também é responsável por esclarecer dúvidas relacionadas ao domínio do problema e manter a coerência entre escopo, valor entregue e expectativas dos stakeholders.

## 2.2. Tech Lead

O Tech Lead é o responsável pela liderança técnica do projeto. Sua função consiste em coordenar as decisões arquiteturais, definir padrões de desenvolvimento, estabelecer diretrizes de qualidade e orientar tecnicamente a equipe. É incumbido de detalhar funcionalidades sob a perspectiva técnica, garantindo viabilidade, escalabilidade, segurança e manutenibilidade da solução. Além disso, supervisiona revisões de código, promove boas práticas de engenharia de software e assegura que as implementações estejam alinhadas à arquitetura definida.

## 2.3. Analista

O Analista é responsável pela modelagem conceitual e estrutural do sistema. Atua na elicitação, análise e organização dos requisitos, transformando necessidades de negócio em especificações técnicas compreensíveis pela equipe de desenvolvimento. Elabora os principais artefatos UML, tais como diagramas de casos de uso e classes, além de contribuir para a definição da arquitetura funcional do sistema. Seu papel é garantir consistência entre requisitos, modelagem e implementação.

## 2.4. Designer

O Designer é responsável pela concepção da experiência do usuário e pela definição da identidade visual do sistema. Desenvolve protótipos, define a composição visual das interfaces, estabelece padrões de tipografia, cores e componentes, e assegura a coerência com princípios de usabilidade e acessibilidade. Também formaliza regras de design e diretrizes de interface, promovendo consistência estética e funcional em todo o produto.

## 2.5. DevOps

O profissional de DevOps é responsável pela integração entre desenvolvimento e operações, assegurando a automação, padronização e confiabilidade do ciclo de vida da aplicação. Compete a esse papel configurar e manter ambientes de desenvolvimento, homologação e produção, gerenciar infraestrutura (local ou em nuvem), implementar pipelines de integração e entrega contínua (CI/CD), monitorar desempenho e disponibilidade do sistema, além de garantir práticas adequadas de segurança, backup e recuperação de dados. O DevOps também atua na prevenção e resolução de incidentes, promovendo estabilidade operacional e escalabilidade da solução ao longo do tempo.

## 2.6. Desenvolvedor (Dev)

O Desenvolvedor é responsável pela implementação das funcionalidades do sistema conforme as especificações técnicas e regras de negócio definidas. Sua atuação engloba o desenvolvimento das aplicações front-end e back-end, a modelagem e manipulação do banco de dados, bem como a integração com serviços externos e recursos do servidor. Deve garantir que o código produzido esteja em conformidade com os padrões estabelecidos, priorizando qualidade, desempenho, segurança e manutenibilidade.

# 3. Kanban

Esta seção detalha os artefatos fundamentais utilizados no gerenciamento ágil do projeto: os **Tickets** (unidades de trabalho) e os **Fluxos** (trajetória técnica das atividades).

Para a organização e rastreabilidade, são utilizados quadros Kanban através do Jira, permitindo o gerenciamento do fluxo contínuo de trabalho e a visualização em tempo real das tarefas em progresso.

## 3.1. Tickets

A imagem abaixo representa os tipos de tickets e seus respectivos fluxos:

![Tickets](<imgs/modelagem de processos-Tickets.jpg>)

### 3.1.1. Tipos

Essa seção descreve os tipos de tickets:

- **Epic**: Conjunto macro de funcionalidades relacionadas a um objetivo de negócio específico, organizando demandas e tarefas dentro do fluxo operacional.
- **Design**: Definição de protótipos e diretrizes visuais da funcionalidade, assegurando alinhamento com requisitos e validação da experiência do usuário antes da implementação técnica.
- **Modeling**: Elaboração dos artefatos de modelagem do sistema, como diagramas UML, com o objetivo de representar formalmente os requisitos e orientar a implementação técnica.
- **DevOps**: Preparação e configuração dos ambientes e infraestrutura conforme necessário, viabilizando o início da fase de execução.
- **Feature**: Implementação de nova funcionalidade conforme requisitos e definições técnicas previamente estabelecidas.
- **Change Request**: Alteração formal em requisito, regra de negócio ou comportamento já definido, implicando ajuste controlado no escopo previamente aprovado.
- **Refactory**: Reestruturação ou melhoria de código existente, sem alteração de comportamento funcional, visando qualidade, legibilidade ou desempenho.
- **Bug**: Correção de falha identificada no sistema, restaurando o comportamento esperado conforme especificação.
- **Back-end**: Desenvolvimento das regras de negócio, integrações, APIs, banco de dados e demais componentes do lado servidor, conforme definições técnicas estabelecidas.
- **Front-end**: Desenvolvimento das interfaces, componentes visuais e interações com o usuário, aderindo ao design definido e correta integração com os serviços de back-end.

### 3.1.2. Estrutura

Esta seção define a estrutura padronizada para o detalhamento dos tickets, assegurando que cada unidade de trabalho possua as informações necessárias para sua execução e validação. Alguns campos podem ser opcionais dependendo da complexidade da tarefa:

- **Contexto**: Fundamentação técnica e contextualização da demanda. Deve apresentar claramente os delimitadores de contexto, especificando o que a tarefa deve e, principalmente, o que não deve solucionar.
- **Descrição**: Especificação detalhada dos requisitos funcionais, técnicos e comportamentais esperados.
- **Objetivo**: Definição clara do resultado final a ser alcançado e do valor agregado ao projeto.
- **Critérios de Aceitação**: Parâmetros verificáveis e mensuráveis para validação da conclusão. Inclui exemplos como testes automatizados, aplicação correta das regras de negócio e atendimento a requisitos não funcionais.
- **Referências**: Documentação externa, manuais técnicos ou links de suporte que embasam a execução.
- **Anexos**: Ativos visuais ou técnicos, como diagramas de arquitetura, protótipos de design (Figma), modelos de dados ou referências de inspiração externa.
- **Observações**: Notas suplementares, ressalvas técnicas ou dependências identificadas.

### 3.1.3. Atributos e Metadados

Para uma gestão eficiente do fluxo de trabalho e metrificação do desempenho da equipe, recomenda-se que cada ticket contenha os seguintes atributos de controle:

- **Responsável (Assignee)**: Membro da equipe encarregado da execução da tarefa.
- **Data de Início**: Registro da data efetiva em que o trabalho na tarefa foi iniciado.
- **Estimativa de Entrega**: Prazo previsto para a conclusão da atividade, acordado durante os ritos de planejamento.
- **Story Points**: Unidade de medida que representa a complexidade, esforço e incerteza da tarefa. Utiliza-se geralmente a escala de Fibonacci para essa metrificação.
- **Prioridade**: Definição do nível de urgência e importância da demanda (ex: Baixa, Média, Alta, Crítica).
- **Status**: Estado atual da tarefa no fluxo Kanban, permitindo visibilidade imediata do progresso.

## 3.2. Fluxos

A imagem abaixo representa os fluxos de trabalho dos quadros Kanban do projeto:

![Fluxos](<imgs/modelagem de processos-Fluxos.jpg>)

### 3.2.1. Operational

Fluxo macro destinado à gestão de negócio e coordenação estratégica, onde são gerenciados os tickets do tipo **Epic**.

![Operational](<imgs/modelagem de processos-Operational.jpg>)

A cronologia do fluxo e as responsabilidades são definidas pelos seguintes estados:

- **1. Backlog (Elicitação)**: Identificação e registro inicial de demandas de alto nível (**PO e Tech Lead**).
- **2. Validation**: Análise de viabilidade e valor de negócio (**PO**).
- **3. Architectural**: Definição da estratégia técnica e desdobramento para o fluxo arquitetural (**Tech Lead**).
- **4. DevOps**: Planejamento de infraestrutura necessária (**Tech Lead**).
- **5. Execution**: Monitoramento do ciclo de desenvolvimento das funcionalidades vinculadas (**Tech Lead**).
- **6. Retrospective**: Avaliação dos resultados e lições aprendidas após a conclusão das funcionalidades (**PO e Tech Lead**).
- **7. Deploy**: Realização do merge da branch `beta` para a `main` (Produção) (**DevOps**).
- **8. Completed**: Encerramento formal do épico após a confirmação em produção (**PO**).
- **0. Canceled**: Descontinuidade da demanda por perda de prioridade ou inviabilidade (**PO**).

### 3.2.2. Architectural

Fluxo especializado na concepção técnica, design de interface e modelagem de sistemas, gerindo tickets de **Design** e **Modeling**.

![Architectural](<imgs/modelagem de processos-Architectural.jpg>)

A cronologia técnica segue as etapas:

- **3.1. Backlog**: Levantamento de necessidades de prototipação ou modelagem (**PO e Tech Lead**).
- **3.2. Validation**: Verificação da conformidade com os requisitos de negócio (**Tech Lead**).
- **3.3. To Do**: Autorização para início da elaboração técnica (**Tech Lead**).
- **3.4. Elaboration**: Fase de criação de protótipos ou diagramas UML (**Designer / Analista**).
- **3.5. Validation**: Validação técnica e funcional do artefato gerado (**PO e Tech Lead**).
- **3.6. Completed**: Artefato homologado e pronto para servir de base ao desenvolvimento (**Tech Lead**).
- **3.0. Canceled**: Abandono da proposta de design ou modelagem (**PO e Tech Lead**).

### 3.2.3. DevOps

Fluxo focado na automação de processos, gestão de infraestrutura e manutenção de ambientes, gerindo tickets de **DevOps**.

![DevOps](<imgs/modelagem de processos-DevOps.jpg>)

As etapas operacionais consistem em:

- **4.1. Backlog**: Identificação de necessidades de ambiente, CI/CD ou segurança (**Tech Lead**).
- **4.2. To Do**: Priorização da tarefa de infraestrutura (**Tech Lead**).
- **4.3. Implement**: Execução técnica das configurações e scripts de automação (**DevOps**).
- **4.4. Completed**: Ambiente ou recurso operacional e validado (**Tech Lead**).
- **4.0. Canceled**: Cancelamento da implementação por mudança de estratégia de infra (**Tech Lead**).

### 3.2.4. Execution

Fluxo central que coordena o ciclo de vida das funcionalidades, gerindo tickets de **Feature**, **Bug**, **Change Request** e **Refactory**.

![Execution](<imgs/modelagem de processos-Execution.jpg>)

A trajetória dos tickets é gerenciada pelo Tech Lead, integrando o desenvolvimento técnico:

- **5.1. Backlog**: Triagem e registro de novas demandas de software (**Tech Lead**).
- **5.2. Validation**: Verificação técnica inicial e detalhamento de requisitos (**Tech Lead**).
- **5.3. Development**: Período de codificação ativa, acionando o fluxo 4.2.5 (**Tech Lead**).
- **5.4. Review**: Validação de qualidade e funcionamento pré-deploy (**Tech Lead**).
- **5.5. Deploy**: Realização do merge da branch `staging` para a `beta` (**DevOps**).
- **5.6. Completed**: Funcionalidade entregue e operacional (**Tech Lead**).
- **5.0. Canceled**: Descarte da demanda de execução (**Tech Lead**).

### 3.2.5. Development

Fluxo técnico de nível granular, focado na implementação e testes unitários, gerindo tickets de **Back-end** e **Front-end**.

![Development](<imgs/modelagem de processos-Development.jpg>)

A cronologia técnica de desenvolvimento segue o rigor:

- **5.3.1. Backlog**: Organização técnica das tarefas de código (**Tech Lead**).
- **5.3.2. To Do**: Disponibilização da tarefa para desenvolvimento (**Tech Lead**).
- **5.3.3. Development**: Implementação ativa das regras de negócio ou interfaces (**Desenvolvedor (Dev)**).
- **5.3.4. Test**: Escrita e realização de testes automatizados (**Desenvolvedor (Dev)**).
- **5.3.5. Validation**: Revisão técnica de código (_Code Review_) e validação técnica (**Tech Lead**).
- **5.3.6. Completed**: Código integrado ao repositório principal (**Tech Lead**).
- **5.3.0. Canceled**: Cancelamento da implementação técnica (**Tech Lead**).

# 4. Ambientes

Esta seção descreve os ambientes utilizados ao longo do ciclo de desenvolvimento e disponibilização do sistema. A separação em múltiplos ambientes visa reduzir riscos, assegurar qualidade e permitir validações progressivas antes da liberação definitiva ao usuário final.

## 4.1. Desenvolvimento

O ambiente de Desenvolvimento corresponde ao ambiente local utilizado individualmente por cada desenvolvedor para implementação e testes iniciais das funcionalidades. Trata-se de um ambiente isolado, voltado à codificação, execução de testes unitários e validações técnicas preliminares antes da integração com o restante do sistema.

A padronização desse ambiente deverá ocorrer por meio da utilização de contêineres Docker, permitindo a orquestração dos serviços necessários à aplicação, tais como servidor de aplicação, banco de dados e demais dependências. Essa abordagem visa garantir uniformidade entre os ambientes dos diferentes desenvolvedores, reduzir conflitos de configuração e facilitar a replicação do sistema.

Alternativamente, o ambiente de Staging poderá ser utilizado para testes durante o desenvolvimento, desde que não haja conflito com o trabalho simultâneo de outros membros da equipe. Nesses casos, deve-se assegurar que as alterações não comprometam a estabilidade temporária do ambiente compartilhado nem interfiram nas validações em andamento.

## 4.2. Staging

O ambiente de Staging consiste em um ambiente interno, temporário e restrito à equipe de desenvolvimento, destinado à integração contínua das funcionalidades implementadas e à realização de testes técnicos preliminares.

Trata-se de um ambiente de natureza efêmera, não havendo garantia de persistência de dados ao longo do tempo. As bases de dados podem ser reinicializadas, sobrescritas ou descartadas conforme a necessidade do processo de desenvolvimento. Em razão de sua finalidade experimental, também não há garantia de estabilidade contínua, podendo ocorrer indisponibilidades ou inconsistências decorrentes de testes, ajustes estruturais e validações técnicas.

Nesse ambiente são realizadas validações de integração entre módulos, testes de regressão, verificação de consistência estrutural do banco de dados e demais procedimentos técnicos prévios à disponibilização para validação ampliada. Não se destina ao uso por stakeholders externos.

A responsabilidade por sua configuração, manutenção e disponibilidade é da equipe de desenvolvimento. A infraestrutura poderá ser provisionada conforme decisão conjunta entre equipe e stakeholders, ficando a critério destes a disponibilização do servidor.

## 4.3. Beta

O ambiente Beta é destinado à validação funcional do sistema por todos os stakeholders, incluindo equipe e clientes. Sua finalidade é permitir testes em condições próximas às reais de uso, possibilitando identificação de inconsistências, falhas de usabilidade e ajustes finais antes da liberação oficial.

Diferentemente do Staging, o ambiente Beta deve apresentar maior estabilidade e garantir persistência dos dados durante o período de validação, ainda que não possua o mesmo nível de robustez do ambiente de Produção.

Este ambiente deve se assemelhar ao máximo ao ambiente de Produção, tanto em configuração quanto em arquitetura, a fim de reduzir discrepâncias entre testes e operação real.

A responsabilidade técnica por sua implantação, configuração e manutenção é da equipe de desenvolvimento. Assim como no Staging, a disponibilização da infraestrutura poderá depender de definição conjunta entre equipe e stakeholders.

## 4.4. Produção

O ambiente de Produção corresponde ao ambiente oficial e definitivo do sistema, destinado ao uso real pelos usuários finais.

Diferentemente dos demais ambientes, sua infraestrutura deverá ser disponibilizada pelo cliente, que também será responsável por sua manutenção, custos operacionais e garantia de disponibilidade. A equipe de desenvolvimento poderá prestar suporte técnico conforme acordado, porém não será responsável direta pela gestão da infraestrutura produtiva.

Este ambiente deve assegurar estabilidade, segurança, desempenho adequado, persistência de dados e conformidade com as exigências institucionais estabelecidas para o projeto.

# 5. Versionamento

Esta seção descreve a estratégia de versionamento de código adotada para os repositórios de back-end e front-end, garantindo rastreabilidade, padronização e automação no ciclo de entrega.

## 5.1. Padrão de Commits

O projeto adota a especificação [Conventional Commits](https://www.conventionalcommits.org/en/v1.0.0/), que fornece um conjunto de regras para criar um histórico de commit explícito. Cada commit deve seguir a estrutura: `<tipo>(<escopo>): <descrição>`.

- **Tipos principais:**
  - `feat`: Uma nova funcionalidade ou mudança em uma já existente.
  - `fix`: Uma correção de bug.
  - `docs`: Alterações na documentação.
  - `style`: Alterações que não afetam o sentido do código (espaço em branco, formatação, etc).
  - `refactor`: Alteração de código que não corrige um bug nem adiciona uma funcionalidade.
  - `test`: Adição de testes ausentes ou correção de testes existentes.
  - `chore`: Atualizações de tarefas de build, configurações de pacotes, etc.

**Exemplos:**

- `feat(auth): implementação da validação de JWT`
- `fix(api): correção de vazamento de memória na rota de usuários`
- `docs(readme): atualização das instruções de versionamento`

## 5.2. Versionamento Semântico (SemVer)

O controle de versões baseia-se no [Semantic Versioning 2.0.0](https://semver.org/). A numeração segue o formato `MAJOR.MINOR.PATCH`:

- **MAJOR**: Quando há mudanças incompatíveis na API.
- **MINOR**: Quando são adicionadas funcionalidades compatíveis com versões anteriores.
- **PATCH**: Quando são feitas correções de bugs compatíveis com versões anteriores.

> [!IMPORTANT]
> A declaração da versão (Tag/Release) ocorre exclusivamente na branch `main`, uma vez que esta representa o artefato final entregue ao cliente.
>
> **Exemplo de Ciclo:** `1.0.0` (Lançamento) -> `1.0.1` (Correção) -> `1.1.0` (Nova Feature).

## 5.3. Fluxo de Branches

A estratégia de ramificação é sincronizada com os ambientes definidos na Seção 4:

- **main**: Reflete o ambiente de **Produção**. Estável e pronta para uso final.
- **beta**: Reflete o ambiente **Beta**. Utilizada para validação final com stakeholders.
- **staging**: Reflete o ambiente de **Staging**. Destinada à integração técnica e testes de regressão.
- **feature/[ID-DA-TAREFA]**: Branches temporárias para desenvolvimento. O nome deve conter o ID do ticket do Kanban (ex: `feature/PI-12`).

## 5.4. Integração CI/CD e Infraestrutura

Para garantir a consistência e qualidade do código visionado, aplicam-se as seguintes recomendações:

- **GitHub Actions**: Workflows configurados para todas as branches, automatizando a execução de testes unitários e de integração (definidos pelo papel de **DevOps**).
- **Docker**: Cada repositório deve conter um `Dockerfile` e arquivos de orquestração (`docker-compose`) configurados.
- **README do Repositório**: Além da metodologia global, cada repositório deve possuir um README local com instruções claras de como executar a aplicação e seus serviços em ambiente Docker.

## 5.5. Integração GitHub x Kanban

O fluxo de trabalho no GitHub deve corresponder a mudanças de estado no Kanban:

| Ação no GitHub                                | Estado no Kanban   |
| :-------------------------------------------- | :----------------- |
| Início de desenvolvimento na branch `feature` | 5.3.3. Development |
| Início de testes automatizados                | 5.3.4. Test        |
| Abertura de Pull Request para `staging`       | 5.3.5. Validation  |
| Merge em `staging`                            | 5.3.6. Completed   |
| Merge `staging` -> `beta`                     | 5.5. Deploy        |
| Merge `beta` -> `main`                        | 7. Deploy          |

# 6. Ritos e Comunicação

Esta seção descreve a cadência de reuniões e os protocolos de comunicação adotados para garantir o alinhamento técnico e a transparência no andamento do projeto.

## 6.1. Reunião Semanal de Alinhamento

A equipe realiza uma reunião geral obrigatória uma vez por semana. O objetivo principal é a discussão do progresso global, identificação de riscos transversais e a atualização de status para todos os membros.

## 6.2. Diário de Bordo

Como resultado da Reunião Semanal, deve-se manter um **Diário de Bordo**. Este documento serve como um registro histórico do projeto, onde são anotados:

- O resumo do andamento da semana.
- Decisões técnicas ou de negócio tomadas.
- Impedimentos resolvidos ou identificados.
- Próximos passos prioritários.

## 6.3. Alinhamentos Pontuais

Além da reunião semanal, ocorrem alinhamentos de menor escala conforme a necessidade:

- **Alinhamento de Escopo:** Sempre que uma tarefa de menor complexidade for atribuída a um membro, deve haver um alinhamento rápido sobre as expectativas e requisitos específicos.
- **Pequenos Grupos/Individuais:** Discussões técnicas focadas entre membros de diferentes frentes (ex: Desenvolvedor e Designer) para resolução de dúvidas pontuais ou integração de artefatos, evitando sobrecarregar a pauta da reunião semanal.
