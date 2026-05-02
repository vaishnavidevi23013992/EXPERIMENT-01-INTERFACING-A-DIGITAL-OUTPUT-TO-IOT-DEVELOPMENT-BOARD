# EXPERIMENT-01-INTERFACING-A-DIGITAL-OUTPUT-TO-IOT-DEVELOPMENT-BOARD

**DATE:** 30-04-2026

**NAME:** VAISHNAVIDEVI V

**ROLL NO:** 212223040230

**DEPARTMENT:** Computer Science and Engineering

## Aim

To Interface a Digital output (LED) to ARM IOT development board and write a program to blink an LED.

## Components required

- STM32 CUBE IDE
- ARM IOT development board
- STM programmer tool

## Theory

The ARM (Advanced RISC Machine) architecture is widely used in microcontrollers and processors due to its efficiency, low power consumption, and high performance. ARM processors follow the Reduced Instruction Set Computer (RISC) design philosophy, which allows them to execute instructions at a much faster rate compared to Complex Instruction Set Computer (CISC) processors while consuming significantly less power.

One such microcontroller is the STM32WLE5JC, which is part of the STM32 family and is based on the ARM Cortex-M4 core. It is specifically designed for LoRaWAN® and other sub-GHz wireless communication protocols. This microcontroller combines the power efficiency of ARM architecture with specialized wireless communication capabilities, making it ideal for Internet of Things (IoT) applications.

The STM32WLE5JC is known for its ultra-low power consumption, making it perfect for battery-operated IoT devices such as smart agriculture sensors, environmental monitoring systems, industrial automation systems, and smart city applications. The microcontroller operates at a frequency of up to 48 MHz, providing sufficient processing power for complex IoT tasks.

With its power-efficient design, built-in LoRaWAN support, and flexible communication options, the STM32WLE5JC is an excellent choice for developers looking to build long-range, low-power IoT applications that require reliable wireless connectivity and extended battery life.

## Procedure

### 1. Click on STM 32 CUBE IDE

The following screen will appear when you launch STM32 CubeMX.

![image](https://user-images.githubusercontent.com/36288975/226189166-ac10578c-c059-40e7-8b80-9f84f64bf088.png)

### 2. Create a New STM32 Project

Click on **FILE**, then select **New STM32 project**.

![image](https://user-images.githubusercontent.com/36288975/226189215-2d13ebfb-507f-44fc-b772-02232e97c0e3.png)
![image](https://user-images.githubusercontent.com/36288975/226189230-bf2d90dd-9695-4aaf-b2a6-6d66454e81fc.png)

### 3. Select the Target MCU

Select the target microcontroller to be programmed as shown below and click on **Next**.

![Screenshot 2025-03-11 134231](https://github.com/user-attachments/assets/09e61f3d-224f-4ca8-96d4-7336869df5c7)

### 4. Select the Program Name

Choose an appropriate name for your project.

![image](https://user-images.githubusercontent.com/36288975/226189316-09832a30-4d1a-4d4f-b8ad-2dc28f137711.png)

### 5. IOC File Generation

The corresponding IOC (Initialization and Configuration) file will be generated automatically.

![Screenshot 2025-03-11 134528](https://github.com/user-attachments/assets/df427edd-e24a-4612-a858-aeae859b379f)

### 6. Configure GPIO Pins

Select the appropriate pins as GPIO (input or output), USART, or other required options and configure them accordingly.

![Screenshot 2025-03-11 134617](https://github.com/user-attachments/assets/125ee548-30b1-4c88-932f-adf07984522f)

![Screenshot 2025-03-11 134642](https://github.com/user-attachments/assets/0adfbb58-4cad-408a-9300-f4808b53cac4)

### 7. Generate C Program

Click on **Ctrl+S**, and the C program will be generated automatically.

![Screenshot 2025-03-11 134709](https://github.com/user-attachments/assets/70b83b79-1569-4f14-99d5-e2adbb4e692d)

### 8. Edit the Program

Edit the generated program as per your requirements.

![image](https://user-images.githubusercontent.com/36288975/226189461-a573e62f-a109-4631-a250-a20925758fe0.png)

### 9. Build the Project

Use **Project > Build All** to compile your project.

![image](https://user-images.githubusercontent.com/36288975/226189554-3f7101ac-3f41-48fc-abc7-480bd6218dec.png)

### 10. Project Build Complete

Once the project build is complete, you will see a confirmation message.

![image](https://user-images.githubusercontent.com/36288975/226189577-c61cc1eb-3990-4968-8aa6-aefffc766b70.png)

### 11. Connect the IoT Board

Connect the IoT development board to the power supply and USB port.

### 12. Open STM Cube Programmer

After connecting the board, open the STM32 Cube Programmer tool.

![Screenshot 2025-03-11 135208](https://github.com/user-attachments/assets/bb67ab6b-81a5-450c-b170-4276a9b87ef2)

### 13. Upload the Program

Connect the STM board through the COM port, then upload the corresponding project ELF file, Hex file, or Bin file in the **Erasing & Programming Window**, while ensuring the board is in **flash mode**, and click the **Start** button.

![image](https://github.com/user-attachments/assets/9383531d-8204-4697-9321-55afb6abee2e)

### 14. Test the Output

After the file download is complete, switch your board to **run mode** and press the **reset button** to see the output.

## STM32 CUBE PROGRAM

```c
#include "main.h"
void SystemClock_Config(void);
static void MX_GPIO_Init(void);
int main(void)
{
  HAL_Init();
  SystemClock_Config();
  MX_GPIO_Init();
  while (1)
  {
    HAL_GPIO_WritePin(GPIOA, GPIO_PIN_0, GPIO_PIN_SET);
    HAL_Delay(4000);
    HAL_GPIO_WritePin(GPIOA, GPIO_PIN_0, GPIO_PIN_RESET);
    HAL_Delay(2000);
  }
}
```

## OUTPUT

The LED blinks on and off with the specified delays (4 seconds ON, 2 seconds OFF).

![exp1-1](https://github.com/user-attachments/assets/658737a8-0efb-4c8c-8c33-6549ac1574bb)

![exp1-2](https://github.com/user-attachments/assets/510a2144-74fd-4f58-a508-6efd1516aae3)

## Result

Interfacing a digital output with ARM microcontroller-based IoT development board was successfully executed and the results were verified. The LED blinks as expected with the configured timing intervals.

---
