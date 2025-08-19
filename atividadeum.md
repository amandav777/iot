# Projeto IoT – Semana 1  
## Especificação Inicial

---

## 1. Introdução  
Nosso projeto será feito usando o **ESP32**, que é um microcontrolador com Wi-Fi e Bluetooth já integrados.  
A ideia é montar um sistema IoT simples para mostrar como um computador é formado: tem um “cérebro” (o processador), memória, dispositivos de entrada (sensores), saída (atuadores) e comunicação.  

---

## 2. Análise Técnica do ESP32  

### 2.1 Informações principais do ESP32  
- Processador: dois núcleos de 32 bits (Xtensa LX6).  
- Velocidade: até 240 MHz.  
- Memória RAM: 520 KB.  
- Memória Flash: normalmente 4 MB (depende do módulo).  
- Conexões:  
  - Wi-Fi.  
  - Bluetooth.  
  - Várias portas (GPIOs) para ligar sensores e atuadores.  
  - Interfaces como I2C, SPI e UART (para comunicação com outros dispositivos).  

### 2.2 Ligação com os conceitos de arquitetura de computadores  
- O **processador** do ESP32 é a parte que roda os programas.  
- A **memória RAM** guarda dados temporários enquanto o código está rodando.  
- A **memória Flash** é como um “HD”, onde o programa fica salvo.  
- Os **sensores e atuadores** são os dispositivos de entrada e saída.  
- O **Wi-Fi/Bluetooth** permitem que o ESP32 “fale” com outros sistemas, como um celular ou servidor.  

---

## 3. Definição do Projeto  
O projeto que vamos desenvolver é uma **estação de monitoramento ambiental**.  
Ela vai:  
- Ler dados de sensores (temperatura, umidade e qualidade do ar).  
- Enviar esses dados pela rede Wi-Fi para poder ver em uma aplicação simples (como um dashboard).  
- Acionar um atuador (por exemplo, ligar um cooler ou acender um LED) quando algum valor estiver fora do normal.  

---

## 4. Componentes do Sistema  

### 4.1 Processamento  
- **ESP32** → será o “cérebro” do sistema.  

### 4.2 Entrada (Sensores)  
- **DHT22** → mede temperatura e umidade.  
- **MQ-135** → mede qualidade do ar.  

### 4.3 Saída (Atuadores)  
- **Cooler 5V** → liga quando a temperatura estiver muito alta.  
- **LED RGB** → mostra o status do ambiente com cores.  

### 4.4 Comunicação  
- **Wi-Fi** do ESP32 → envia os dados para a internet ou para outro dispositivo.  

---

## 5. Diagrama de Blocos  

```plaintext
[Sensores] ---> [ESP32] ---> [Atuadores]
                      |
                 [Comunicação Wi-Fi]
