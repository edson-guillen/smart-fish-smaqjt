# Relatório de Atendimento dos Requisitos do Projeto Integrador - POO

## Codificou classes? Quais classes? Para que servem?

1. No arquivo `SmartfishApplication.java`:
   - Classe `SmartfishApplication`:
     - Descrição: A classe principal do aplicativo Spring Boot é responsável por inicializar a aplicação. Ela é responsável por carregar as configurações do aplicativo, criar o contexto Spring e iniciar o servidor.

2. No arquivo `FirebaseConfig.java`:
   - Classe `FirebaseConfig`:
     - Descrição: A classe de configuração do Firebase é responsável por configurar a conexão com o Firebase. Ela fornece métodos para obter as chaves de API do Firebase, criar um cliente Firebase e configurar as opções de conexão.

3. No arquivo `RabbitMQConfig.java`:
   - Classe `RabbitMQConfig`:
     - Descrição: A classe de configuração do RabbitMQ é responsável por configurar a comunicação com o RabbitMQ. Ela fornece métodos para configurar as propriedades do broker, criar conexões e filas, e definir políticas de entrega.

4. No arquivo `RabbitMQConstant.java`:
   - Interface `RabbitMQConstant`:
     - Descrição: A interface RabbitMQConstants define constantes relacionadas ao RabbitMQ, como nomes de filas e trocas. Essas constantes podem ser usadas para simplificar a configuração e o uso do RabbitMQ.

5. No arquivo `ComponentConsumer.java`:
   - Classe `ComponentConsumer`:
     - Descrição: A classe ComponentConsumer é um consumidor RabbitMQ responsável por processar mensagens relacionadas a componentes. Ela é responsável por receber mensagens da fila de componentes, processar as mensagens e gerar respostas.

6. No arquivo `SensorConsumer.java`:
   - Classe `SensorConsumer`:
     - Descrição: A classe SensorConsumer é um consumidor RabbitMQ responsável por processar mensagens relacionadas a sensores. Ela é responsável por receber mensagens da fila de sensores, processar as mensagens e gerar respostas.

7. No arquivo `ComponentController.java`:
   - Classe `ComponentController`:
     - Descrição: A classe ComponentController é um controlador responsável por lidar com solicitações relacionadas a componentes. Ela fornece métodos para criar, ler, atualizar e excluir componentes.

8. No arquivo `SensorController.java`:
   - Classe `SensorController`:
     - Descrição: A classe SensorController é um controlador responsável por lidar com solicitações relacionadas a sensores. Ela fornece métodos para criar, ler, atualizar e excluir sensores.

9. No arquivo `Response.java`:
   - Classe `Response`:
     - Descrição: A classe APIResponse representa uma resposta padrão da API, contendo dados e possíveis erros..

10. No arquivo `ComponentDto.java`:
    - Classe `ComponentDto`:
      - Descrição: A classe ComponentDto é um DTO (Data Transfer Object) que representa objetos de dados relacionados a componentes.

11. No arquivo `SensorDto.java`:
    - Classe `SensorDto`:
      - Descrição: A classe SensorDto é um DTO que representa objetos de dados relacionados a sensores.

12. No arquivo `ComponentService.java`:
    - Classe `ComponentService`:
      - Descrição: A classe ComponentService é responsável por lidar com a lógica de negócios relacionada a componentes.
13. No arquivo `SensorService.java`:
    - Classe `SensorService`:
      - Descrição: A classe SensorService fornece operações de negócios para sensores.

## Codificou atributos? Em quais classes? Quais atributos? Por que esses nomes e tipos?

14. **No arquivo `FirebaseConfig.java`**:

- Atributo `private AmqpAdmin amqpAdmin`:
  - Descrição: Atributo usado para administrar objetos do RabbitMQ.

15. **No arquivo `RabbitMQConfig.java`**:

- Atributo `private static final String EXCHANGE_NAME`:
  - Descrição: Constante que representa o nome da troca no RabbitMQ.

16. **No arquivo `ComponentConsumer.java`**:

- Atributo `private ComponentService componentService`:
  - Descrição: Injeta uma instância de ComponentService para processar mensagens de componentes.

17. **No arquivo `SensorConsumer.java`**:

- Atributo `private SensorService sensorService`:
  - Descrição: Injeta um SensorService para processar mensagens de sensores.

## Codificou métodos? Em quais classes? Quais métodos? Por que esses nomes e parâmetros?

18. **No arquivo `FirebaseConfig.java`**:

- Método `init`:
  - Descrição: Inicializa a conexão com o Firebase usando um arquivo JSON de credenciais.

19. **No arquivo `RabbitMQConfig.java`**:

- Métodos privados `queue`, `topicExchange`, `binding`, e `add`:
  - Descrição: Métodos privados para configurar filas, trocas e ligações no RabbitMQ.

20. **No arquivo `ComponentConsumer.java`**:

- Método `createComponent`:
  - Descrição: Este método é um ouvinte RabbitMQ que cria componentes com base nas mensagens recebidas. Ele extrai informações das mensagens JSON e chama o serviço `create` para criar componentes no Firebase.

21. **No arquivo `SensorConsumer.java`**:

- Método `registrySensor`:
  - Descrição: Este método é um ouvinte RabbitMQ que registra informações de sensores com base nas mensagens recebidas. Ele extrai informações das mensagens JSON e chama o serviço `registry` para registrar os dados dos sensores no Firebase.

22. **No arquivo `ComponentController.java`**:

- Método `activate`:
  - Descrição: Ativa componentes enviando dados JSON para o RabbitMQ.

23. **No arquivo `SensorController.java`**:

- Métodos `getRegistryById` e `getAllRegistryByIdentifier`:
  - Descrição: Obtém informações de sensores chamando os serviços correspondentes no Firebase.

24. **No arquivo `ComponentService.java`**:

- Método `create`:
  - Descrição: Ativa componentes e envia mensagens para o RabbitMQ.

- Método `activate`:
  - Descrição: Este método é usado para ativar componentes e enviar mensagens para o RabbitMQ. Ele aceita um objeto `ComponentDto` como parâmetro.

25. **No arquivo `SensorService.java`**:

- Métodos `registry`, `getRegistryById` e `getAllRegistryByIdentifier`:
  - Descrição: Registra e recupera informações de sensores no Firestore.

## Codificou atributos estáticos? Em quais classes? Por que eles são estáticos? Por que esses nomes e tipos?

26. **No arquivo `RabbitMQConfig.java`**:

- Atributo `private static final String EXCHANGE_NAME`:
  - Atributo estático que armazena o nome da troca do RabbitMQ.

## Codificou métodos estáticos? Em quais classes? Quais métodos? Por que esses nomes e parâmetros?

27. **No arquivo `FirebaseConfig.java`**:

- Método `init`:
  - Método estático que configura o Firebase com base nas credenciais fornecidas em um arquivo JSON.

28. **No arquivo `RabbitMQConfig.java`**:

- Método privado `queue`:
  - Descrição: Método estático que cria uma fila no RabbitMQ.

- Método privado `topicExchange`:
  - Descrição: Método estático que cria uma troca do tipo tópico no RabbitMQ.

- Método privado `binding`:
  - Descrição: Método estático que cria uma ligação entre uma fila e uma troca no RabbitMQ.

## Codificou métodos construtores? Em quais classes?

29. **No arquivo `RabbitMQConfig.java`**:

- Construtor `public RabbitMQConfig(AmqpAdmin amqpAdmin)`:
  - Descrição: Construtor que injeta um AmqpAdmin na classe RabbitMQConfig.

## Codificou atributos protegidos e/ou privados? Em quais classes? Quais atributos? Por que não são públicos?

30. **No arquivo `FirebaseConfig.java`**:

- Atributo `private AmqpAdmin amqpAdmin`:
  - Descrição: Atributo privado usado internamente para administrar objetos do RabbitMQ.

## Codificou métodos protegidos e/ou privados? Em quais classes? Quais métodos? Por que não são públicos?

31. **No arquivo `RabbitMQConfig.java`**:

- Métodos privados `queue`, `topicExchange`, `binding`, e `add`:
  - Descrição: Esses métodos são privados porque são auxiliares internos da classe `RabbitMQConfig` e não devem ser acessados diretamente por outras classes. Eles são usados para configurar o RabbitMQ.

## Codificou interfaces ou classes puramente virtuais? Quais classes/interfaces?

Nenhum arquivo do projeto apresenta a codificação de interfaces ou classes puramente virtuais.

## Codificou classes abstratas ou classes virtuais? Quais classes?

Nenhum arquivo do projeto apresenta a codificação de classes abstratas ou classes virtuais.

## Instanciou objetos? Quais objetos?

32. - No arquivo `FirebaseConfig.java`, é instanciado um objeto `FirebaseOptions` e um objeto `FirebaseApp` durante a inicialização para conectar o Firebase.

## Instalou e usou bibliotecas de terceiros? Quais bibliotecas? Para que servem?

33. - No arquivo `FirebaseConfig.java`, a biblioteca de terceiros `Google Firebase` é usada para configurar a conexão com o Firebase. Ela é responsável por fornecer a integração com o Firebase.

34. - No arquivo `RabbitMQConfig.java`, a biblioteca de terceiros `Spring AMQP` é usada para configurar a comunicação com o RabbitMQ. Ela fornece classes e métodos para interagir com o RabbitMQ de forma simplificada.

## Codificou enums? Quais enums?

35. - No arquivo `RabbitMQConstant.java`, são definidas constantes em forma de enumeração para representar nomes de filas e trocas no RabbitMQ. Exemplo: `REGISTRY_ESP` e `STATUS_ESP`.

## Identificou e codificou classes de dados? Quais classes?

36. - No arquivo `ComponentDto.java`, a classe `ComponentDto` é uma classe de dados que representa objetos de dados relacionados a componentes. Ela contém atributos como `identifier`, `active`, `angle`, e `time`.

37. - No arquivo `SensorDto.java`, a classe `SensorDto` é uma classe de dados que representa objetos de dados relacionados a sensores. Ela contém atributos como `identifier`, `temp`, `ph`, `water_level`, `turbidity` e `created_at`.

## Identificou e codificou classes de comportamento? Quais classes?

38. - No arquivo `ComponentService.java`, a classe `ComponentService` é uma classe de comportamento que lida com a lógica de negócios relacionada a componentes. Ela contém métodos como `create` e `activate` para criar e ativar componentes.

39. - No arquivo `SensorService.java`, a classe `SensorService` é uma classe de comportamento que lida com a lógica de negócios relacionada a sensores. Ela contém métodos como `registry`, `getRegistryById` e `getAllRegistryByIdentifier` para registrar e recuperar informações de sensores.

## Usou polimorfismo? Com quais classes?

Não foram identificados exemplos de uso de polimorfismo no projeto.

## Usou objetos imutáveis? Quais objetos?

40. - No arquivo `ComponentDto.java`, a classe `ComponentDto` possui atributos imutáveis, como `identifier` e `active`, uma vez que são declarados como `final` e não podem ser modificados após a inicialização.

41. - No arquivo `SensorDto.java`, a classe `SensorDto` possui atributos imutáveis, como `identifier`, `temp`, `ph`, `water_level`, `turbidity`, e `created_at`, uma vez que são declarados como `final` e não podem ser modificados após a inicialização.

## Usou diagramas UML para discutir a solução? Fazer upload dos diagramas?

Não foram fornecidos diagramas UML no projeto.

## Ocultou informações usando atributos e/ou métodos protected/private? Em quais classes? Quais atributos e métodos? Por que foi importante ocultar esses dados?

42. - No arquivo `FirebaseConfig.java`, o atributo `private AmqpAdmin amqpAdmin` é oculto com o modificador `private` para encapsular a implementação da classe e evitar o acesso direto a ele por outras classes. A administração do RabbitMQ é uma preocupação interna dessa classe.

## Ocultou informações usando interfaces ou classes puramente virtuais? Em quais classes/interfaces?

Não foram usadas interfaces ou classes puramente virtuais no projeto.

## Codificou classes imutáveis? Quais classes? Por que foi importante elas serem imutáveis?

- As classes `ComponentDto` e `SensorDto` são classes imutáveis. Elas são importantes para garantir que os objetos de dados relacionados a componentes e sensores não sejam modificados após a criação, mantendo a integridade dos dados. Isso é útil em cenários onde a imutabilidade dos objetos é desejada para evitar efeitos colaterais indesejados.
