# robocar-racer-controller-2025

## Visão Geral
Este repositório contém o projeto de hardware da **placa controladora** desenvolvida pela **Equipe Laser** para a competição **Robocar Racer 2025**. A placa recebe e interpreta dados da **Raspberry Pi** para controlar o motor brushless (ESC) e o servo motor, implementando isolamento galvânico e redundância via rádio controle.

---

## Visualização do Projeto

### Modelo 3D
![Vista 3D da Controladora](Assets/Car_v1_foto.png)

### Documentação Técnica (PDF)
Para detalhes de roteamento e conexões, acesse os arquivos abaixo:
* [📄 Esquemático Completo](Assets/Esquemático.pdf)
* [📄 Layout da PCB](Assets/PCB_layout.pdf)

---

## Especificações Técnicas
* **Microcontrolador:** ESP32 (NodeMCU/DevKit V1)
* **Software de EDA:** KiCad 8.0.6
* **Dimensões da PCB:** 91.00 mm x 67.75 mm
* **Isolamento:** Optoacopladores **PC817** (Separação entre lógica/USB e potência/Bateria).

## Operação e Segurança
O sistema gerencia a tração e direção do veículo em três estados:
1. **Modo Autônomo:** Controle via Raspberry Pi (Serial/USB).
2. **Modo Manual (Radio):** Redundância via rádio controle externo (Fail-safe).
3. **Modo Neutro:** Veículo parado por segurança.

## Interfaces de Hardware
* **Barramento GY-87:** Conexão I2C para IMU (Telemetria e estabilização).
* **Feedback Visual:** 4 LEDs (Power, Estado 1, Estado 2, Estado 3).
* **Isolamento de Terra:** Separação física entre `GND_CAR` e `Earth` (GND lógico).

## Estrutura do Repositório
* **`/Gerber`**: Arquivos finais de fabricação e furação.
* **`/Assets`**: Fotos, modelos 3D e documentação técnica em PDF.
* **`/Meus footprints.pretty`**: Biblioteca de footprints personalizados.
* **`Car_v1.kicad_...`**: Arquivos fonte do projeto para edição no KiCad.
