# Arquivos de Fabricação (Gerber)

Estes ficheiros são os ativos finais necessários para a produção da PCB, seja via fabricação industrial (JLCPCB, PCBWay, etc.) ou fresagem CNC.

## Especificações para Fabricação

* **Formato:** Gerber RS-274X.
* **Furação:** Excellon Drill Files.
* **Camadas incluídas:**
    * Cobre (Top/Bottom)
    * Máscara de solda (Solder Mask)
    * Legenda/Serigrafia (Silkscreen)
    * Corte de borda (Edge Cuts)

## Instruções

Estes ficheiros foram gerados a partir do KiCad 8.0.6. Se for realizar a fresagem via CNC (ex: utilizando **FlatCAM**), utilize preferencialmente os ficheiros de isolamento gerados para as camadas de cobre.
