# Complimentary PWM Signals Using STM32 Micro controller
The project demonstrates PWM (Pulse Width Modulation) and OC (Output Compare) functionalities of TIM1 and TIM8 timers respectively.

## How to Use Example

### Hardware Required
* Any STM32 Microcontroller based Development Board - Nucleo (Tested on STM32F4xx series)
* USB to UART converter (for debugging)

### Hardware Setup:
* Connect the Pins PE9 (D6) for timer TIM1 and PC6 (D16) for timer TIM8 to the STM32 microcontroller.
* Connect the USB to UART converter to the STM32 microcontroller for debugging.

## Example Output

````bash
TIM1:
- Initializes PWM with a 50% duty cycle.
- The OC (Output Compare) function continually checks the PWM signal's output. When the PWM signal hits the 50% mark, the OC triggers an event and TIM1 sets duty cycle to zero (0%) until TIM8 reaches 50% duty cycle.

TIM8:
- Awaits an OC event from TIM1.
- Once TIM1's OC detects a 50% duty cycle, it sends an event to TIM8, prompting it to start its PWM operation.
- After reaching its 50% duty cycle, TIM1 again sets 50% duty cycle and TIM8 waits for OC event to trigger.

````
