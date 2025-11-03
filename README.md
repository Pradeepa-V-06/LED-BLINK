# LED-BLINK
# 💡 Experiment 01 – Interfacing a Digital Output (LED) with ARM Development Board

### 🎯 **Aim**
To interface a digital output (LED) to an ARM development board and write a blink code.

---

### ⚙️ **Components Required**
- STM32CubeIDE  
- NUCLEO ARM Development Board  

---

### 🧠 **Theory**

**ARM (Advanced RISC Machine)** is a 32-bit processor architecture developed by ARM Holdings. It is widely used in embedded systems and SoC (System-on-Chip) products. Many semiconductor companies like Samsung, Atmel, and Texas Instruments license ARM architecture to design their own SoCs.
### 🧩 **What is an ARM7 Processor?**
The **ARM7 processor** is commonly used in embedded system applications. It provides a balance between the classic ARM architecture and the newer Cortex series, offering an excellent platform for both hardware and software development.
### 🔍 **LPC2148 Microcontroller**
The **LPC2148**, developed by NXP Semiconductors (Philips), is a 16/32-bit ARM7-based microcontroller featuring a wide range of peripherals.
#### **Key Features**
- 16/32-bit ARM7TDMI-S core in LQFP64 package  
- On-chip **Flash memory**: 32 KB – 512 KB  
- On-chip **SRAM**: 8 KB – 40 KB  
- **ISP/IAP** via on-chip bootloader  
- **Embedded ICE-RT** and **Real Monitor** for real-time debugging  
- **USB 2.0** full-speed device controller with 2 KB endpoint RAM  
- **10-bit ADC** (6 or 14 channels, 2.44 μs conversion time)  
- **10-bit DAC** for analog output  
- **Timers:** Two 32-bit timers, watchdog, and PWM unit  
- **RTC** with 32 kHz clock input  
- **UARTs (2x), I²C (2x)** up to 400 kbit/s  
- **5V-tolerant GPIOs**, 21 external interrupt pins  
- **Max CPU Clock:** 60 MHz using on-chip PLL (lock time 100 µs)  
- **Crystal Frequency:** 1 MHz – 25 MHz  
- **Power modes:** Idle and Power-down with peripheral clock scaling  

---
### 🧭 **Procedure**

1. Open **STM32CubeIDE**.<img width="1919" height="1197" alt="image" src="https://github.com/user-attachments/assets/cce7a1da-5a0c-448b-b55c-b1a66e8ff31a" />

2. Click **File → New STM32 Project**.<img width="1916" height="1196" alt="image" src="https://github.com/user-attachments/assets/8a4d7011-e590-47f0-ab05-17a25a30f750" />
<img width="1914" height="1194" alt="image" src="https://github.com/user-attachments/assets/3eedd240-890f-4c70-a9ef-0ac3e99bad20" />

4. Select the **target microcontroller** or board and click **Next**.
  <img width="1919" height="1199" alt="image" src="https://github.com/user-attachments/assets/9731e066-2bd8-4cf6-be92-77c67bf29954" />

5. Name the project.
<img width="1916" height="1196" alt="image" src="https://github.com/user-attachments/assets/c5738689-96d0-4b0a-9bbb-90acde62f91a" />

6. The corresponding `.ioc` file will be generated automatically.
 <img width="1918" height="1197" alt="image" src="https://github.com/user-attachments/assets/c49976cc-1538-42f3-924e-379fe29f04cc" />

7. Configure the pins as **GPIO (Input/Output)**, **USART**, etc. as needed. <img width="1915" height="1199" alt="image" src="https://github.com/user-attachments/assets/31098971-cf0a-467f-a362-3815c8095d07" />
  <img width="1919" height="1199" alt="image" src="https://github.com/user-attachments/assets/fc65cfba-de81-4297-b9e0-dd85ed4b885e" />

8. Save the configuration (`Ctrl + S`) – the base C program will be generated automatically.
   <img width="1913" height="1195" alt="image" src="https://github.com/user-attachments/assets/24f98efa-479a-4a78-805f-afe2666d7abd" />

 
9. Edit the generated main program as required.<img width="1908" height="1199" alt="image" src="https://github.com/user-attachments/assets/d5481c5e-353a-4915-9af6-0b5ed786a101" />
  <img width="1916" height="1199" alt="image" src="https://github.com/user-attachments/assets/408e2eba-85bf-4503-9004-72996d39ced9" />

10. Click **Project → Build All**.
   <img width="787" height="407" alt="image" src="https://github.com/user-attachments/assets/4bfa640c-30c0-448e-8368-2fe9d1655ba1" />

11. Link the **HEX file** using the post-build process.
   <img width="1918" height="1193" alt="image" src="https://github.com/user-attachments/assets/341e8bed-a080-4345-9cab-2b03a27f971f" />

12. Click **Debug** and connect the **STM Nucleo Board**.
   <img width="1918" height="1193" alt="image" src="https://github.com/user-attachments/assets/b8cda178-6fb5-49c5-bb7e-fb8c98180158" />

13. Click **Run** to execute the program.   
---
### 💻 **Program**
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
        HAL_GPIO_WritePin(GPIOA, GPIO_PIN_5, GPIO_PIN_RESET);
        HAL_Delay(1000);
        HAL_GPIO_WritePin(GPIOA, GPIO_PIN_5, GPIO_PIN_SET);
        HAL_Delay(1000);
    }
}
```
---
### OUTPUT
CASE 1: LED ON 
<img width="603" height="432" alt="image" src="https://github.com/user-attachments/assets/d071869d-34bf-4217-b979-22b43d89f970" />
CASE 2: LED OFF
<img width="596" height="416" alt="image" src="https://github.com/user-attachments/assets/2f69f542-062f-4599-a23f-f476301f51f8" />
---
### RESULT
Interfacing a digital output with ARM microcontroller is executed and the results are verified.
