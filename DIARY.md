# Diário de trabalho

Neste diário vou documentar problemas, soluções, descobertas etc. ao longo dos dias pra evitar a raiva - que estou passando enquanto crio esse documento 🤦‍♂️ - de solucionar as coisas e esquecer depois como fiz.

## 23/05/2025

- **PROBLEMA:** A impressora não comunica quando espeto o USB. Reinicia quando isso acontece, então aparentemente a conexão física está boa, mas a comunicação dá timeout.
- Acabei de instalar o Repetier Host pela primeira vez nessa máquina
- Talvez reinicie ela do zero. Esses são os steps/mm após calibração (com régua):
  - X: 80.1
  - Y: 80.1
  - Z: 2573.5
  - E: 95.5
- Resolvi configurar do 0 novamente. Baixei o [Auto Build Marlin](https://marlinfw.org/docs/basics/auto_build_marlin.html) e descobri que tem um [repo deles](https://github.com/MarlinFirmware/Configurations/tree/release-2.1.2.1/config/examples) com exemplos de várias impressoras, inclusive a minha.
  - **IMPORTANTE:** Se pegar link de algum fórum, conferir se é o exemplo do release que estou usando ou vai dar erro de versão (deu kkkkk)
- Apanhei pra descobrir se a minha é do tipo threaded rod ou lead screw - estou chutando threaded rod
- Estou desabilitando `SKEW_CORRECTION` p/ fazer uns testes. Tenho que reabilitar, arrumar um paquímetro e fazer a calibração quando o filamento novo chegar.
- Recap das coisas que quero fazer ainda:
  - Calibration cube e skew factor com paquímetro
  - Guia p/ filamento
  - Suporte p/ cooler do bico e BLTouch
  - Configurar firmware com BLTouch (instruções [aqui](https://github.com/MarlinFirmware/Configurations/tree/release-2.1.2.1/config/examples/Geeetech/Prusa%20i3%20Pro%20B/noprobe#3dtouch-auto-leveling-sensor))
  - Porta controles
- Tem duas arquiteturas p/ a placa dessa impressora: 2560 e 1280. No chip está escrito ATMega2560 então vou no 2560.
- Consegui fazer o upload do firmware e atualizei manualmente pela IHM os steps/mm
- No fim das contas, não estava respondendo pq o baud rate estava errado. **O baud rate dessa impressora é 250k.**
- **PROBLEMA:** Clico pra habilitar o bico no controle manual do Repetier e ele imediatamente desabilita. Temperatura máxima do bico estava configurada em 0 graus. Alterei, fucei alterando pela impressora e depois pelo software e deu certo.
- Tive que ajustar velocidade do eixo Z e velocidade de extrusão manual - Printer Settings > Printer > Z-Axis Feed Rate (100 -> 200)/Manual Extrustion Speed (1000 -> 100)
- GCode p/ permitir cold extrusion (útil p/ fazer cold pull): `M302 P` [[docs](https://marlinfw.org/docs/gcode/M302.html)]
