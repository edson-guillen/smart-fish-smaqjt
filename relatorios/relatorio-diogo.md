# Relatório de Atendimento dos Requisitos do Projeto Integrador - POO

**Nome:** Diogo Saffiotte Zafani  
**RA:** 1959438  
**Turma:** A  

## 1. SmartfishApplication.java

### Classe SmartfishApplication:
- **Descrição:** Esta classe representa a classe principal do aplicativo Spring Boot, encarregada de iniciar a aplicação.

## 2. FirebaseConfig.java

### Classe FirebaseConfig:
- **Descrição:** Esta classe é responsável por ajustar a conexão com o Firebase.

## 3. RabbitMQConfig.java

### Classe RabbitMQConfig:
- **Descrição:** Esta classe cuida da configuração da comunicação com o RabbitMQ.

## 4. RabbitMQConstant.java

### Interface RabbitMQConstant:
- **Descrição:** Esta interface define constantes relacionadas ao RabbitMQ, como nomes de filas e trocas.

## 5. ComponentConsumer.java

### Classe ComponentConsumer:
- **Descrição:** Este componente é um consumidor RabbitMQ encarregado de processar mensagens associadas a componentes.

## 6. SensorConsumer.java

### Classe SensorConsumer:
- **Descrição:** Este componente é um consumidor RabbitMQ encarregado de processar mensagens associadas a sensores.

## 7. ComponentController.java

### Classe ComponentController:
- **Descrição:** Esta classe funciona como um controlador responsável por tratar solicitações associadas a componentes.

## 8. SensorController.java

### Classe SensorController:
- **Descrição:** Esta classe funciona como um controlador responsável por tratar solicitações associadas a sensores.

## 9. Response.java

### Classe Response:
- **Descrição:** Este componente representa uma resposta padrão da API, contendo dados e possíveis erros.

## 10. ComponentDto.java

### Classe ComponentDto:
- **Descrição:** Esta classe é um DTO (Objeto de Transferência de Dados) que representa objetos de dados associados a componentes.

## 11. SensorDto.java

### Classe SensorDto:
- **Descrição:** Este componente é um DTO que representa objetos de dados associados a sensores.

## 12. ComponentService.java

### Classe ComponentService:
- **Descrição:** Este componente é encarregado de lidar com a lógica de negócios associada a componentes.

## 13. SensorService.java

### Classe SensorService:
- **Descrição:** Este componente é encarregado de lidar com a lógica de negócios associada a sensores.

## 14. FirebaseConfig.java

### Atributo `private AmqpAdmin amqpAdmin`:
- **Descrição:** Este atributo é utilizado para administrar objetos no RabbitMQ.

## 15. RabbitMQConfig.java

### Atributo `private static final String EXCHANGE_NAME`:
- **Descrição:** Este atributo é uma constante que representa o nome da troca no RabbitMQ.

## 16. ComponentConsumer.java

### Atributo `private ComponentService componentService`:
- **Descrição:** Este atributo injeta uma instância de ComponentService para processar mensagens relacionadas a componentes.

## 17. SensorConsumer.java

### Atributo `private SensorService sensorService`:
- **Descrição:** Este atributo injeta uma instância de SensorService para processar mensagens relacionadas a sensores.

## 18. FirebaseConfig.java

### Método `init`:
- **Descrição:** O método init é utilizado para iniciar a conexão com o Firebase. Ele lê um arquivo JSON de credenciais e configura o Firebase com base nessas informações.

## 19. RabbitMQConfig.java

### Métodos privados `queue`, `topicExchange`, `binding`, e `add`:
- **Descrição:** Esses métodos privados são empregados para configurar filas, trocas e ligações no RabbitMQ, contribuindo para a organização da comunicação entre os componentes do sistema.

## 20. ComponentConsumer.java

### Método `createComponent`:
- **Descrição:** Este método é um ouvinte RabbitMQ que cria componentes com base nas mensagens recebidas. Ele extrai informações das mensagens JSON e chama o serviço `create` para criar componentes no Firebase.

## 21. SensorConsumer.java

### Método `registrySensor`:
- **Descrição:** Este método é um ouvinte RabbitMQ que registra informações de sensores com base nas mensagens recebidas. Ele extrai informações das mensagens JSON e chama o serviço `registry` para registrar os dados dos sensores no Firebase.

## 22. ComponentController.java

### Método `activate`:
- **Descrição:** Este método é usado para ativar componentes. Recebe dados no formato JSON e os envia para o RabbitMQ.

## 23. SensorController.java

### Métodos `getRegistryById` e `getAllRegistryByIdentifier`:
- **Descrição:** Esses métodos são usados para obter informações de sensores com base em seus identificadores. Eles chamam os serviços correspondentes para recuperar os dados no Firebase.

## 24. ComponentService.java

### Método `create`:
- **Descrição:** Este método cria componentes no Firestore do Firebase com base nos dados recebidos. Ele verifica se o componente já existe no Firestore antes de criar um novo.

### Método `activate`:
- **Descrição:** Este método é usado para ativar componentes e enviar mensagens para o RabbitMQ. Ele aceita um objeto `ComponentDto` como parâmetro.

## 25. SensorService.java

### Métodos `registry`, `getRegistryById` e `getAllRegistryByIdentifier`:
- **Descrição:** Esses métodos são usados para registrar e recuperar informações de sensores no Firestore do Firebase com base em seus identificadores. Eles interagem com o Firestore para realizar essas operações.

## 26. RabbitMQConfig.java

### Atributo `private static final String EXCHANGE_NAME`:
- **Descrição:** Este atributo é estático porque representa um valor constante usado em toda a classe. Ele armazena o nome da troca do RabbitMQ, que é uma configuração importante e não deve ser modificada.

## 27. FirebaseConfig.java

### Método `init`:
- **Descrição:** Este método é estático porque é chamado na inicialização da classe `FirebaseConfig` e não depende de instâncias específicas da classe. Ele recebe um arquivo JSON como parâmetro para configurar o Firebase com base nas credenciais fornecidas.

## 28. RabbitMQConfig.java

### Métodos privados `queue`, `topicExchange`, `binding`, e `add`:
- **Descrição:** Esses métodos são estáticos porque são auxiliares internos da classe `RabbitMQConfig` e não devem ser acessados diretamente por outras classes. Eles são empregados para configurar o RabbitMQ.

## 29. RabbitMQConfig.java

### Construtor `public RabbitMQConfig(AmqpAdmin amqpAdmin)`:
- **Descrição:** Este construtor é usado para injetar uma instância de `AmqpAdmin` na classe `RabbitMQConfig`. Ele recebe um parâmetro do tipo `AmqpAdmin` para inicializar o atributo `amqpAdmin`.

## 30. FirebaseConfig.java

### Atributo `private AmqpAdmin amqpAdmin`:
- **Descrição:** Este atributo é restrito para encapsular a implementação da classe e impedir o acesso direto por outras classes. Ele é utilizado internamente para gerenciar objetos do RabbitMQ.

## 31. RabbitMQConfig.java

### Métodos privados `queue`, `topicExchange`, `binding`, e `add`:
- **Descrição:** Esses métodos são privados, pois são auxiliares internos da classe `RabbitMQConfig` e não devem ser acessados diretamente por outras classes. Eles são empregados para configurar o RabbitMQ.
