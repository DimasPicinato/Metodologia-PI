# Metodologia

Este documento busca responder e documentar: Quem faz?, Como faz? e Quando faz? em uma proposta de metodologia de desenvolvimento para o projeto integrador dos alunos da Fatec Lins - Professor Antonio Seabra no curso de Análise e Desenvolvimento de Sistemas.

> Elaborado por **Dimas Picinato**.  
> Data da última atualização: **28/02/2026**.

# Sumário

- [Metodologia](#metodologia)
- [Sumário](#sumário)
- [1. Ferramentas](#1-ferramentas)
  - [1.1. Jira](#11-jira)
  - [1.2. GitHub](#12-github)
- [2. Ambientes](#2-ambientes)
  - [2.1. Desenvolvimento](#21-desenvolvimento)
  - [2.2. Staging](#22-staging)
  - [2.3. Beta](#23-beta)
  - [2.4. Produção](#24-produção)
- [3. Equipe](#3-equipe)
  - [3.1. Product Owner (PO)](#31-product-owner-po)
  - [3.2. Tech Lead](#32-tech-lead)
  - [3.3. Analista](#33-analista)
  - [3.4. Designer](#34-designer)
  - [3.5. DevOps](#35-devops)
  - [3.6. Desenvolvedor (Dev)](#36-desenvolvedor-dev)
- [4. Quadros Kanban](#4-quadros-kanban)
  - [4.1. Tickets](#41-tickets)
    - [4.1.1. Níveis](#411-níveis)
    - [4.1.2. Estrutura](#412-estrutura)
  - [4.2. Fluxos](#42-fluxos)
    - [4.2.1. Operational](#421-operational)
    - [4.2.2. Architectural](#422-architectural)
    - [4.2.3. DevOps](#423-devops)
    - [4.2.4. Execution](#424-execution)
    - [4.2.5. Development](#425-development)

# 1. Ferramentas

Nesta seção são descritas as ferramentas utilizadas para organização, controle e execução do processo de desenvolvimento. A adoção de ferramentas padronizadas visa garantir rastreabilidade, colaboração estruturada e controle de qualidade ao longo do ciclo de vida do projeto.

## 1.1. Jira

O [Jira](https://www.atlassian.com/software/jira) é a ferramenta adotada para gestão de tarefas e acompanhamento do fluxo de trabalho do projeto. Nele são registrados requisitos, histórias de usuário, tarefas técnicas, correções de bugs e demais atividades relacionadas ao desenvolvimento.

Sua utilização deve estar estruturada no modelo Kanban, permitindo a visualização do estado das atividades em quadros organizados por etapas do processo. A ferramenta também possibilita definição de responsáveis, prazos, prioridades e critérios de aceite, garantindo rastreabilidade, transparência e controle do andamento do projeto.

## 1.2. GitHub

O [GitHub](https://github.com) é a plataforma utilizada para controle de versão e hospedagem do código-fonte do projeto, baseada no sistema Git. Por meio dela é mantido o repositório central da aplicação, assegurando histórico e integridade das alterações realizadas.

A ferramenta é empregada para gerenciamento de branches, submissão e revisão de pull requests, além de permitir integração com processos de integração contínua (CI). Dessa forma, promove colaboração estruturada, controle de qualidade do código e padronização do processo de entrega.

# 2. Ambientes

Esta seção descreve os ambientes utilizados ao longo do ciclo de desenvolvimento e disponibilização do sistema. A separação em múltiplos ambientes visa reduzir riscos, assegurar qualidade e permitir validações progressivas antes da liberação definitiva ao usuário final.

## 2.1. Desenvolvimento

O ambiente de Desenvolvimento corresponde ao ambiente local utilizado individualmente por cada desenvolvedor para implementação e testes iniciais das funcionalidades. Trata-se de um ambiente isolado, voltado à codificação, execução de testes unitários e validações técnicas preliminares antes da integração com o restante do sistema.

A padronização desse ambiente deverá ocorrer por meio da utilização de contêineres Docker, permitindo a orquestração dos serviços necessários à aplicação, tais como servidor de aplicação, banco de dados e demais dependências. Essa abordagem visa garantir uniformidade entre os ambientes dos diferentes desenvolvedores, reduzir conflitos de configuração e facilitar a replicação do sistema.

Alternativamente, o ambiente de Staging poderá ser utilizado para testes durante o desenvolvimento, desde que não haja conflito com o trabalho simultâneo de outros membros da equipe. Nesses casos, deve-se assegurar que as alterações não comprometam a estabilidade temporária do ambiente compartilhado nem interfiram nas validações em andamento.

## 2.2. Staging

O ambiente de Staging consiste em um ambiente interno, temporário e restrito à equipe de desenvolvimento, destinado à integração contínua das funcionalidades implementadas e à realização de testes técnicos preliminares.

Trata-se de um ambiente de natureza efêmera, não havendo garantia de persistência de dados ao longo do tempo. As bases de dados podem ser reinicializadas, sobrescritas ou descartadas conforme a necessidade do processo de desenvolvimento. Em razão de sua finalidade experimental, também não há garantia de estabilidade contínua, podendo ocorrer indisponibilidades ou inconsistências decorrentes de testes, ajustes estruturais e validações técnicas.

Nesse ambiente são realizadas validações de integração entre módulos, testes de regressão, verificação de consistência estrutural do banco de dados e demais procedimentos técnicos prévios à disponibilização para validação ampliada. Não se destina ao uso por stakeholders externos.

A responsabilidade por sua configuração, manutenção e disponibilidade é da equipe de desenvolvimento. A infraestrutura poderá ser provisionada conforme decisão conjunta entre equipe e stakeholders, ficando a critério destes a disponibilização do servidor.

## 2.3. Beta

O ambiente Beta é destinado à validação funcional do sistema por todos os stakeholders, incluindo equipe e clientes. Sua finalidade é permitir testes em condições próximas às reais de uso, possibilitando identificação de inconsistências, falhas de usabilidade e ajustes finais antes da liberação oficial.

Diferentemente do Staging, o ambiente Beta deve apresentar maior estabilidade e garantir persistência dos dados durante o período de validação, ainda que não possua o mesmo nível de robustez do ambiente de Produção.

Este ambiente deve se assemelhar ao máximo ao ambiente de Produção, tanto em configuração quanto em arquitetura, a fim de reduzir discrepâncias entre testes e operação real.

A responsabilidade técnica por sua implantação, configuração e manutenção é da equipe de desenvolvimento. Assim como no Staging, a disponibilização da infraestrutura poderá depender de definição conjunta entre equipe e stakeholders.

## 2.4. Produção

O ambiente de Produção corresponde ao ambiente oficial e definitivo do sistema, destinado ao uso real pelos usuários finais.

Diferentemente dos demais ambientes, sua infraestrutura deverá ser disponibilizada pelo cliente, que também será responsável por sua manutenção, custos operacionais e garantia de disponibilidade. A equipe de desenvolvimento poderá prestar suporte técnico conforme acordado, porém não será responsável direta pela gestão da infraestrutura produtiva.

Este ambiente deve assegurar estabilidade, segurança, desempenho adequado, persistência de dados e conformidade com as exigências institucionais estabelecidas para o projeto.

# 3. Equipe

Nesta seção, são detalhadas as atribuições e responsabilidades de cada função desempenhada pelos membros da equipe durante o ciclo de vida do projeto. A definição clara dos papéis visa otimizar a colaboração, mitigar conflitos de escopo e assegurar que todos os aspectos técnicos, de design e de negócio sejam devidamente atendidos.

![Equipe](<imgs/modelagem de processos-Equipe.jpg>)

## 3.1. Product Owner (PO)

O Product Owner é o responsável pela definição, consolidação e priorização das regras de negócio do sistema. Atua como principal representante das partes interessadas, assegurando que os requisitos funcionais e não funcionais estejam alinhados às necessidades institucionais e aos objetivos do projeto. Compete ao PO validar os artefatos desenvolvidos pela equipe, garantindo aderência às regras estabelecidas, bem como aprovar as entregas parciais e finais. Também é responsável por esclarecer dúvidas relacionadas ao domínio do problema e manter a coerência entre escopo, valor entregue e expectativas dos stakeholders.

## 3.2. Tech Lead

O Tech Lead é o responsável pela liderança técnica do projeto. Sua função consiste em coordenar as decisões arquiteturais, definir padrões de desenvolvimento, estabelecer diretrizes de qualidade e orientar tecnicamente a equipe. É incumbido de detalhar funcionalidades sob a perspectiva técnica, garantindo viabilidade, escalabilidade, segurança e manutenibilidade da solução. Além disso, supervisiona revisões de código, promove boas práticas de engenharia de software e assegura que as implementações estejam alinhadas à arquitetura definida.

## 3.3. Analista

O Analista é responsável pela modelagem conceitual e estrutural do sistema. Atua na elicitação, análise e organização dos requisitos, transformando necessidades de negócio em especificações técnicas compreensíveis pela equipe de desenvolvimento. Elabora os principais artefatos UML, tais como diagramas de casos de uso e classes, além de contribuir para a definição da arquitetura funcional do sistema. Seu papel é garantir consistência entre requisitos, modelagem e implementação.

## 3.4. Designer

O Designer é responsável pela concepção da experiência do usuário e pela definição da identidade visual do sistema. Desenvolve protótipos, define a composição visual das interfaces, estabelece padrões de tipografia, cores e componentes, e assegura a coerência com princípios de usabilidade e acessibilidade. Também formaliza regras de design e diretrizes de interface, promovendo consistência estética e funcional em todo o produto.

## 3.5. DevOps

O profissional de DevOps é responsável pela integração entre desenvolvimento e operações, assegurando a automação, padronização e confiabilidade do ciclo de vida da aplicação. Compete a esse papel configurar e manter ambientes de desenvolvimento, homologação e produção, gerenciar infraestrutura (local ou em nuvem), implementar pipelines de integração e entrega contínua (CI/CD), monitorar desempenho e disponibilidade do sistema, além de garantir práticas adequadas de segurança, backup e recuperação de dados. O DevOps também atua na prevenção e resolução de incidentes, promovendo estabilidade operacional e escalabilidade da solução ao longo do tempo.

## 3.6. Desenvolvedor (Dev)

O Desenvolvedor é responsável pela implementação das funcionalidades do sistema conforme as especificações técnicas e regras de negócio definidas. Sua atuação engloba o desenvolvimento das aplicações front-end e back-end, a modelagem e manipulação do banco de dados, bem como a integração com serviços externos e recursos do servidor. Deve garantir que o código produzido esteja em conformidade com os padrões estabelecidos, priorizando qualidade, desempenho, segurança e manutenibilidade.

# 4. Quadros Kanban

Essa seção detalha os quadros e tickets utilizados no projeto.

Para a organização do projeto, são utilizados quadros Kanban através do Jira, que permitem o gerenciamento do fluxo de trabalho e a visualização das tarefas em progresso.

## 4.1. Tickets

A imagem abaixo representa os tipos de tickets e seus respectivos quadros:

![Tickets](<imgs/modelagem de processos-Tickets.jpg>)

### 4.1.1. Níveis

Essa seção descreve os níveis de tickets utilizados no projeto:

- **Operational**: É o nível mais alto de trabalho, do qual possui o ticket **Epic** e engloba os tickets dos níveis abaixo:
  - **Architectural**: É o nível do qual representa o trabalho de arquitetura e planejamento e se trabalha com os tickets **Design** e **Modeling**.
  - **DevOps**: É o nível do qual representa o trabalho de arquitetura e planejamento e se trabalha com os tickets **Design** e **Modeling**.
  - **Execution**: É o nível do qual representa o trabalho de arquitetura e planejamento e se trabalha com os tickets **Design** e **Modeling**.
  - **Development**: É o nível do qual representa o trabalho de arquitetura e planejamento e se trabalha com os tickets **Design** e **Modeling**.

### 4.1.2. Estrutura

Essa seção descreve a estrutura base para detalhamento dos tickets:

- Contexto:

## 4.2. Fluxos

A imagem abaixo representa os fluxos de trabalho dos quadros Kanban do projeto:

![Fluxos](<imgs/modelagem de processos-Fluxos.jpg>)

### 4.2.1. Operational

![Operational](<imgs/modelagem de processos-Operational.jpg>)

### 4.2.2. Architectural

![Architectural](<imgs/modelagem de processos-Architectural.jpg>)

### 4.2.3. DevOps

![DevOps](<imgs/modelagem de processos-DevOps.jpg>)

### 4.2.4. Execution

![Execution](<imgs/modelagem de processos-Execution.jpg>)

### 4.2.5. Development

![Development](<imgs/modelagem de processos-Development.jpg>)
