# Relatório do Projeto Integrador POO

## 1ª) Classes e Suas Funções

### SmartFishApplication.java

- **Classe:** SmartfishApplication
- **Resposta:** Esta é a classe principal responsável por iniciar a aplicação. Ela importa a anotação `@SpringBootApplication`, que inicia uma aplicação Spring Boot, permitindo que a `SmartfishApplication` inicie a aplicação.

### FirebaseConfig.java

- **Classe:** FirebaseConfig
- **Resposta:** Esta classe tem a função de inicializar o Firebase para autenticar a aplicação. Ela utiliza o arquivo `serviceAccountKey.json` para autenticação.

### RabbitMQConstant.java

- **Classe:** RabbitMQConstant
- **Resposta:** Esta classe de configuração Spring Boot é responsável por gerenciar filas de mensagens com o RabbitMQ, permitindo a comunicação com outros componentes da aplicação ou sistemas externos.

### ComponentConsumer.java

- **Classe:** ComponentConsumer
- **Resposta:** Esta classe atua como um consumidor, responsável por consumir mensagens na fila `StatusQueue` no RabbitMQ e criar componentes na aplicação.

### SensorConsumer.java

- **Classe:** SensorConsumer
- **Resposta:** A classe SensorConsumer tem a função de consumir mensagens na fila `RegistryQueue` no RabbitMQ e registrar sensores na aplicação.

### ComponentController.java

- **Classe:** ComponentController
- **Resposta:** Esta classe é um controlador REST que lida com requisições HTTP, controlando componentes na aplicação.

### SensorController.java

- **Classe:** SensorController
- **Resposta:** Esta classe é um controlador REST que lida com requisições HTTP, controlando sensores na aplicação.

### Response.java

- **Classe:** Response
- **Resposta:** Esta é uma classe de transferência de dados usada pelo servidor para enviar respostas ao usuário quando este faz uma requisição HTTP.

### ComponentDto.java

- **Classe:** ComponentDto
- **Resposta:** Esta classe de transferência de dados é capaz de armazenar informações de um componente e enviá-las ao usuário quando ele faz uma requisição HTTP. O servidor recebe o objeto ComponentDto como entrada e o utiliza para manipular o componente.

### SensorDto.java

- **Classe:** SensorDto
- **Resposta:** Esta classe é usada pelo servidor para controlar registros de sensores. O servidor recebe os objetos SensorDto como entrada e os utiliza para manipular os registros dos sensores.

### ComponentService.java

- **Classe:** ComponentService
- **Resposta:** Esta classe de serviço tem a função de criar, ler e excluir componentes. Ela utiliza o Firestore para armazenar os dados dos componentes e o RabbitMQ para ativá-los por meio de mensagens.

### SensorService.java

- **Classe:** SensorService
- **Resposta:** Esta classe é utilizada pelo servidor de aplicação para gerenciar a parte lógica dos registros de sensores.

## 2ª) Codificação de Atributos

### Firebaseconfig.java

- **Atributo:** private AmqpAdmin amqpAdmin
- **Resposta:** Este atributo tem a função de administrar objetos do RabbitMQ.

### RabbitMQConfig.java

- **Atributo:** private static final String EXCHANGE_NAME
- **Resposta:** Este atributo é uma constante que representa o nome da troca no RabbitMQ.

### ComponentConsumer.java

- **Atributo:** private ComponentService componentService
- **Resposta:** Este atributo é responsável por processar mensagens de componentes.

### SensorConsumer.java

- **Atributo:** private SensorService sensorService
- **Resposta:** Este atributo é responsável por processar mensagens de sensores.

## 3ª) Codificação de Métodos

### FirebaseConfig.java

- **Método:** init
- **Resposta:** A função deste método é realizar a conexão com o Firebase, lendo um arquivo JSON de credenciais e configurando o Firebase com base nesses dados.

### RabbitMQConfig.java

- **Métodos:** queue, topicExchange, binding e add
- **Resposta:** A função desses métodos é auxiliar na organização da comunicação dos componentes por meio do RabbitMQ.

### ComponentConsumer.java

- **Método:** createComponent
- **Resposta:** Este método é um ouvinte do RabbitMQ e sua função é criar componentes com base nas mensagens JSON recebidas, utilizando o "Create" para criá-los no Firebase.

### SensorConsumer.java

- **Método:** registrySensor
- **Resposta:** Este método é um ouvinte do RabbitMQ e sua função é registrar informações com base nas mensagens JSON recebidas, utilizando o "registry" para registrar as informações dos sensores no Firebase.

### ComponentController.java

- **Método:** activate
- **Resposta:** A função deste método é ativar componentes e receber/enviar dados em JSON para o RabbitMQ.

### SensorController.java

- **Métodos:** getRegistryById e getAllRegistryByIdentifier
- **Resposta:** A função desses métodos é obter informações de sensores com base em seus identificadores.

### ComponentService.java

- **Método:** create
- **Resposta:** A função deste método é criar componentes no Firestore do Firebase com base nos dados recebidos e verificar se o componente já existe antes de criar um novo.

- **Método:** activate
- **Resposta:** A função deste método é ativar componentes e enviar mensagens para o RabbitMQ.

### SensorService.java

- **Métodos:** registry, getRegistryById e getAllRegistryByIdentifier
- **Resposta:** A função desses métodos é registrar e recuperar informações de sensores no Firestore do Firebase com base em seus identificadores.

## 4ª) Atributos Estáticos

### RabbitMQConfig.java

- **Atributo:** private static final String EXCHANGE_NAME
- **Resposta:** Este atributo é estático porque representa um valor constante usado em toda a classe para armazenar o nome da troca do RabbitMQ.

## 5ª) Métodos Estáticos

### FirebaseConfig.java

- **Método:** init
- **Resposta:** Este método é estático porque é chamado na inicialização da classe "FirebaseConfig" e não depende de instâncias específicas da classe. Ele recebe um arquivo JSON como parâmetro para configurar o Firebase com base nas credenciais fornecidas.

### RabbitMQConfig.java

- **Método privado:** queue
- **Resposta:** Este método é estático porque não depende de instâncias da classe e sua função é criar filas no RabbitMQ.

- **Método privado:** topicExchange
- **Resposta:** Este método é estático porque não depende de instâncias da classe e não possui parâmetros. Sua função é criar uma troca do tipo tópico no RabbitMQ.

- **Método privado:** binding
- **Resposta:** Este método é estático porque recebe nomes de filas e trocas como parâmetros e não depende de instâncias da classe. Sua função é criar ligações entre filas e trocas no RabbitMQ.

## 6ª) Métodos Construtores em Classes

### RabbitMQConfig.java

- **Método construtor:** public RabbitMQConfig(AmqpAdmin amqpAdmin)
- **Resposta:** A função deste método construtor é inserir uma instância de "AmqpAdmin" na classe "RabbitMQConfig". Ele recebe um parâmetro do tipo "AmqpAdmin" para inicializar o atributo "amqpAdmin".

## 7ª) Métodos Protegidos ou Privados em Classes

### RabbitMQConfig.java

- **Métodos:** queue, topicExchange, binding e add
- **Resposta:** Esses métodos são privados porque são auxiliares internos da classe e têm a função de configurar o RabbitMQ.

## 8ª) Classes ou Interfaces Virtuais

**Resposta:** Não, nenhuma classe ou interface no código do projeto é puramente virtual.

## 9ª) Classes Abstratas ou Virtuais

**Resposta:** Não, nenhuma classe no código do projeto é abstrata ou virtual.

## 10ª) Instanciou Objetos

**Resposta:** Sim, o FirebaseOptions e FirebaseApp são instanciados durante a inicialização.

## 11ª) Instalou e Usou Bibliotecas de Terceiros

**Resposta:** Sim, a biblioteca Google Firebase foi instalada e usada para configurar a conexão com o Firebase.

## 12ª) Codificou Enums

**Resposta:** (A informação sobre enums não foi fornecida no texto original.)
