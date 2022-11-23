#  ESP32

  # Envio de Dados por Email Usando o ESP32.

  Neste Projeto foi utilizada a plataforma Wokwi para simular a montagem e funcionamento dos dispositivos utilizados, também foram utilizadas as plataformas HiveMQ, para conferir o envio e recebimento de dados, e o Node Red, para conectar o projeto à internet proporcionando o envio automatico de email. 
Abaixo a lista de materiais e softwares utilizados no projeto:

    1 ESP32;
    1 Sensor DHT22;
    1 Pushbutton;
    1 LED Azul;
    9 Cabos Jumpers;
    1 Resistor de 150 Ohms;
    1 Resistor de 10k Ohms;
    Plataforma Wokwi;
    Plataforma HiveMQ;
    Plataforma Node Red

  Para atingir o objetivo proposto, o projeto foi dividido em fases:
  
    Primeira fase: utilização da ferramenta eletrônica Wokwi para simular o esquema de construção e programação do modelo proposto;
    Segunda fase: teste de envio de dados utilizando o simulador HiveMQ;
    Terceira fase: Utilização do Node Red, este foi configurado para recebimento de dados e programado para o envio automático de emails;

Descrição da Primeira Fase:
 
    1.Acessar a plataforma Worwi através do site: https://wokwi.com/ ;
    2.Selecionar a opção ESP32 + DHT22 Sensor;
    3.Adicionar o Led, os resistores e o Pushbutton clicando em Add a new part;
    4.Simular as ligação entre os componentes:
    4.1. Conexões do LED: 
      Led1A ligado ao esp:GND.1;
      Led1C ligado ao r2:1;
      R2:2 ligado ao esp:D2;
    4.2.Conexões do DHT22:
      Dht1:GND ligado ao espGND.1;
      Dht1:SDA ligado ao esp:D15;
      Dht1:VCC ligado ao esp:3v3
    4.3. Conexões do PushButton:
      Btn1:2.r ligado ao esp:D13;
      Btn1:2.l ligado ao r1.1;
      R1:2 ligado ao esp:GND.2;
      Btn1:1.r ligado ao esp:3V3;

Descrição da Segunda Fase:

    1.Acessar a plataforma HiveMQ através do site: http://www.hivemq.com/demos/websocket-client/ ;
    2.Clicar em conectar;
    3.Criar uma Subscriptions em Add New Topic Subscription:
    4.Criar uma Subscribe utilizando a matrícula, TIA, e o nome pessoal; 
    5.Adicionar o Topic criado ao código no Wokwi no campo MQTT_TOPIC:
    6.Adicionar o Topic criado ao código no Wokwi no campo MQTT_TOPIC:

Descrição da Terceira Fase:

    1.Instalar o Node Red: 
      1.1. Abrir o Prompt de Comando;
      1.2. Digitar o comando: npm install -g --unsafe-perm node-red;
      1.3. Enter para iniciar o download e instalação;
    2.Digitar no Prompt de Comando: Node-RED;
    3.Digitar no browser localhost:1880, para acessar o Node Red;
    4.Iniciar a construção de um nó usando o mqtt in ligado ao email;
    5.Iniciar a configuração do mqtt in:
      5.1. Adicionar o Server:
        5.1.1. Duplo clique em mqtt in;
        5.1.2. Clicar em Properties;
        5.1.3. Adicionar no Server o broker mencionado na plataforma Worwi;
        5.1.4. Clicar em Update, para salvar as configurações;
      5.2. Adicionar o Topic:
        5.2.1. Duplo clique em mqtt in;
        5.2.2. Adicionar no Topic o Topic criado na plataforma Worwi:
        5.2.3. Clicar em Done, para salvar as configurações;
    6.Configurar o email:
      6.1. Adicionar no To, o email que irá receber as notificações de atualizações;
      6.2. Digitar no Server smtp.office365.com;
      6.3. Digitar no Userid o email que estará enviando as notificações;
      6.4. Digitar no Password a senha do email que irá enviar as notificações, para que o Node RED tenha acesso ao envio;
