# 🌐 Global Solutions 2025 - Smart Office Monitor
**O Futuro do Trabalho: Saúde, Bem-Estar e Ergonomia com IoT**

## 👥 Integrantes
* **Camila Mendonça** - RM565491
* **Fernando Kenzo Sassaki Cunha** - RM562343
* **Marcello Lassalla de Mello Castanho e Oliveira** - RM561879

---

## 📝 Descrição do Projeto
O **Smart Office Monitor** é uma solução IoT desenvolvida para enfrentar os desafios do trabalho híbrido e remoto. Com o aumento do Home Office, problemas como **Burnout** (estresse excessivo), **LER/DORT** (má postura) e desconforto ambiental tornaram-se invisíveis para os gestores.

Nossa solução monitora em tempo real a saúde do colaborador e o ambiente de trabalho, atuando de forma preventiva através de feedbacks imediatos (alertas visuais e sonoros) e análise de dados em nuvem.

### 🎯 Funcionalidades
1.  **Monitoramento de Estresse (Simulado):** Utiliza um potenciômetro para simular a variação de batimentos cardíacos (BPM). Se o nível ultrapassar 110 BPM, o sistema sugere uma pausa respiratória.
2.  **Ergonomia Inteligente:** Um sensor ultrassônico mede a distância do usuário em relação à tela. Se for inferior a 30cm, alerta sobre risco à visão e postura.
3.  **Conforto Ambiental:** Monitora Temperatura e Umidade (DHT22). Se o ambiente estiver insalubre (>35°C ou <30% umidade), sugere hidratação.
4.  **Dashboard em Nuvem:** Envia dados a cada 15 segundos para o **ThingSpeak**, permitindo a gestão de saúde a longo prazo.

---

## 🛠️ Hardware Utilizado (Simulação Wokwi)
* **ESP32 DevKit V1:** Microcontrolador principal com Wi-Fi.
* **Sensor DHT22:** Para leitura de temperatura e umidade.
* **Sensor Ultrassônico (HC-SR04):** Para medição de distância (Ergonomia).
* **Potenciômetro:** Para simulação de dados biométricos (BPM).
* **LED (Vermelho):** Atuador visual de alerta.
* **Buzzer:** Atuador sonoro para feedback imediato.
* **Resistores:** Para proteção do circuito.

---

## 💻 Configuração e Execução

### Pré-requisitos
* Conta no [Wokwi](https://wokwi.com/)
* Conta no [ThingSpeak](https://thingspeak.com/)

### Passo a Passo
1.  Acesse o projeto no Wokwi através do link: **https://wokwi.com/projects/447902818840834049**
2.  O código utiliza as seguintes bibliotecas:
    * `WiFi.h` (Conectividade)
    * `HTTPClient.h` (Protocolo HTTP)
    * `DHT.h` (Sensor de Temperatura)
3.  Ao iniciar a simulação:
    * **Gire o Potenciômetro** para simular o aumento dos batimentos cardíacos.
    * **Altere a distância no HC-SR04** para testar o alerta de postura.
    * **Altere a temperatura no DHT22** para testar o alerta ambiental.
4.  Os dados serão visualizados em tempo real no Dashboard do ThingSpeak.

---

## 📡 Comunicação e Protocolos

O projeto utiliza o protocolo **HTTP** (Hypertext Transfer Protocol) para comunicação com a nuvem.
* **Método:** GET Request.
* **Endpoint:** API do ThingSpeak (`http://api.thingspeak.com/update`).
* **Payload:** A cada 15 segundos, o ESP32 envia uma string contendo a API Key de escrita e os valores dos sensores (`field1` a `field4`).

A escolha pelo HTTP se deve à simplicidade e robustez para envio de dados telemétricos em intervalos regulares, garantindo que o histórico de saúde do trabalhador seja preservado para análise futura.

---

## 🎥 Link do Vídeo Explicativo
[INSIRA O LINK DO YOUTUBE AQUI]


