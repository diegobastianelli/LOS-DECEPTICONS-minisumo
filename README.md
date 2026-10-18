# LOS DECEPTICONS — Robot Mini-Sumo
Robot de mini-sumo autónomo diseñado y fabricado por el equipo **LOS DECEPTICONS** para la asignatura **Tecnología Eléctrica** de la **Universidade de Santiago de Compostela (USC)**.

## Equipo

- Diego Bastianelli Lorenzo
- Rubén Célix Rodríguez
- Samuel Aprorar Magariños

## Descripción

El robot cumple la normativa estándar de mini-sumo: base de máximo 10 × 10 cm, masa máxima de 500 g y retardo obligatorio de 5 s antes de moverse. La electrónica se integra en una PCB propia de dos capas que actúa como placa base (*shield*): los módulos comerciales (microcontrolador, driver de motores y regulador) se insertan en zócalos, y los sensores se conectan por cable.

## Hardware

| Bloque | Componente |
|---|---|
| Microcontrolador | ESP32-S3 Zero (Waveshare) |
| Driver de motores | TB6612FNG (módulo dual) |
| Motores | 2 × N20 micromotorreductor 6 V, 600 RPM (tracción diferencial 2WD) |
| Batería | LiPo 2S 7.4 V, 450 mAh, 75C, conector XT30 |
| Regulador | DD4012SA, salida fija 5 V / 1 A |
| Sensores de oponente | 5 × Sharp GP2Y0A41SK0F (4–30 cm), 3 frontales y 2 laterales |
| Sensores de borde | 2 × QRE1113 (salida digital por descarga RC) |
| Selección de estrategia y arranque | DIP switch de 4 posiciones |
| Chasis | PLA impreso en 3D |
| Ruedas | Silicona |

### PCB

- Diseñada en KiCad 10, 60 × 80 mm, dos capas, FR-4 de 1.6 mm, acabado HASL.
- Divisores de tensión resistivos (10 kΩ / 20 kΩ) para adaptar la salida de los Sharp (5 V) al ADC del ESP32 (3.3 V).
- Pistas de 0.8 mm para potencia y 0.25 mm para señal; plano de masa en la capa inferior.
- Fabricada por JLCPCB. Gerbers en `hardware/gerbers/`.

## Estructura del repositorio

```
hardware/
  pcb/        Proyecto KiCad (esquemático y PCB)
  gerbers/    Archivos de fabricación
mecanica/     Diseño 3D del chasis y la pala
firmware/     Código del ESP32-S3 Zero
docs/         Ficha técnica, informe y fotos
```

## Estado del proyecto

- [x] Esquemático y PCB diseñados
- [x] PCB enviada a fabricar
- [ ] Diseño e impresión del chasis
- [ ] Montaje y soldadura
- [ ] Firmware
- [ ] Pruebas y campeonato

## Licencia

- Hardware (`hardware/`, `mecanica/`): [CERN-OHL-P v2](LICENSE)
- Firmware (`firmware/`): MIT
