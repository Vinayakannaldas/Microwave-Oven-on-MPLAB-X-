# Microwave-Oven-on-MPLAB-X-
This project implements a basic control system for a microwave oven using a PIC16F877A microcontroller. It features different cooking modes (Micro, Grill, Convection), time setting, temperature setting for convection, and basic operational controls like Start/Resume, Pause, and Stop, all managed via a matrix keypad and displayed on a Character LCD.
# Microwave Oven System

## Project Brief
This project implements a basic control system for a microwave oven using a PIC16F877A microcontroller. It features different cooking modes (Micro, Grill, Convection), time setting, temperature setting for convection, and basic operational controls like Start/Resume, Pause, and Stop, all managed via a matrix keypad and displayed on a Character LCD.

## Technologies Used
*   **Microcontroller:** PIC16F877A
*   **Development Environment:** MPLAB X IDE
*   **Compiler:** XC8 Compiler
*   **Peripherals:**
    *   Character Liquid Crystal Display (CLCD)
    *   Matrix Keypad
    *   Timers (Timer2 for countdown)
    *   Buzzer
    *   Cooling Fan
*   **Programming Language:** C

## How to Compile and Run
This project is designed for the Microchip PIC16F877A microcontroller and is typically compiled using the XC8 compiler within MPLAB X IDE.

**Steps to Compile and Run:**

1.  **Install MPLAB X IDE and XC8 Compiler:**
    *   Download and install MPLAB X IDE from the Microchip website.
    *   Download and install the XC8 C Compiler (v3.00 or compatible) from the Microchip website. Ensure the toolchain directory is correctly set in MPLAB X.

2.  **Open the Project:**
    *   Clone this repository to your local machine.
    *   Open MPLAB X IDE.
    *   Go to `File > Open Project...` and navigate to the cloned directory. Select the `Microwave_oven_by_Vinayak_Annaldas.X` project folder and click `Open Project`.

3.  **Build the Project:**
    *   In MPLAB X IDE, go to `Clean and Build Main Project` (hammer with broom icon) or `Build Main Project` (hammer icon) in the toolbar.
    *   Alternatively, go to `Run > Clean and Build Main Project` or `Run > Build Main Project`.
    *   The compiler will generate the `.hex` file (e.g., `Microwave_oven_by_Vinayak_Annaldas.X.production.hex`) in the `dist/default/production` directory within your project folder.

4.  **Program the Microcontroller:**
    *   Connect your PIC16F877A development board to your computer using a compatible PIC programmer (e.g., PICkit 3, PICkit 4, ICD 3/4).
    *   In MPLAB X IDE, select your connected programmer from the project properties or the dashboard.
    *   Go to `Run > Program Main Project` (green arrow icon). This will flash the generated `.hex` file onto the PIC16F877A microcontroller.

5.  **Hardware Setup:**
    *   Ensure all peripherals (CLCD, matrix keypad, buzzer, fan) are correctly wired to the PIC16F877A as per the circuit design.
    *   Power on the development board.

6.  **Interaction:**
    *   Upon power-on, the CLCD will display a "Powering ON" message.
    *   The main menu will then appear, allowing selection of cooking modes:
        *   **1. Micro:** Microwave mode. Allows setting cooking time.
        *   **2. Grill:** Grill mode. Allows setting cooking time.
        *   **3. Convection:** Convection mode. Requires setting a temperature first (max 250°C), followed by a pre-heating phase, and then allows setting cooking time.
        *   **4. Start:** Initiates cooking with a default 30-second timer if no mode is selected, or resumes a paused operation. Also adds 30 seconds to existing time in `TIME_DISPLAY` mode.
        *   **5. Pause:** Pauses the current cooking operation.
        *   **6. Stop:** Stops the current cooking operation and returns to the main menu.
    *   The buzzer will sound when cooking time is up or for invalid temperature input in convection mode.
    *   The fan will operate during cooking and pre-heating.

## Key Learnings / Challenges
*   **User Interface (UI) Implementation:** Developed an interactive user interface using a matrix keypad for input and a CLCD for displaying modes, time, and status.
*   **Mode Management:** Implemented a state-based system to handle different cooking modes and transitions between them (e.g., `NOT_PRESSED`, `MICRO`, `GRILL`, `CONVECTION`, `START`, `PAUSE`, `STOP`).
*   **Timer-Based Control:** Utilized Timer2 for precise countdowns, crucial for cooking time management and pre-heating phases.
*   **Input Handling:** Managed keypad inputs, including distinguishing between different key presses and handling input sequences for setting time and temperature.
*   **Peripheral Control:** Integrated and controlled output peripherals like a buzzer and a cooling fan based on the operational state of the microwave.
*   **Error Handling:** Implemented basic error checking, such as validating temperature input in convection mode.

## Author
Vinayak Annaldas
