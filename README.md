# Monitoramento de Potência Solar com ESP32, MQTT e Node-RED

Este projeto implementa um sistema de monitoramento em tempo real da potência gerada por uma placa solar, utilizando o sensor LDR para leitura da luminosidade, envio dos dados via MQTT e visualização no Node-RED.

## Principais Funcionalidades

- **Leitura de sensores**: Utilização do LDR para captar dados de luminosidade.
- **Cálculo da potência gerada**: Baseado na área e eficiência da placa solar.
- **Integração MQTT**: Envio dos dados em tempo real para um broker MQTT configurado.
- **Dashboard no Node-RED**: Visualização dos dados de potência gerada de forma intuitiva.

## Estrutura do Projeto

- **ESP32**: Utilizado para coletar os dados do sensor e enviá-los ao broker MQTT.
- **Node-RED**: Configurado para receber os dados MQTT e criar dashboards dinâmicos.
- **Broker MQTT**: Responsável por intermediar a comunicação entre o ESP32 e o Node-RED.
- **Simulação com Wokwi**: Simulação do ESP32 e LDR para desenvolvimento do projeto.

## Requisitos

Antes de rodar o projeto, certifique-se de que possui:

1. **Node-RED** instalado (veja [aqui](https://nodered.org/docs/getting-started) como instalar).
2. **Broker MQTT** configurado (pode ser o [Mosquitto](https://mosquitto.org/)).
3. **Arduino IDE** ou outra IDE que suporte ESP32.
4. **Wokwi** para simulação, acessível em [https://wokwi.com](https://wokwi.com).

## Configuração

### **ESP32**

1. Instale a **IDE Arduino**.
2. Adicione o suporte para placas ESP32:
   - Acesse **Arquivo > Preferências** e adicione o seguinte URL em *URLs Adicionais*:
     ```
     https://dl.espressif.com/dl/package_esp32_index.json
     ```
   - Vá em **Ferramentas > Placa > Gerenciador de Placas**, pesquise por "ESP32" e instale.
3. Configure o código:
   - Atualize as credenciais de Wi-Fi e MQTT no código:
     ```cpp
     const char* SSID = "SeuWiFi";
     const char* PASSWORD = "SuaSenha";
     const char* BROKER_MQTT = "IP_Do_Seu_Broker";
     ```
4. Faça upload do código para o ESP32.

### **Node-RED**

1. Instale o Node.js e o Node-RED:
   ```bash
   npm install -g --unsafe-perm node-red
