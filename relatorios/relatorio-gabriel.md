# Relatório do Projeto Integrador - POO
**Autor:** Gabriel Simonetti Marconato  
**RA:** 1960685  
**Turma:** A

## 1ª) Classes e Suas Funções

### SmartFishApplication.java
**Classe:** SmartfishApplication  
**Resposta:** Esta é a classe principal, responsável por iniciar a aplicação Spring Boot. Ela recebe a anotação `@SpringBootApplication`, que inicia uma aplicação Spring Boot, fazendo com que a `SmartfishApplication` inicie a aplicação.

### FirebaseConfig.java
**Classe:** FirebaseConfig  
**Resposta:** Esta classe tem a função de inicializar o Firebase para autenticar a aplicação, usando o arquivo `serviceAccountKey.json`.

### RabbitMQConstant.java
**Classe:** RabbitMQConstant  
**Resposta:** Esta classe de configuração Spring Boot é responsável por gerenciar filas de mensagens com o RabbitMQ, tornando possível a comunicação com outros componentes de suas aplicações ou sistemas externos.

### ComponentConsumer.java
**Classe:** ComponentConsumer  
**Resposta:** Esta é uma classe de consumidor que realiza a função de consumir mensagens na fila `StatusQueue` no RabbitMQ e criar os componentes na sua aplicação.

### SensorConsumer.java
**Classe:** SensorConsumer  
**Resposta:** A classe `SensorConsumer` tem a função de consumir mensagens na fila `RegistryQueue` no RabbitMQ e registrar sensores na aplicação.

### ComponentController.java
**Classe:** ComponentController  
**Resposta:** Esta é um controlador REST que lida com requisições HTTP. Na aplicação, ela controla os componentes.

### SensorController.java
**Classe:** SensorController  
**Resposta:** Esta é um controlador REST que lida com requisições HTTP. Na aplicação, ela controla os sensores.

### Response.java
**Classe:** Response  
**Resposta:** Esta é uma classe de transferência de dados usada pelo servidor para enviar respostas para o usuário quando ele faz uma requisição HTTP.

### ComponentDto.java
**Classe:** ComponentDto  
**Resposta:** Esta é uma classe de transferência de dados capaz de armazenar informações de um componente e enviá-las ao usuário quando ele faz uma requisição HTTP. O servidor recebe o objeto `ComponentDto` como entrada e então manipula o componente.

### SensorDto.java
**Classe:** SensorDto  
**Resposta:** Ela é usada pelo servidor para controlar registros de sensores. O servidor recebe os objetos `SensorDto` como entrada e utiliza-os para manipular os registros dos sensores.

### ComponentService.java
**Classe:** ComponentService  
**Resposta:** Esta é uma classe de serviço com a função de criar, ler e excluir componentes. Ela usa o Firestore para armazenar os dados dos componentes e o RabbitMQ para ativá-los através de mensagens.

### SensorService.java
**Classe:** SensorService  
**Resposta:** É utilizado pelo servidor de aplicação para gerenciar a parte lógica dos registros de sensores.

## 2ª) Codificou Atributos

### Firebaseconfig.java
**Atributo:** `private AmqpAdmin amqpAdmin`  
**Resposta:** A função deste atributo é administrar objetos do RabbitMQ.

### RabbitMQConfig.java
**Atributo:** `private static final String EXCHANGE_NAME`  
**Resposta:** Este atributo é uma constante que representa o nome de troca do RabbitMQ.

### ComponentConsumer.java
**Atributo:** `private ComponentService componentService`  
**Resposta:** A função deste atributo é processar mensagens de componentes.

### SensorConsumer.java
**Atributo:** `private SensorService sensorService`  
**Resposta:** A função deste atributo é processar mensagens de sensores.

## 3ª) Codificou Métodos

### FirebaseConfig.java
**Método:** `init`  
**Resposta:** A função do método `init` é realizar a conexão com a Firebase. Para isso, ele lê um arquivo JSON de credenciais e realiza a configuração da Firebase com base na leitura dos arquivos.

### RabbitMQConfig.java
**Métodos:** `queue`, `topicExchange`, `binding` e `add`  
**Resposta:** A função destes métodos é auxiliar na organização da comunicação dos componentes através do RabbitMQ.

### ComponentConsumer.java
**Método:** `createComponent`  
**Resposta:** Este método é um ouvinte RabbitMQ, sua função é criar componentes com base em mensagens JSON que ele recebe, utilizando o “Create” na criação de componentes no Firebase.

### SensorConsumer.java
**Método:** `registrySensor`  
**Resposta:** Este método é um ouvinte RabbitMQ, sua função é registrar informações com base em mensagens JSON que ele recebe e, em seguida, utiliza o “registry” para registrar as informações dos sensores no Firebase.

### ComponentController.java
**Método:** `activate`  
**Resposta:** A função deste método é ativar componentes e também receber e enviar dados em JSON para o RabbitMQ.

### SensorController.java
**Métodos:** `getRegistryById` e `getAllRegistryByIdentifier`  
**Resposta:** A função desses métodos é obter informações de sensores com seus respectivos identificadores.

### ComponentService.java
