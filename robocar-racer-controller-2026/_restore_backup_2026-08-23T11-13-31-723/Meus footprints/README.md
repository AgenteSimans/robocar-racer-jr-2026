# Minha Biblioteca de Footprints Personalizada

Esta pasta contém a minha coleção de footprints desenvolvida para o projeto **Robocar Racer 2025** e outros componentes customizados.

## Sobre a Biblioteca
Esta é uma biblioteca autoral que reúne todos os modelos de componentes que eu desenvolvi ou modifiquei para garantir a precisão do hardware. Optei por incluir a biblioteca completa neste repositório para assegurar que todos os footprints utilizados no layout da PCB estejam disponíveis para consulta e edição.

### Destaques:
* **Módulos Integrados:** Footprints validados para ESP32, sensores e IMUs.
* **Otimização de Soldagem:** Pads ajustados para facilitar a montagem manual e garantir durabilidade.
* **Componentes Customizados:** Modelos criados do zero para componentes que não constam nas bibliotecas padrão do KiCad.

## Uso no Projeto
Para que o KiCad reconheça as peças corretamente ao abrir o arquivo `.kicad_pcb`:
1. Vá em **Preferences** > **Manage Footprint Libraries**.
2. Na aba **Project Specific Libraries**, adicione esta pasta (`Meus footprints.pretty`).

**Nota:** Por ser uma biblioteca completa, ela pode conter componentes adicionais que não estão em uso nesta versão específica da placa, mas que fazem parte do meu fluxo de design.
