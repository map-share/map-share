# RFC - CacheHunt: Aplicativo de Geocaching com Gamificação em .NET Aspire e Angular

* **Título do Projeto**: CacheHunt - Plataforma de Geocaching com Elementos de Gamificação
* **Nome do Estudante**: Ryan Gabriel Mazzei Bromati
* **Curso**: Engenharia de Software
* **Data de Entrega**: [Data]

## Resumo

Este documento apresenta a proposta de desenvolvimento do CacheHunt, uma plataforma de geocaching com elementos de gamificação desenvolvida em .NET Aspire e Angular. O projeto visa criar uma solução completa para entusiastas de geocaching, implementando as principais regras e conceitos do jogo, além de incorporar um sistema de conquistas, níveis e recompensas para aumentar o engajamento dos usuários. O documento detalha a arquitetura, requisitos, stack tecnológica e considerações de design para este trabalho de conclusão de curso em Engenharia de Software.

## 1. Introdução

### **Contexto**

Geocaching é uma atividade recreativa outdoor que combina elementos de caça ao tesouro e exploração, onde participantes usam dispositivos com GPS para esconder e encontrar recipientes chamados "geocaches" ou "caches" em locais ao redor do mundo. O CacheHunt surge como uma solução moderna para esta prática, trazendo elementos de gamificação para enriquecer a experiência dos usuários.

### **Justificativa**

O desenvolvimento do CacheHunt é relevante para o campo da Engenharia de Software por diversos motivos:

1. Integra tecnologias modernas (.NET Aspire e Angular) para resolver problemas reais de geolocalização e interação social
2. Implementa conceitos avançados de desenvolvimento de software
3. Aplica princípios de gamificação para aumentar engajamento do usuário
4. Explora desafios técnicos como persistência de dados geoespaciais, autenticação segura e integração com APIs de mapas

### **Objetivos**

#### Objetivo Principal:
Desenvolver uma plataforma completa de geocaching com elementos de gamificação que permita aos usuários criar, localizar e registrar caches, além de um sistema de conquistas.

#### Objetivos Secundários:
- Implementar as regras oficiais e principais conceitos do geocaching
- Criar um sistema de gamificação com conquistas, níveis e recompensas
- Desenvolver uma plataforma responsiva e acessível em diferentes dispositivos
- Implementar funcionalidades sociais como rankings, eventos e compartilhamento

## 2. Descrição do Projeto

### **Tema do Projeto**

O CacheHunt é uma plataforma de geocaching que permitirá aos usuários:
- Criar e registrar novos geocaches com informações detalhadas (coordenadas, dicas, dificuldade, tipo)
- Buscar caches próximos com base na localização do usuário
- Registrar visitas e encontros de caches ("logs")
- Participar de um sistema de conquistas e progressão de nível
- Interagir com outros usuários através de funcionalidades sociais
- Visualizar estatísticas pessoais e rankings gerais

O sistema será desenvolvido com .NET Aspire no backend e Angular no frontend, proporcionando uma experiência moderna, responsiva e de alta performance.

### **Problemas a Resolver**

1. Falta de elementos de gamificação para manter usuários engajados a longo prazo
2. Necessidade de uma plataforma que implemente corretamente todas as regras e conceitos do geocaching
3. Carência de recursos sociais que promovam a formação de comunidades
4. Limitações de performance e escalabilidade em soluções existentes
5. Insuficiência de recursos para criadores de cache monitorarem e gerenciarem seus caches

### **Limitações**

Este projeto NÃO abordará:
- Desenvolvimento de aplicativos nativos para iOS ou Android (focará em web responsivo)
- Integração direta com plataformas de geocaching existentes para importação/exportação de dados
- Implementação de recursos de realidade aumentada
- Desenvolvimento de hardware específico para geocaching
- Implementação de um sistema de pagamento ou monetização

## 3. Especificação Técnica

### 3.1. Requisitos de Software

#### **Lista de Requisitos**

##### Requisitos Funcionais (RF):

1. **RF01**: O sistema deve permitir o cadastro de usuários com perfil, preferências e estatísticas
2. **RF02**: O sistema deve permitir a autenticação segura de usuários
3. **RF03**: O sistema deve permitir a criação e edição de caches por usuários autorizados
4. **RF04**: O sistema deve validar as coordenadas geográficas dos caches cadastrados
5. **RF05**: O sistema deve exibir caches próximos à localização atual do usuário
6. **RF06**: O sistema deve permitir filtrar caches por tipo, dificuldade, tamanho e distância
7. **RF07**: O sistema deve permitir ao usuário registrar o encontro de um cache (log)
8. **RF08**: O sistema deve permitir o upload de fotos nos logs de visita
9. **RF09**: O sistema deve calcular e atribuir conquistas automaticamente
10. **RF10**: O sistema deve disponibilizar um painel de estatísticas para o usuário
11. **RF11**: O sistema deve implementar um sistema de ranking e comparação entre usuários
12. **RF13**: O sistema deve permitir a criação e participação em eventos comunitários
13. **RF14**: O sistema deve fornecer mecanismos de denúncia de problemas com caches
14. **RF15**: O sistema deve permitir a troca de mensagens entre usuários

##### Requisitos Não-Funcionais (RNF):

1. **RNF01**: O sistema deve ser responsivo, adaptando-se a diferentes tamanhos de tela
2. **RNF02**: O sistema deve ter tempo de resposta menor que 3segundos para operações comuns
3. **RNF03**: O sistema deve suportar pelo menos 1000 usuários simultâneos
4. **RNF04**: O sistema deve garantir a privacidade dos dados dos usuários conforme LGPD - avaliar
5. **RNF05**: O sistema deve estar disponível em português e inglês - avaliar
6. **RNF06**: O sistema deve implementar medidas de segurança contra ataques comuns (XSS, CSRF, SQL Injection)
7. **RNF07**: O sistema deve ser acessível conforme diretrizes WCAG 2.1 nível AA - avaliar
8. **RNF08**: O sistema deve funcionar nos principais navegadores modernos
9. **RNF09**: O sistema deve implementar cache eficiente para reduzir consumo de dados
10. **RNF10**: O sistema deve permitir operações básicas em modo offline com sincronização posterior - avaliar

#### **Representação dos Requisitos**

**Diagrama de Casos de Uso (UML)**

```
[Este é um espaço reservado para o Diagrama de Casos de Uso UML, que deverá ser desenvolvido e incluído posteriormente. O diagrama deverá representar visualmente os principais casos de uso do sistema, incluindo atores como "Usuário não autenticado", "Usuário autenticado", "Criador de cache" e "Administrador", e suas interações com funcionalidades como "Cadastrar-se", "Buscar caches", "Registrar encontro", "Criar cache", etc.]
```

### 3.2. Considerações de Design

#### **Visão Inicial da Arquitetura**

O CacheHunt será desenvolvido utilizando uma arquitetura de microsserviços orquestrada pelo .NET Aspire, com frontend em Angular. Os principais componentes da arquitetura são:

1. **Frontend (Angular)**
   - Interface de usuário responsiva e acessível
   - Comunicação com backend via REST API
   - Gerenciamento de estado com NGRX
   - Componentes reutilizáveis com Material Design

2. **Backend (.NET Aspire)**
   - API Gateway para gerenciamento de requisições
   - Microsserviço de Autenticação e Autorização
   - Microsserviço de Geocaches (criação, busca, gerenciamento)
   - Microsserviço de Usuários e Perfis
   - Microsserviço de Gamificação (conquistas, níveis, desafios - avaliar)
   - Microsserviço de Eventos e Notificações
   - Microsserviço de Analytics e Estatísticas - avaliar

3. **Persistência de Dados**
   - Banco de dados relacional para dados estruturados (SQL Server)
   - Banco de dados geoespacial para informações de localização (integração com PostGIS)
   - Cache distribuído para melhorar performance (Redis)
   - Armazenamento de objetos para mídias e arquivos (Blob Storage)

4. **Serviços de Infraestrutura**
   - Sistema de mensageria para comunicação assíncrona entre serviços (RabbitMQ)
   - Serviço de logs centralizados (Serilog, Elastic Stack)
   - Monitoramento e métricas (Prometheus, Grafana)
   - CDN para distribuição de conteúdo estático

#### **Padrões de Arquitetura**

- **Microsserviços**: Para permitir desenvolvimento, implantação e escalabilidade independentes
- **Clean Architecture**: Separação clara de responsabilidades entre camadas
- **CQRS (Command Query Responsibility Segregation)**: Separação entre operações de leitura e escrita
- **Event-Driven Architecture**: Comunicação assíncrona entre serviços via eventos
- **Repository Pattern**: Abstração do acesso a dados
- **MVC (Model-View-Controller)**: Para organização do frontend
- **DDD (Domain-Driven Design)**: Para modelagem de domínios complexos

#### **Modelos C4**

##### Nível 1: Diagrama de Contexto

```
[Espaço reservado para diagrama C4 de Contexto que mostrará o CacheHunt como um sistema central, interagindo com usuários, APIs externas de mapas, serviços de armazenamento e notificações]
```

##### Nível 2: Diagrama de Contêineres

```
[Espaço reservado para diagrama C4 de Contêineres que detalhará os principais contêineres da aplicação: Frontend SPA, Backend API, Bancos de Dados, Serviços de Mensageria, etc.]
```

##### Nível 3: Diagrama de Componentes

```
[Espaço reservado para diagrama C4 de Componentes que detalhará os componentes dentro de cada contêiner, como controladores, serviços, repositórios, etc.]
```

##### Nível 4: Diagrama de Código

```
[Espaço reservado para diagrama C4 de Código que mostrará exemplos de classes e interfaces para componentes críticos do sistema]
```

### 3.3. Stack Tecnológica

#### **Linguagens de Programação**

- **C#**: Escolhida para o backend devido à robustez, performance e integração nativa com .NET Aspire
- **TypeScript**: Selecionada para o frontend por proporcionar tipagem estática ao JavaScript, facilitando a manutenção e reduzindo erros
- **SQL**: Para consultas e manipulação de dados em bancos relacionais
- **HTML/CSS**: Para estruturação e estilização da interface do usuário

#### **Frameworks e Bibliotecas**

**Backend**
- **.NET Aspire**: Framework para desenvolvimento de aplicações distribuídas e em nuvem
- **ASP.NET Core**: Framework web para construção de APIs
- **Entity Framework Core**: ORM para acesso a dados
- **AutoMapper**: Mapeamento objeto-objeto - substituir por outro
- **MediatR**: Implementação de padrões mediator para CQRS
- **FluentValidation**: Validação de entrada de dados
- **Serilog**: Logging estruturado
- **Hangfire**: Agendamento e processamento de tarefas em background
- **NetTopologySuite**: Biblioteca para operações geoespaciais
- **IdentityServer**: Autenticação e autorização

**Frontend**
- **Angular**: Framework para desenvolvimento de aplicações web SPA
- **Angular Material**: Componentes de UI
- **NgRx**: Gerenciamento de estado baseado em Redux
- **RxJS**: Programação reativa
- **Leaflet/OpenLayers**: Bibliotecas de mapas para web
- **Chart.js**: Visualização de dados
- **TailwindCSS**: Framework CSS utilitário
- **Angular PWA**: Recursos de Progressive Web App

#### **Ferramentas de Desenvolvimento e Gestão de Projeto**

- **Rider**: IDE para desenvolvimento backend
- **Visual Studio Code**: Editor para desenvolvimento frontend e backend
- **Azure DevOps/GitHub**: Repositório de código e CI/CD
- **Docker/Kubernetes**: Containerização e orquestração
- **Postman/Swagger**: Teste e documentação de API
- **SonarQube**: Análise estática de código -- utilizar outro
- **Mermaid**: // preencher

### 3.4. Considerações de Segurança

O CacheHunt implementará diversas medidas de segurança para proteger os dados dos usuários e a integridade do sistema:

1. **Autenticação e Autorização**
   - Implementação de OAuth 2.0/OpenID Connect para autenticação segura
   - JWT (JSON Web Tokens) para gerenciamento de sessão
   - Autorização baseada em roles e claims
   - Mecanismo de refresh token com rotação segura

2. **Proteção de Dados**
   - Criptografia de dados sensíveis em repouso
   - TLS/SSL para todas as comunicações
   - Implementação das diretrizes da LGPD para proteção de dados pessoais
   - Anonimização de dados quando apropriado

3. **Segurança da Aplicação**
   - Proteção contra ataques comuns (XSS, CSRF, SQL Injection)
   - Implementação de rate limiting para prevenir abusos
   - Validação rigorosa de entradas em todas as camadas
   - Sanitização de dados de saída

5. **Privacidade dos Usuários**
   - Coordenadas exatas de caches visíveis apenas para usuários autenticados
   - Opção de ocultar estatísticas e atividades do perfil público
   - Controle de visibilidade de logs e fotos
   - Mecanismos para usuários exercerem direitos de acesso, retificação e exclusão de dados

## 4. Próximos Passos

Após a aprovação deste RFC, o desenvolvimento do CacheHunt seguirá o seguinte cronograma aproximado:

### Portfólio

6 meses de de desenvolvimento divididos em 3 partes, primeira vai ser definida pelo reginamento dos requisitos, arquitetura detalhada configuração da infra na vps e CI/CD, inicialização do projeto backend com aspire, servico de authenticaão, 2 parte finalização dos outros serviços back end, 3 parte front end e junção do back com front. // ajustar isso acima para e formatar como foi feito abaixo anteriormete

<!-- 1. **Mês 1-2**:
   - Refinamento de requisitos e casos de uso
   - Design detalhado da arquitetura
   - Prototipação da interface do usuário
   - Configuração do ambiente de desenvolvimento

2. **Mês 3-4**:
   - Implementação do core backend (autenticação, geocaches básicos)
   - Desenvolvimento da estrutura base do frontend
   - Integração com serviços de mapas
   - Testes unitários e integração contínua

3. **Mês 5-6**:
   - Implementação de funcionalidades básicas de usuário
   - Sistema básico de logs e registros
   - Apresentação de Portfólio I com MVP funcional

### Portfólio II (2º Semestre)

4. **Mês 7-8**:
   - Implementação do sistema de gamificação (conquistas, níveis)
   - Desenvolvimento de recursos sociais
   - Otimização de performance e UX

5. **Mês 9-10**:
   - Implementação de funcionalidades avançadas (eventos, desafios)
   - Testes de usabilidade e correções
   - Documentação técnica completa

6. **Mês 11-12**:
   - Refinamentos finais e otimizações
   - Testes de segurança e performance
   - Preparação para apresentação final
   - Entrega e defesa do TCC -->

## 5. Referências

[Lista de referências a ser completada pelo estudante, incluindo:]

<!-- colocar texto com os link para referencias -->

- Documentação oficial do .NET Aspire
- Documentação oficial do Angular
- Literatura sobre geocaching e suas regras
- Artigos científicos sobre gamificação
- Referências sobre arquitetura de software e microserviços
- Padrões de design e boas práticas de desenvolvimento
- Artigos e recursos sobre segurança web
- Documentação de APIs de mapas e serviços geoespaciais
- Estudos sobre usabilidade e experiência do usuário
- Recursos sobre DevOps e CI/CD

## 6. Apêndices (Opcionais)

[Espaço reservado para conteúdo adicional como mockups iniciais da interface, exemplos de diagramas de fluxo, detalhes específicos sobre regras de geocaching a serem implementadas, etc.]

## 7. Avaliações de Professores

### Considerações Professor/a:

[Espaço reservado para considerações e assinatura]

### Considerações Professor/a:

[Espaço reservado para considerações e assinatura]

### Considerações Professor/a:

[Espaço reservado para considerações e assinatura]