# Relatório de Atendimento dos Requisitos do Projeto Integrador - POO

Este relatório apresenta o projeto de Programação Orientada a Objetos (POO) desenvolvido por Davi Pelloso, RA: 1976516. O projeto é composto por um conjunto de classes Java que desempenham funções específicas em um sistema. A seguir, são apresentados detalhes sobre as classes, atributos, métodos e práticas utilizadas no projeto.

## Conceitos Básicos

### Classes

   **No arquivo `SmartfishApplication.java`**:
   - Classe `SmartfishApplication`:

     - **Descrição:** A classe Application é a classe principal do aplicativo Spring Boot. Ela é responsável por inicializar o aplicativo e carregar as configurações.

   **No arquivo `FirebaseConfig.java`**:
   - Classe `FirebaseConfig`:
     - **Descrição:** A classe FirebaseConfig é responsável por configurar a conexão com o Firebase. Ela usa a biblioteca de terceiros Google Firebase para fazer isso.

   **No arquivo `RabbitMQConfig.java`**:
   - Classe `RabbitMQConfig`:
     - **Descrição:** A classe RabbitMQConfig é responsável por configurar a comunicação com o RabbitMQ. Ela usa a biblioteca de terceiros Spring AMQP para fazer isso.

   **No arquivo `RabbitMQConstant.java`**:
   - Interface `RabbitMQConstant`:
     - **Descrição:** A interface RabbitMQConstant define constantes relacionadas ao RabbitMQ, como nomes de filas e trocas. Isso torna mais fácil acessar esses valores em todo o aplicativo.

   **No arquivo `ComponentConsumer.java`**:
   - Classe `ComponentConsumer`:
     - **Descrição:** A classe ComponentConsumer é um consumidor RabbitMQ que processa mensagens relacionadas a componentes. Ela recebe mensagens JSON do RabbitMQ e usa os dados para criar ou ativar componentes no Firebase.

   **No arquivo `SensorConsumer.java`**:
   - Classe `SensorConsumer`:
     - **Descrição:** A classe SensorConsumer é um consumidor RabbitMQ que processa mensagens relacionadas a sensores. Ela recebe mensagens JSON do RabbitMQ e usa os dados para registrar informações de sensores no Firebase.

   **No arquivo `ComponentController.java`**:
   - Classe `ComponentController`:
     - **Descrição:** A classe ComponentController é um controlador responsável por lidar com solicitações relacionadas a componentes. Ela fornece endpoints REST para criar, ativar e obter componentes.

   **No arquivo `SensorController.java`**:
   - Classe `SensorController`:
     - **Descrição:** A classe SensorController é um controlador responsável por lidar com solicitações relacionadas a sensores. Ela fornece endpoints REST para registrar, obter e atualizar informações de sensores.

   **No arquivo `Response.java`**:
   - Classe `Response`:
     - **Descrição:** A classe Response representa uma resposta padrão da API. Ela contém dados e possíveis erros.

     **No arquivo `ComponentDto.java`**:
    - Classe `ComponentDto`:
      - **Descrição:** A classe ComponentDto é um DTO que representa objetos de dados relacionados a componentes. Ela contém atributos como identifier, active, angle, e time.

      **No arquivo `SensorDto.java`**:
    - Classe `SensorDto`:
      - **Descrição:** A classe SensorDto é um DTO que representa objetos de dados relacionados a sensores. Ela contém atributos como identifier, temp, ph, water_level, turbidity e created_at.

      **No arquivo `ComponentService.java`**:
    - Classe `ComponentService`:
      - **Descrição:** A classe ComponentService é responsável por lidar com a lógica de negócios relacionada a componentes. Ela fornece métodos para criar, ativar e obter componentes.

      **No arquivo `SensorService.java`**:
    - Classe `SensorService`:
      - **Descrição:** A classe SensorService é responsável por lidar com a lógica de negócios relacionada a sensores. Ela fornece métodos para registrar, obter e atualizar informações de sensores.

### Atributos

**No arquivo `FirebaseConfig.java`**:

- Atributo `private AmqpAdmin amqpAdmin`:
  - **Descrição:** O atributo amqpAdmin da classe RabbitMQConfig é usado para administrar objetos do RabbitMQ. Ele é um objeto da classe AmqpAdmin do Spring AMQP.

**No arquivo `RabbitMQConfig.java`**:

- Atributo `private static final String EXCHANGE_NAME`:
  - **Descrição:** A constante EXCHANGE_NAME da classe RabbitMQConstant representa o nome da troca no RabbitMQ. Ela é usada para rotear mensagens para filas específicas.

**No arquivo `ComponentConsumer.java`**:

- Atributo `private ComponentService componentService`:
  - **Descrição:** O atributo componentService da classe ComponentConsumer injeta uma instância de ComponentService para processar mensagens relacionadas a componentes. Isso permite que o consumidor use os métodos da classe ComponentService para criar ou ativar componentes no Firebase.

**No arquivo `SensorConsumer.java`**:

- Atributo `private SensorService sensorService`:
  - **Descrição:** Este atributo injeta uma instância de `SensorService` para processar mensagens relacionadas a sensores.

### Métodos

**No arquivo `FirebaseConfig.java`**:

- Método `init`:
  - **Descrição:** O método init da classe FirebaseConfig é usado para inicializar a conexão com o Firebase. Ele lê um arquivo JSON de credenciais e configura o Firebase com base nele.

**No arquivo `RabbitMQConfig.java`**:

- Métodos privados `queue`, `topicExchange`, `binding`, e `add`:
  - **Descrição:** Os métodos privados add, topicExchange e binding da classe RabbitMQConfig são usados para configurar filas, trocas e ligações no RabbitMQ. Isso ajuda na organização da comunicação entre componentes do sistema.

**No arquivo `ComponentConsumer.java`**:

- Método `createComponent`:
  - **Descrição:** O método createComponent da classe ComponentConsumer é um ouvinte RabbitMQ que cria componentes com base nas mensagens recebidas. Ele extrai informações das mensagens JSON e chama o método create da classe ComponentService para criar componentes no Firebase.

**No arquivo `SensorConsumer.java`**:

- Método `registrySensor`:
  - **Descrição:** O método registrySensor da classe SensorConsumer é um ouvinte RabbitMQ que registra informações de sensores com base nas mensagens recebidas. Ele extrai informações das mensagens JSON e chama o método registry da classe SensorService para registrar os dados dos sensores no Firebase.

**No arquivo `ComponentController.java`**:

- Método `activate`:
  - **Descrição:** O método activate da classe ComponentController é usado para ativar componentes. Ele recebe dados no formato JSON
 
**No arquivo `SensorComponent.java`**:
- Métodos `getRegistryById` e `getAllRegistryByIdentifier`:
  - **Descrição:** Obtém informações de sensores com base em identificadores.

**No arquivo `ComponentService.java`**:
- Métodos `create` e `activate`:
   - **Descrição**: Criam e ativam componentes, interagindo com o Firebase.
   
**No arquivo `SensorService.java`**:
 - Métodos `registry`, `getRegistryById` e `getAllRegistryByIdentifier`:
   - **Descrição**: Registram e recuperam informações de sensores no Firebase. 

### Atributos Estáticos e Métodos Estáticos

**No arquivo `RabbitMQConfig.java`:**
- Atributo Estático: `private static final String EXCHANGE_NAME`
  - **Descrição**: Estático para representar uma constante usada em toda a classe. Armazena o nome da troca do RabbitMQ.

**No arquivo `FirebaseConfig.java`:**
- Método Estático: `init`
  - **Descrição**: Estático, chamado na inicialização da classe para configurar o Firebase a partir de um arquivo JSON.

**No arquivo `RabbitMQConfig.java`:**
- Métodos privados: `queue`, `topicExchange`, `binding` e `add`
  - **Descrição**: Estáticos, usados internamente para configurar o RabbitMQ.

### Métodos Construtores

**No arquivo `RabbitMQConfig.java`:**
- Construtor: `public RabbitMQConfig(AmqpAdmin amqpAdmin)`
  - **Descrição**: Usado para injetar uma instância de AmqpAdmin.

### Atributos e Métodos Protegidos e/ou Privados

**No arquivo `FirebaseConfig.java`:**
- Atributo Privado: `private AmqpAdmin amqpAdmin`
  - **Descrição**: Privado para encapsular a implementação da classe e evitar acesso direto.

**No arquivo `RabbitMQConfig.java`:**
- Métodos privados: `queue`, `topicExchange`, `binding` e `add`
  - **Descrição**: Privados para serem usados internamente na classe RabbitMQConfig.
   
### Interfaces ou Classes Puramente Virtuais

- Não foram codificadas interfaces ou classes puramente virtuais.

### Classes Abstratas ou Classes Virtuais

- Não foram codificadas classes abstratas ou classes virtuais.

### Instanciação de Objetos

- **No arquivo `FirebaseConfig.java`**, são instanciados objetos `FirebaseOptions` e `FirebaseApp` durante a inicialização para conectar o Firebase.

### Bibliotecas de Terceiros

- **No arquivo `FirebaseConfig.java`**, a biblioteca de terceiros Google Firebase é usada para configurar a conexão com o Firebase.
- **No arquivo `RabbitMQConfig.java`**, a biblioteca de terceiros Spring AMQP é usada para configurar a comunicação com o RabbitMQ.

### Enums

**No arquivo `RabbitMQConstant.java`:**
- Definição de constantes em forma de enumeração para representar nomes de filas e trocas no RabbitMQ.

### Classes de Dados

**No arquivo `ComponentDto.java`:**
- Classe de dados que representa objetos de dados relacionados a componentes.

**No arquivo `SensorDto.java`:**
- Classe de dados que representa objetos de dados relacionados a sensores.

### Classes de Comportamento

**No arquivo `ComponentService.java`:**
- Classe de comportamento que lida com a lógica de negócios relacionada a componentes.

**No arquivo `SensorService.java`:**
- Classe de comportamento que lida com a lógica de negócios relacionada a sensores.

## Práticas de Programação

### Polimorfismo

- Não foi utilizado polimorfismo no projeto.

### Objetos Imutáveis

- No arquivo ComponentDto.java, a classe ComponentDto possui atributos imutáveis, como `identifier` e `active`, uma vez que são declarados como `final`.
- No arquivo SensorDto.java, a classe SensorDto possui atributos imutáveis, como `identifier`, `temp`, `ph`, `water_level`, `turbidity` e `created_at`, uma vez que são declarados como `final`.

### Ocultação de Informações

**No arquivo `FirebaseConfig.java`:**
- Atributo privado `AmqpAdmin amqpAdmin`: 
  - **Descrição**: Atributo privado para encapsular a implementação interna da classe e evitar acesso direto.

### Classes Imutáveis

- As classes `ComponentDto` e `SensorDto` são classes imutáveis para garantir que os objetos de dados relacionados a componentes e sensores não sejam modificados após a criação, mantendo a integridade dos dados.


