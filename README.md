# stm32 nucleo-learning</br>
## REFERENCES</br>
Carmine Novellio</br>
Advanced Programming with STM32 Microcontrollers</br>
Stm32 ARM Programming for Embedded Systems</br>
STM32F446RE datasheet</br>

### C for embedded systems
- aligned and unaligned allocation
- A 32-bit processor such as the Arm architecture with 32-bit data bus reads the memory with a minimum of 32 bits on the 4-byte boundary (addressending in 0, 4, 8, and C in hex)
- If a short int variable is allocated straddling the 4-byte boundary, access to that variable is called an unaligned access.
### Nomenclature
- STM32
- F means foundation series. Others are:L,G,U,etc.
- Consecutive 4 refers to the ARM-Cortex M architecture number i.e M4.
### Other features of this board
- Comes with built-in st-link.
- Since, based on M4, it supports SWV(Serial Wire View).(SWV is supported from M3 onwards.)
### Updated firmware of St-link in stm32 nucleo board of mine</br>
R0-R12 general purpose registers.</br>
R13 Stack Pointer(SP) which is said to be banked, this means that register content changes according to current CPU mode(privileged or unprivileged).This is used by RTOS to do context switching.</br>
bit_band_address = alias_region_base + (region_base_offset x 32) + (bit_number x 4)</br>
## STM32 Programmer</br>
  1.Open</br>
  2.Update firmware(if necessary).</br>
  3.Erasing and Programming.</br>
  4.Tick Verify Program and Run program</br>
  5.Continue.</br>
## HAL Library</br>
The System bus connects the system bus of the Cortex-M core to a Bus Matrix, which manages
the arbitration between the core and the DMA. Both the core and the the DMA act as masters.</br>
• The DMA bus connects the Advanced High-performance Bus(AHB) master interface of the
DMA to the BusMatrix, which manages the access of CPU and DMA to SRAM, flash memory
and peripherals.</br>
• The BusMatrix manages the access arbitration between the core system bus and the DMA
master bus. The arbitration uses a Round Robin algorithm. The BusMatrix is composed of two
masters (CPU, DMA) and four slaves (FLASH memory interface, SRAM, AHB1 with AHB to
Advanced Peripheral Bus(APB) bridge and AHB2). AHB peripherals are connected on system
bus through a Bus Matrix to allow DMA access.</br>
• The AHB to APB bridge provides full synchronous connections between the AHB and the APB
bus, where the most of peripherals are connected.</br>
### Memory Map
- 4 GB (2 ^32)
### Differences between USART and UART</br>
Clock signal in USART</br>
### Resolution of ADC
In an analogue
to digital converter with a reference voltage of 3.3 V and 12-bit resolution, the resolution
coefficient is calculated as the below equation.</br>
Resolution coefficient = reference voltage/(2^12-1)=805.86080 uV.</br>
This is the accuracy of ADC. Thus, it cannot read voltage less than this value.</br>
##### GPIO_InitTypeDef.Mode
###### Pin Mode                            
GPIO_MODE_INPUT-Input Floating Mode </br>
GPIO_MODE_OUTPUT_PP-Output Push Pull Mode</br>
GPIO_MODE_OUTPUT_OD-Output Open Drain Mode</br>
GPIO_MODE_AF_PP-Alternate Function Push Pull Mode</br>
GPIO_MODE_AF_OD-Alternate Function Open Drain Mode</br>
GPIO_MODE_ANALOG-Analog Mode</br>
GPIO_MODE_IT_RISING-External Interrupt Mode with Rising edge trigger detection</br>
GPIO_MODE_IT_FALLING-External Interrupt Mode with Falling edge trigger detection</br>
GPIO_MODE_IT_RISING_FALLING-External Interrupt Mode with Rising/Falling edge trigger detection</br>
GPIO_MODE_EVT_RISING-External Event Mode with Rising edge trigger detection</br>
GPIO_MODE_EVT_FALLING-External Event Mode with Falling edge trigger detection</br>
GPIO_MODE_EVT_RISING_FALLING-External Event Mode with Rising/Falling edge trigger detection</br>
####  DAC

- the register bits are modified using “|=” operator to set the bit and “&=” to clear the bit
