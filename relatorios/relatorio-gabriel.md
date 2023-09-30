# Relatório do Projeto Integrador - POO

## 1ª) Classes e suas funções

### SmartFishApplication.java
- **Classe:** SmartfishApplication.
- **Função:** Esta é a classe principal responsável por iniciar a aplicação Spring Boot.

### FirebaseConfig.java
- **Classe:** FirebaseConfig.
- **Função:** Esta classe tem a função de inicializar o Firebase, autenticando a aplicação usando o arquivo `serviceAccountKey.json`.

### RabbitMQConstant.java
- **Classe:** RabbitMQConstant.
- **Função:** Esta classe de configuração Spring Boot gerencia filas de mensagens com o RabbitMQ, permitindo a comunicação com outros componentes da aplicação ou sistemas externos.

### ComponentConsumer.java
- **Classe:** ComponentConsumer.
- **Função:** Esta classe atua como um consumidor de mensagens na fila `StatusQueue` do RabbitMQ e cria componentes na aplicação.

### SensorConsumer.java
- **Classe:** SensorConsumer.
- **Função:** A classe SensorConsumer consome mensagens na fila `RegistryQueue` do RabbitMQ e registra sensores na aplicação.

### ComponentController.java
- **Classe:** ComponentController.
- **Função:** Este é um controlador REST que lida com requisições HTTP relacionadas a componentes na aplicação.

### SensorController.java
- **Classe:** SensorController.
- **Função:** Este é um controlador REST que lida com requisições HTTP relacionadas a sensores na aplicação.

### Response.java
- **Classe:** Response.
- **Função:** Esta classe é usada para enviar respostas para o usuário quando ele faz uma requisição HTTP no servidor.

### ComponentDto.java
- **Classe:** ComponentDto.
- **Função:** Esta classe de transferência de dados armazena informações de componentes e envia-as ao usuário quando ele faz uma requisição HTTP.

### SensorDto.java
- **Classe:** SensorDto.
- **Função:** Esta classe é usada para controlar registros de sensores, permitindo ao servidor receber e manipular informações de sensores em formato de objetos.

### ComponentService.java
- **Classe:** ComponentService.
- **Função:** Esta classe de serviço é responsável por criar, ler e excluir componentes. Ela utiliza o Firebase para armazenar os dados dos componentes e o RabbitMQ para ativar componentes por meio de mensagens.

### SensorService.java
- **Classe:** SensorService.
- **Função:** Esta classe é utilizada pelo servidor de aplicação para gerenciar a parte lógica dos registros de sensores.

## 2ª) Codificou atributos

### FirebaseConfig.java
- **Atributo:** `private AmqpAdmin amqpAdmin`.
- **Função:** Este atributo é utilizado para administrar objetos do RabbitMQ.

### RabbitMQConfig.java
- **Atributo:** `private static final String EXCHANGE_NAME`.
- **Função:** Este atributo é uma constante que representa o nome da troca no RabbitMQ.

### ComponentConsumer.java
- **Atributo:** `private ComponentService componentService`.
- **Função:** Este atributo é usado para processar mensagens relacionadas a componentes.

### SensorConsumer.java
- **Atributo:** `private SensorService sensorService`.
- **Função:** Este atributo é usado para processar mensagens relacionadas a sensores.

## 3ª) Codificou métodos

### FirebaseConfig.java
- **Método:** `init`.
- **Função:** Este método realiza a inicialização da conexão com o Firebase, lendo um arquivo JSON de credenciais e configurando o Firebase com base nas informações lidas.

### RabbitMQConfig.java
- **Métodos:** `queue`, `topicExchange`, `binding` e `add`.
- **Função:** Estes métodos auxiliam na configuração e organização da comunicação entre componentes usando o RabbitMQ.

### ComponentConsumer.java
- **Método:** `createComponent`.
- **Função:** Este método atua como um ouvinte do RabbitMQ e tem a função de criar componentes com base nas mensagens JSON recebidas, utilizando o Firebase para a criação.

### SensorConsumer.java
- **Método:** `registrySensor`.
- **Função:** Este método atua como um ouvinte do RabbitMQ e registra informações de sensores com base nas mensagens JSON recebidas, utilizando o Firebase para o registro.

### ComponentController.java
- **Método:** `activate`.
- **Função:** Este método lida com a ativação de componentes, recebendo e enviando dados em formato JSON via requisições HTTP.

### SensorController.java
- **Métodos:** `getRegistryById` e `getAllRegistryByIdentifier`.
- **Função:** Estes métodos são responsáveis por obter informações de sensores com base em seus identificadores por meio de requisições HTTP.

### ComponentService.java
- **Método:** `create`.
- **Função:** Este método cria componentes no Firestore do Firebase com base nos dados recebidos e verifica se o componente já existe antes de criar um novo.

- **Método:** `activate`.
- **Função:** Este método ativa componentes e envia mensagens ao RabbitMQ para a ativação.

### SensorService.java
- **Métodos:** `registry`, `getRegistryById` e `getAllRegistryByIdentifier`.
- **Função:** Estes métodos são responsáveis por registrar e recuperar informações de sensores no Firestore do Firebase com base em seus identificadores.

## 4ª) Atributos estáticos

### RabbitMQConfig.java
- **Atributo:** `private static final String EXCHANGE_NAME`.
- **Função:** Este atributo é estático porque representa um valor constante usado em toda a classe para armazenar o nome da troca no RabbitMQ.

## 5ª) Métodos estáticos

### FirebaseConfig.java
- **Método:** `init`.
- **Função:** Este método é estático e é chamado durante a inicialização da classe `FirebaseConfig`. Ele não depende de instâncias específicas da classe e recebe um arquivo JSON como parâmetro para configurar o Firebase.

### RabbitMQConfig.java
- **Método privado:** `queue`.
- **Função:** Este método é estático, não depende de instâncias da classe e é usado para criar filas no RabbitMQ.

- **Método privado:** `topicExchange`.
- **Função:** Este método é estático, não depende de instâncias da classe e é usado para criar uma troca do tipo tópico no RabbitMQ.

- **Método privado:** `binding`.
- **Função:** Este método é estático, não depende de instâncias da classe e é usado para
