# REST e JSON

## REST (Representational State Transfer)
- **Definição**: Estilo de arquitetura para sistemas distribuídos que utiliza HTTP para operações CRUD (Create, Read, Update, Delete).
- **Características**: Stateless (sem estado), cacheable (pode ser armazenado em cache), usa URLs para identificar recursos e métodos HTTP para ações.
- **Benefícios**: Simplicidade, escalabilidade, e interoperabilidade.

## JSON (JavaScript Object Notation)
- **Definição**: Formato de dados leve e legível por humanos, usado para troca de dados.
- **Características**: Baseado em pares chave-valor, amplamente utilizado em APIs RESTful.
- **Benefícios**: Simplicidade e compatibilidade com muitas linguagens de programação.

# Service-Oriented Architectures (SOA)

## SOA
- **Definição**: Estilo de arquitetura que permite a integração de serviços distintos, geralmente de diferentes domínios de negócios, em uma única aplicação coesa.
- **Componentes**: Serviços, contratos de serviço, bus de serviço empresarial (ESB).
- **Benefícios**: Reutilização de serviços, integração mais fácil de sistemas heterogêneos, maior flexibilidade.

# Microservices

## Microservices
- **Definição**: Arquitetura onde a aplicação é dividida em serviços pequenos, independentes e de fácil manutenção, que podem ser desenvolvidos, implantados e escalados de forma independente.
- **Componentes**: Microsserviços, APIs, contêineres.
- **Benefícios**: Maior escalabilidade, isolamento de falhas, deploy contínuo, melhor alinhamento com equipes ágeis.

# Immutable Servers

## Immutable Servers
- **Definição**: Servidores que, uma vez configurados e implantados, não são modificados; qualquer alteração é feita criando uma nova imagem de servidor.
- **Benefícios**: Consistência, facilidade de rollback, menor risco de configurações inconsistentes.

# Loose Coupling

## Loose Coupling
- **Definição**: Princípio de design onde os componentes de um sistema são independentes e minimamente dependentes uns dos outros.
- **Benefícios**: Maior flexibilidade, facilidade de manutenção e escalabilidade.

# Segurança: XSS, SQL Injections, Verbose Error Reports, API Authentication, Encryption

## Cross-Site Scripting (XSS)
- **Descrição**: Ataque que injeta scripts maliciosos em páginas web visualizadas por outros usuários.
- **Mitigação**: Escapamento de saída, Content Security Policy (CSP), validação e sanitização de entradas.

## SQL Injections
- **Descrição**: Injeção de código SQL malicioso em consultas SQL, permitindo a manipulação do banco de dados.
- **Mitigação**: Uso de prepared statements, validação e sanitização de entradas, uso de ORMs.

## Verbose Error Reports
- **Descrição**: Relatórios de erro detalhados podem expor informações sensíveis.
- **Mitigação**: Configurar relatórios de erro para ambientes de produção de forma que não exponham detalhes técnicos.

## API Authentication
- **Descrição**: Garantir que apenas usuários autenticados possam acessar a API.
- **Mitigação**: Uso de tokens (ex. JWT), OAuth, e outras técnicas de autenticação robusta.

## Encryption (Criptografia)
- **Descrição**: Proteger dados em trânsito e em repouso usando criptografia.
- **Mitigação**: Uso de HTTPS para transporte seguro, criptografia de dados sensíveis armazenados.

# CORS Headers e CSRF Tokens

## CORS Headers
- **Descrição**: Configurações de CORS (Cross-Origin Resource Sharing) controlam como recursos em um servidor podem ser solicitados de um domínio diferente.
- **Mitigação**: Configurar cabeçalhos CORS corretamente para permitir apenas origens confiáveis.

## CSRF Tokens
- **Descrição**: Tokens CSRF (Cross-Site Request Forgery) são usados para proteger contra ataques CSRF, onde ações indesejadas são realizadas em nome de um usuário autenticado.
- **Mitigação**: Inclusão de tokens CSRF em formulários e verificação no servidor.

# ACID Properties e CAP Theorem

## ACID Properties
- **Definição**: Conjunto de propriedades que garantem transações de banco de dados confiáveis.
  - **Atomicidade**: Transações são tudo ou nada.
  - **Consistência**: Transações levam o banco de dados de um estado válido a outro estado válido.
  - **Isolamento**: Transações isoladas não interferem umas nas outras.
  - **Durabilidade**: Dados de transações confirmadas são permanentes.

## CAP Theorem
- **Definição**: Teorema que afirma que um sistema de armazenamento distribuído pode ter apenas duas das três garantias: Consistência, Disponibilidade e Tolerância a Partições.
  - **Consistência**: Todos os nós veem os mesmos dados ao mesmo tempo.
  - **Disponibilidade**: Cada solicitação recebe uma resposta (sucesso ou falha).
  - **Tolerância a Partições**: O sistema continua a operar apesar das falhas de comunicação entre partes do sistema.

# Conclusão

Todos os temas mencionados foram abordados detalhadamente na conversa. Se precisar de mais esclarecimentos sobre qualquer um dos tópicos, sinta-se à vontade para perguntar.