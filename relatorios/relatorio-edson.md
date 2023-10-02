# Relatório do Projeto de Programação Orientada a Objetos (POO)

Este relatório apresenta o projeto de Programação Orientada a Objetos (POO) desenvolvido por Edson Hila Guillen Lopes, RA: 1959483. O projeto é composto por um conjunto de classes Java que desempenham funções específicas em um sistema. A seguir, são apresentados detalhes sobre as classes, atributos, métodos e práticas utilizadas no projeto.

## Conceitos Básicos

### Codificou classes? Quais classes? Para que servem?

1. No arquivo `SmartfishApplication.java`:
   - Classe `SmartfishApplication.java`: Responsável por inicializar a aplicação.

2. No arquivo `FirebaseConfig.java`:
   - Classe `FirebaseConfig.java`: Configura a conexão com o Firebase.

3. No arquivo `RabbitMQConfig.java`:
   - Classe `RabbitMQConfig.java`: Configura a comunicação com o RabbitMQ.

4. No arquivo `RabbitMQConstant.java`:
   - Interface `RabbitMQConstant.java`: Define constantes relacionadas ao RabbitMQ, como nomes de filas e trocas.

5. No arquivo `ComponentConsumer.java`:
   - Classe `ComponentConsumer.java`: Processa mensagens relacionadas a componentes.

6. No arquivo `SensorConsumer.java`:
   - Classe `SensorConsumer.java`: Processa mensagens relacionadas a sensores.

7. No arquivo `ComponentController.java`:
   - Classe `ComponentController.java`: Controla solicitações relacionadas a componentes.

8. No arquivo `SensorController.java`:
   - Classe `SensorController.java`: Controla solicitações relacionadas a sensores.

9. No arquivo `Response.java`:
   - Classe `Response.java`: Representa uma resposta padrão da API.

10. No arquivo `ComponentDto.java`:
    - Classe `ComponentDto.java`: Define objetos de dados relacionados a componentes.

11. No arquivo `SensorDto.java`:
    - Classe `SensorDto.java`: Define objetos de dados relacionados a sensores.

12. No arquivo `ComponentService.java`:
    - Classe `ComponentService.java`: Lida com a lógica de negócios relacionada a componentes.

13. No arquivo `SensorService.java`:
    - Classe `SensorService.java`: Lida com a lógica de negócios relacionada a sensores.

### Codificou atributos? Em quais classes? Quais atributos? Por que esses nomes e tipos?

**No arquivo `FirebaseConfig.java`**:

- Atributo `private AmqpAdmin amqpAdmin`: Usado para administrar objetos do RabbitMQ.

**No arquivo `RabbitMQConfig.java`**:

- Atributo `private static final String EXCHANGE_NAME`: Constante que representa o nome da troca no RabbitMQ.

**No arquivo `ComponentConsumer.java`**:

- Atributo `private ComponentService componentService`: Injetado para processar mensagens relacionadas a componentes.

**No arquivo `SensorConsumer.java`**:

- Atributo `private SensorService sensorService`: Injetado para processar mensagens relacionadas a sensores.

### Codificou métodos? Em quais classes? Quais métodos? Por que esses nomes e parâmetros?

**No arquivo `FirebaseConfig.java`**:

- Método `init`: Inicializa a conexão com o Firebase a partir de um arquivo JSON de credenciais.

**No arquivo `RabbitMQConfig.java`**:

- Métodos privados `queue`, `topicExchange`, `binding` e `add`: Configuram filas, trocas e ligações no RabbitMQ.

**No arquivo `ComponentConsumer.java`**:

- Método `createComponent`: Cria componentes com base em mensagens do RabbitMQ.

**No arquivo `SensorConsumer.java`**:

- Método `registrySensor`: Registra informações de sensores a partir de mensagens do RabbitMQ.

**No arquivo `ComponentController.java`**:

- Método `activate`: Ativa componentes e envia mensagens para o RabbitMQ.

**No arquivo `SensorController.java`**:

- Métodos `getRegistryById` e `getAllRegistryByIdentifier`: Obtêm informações de sensores com base em identificadores.

**No arquivo `ComponentService.java`**:

- Métodos `create` e `activate`: Criam e ativam componentes, interagindo com o Firebase.

**No arquivo `SensorService.java`**:

- Métodos `registry`, `getRegistryById` e `getAllRegistryByIdentifier`: Registram e recuperam informações de sensores no Firebase.

### Codificou atributos estáticos? Em quais classes? Por que eles são estáticos? Por que esses nomes e tipos?

**No arquivo `RabbitMQConfig.java`**:

- Atributo `private static final String EXCHANGE_NAME`: Estático para representar uma constante usada em toda a classe. Armazena o nome da troca do RabbitMQ.

### Codificou métodos estáticos? Em quais classes? Quais métodos? Por que esses nomes e parâmetros?

**No arquivo `FirebaseConfig.java`**:

- Método `init`: Estático, chamado na inicialização da classe para configurar o Firebase a partir de um arquivo JSON.

**No arquivo `RabbitMQConfig.java`**:

- Métodos privados `queue`, `topicExchange`, `binding` e `add`: Estáticos, usados internamente para configurar o RabbitMQ.

### Codificou métodos construtores? Em quais classes?

**No arquivo `RabbitMQConfig.java`**:

- Construtor `public RabbitMQConfig(AmqpAdmin amqpAdmin)`: Usado para injetar uma instância de `AmqpAdmin`.

### Codificou atributos protegidos e/ou privados? Em quais classes? Quais atributos? Por que não são públicos?

**No arquivo `FirebaseConfig.java`**:

- Atributo `private AmqpAdmin amqpAdmin`: Privado para encapsular a implementação da classe e evitar acesso direto.

### Codificou métodos protegidos e/ou privados? Em quais classes? Quais métodos? Por que não são públicos?

**No arquivo `RabbitMQConfig.java`**:

- Métodos privados `queue`, `topicExchange`, `binding` e `add`: Privados para serem usados internamente na classe `RabbitMQConfig`.

### Codificou interfaces ou classes puramente virtuais? Quais classes/interfaces?

Não foram codificadas interfaces ou classes puramente virtuais.

### Codificou classes abstratas ou classes virtuais? Quais classes?

Não foram codificadas classes abstratas ou classes virtuais.

### Instanciou objetos? Quais objetos?

- No arquivo `FirebaseConfig.java`, são instanciados objetos `FirebaseOptions` e `FirebaseApp` durante a inicialização para conectar o Firebase.

### Instalou e usou bibliotecas de terceiros? Quais bibliotecas? Para que servem?

- No arquivo `FirebaseConfig.java`, a biblioteca de terceiros `Google Firebase` é usada para configurar a conexão com o Firebase.

- No arquivo `RabbitMQConfig.java`, a biblioteca de terceiros `Spring AMQP` é usada para configurar a comunicação com o RabbitMQ.

### Codificou enums? Quais enums?

- No arquivo `RabbitMQConstant.java`, são definidas constantes em forma de enumeração para representar nomes de filas e trocas no RabbitMQ.

### Identificou e codificou classes de dados? Quais classes?

- No arquivo `ComponentDto.java`, a classe `ComponentDto` é uma classe de dados que representa objetos de dados relacionados a componentes.

- No arquivo `SensorDto.java`, a classe `SensorDto` é uma classe de dados que representa objetos de dados relacionados a sensores.

### Identificou e codificou classes de comportamento? Quais classes?

- No arquivo `ComponentService.java`, a classe `ComponentService` é uma classe de comportamento que lida com a lógica de negócios relacionada a componentes.

- No arquivo `SensorService.java`, a classe `SensorService` é uma classe de comportamento que lida com a lógica de negócios relacionada a sensores.

### Usou polimorfismo? Com quais classes?

Não foi utilizado polimorfismo no projeto.

### Usou objetos imutáveis? Quais objetos?

- No arquivo `ComponentDto.java`, a classe `ComponentDto` possui atributos imutáveis, como `identifier` e `active`, uma vez que são declarados como `final`.

- No arquivo `SensorDto.java`, a classe `SensorDto` possui atributos imutáveis, como `identifier`, `temp`, `ph`, `water_level`, `turbidity` e `created_at`, uma vez que são declarados como `final`.

### Ocultou informações usando atributos e/ou métodos protected/private? Em quais classes? Quais atributos e métodos? Por que foi importante ocultar esses dados?

**No arquivo `FirebaseConfig.java`**:

- Atributo `private AmqpAdmin amqpAdmin`: Atributo privado para encapsular a implementação interna da classe e evitar acesso direto.

### Ocultou informações usando interfaces ou classes puramente virtuais? Em quais classes/interfaces?

Não foram usadas interfaces ou classes puramente virtuais no projeto.

### Codificou classes imutáveis? Quais classes? Por que foi importante elas serem imutáveis?

- As classes `ComponentDto` e `SensorDto` são classes imutáveis para garantir que os objetos de dados relacionados a componentes e sensores não sejam modificados após a criação, mantendo a integridade dos dados.

