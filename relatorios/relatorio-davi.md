# Relatório de Atendimento dos Requisitos do Projeto Integrador - POO

## Codificou classes? Quais classes? Para que servem?

1. No arquivo `SmartfishApplication.java`:
   - Classe `SmartfishApplication`:

     - **Descrição:** A classe Application é a classe principal do aplicativo Spring Boot. Ela é responsável por inicializar o aplicativo e carregar as configurações.

2. No arquivo `FirebaseConfig.java`:
   - Classe `FirebaseConfig`:
     - **Descrição:** A classe FirebaseConfig é responsável por configurar a conexão com o Firebase. Ela usa a biblioteca de terceiros Google Firebase para fazer isso.

3. No arquivo `RabbitMQConfig.java`:
   - Classe `RabbitMQConfig`:
     - **Descrição:** A classe RabbitMQConfig é responsável por configurar a comunicação com o RabbitMQ. Ela usa a biblioteca de terceiros Spring AMQP para fazer isso.

4. No arquivo `RabbitMQConstant.java`:
   - Interface `RabbitMQConstant`:
     - **Descrição:** A interface RabbitMQConstant define constantes relacionadas ao RabbitMQ, como nomes de filas e trocas. Isso torna mais fácil acessar esses valores em todo o aplicativo.

5. No arquivo `ComponentConsumer.java`:
   - Classe `ComponentConsumer`:
     - **Descrição:** A classe ComponentConsumer é um consumidor RabbitMQ que processa mensagens relacionadas a componentes. Ela recebe mensagens JSON do RabbitMQ e usa os dados para criar ou ativar componentes no Firebase.

6. No arquivo `SensorConsumer.java`:
   - Classe `SensorConsumer`:
     - **Descrição:** A classe SensorConsumer é um consumidor RabbitMQ que processa mensagens relacionadas a sensores. Ela recebe mensagens JSON do RabbitMQ e usa os dados para registrar informações de sensores no Firebase.

7. No arquivo `ComponentController.java`:
   - Classe `ComponentController`:
     - **Descrição:** A classe ComponentController é um controlador responsável por lidar com solicitações relacionadas a componentes. Ela fornece endpoints REST para criar, ativar e obter componentes.

8. No arquivo `SensorController.java`:
   - Classe `SensorController`:
     - **Descrição:** A classe SensorController é um controlador responsável por lidar com solicitações relacionadas a sensores. Ela fornece endpoints REST para registrar, obter e atualizar informações de sensores.

9. No arquivo `Response.java`:
   - Classe `Response`:
     - **Descrição:** A classe Response representa uma resposta padrão da API. Ela contém dados e possíveis erros.

10. No arquivo `ComponentDto.java`:
    - Classe `ComponentDto`:
      - **Descrição:** A classe ComponentDto é um DTO que representa objetos de dados relacionados a componentes. Ela contém atributos como identifier, active, angle, e time.

11. No arquivo `SensorDto.java`:
    - Classe `SensorDto`:
      - **Descrição:** A classe SensorDto é um DTO que representa objetos de dados relacionados a sensores. Ela contém atributos como identifier, temp, ph, water_level, turbidity e created_at.

12. No arquivo `ComponentService.java`:
    - Classe `ComponentService`:
      - **Descrição:** A classe ComponentService é responsável por lidar com a lógica de negócios relacionada a componentes. Ela fornece métodos para criar, ativar e obter componentes.

13. No arquivo `SensorService.java`:
    - Classe `SensorService`:
      - **Descrição:** A classe SensorService é responsável por lidar com a lógica de negócios relacionada a sensores. Ela fornece métodos para registrar, obter e atualizar informações de sensores.

## Codificou atributos? Em quais classes? Quais atributos? Por que esses nomes e tipos?

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

## Codificou métodos? Em quais classes? Quais métodos? Por que esses nomes e parâmetros?

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
