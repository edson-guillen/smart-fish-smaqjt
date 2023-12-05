Relatório do Projeto de Programação Orientada a Objetos (POO)
Detalhes do Projeto
Desenvolvedor
Nome: Diogo Saffiotte Zafani
RA: 1959438
Descrição Geral
O projeto de Programação Orientada a Objetos (POO) consiste em um conjunto de classes Java que desempenham funções específicas em um sistema. Abaixo estão detalhes sobre as classes, atributos, métodos e práticas utilizadas no projeto.

Conceitos Básicos
Classes
SmartfishApplication.java

Responsável por inicializar a aplicação.
FirebaseConfig.java

Configura a conexão com o Firebase.
RabbitMQConfig.java

Configura a comunicação com o RabbitMQ.
RabbitMQConstant.java

Define constantes relacionadas ao RabbitMQ, como nomes de filas e trocas.
ComponentConsumer.java

Processa mensagens relacionadas a componentes.
SensorConsumer.java

Processa mensagens relacionadas a sensores.
ComponentController.java

Controla solicitações relacionadas a componentes.
SensorController.java

Controla solicitações relacionadas a sensores.
Response.java

Representa uma resposta padrão da API.
ComponentDto.java

Define objetos de dados relacionados a componentes.
SensorDto.java

Define objetos de dados relacionados a sensores.
ComponentService.java

Lida com a lógica de negócios relacionada a componentes.
SensorService.java

Lida com a lógica de negócios relacionada a sensores.
Atributos
FirebaseConfig.java
Atributo: private AmqpAdmin amqpAdmin
Usado para administrar objetos do RabbitMQ.
RabbitMQConfig.java
Atributo: private static final String EXCHANGE_NAME
Constante que representa o nome da troca no RabbitMQ.
ComponentConsumer.java
Atributo: private ComponentService componentService
Injetado para processar mensagens relacionadas a componentes.
SensorConsumer.java
Atributo: private SensorService sensorService
Injetado para processar mensagens relacionadas a sensores.
Métodos
FirebaseConfig.java
Método: init
Inicializa a conexão com o Firebase a partir de um arquivo JSON de credenciais.
RabbitMQConfig.java
Métodos privados: queue, topicExchange, binding e add
Configuram filas, trocas e ligações no RabbitMQ.
ComponentConsumer.java
Método: createComponent
Cria componentes com base em mensagens do RabbitMQ.
SensorConsumer.java
Método: registrySensor
Registra informações de sensores a partir de mensagens do RabbitMQ.
ComponentController.java
Método: activate
Ativa componentes e envia mensagens para o RabbitMQ.
SensorController.java
Métodos: getRegistryById e getAllRegistryByIdentifier
Obtêm informações de sensores com base em identificadores.
ComponentService.java
Métodos: create e activate
Criam e ativam componentes, interagindo com o Firebase.
SensorService.java
Métodos: registry, getRegistryById e getAllRegistryByIdentifier
Registram e recuperam informações de sensores no Firebase.
Atributos Estáticos e Métodos Estáticos
RabbitMQConfig.java
Atributo Estático: private static final String EXCHANGE_NAME
Estático para representar uma constante usada em toda a classe. Armazena o nome da troca do RabbitMQ.
FirebaseConfig.java
Método Estático: init
Estático, chamado na inicialização da classe para configurar o Firebase a partir de um arquivo JSON.
RabbitMQConfig.java
Métodos privados: queue, topicExchange, binding e add
Estáticos, usados internamente para configurar o RabbitMQ.
Métodos Construtores
RabbitMQConfig.java
Construtor: public RabbitMQConfig(AmqpAdmin amqpAdmin)
Usado para injetar uma instância de AmqpAdmin.
Atributos e Métodos Protegidos e/ou Privados
FirebaseConfig.java
Atributo Privado: private AmqpAdmin amqpAdmin
Privado para encapsular a implementação da classe e evitar acesso direto.
RabbitMQConfig.java
Métodos privados: queue, topicExchange, binding e add
Privados para serem usados internamente na classe RabbitMQConfig.
Interfaces ou Classes Puramente Virtuais
Não foram codificadas interfaces ou classes puramente virtuais.
Classes Abstratas ou Classes Virtuais
Não foram codificadas classes abstratas ou classes virtuais.
Instanciação de Objetos
No arquivo FirebaseConfig.java, são instanciados objetos FirebaseOptions e FirebaseApp durante a inicialização para conectar o Firebase.
Bibliotecas de Terceiros
No arquivo FirebaseConfig.java, a biblioteca de terceiros Google Firebase é usada para configurar a conexão com o Firebase.
No arquivo RabbitMQConfig.java, a biblioteca de terceiros Spring AMQP é usada para configurar a comunicação com o RabbitMQ.
Enums
RabbitMQConstant.java
Definição de constantes em forma de enumeração para representar nomes de filas e trocas no RabbitMQ.
Classes de Dados
ComponentDto.java
Classe de dados que representa objetos de dados relacionados a componentes.
SensorDto.java
Classe de dados que representa objetos de dados relacionados a sensores.
Classes de Comportamento
ComponentService.java
Classe de comportamento que lida com a lógica de negócios relacionada a componentes.
SensorService.java
Classe de comportamento que lida com a lógica de negócios relacionada a sensores.
Práticas de Programação
Polimorfismo
Não foi utilizado polimorfismo no projeto.
Objetos Imutáveis
No arquivo ComponentDto.java, a classe ComponentDto possui atributos imutáveis, como identifier e active, uma vez que são declarados como final.
No arquivo SensorDto.java, a classe SensorDto possui atributos imutáveis, como identifier, temp, ph, water_level, turbidity e created_at, uma vez que são declarados como final.
Ocultação de Informações
FirebaseConfig.java
Atributo privado AmqpAdmin amqpAdmin: Atributo privado para encapsular a implementação interna da classe e evitar acesso direto.
Classes Imutáveis
As classes ComponentDto e SensorDto são classes imutáveis para garantir que os objetos de dados relacionados a componentes e sensores não sejam modificados após a criação, mantendo a integridade dos dados.

