# Diário de trabalho

Neste diário vou documentar problemas, soluções, descobertas etc. ao longo dos dias pra evitar a raiva - que estou passando enquanto crio esse documento 🤦‍♂️ - de solucionar as coisas e esquecer depois como fiz.

## 23/05/2025

- **PROBLEMA:** A impressora não comunica quando espeto o USB. Reinicia quando isso acontece, então aparentemente a conexão física está boa, mas a comunicação dá timeout.
- Acabei de instalar o Repetier Host pela primeira vez nessa máquina
- Talvez reinicie ela do zero. Esses são os steps/mm após calibração (com régua):
  - X: 80.1
  - Y: 80.1
  - Z: 2573.5
- Resolvi configurar do 0 novamente. Baixei o [Auto Build Marlin](https://marlinfw.org/docs/basics/auto_build_marlin.html) e descobri que tem um [repo deles](https://github.com/MarlinFirmware/Configurations/tree/release-2.1.2.1/config/examples) com exemplos de várias impressoras, inclusive a minha.
