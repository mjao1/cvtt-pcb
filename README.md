# CVTT-PCB
**Custom Embedded PCB for a Computer Vision-Based Table Tennis Robotic System**

<div align="center">
  <img src="assets/CVTT-PCBA.jpg" alt="CVTT-PCBA" width="70%"/>
  <img src="assets/CVTT-PCB-layout.png" alt="CVTT-PCB-layout" width="45%"/>
  <img src="assets/CVTT-PCB-3D.png" alt="CVTT-PCB-3D" width="45%"/>
  <img src="assets/CVTT-sch.png" alt="CVTT-sch" width="90%"/>
</div>

<div align="center">
<em>The dragon on the silkscreen references Ma Long, the goat of table tennis; 'Long (龍)' translates to 'dragon' from Mandarin.</em>
</div>

## Core Components

- **Microcontrollers and Compute:**
  - STM32G0B1RET6
  - Raspberry Pi Zero 2 W

## Actuation System

- **Motor Driver Support:**
  - 2 Brushless DC motors for flywheels
  - 2 Servos for direction and distance control
  - 1 Stepper motor for ball feeding

## Power and Regulation

- **Power Circuitry:**
  - 12V input
  - E-fuse circuit
  - 12V to 5V LDO Regulator
  - 5V to 3.3V LDO Regulator

## User Interface

- **Controls and Feedback:**
  - Manual/CV mode switch
  - LCD screen for manual control
  - LCD navigation buttons
  - Diagnostic LEDs
 
## STM32G0B1RET6 Pinout

### Inputs
| Signal        | Pin   |
|---------------|-------|
| UART_RX       | PB7   |
| LCD_MISO      | PD5   |
| LCD_BUTTONC   | PC4   |
| LCD_BUTTOND   | PC5   |
| LCD_BUTTONU   | PA7   |
| CV_MODE       | PB10  |
| PB13          | PB13  |

### Outputs
| Signal      | Pin  | Signal      | Pin  | Signal      | Pin  | Signal      | Pin  |
|-------------|------|-------------|------|-------------|------|-------------|------|
| UART_TX     | PB6  | LED_G       | PC6  | DRV_EN      | PA0  | LED_R       | PA9  |
| LCD_RESET   | PD2  | PWMB        | PC7  | DRV_STEP    | PA1  | LED_B       | PA10 |
| LCD_LED     | PD3  | STBY        | PC8  | DRV_DIR     | PA2  | LCD_CS      | PA15 |
| LCD_DC/RS   | PD4  | PWMA        | PC11 | BIN2        | PA3  | SERVO1_PWM  | PB0  |
| LCD_MOSI    | PD6  | DRV_SLEEP   | PD8  | BIN1        | PA4  | SERVO2_PWM  | PB1  |
| LCD_SCK     | PB3  | DRV_RST     | PD9  | AIN1        | PA5  | EFUSE_EN    | PB14 |
|             |      |             |      | AIN2        | PA6  |             |      |

### Tag
| Signal  | Pin   |
|---------|-------|
| SWDIO   | PA13  |
| SWKCLK  | PA14  |

## RPI Zero 2 W Pinout

### Inputs
| Signal              | Pin    |
|---------------------|--------|
| SC1174 input        | —      |
| UART_TX             | GPIO15 |

### Outputs
| Signal  | Pin    |
|---------|--------|
| UART_RX | GPIO14 |

## Next Steps
- Programming STM machine logic state machine
  - Design LCD user interface for manual and vision modes
- Programming RPI CV player recognition algorithm
  - Using RPI AI camera (SC1174) for inference acceleration
