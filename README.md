# 🏎️ Robocar Jr — Placa de Controle & Gerenciamento

> Placa de circuito impresso projetada no **KiCad** para o gerenciamento eletrônico de um
> carro autônomo na competição **Robocar Jr**. Um único corpo de prova reúne o cérebro
> (ESP32), os sensores de navegação, a leitura precisa de bateria e as saídas de potência
> dos atuadores.

![Layout da PCB](images/pcb.png)

<p align="center">
  <img alt="KiCad" src="https://img.shields.io/badge/KiCad-7.x-009B70?style=flat&logo=kicad&logoColor=white"/>
  <img alt="ESP32" src="https://img.shields.io/badge/MCU-ESP32--DEVKITC-00979D?style=flat&logo=espressif&logoColor=white"/>
  <img alt="I2C" src="https://img.shields.io/badge/Barramento-I%C2%B2C-orange?style=flat"/>
  <img alt="Licença" src="https://img.shields.io/badge/Licen%C3%A7a-MIT-blue?style=flat"/>
</p>

---

## ✨ O que a placa faz

| Bloco | Papel no veículo |
|-------|------------------|
| 🧠 **ESP32‑DEVKITC** | Microcontrolador principal, montado em soquete (programação via USB). |
| 🧭 **GY‑87 (IMU)** | Orientação e movimento — MPU6050 + HMC5883L + BMP280 via I²C. |
| 📊 **ADS1115** | ADC externo de **16 bits** para medir a bateria com precisão e sem ruído. |
| 🔋 **Monitor de bateria** | Dois canais independentes (Bat3S e Bat2S/ESC) com divisor + filtro RC. |
| 🎯 **Atuadores** | Saídas dedicadas para **servo** (direção) e **ESC/BLDC** (tração). |
| 📡 **Serial (UART)** | Interface TX/RX para telemetria e depuração. |
| ⚡ **Alimentação** | Conversor **Buck** → 5 V, rail **3,3 V** e entrada **USB 5 V**. |

---

## 🔋 Monitoramento de bateria

As tensões da bateria passam por divisores resistores e capacitores de desacoplamento
antes de chegar ao **ADS1115** — leitura muito mais estável que o ADC interno do ESP32:

| Canal | Origem | Divisor | Filtro | Entrada |
|:-----:|--------|:-------:|:------:|:-------:|
| **ADC0** | Bat3S | 330 kΩ / 100 kΩ | 100 nF | A0 |
| **ADC1** | Bat2S / ESC | 180 kΩ / 100 kΩ | 100 nF | A1 |

---

## 🧭 Pinagem & conectores

**Barramento I²C compartilhado** (ADS1115 + GY‑87): `SDA → GPIO21`, `SCL → GPIO22`.

| GPIO | Função | Ligado a |
|:----:|--------|----------|
| 21 | I²C SDA | Sensores |
| 22 | I²C SCL | Sensores |
| 26 | FSYNC | GY‑87 |
| 19 | PWM | Servo Motor |
| 18 | PWM | BLDC (via ESC) |
| 17 / 16 | UART TX / RX | Conector Serial |

**Conectores de campo:** `ServoMotor` (5V·GND·Sinal) · `ESC` (5V·BLDC·Bat2S) ·
`Serial` (GND·TX·RX) · `Bat3S` / `Bat2S` (V+·GND).

---

## 🖼️ Galeria

### Esquemático (hierárquico)
Blocos de alimentação, ADC, IMU, MCU e interfaces de potência.

![Esquemático](images/esquematico.png)

### Layout da PCB
Posicionamento dos conectores de bateria, soquete do ESP32, trilhas de potência e saídas
de motor, com separação cuidadosa de massas.

![PCB](images/pcb.png)

---

## 📄 Licença

Hardware aberto sob licença **MIT** — use, estude e adapte como base para o seu Robocar Jr. 🏁

<sub>Projeto de competição · KiCad · ESP32</sub>
