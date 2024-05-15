# The Twelve-Factor APP

## I CodeBase - Base de codigo

- Uma aplicação 12 fatores deve estar no Git.
- Existe sempre uma correlação um-para-um entre a base. 
  - Se existem várias bases de código, isto não é uma app – é um sistema distribuído.
  - Múltiplas apps compartilhando uma base de código é uma violação dos 12 fatores.
- Existe apenas uma base de código por aplicação, mas existirão vários deploys da mesma.
  - Esses deploys compartilham a mesma base de codigo, mas não o mesmo codigo. 

## II. Dependências
- Declarar e isolar as dependência.
- Use o gerenciador de dependência da sua linguagem. 
- Uma aplicação doze-fatores nunca confia na existência implícita de pacotes em todo o sistema.
  - Ela declara todas as dependências, completa e exatamente.

## III. Configurações
- A configuração de uma aplicação é tudo o que é provável variar entre deploys (homologação, produção, ambientes de desenvolvimento, etc). Isto inclui:
  - Recursos para a base de dados, Memcached, e outros serviços de apoio
  - Credenciais para serviços externos como Amazon S3, Twitter, banco de dados
  - Valores por deploy como o nome canônico do host para o deploy
- **Prova de fogo:** Se sua app for exposta publicamente ela vaza alguma info privada?
- A aplicação doze-fatores armazena configuração em variáveis de ambiente.

## IV. Serviços de Apoio
- Um serviço de apoio é qualquer serviço que o app consuma via rede como parte de sua operação normal.
- App doze-fatores deve ser capaz de trocar um banco de dados MySQL por um gerenciado por terceiros (tais como Amazon RDS) sem realizar quaisquer mudanças no código do app. 

## V. Construa, lance, execute
- Uma base de código é transformada num deploy (de não-desenvolvimento) através de três estágios:
  - O estágio de build é uma transformação que converte um repositório de código em um pacote executável conhecido como build. Usando uma versão do código de um commit especificado pelo processo de desenvolvimento, o estágio de build obtém e fornece dependências e compila binários e ativos.
  - O estágio de Release pega o que foi construido no build e a combina com a atual configuração do deploy. O lançamento resultante contém tanto a build quanto a configuração e está pronta para execução imediata no ambiente de execução.
  - O estágio de run roda o app no ambiente de execução, através do início de alguns dos processos do app com um determinado lançamento.
- Builds são iniciadas pelos desenvolvedores sempre que novos códigos entram no deploy. 
- Esse é um claramente a definição de CICD moderno, como Jenkins.

## VI. Processos
- Execute a aplicação como um ou mais processos que não armazenam estado
- Apps são stateless(não armazenam estado) e share-nothing.
- Quaisquer dados que precise persistir deve ser armazenado em um serviço de apoio stateful(que armazena o seu estado), tipicamente uma base de dados.
- Apps precisam ser efemeras.
- Criadas para o conceito de containers.

## VII. Vínculo de Portas | Port Binding
- Faz com que a app receba requições em uma porta especifica. 
- Serviços de Apoio são consumidos via porta
- Apps podem ser consumidas por outras apps por meio de port binding.

## VIII. Concorrência
- Escale através do processo modelo
- Utilizam fortes sugestões do modelo de processos UNIX para execução de serviços daemon, o desenvolvedor pode arquitetar a aplicação dele para lidar com diversas cargas de trabalho, atribuindo a cada tipo de trabalho a um tipo de processo.

## IX. Descartabilidade
- Em um periodo de mais atividade é possivel escalar rapidamente.
- Em periodos de menos atividades é posssivel dimunuir com cuidado.

## X. Paridade entre desenvolvimento e produção
- Tempo entre deploys baixo.
- Autores de código e deployers são as mesmas pessoas.
- Ambientes de desenvolvimento e produção são o mais similar possível

## XI. Logs
- Todos os logs devem ser enviados para o stout e sterr e coletados por um Serviço de Apoio.
- Logs não devem ser armazenados dentro do container ou aplicação.

## XII. Processos administrativos
- A formação de processos é o conjunto de processos que são usados para fazer as negociações regulares da app como ela é executada 


## Notas para nerds

[A Forma Ideal de Projetos Web | Os 12 Fatores | Fabio Akita][ytakita] 

[ytakita]: https://youtu.be/gpJgtED36U4