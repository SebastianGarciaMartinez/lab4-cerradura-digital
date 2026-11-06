# Lab 4: Cerradura Digital con FSM en Verilog

Este repositorio contiene el desarrollo del Laboratorio 4 de Electrónica Digital, implementando un sistema de cerradura electrónica controlado por una Máquina de Estados Finitos (FSM), un teclado matricial 4x4, registro de desplazamiento y control de posición de un servomotor mediante PWM para una FPGA de la familia Cyclone.

## 📂 Estructura del Repositorio

* `src/` -> Contiene los módulos de diseño de hardware (código fuente sintetizable):
  * `cerradura_top.v` (Módulo integrador principal)
  * `fsm_cerradura.v` (Máquina de estados del sistema)
  * `registro_pass.v` (Registro para almacenamiento temporal de la clave)
  * `teclado_matricial.v` (Controlador y antirrebote del teclado 4x4)
  * `servo_pwm_gen.v` (Generador de pulsos PWM para el servomotor)
* `testbench/` -> Contiene el entorno de pruebas y simulación:
  * `tb_cerradura.v` (Banco de pruebas integral con modelo de teclado físico)

## 🚀 Simulación (Icarus Verilog y GTKWave)

Para compilar y verificar el comportamiento lógico del sistema mediante simulación, ejecuta los siguientes comandos en la terminal desde la carpeta raíz del proyecto:

1. **Compilar los archivos fuente y el banco de pruebas:**
   ```powershell
   iverilog -o sim.vvp testbench/tb_cerradura.v src/cerradura_top.v src/fsm_cerradura.v src/registro_pass.v src/servo_pwm_gen.v src/teclado_matricial.v
