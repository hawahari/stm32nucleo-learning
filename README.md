# stm32nucleo-learning</br>
## REFERENCES</br>
Carmine Novellio</br>
### Updated firmware of St-link in stm32 nucleo board of mine</br>
R0-R12 general purpose registers.</br>
R13 Stack Pointer(SP) which is said to be banked, this means that register content changes according to current CPU mode(privileged or unprivileged).This is used by RTOS to do context switching.</br>
bit_band_address = alias_region_base + (region_base_offset x 32) + (bit_number x 4)</br>
