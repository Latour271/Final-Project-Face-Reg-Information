Project Goal
The goal of this project is to design and implement a Facial Recognition Camera System using an Arduino Mega 2560, integrated with Python-based facial recognition libraries and Google's Teachable Machine. The system will capture facial data, process it for recognition, and display results on an LCD screen. This project demonstrates the integration of hardware (Arduino + sensors) and software (Python + ML models) to create a functional prototype for IT 254.

Hardware & Software Requirements

| Category   | Item / Tool | Version / Details | Hidden Pitfalls (Easily Overlooked) |
|------------|-------------|-------------------|-------------------------------------|
| Hardware   | Arduino Mega 2560 | Official board, latest revision | Ensure correct drivers are installed; counterfeit boards may cause USB connection issues |
|            | Breadboard (Mega size) | Standard 830 tie-points | Loose connections can cause intermittent failures |
|            | LCD Display | 16x2 or 20x4 with I2C adapter | Without I2C adapter, wiring complexity increases significantly |
|            | Jumper Wires | 14 male-to-male | Poor quality wires may break or lose conductivity |
|            | USB Cable | Type A to Type B | Must support data transfer, not just charging |
|            | Individual Computers | Windows/Linux/Mac | Ensure OS supports Python 3.11 and Arduino IDE |
| Software   | Python | 3.11 | Incompatible libraries if using older versions; ensure opencv-python and numpy installed |
|            | Arduino IDE | Latest stable version | Must match board drivers; incorrect board selection breaks upload |
|            | Google Teachable Machine | Latest web version | Requires stable internet connection; exported models must match Python version |
|            | Copilot | Latest version | Used for assisted code generation; ensure internet access |
|            | Visual Studio | Latest version | Must install Python and Arduino extensions; otherwise integration fails |

# Hidden Details That May Break the Project
- Power Supply Issues: Arduino Mega requires a stable 5V; unstable USB ports may cause resets  
- Driver Installation: Missing CH340/ATmega drivers can prevent Arduino from being recognized  
- Library Compatibility: Python libraries (opencv, tensorflow, serial) must match Python 3.11  
- LCD Address Conflicts: I2C LCDs may have different addresses (0x27 vs 0x3F); must be checked with I2C scanner sketch  
- Breadboard Quality: Cheap breadboards often cause loose connections, leading to random failures  
- USB Cable Type: Some cables are power-only; must ensure data-capable cable  
- Teachable Machine Export: Exported models must be compatible with TensorFlow Lite or Python runtime

  
 Wiring Diagram (Arduino Mega + LCD + Breadboard)

Arduino Mega 2560 → LCD (I2C 16x2)
-----------------------------------
5V   → VCC
GND  → GND
SDA  → Pin 20 (SDA)
SCL  → Pin 21 (SCL)

Additional Connections:
- Breadboard used for wire organization
- USB cable connects Arduino Mega to the computer
- Jumper wires connect Arduino to LCD via breadboard

[ Arduino Mega 2560 ] ----> [ Breadboard ] ----> [ LCD (I2C) ]

Connections:
- 5V   → VCC (LCD)   [Red wire]
- GND  → GND (LCD)   [Black wire]
- Pin 20 → SDA (LCD) [Blue wire]
- Pin 21 → SCL (LCD) [Yellow wire]

Tips:
- Place Arduino on the left, Breadboard in the center, LCD on the right
- Use color coding for wires (Red = VCC, Black = GND, Blue = SDA, Yellow = SCL)
- Label all wires clearly in your diagram

- End of README
