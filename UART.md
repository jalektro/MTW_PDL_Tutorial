# UART PDL

## Hyperlink to UART Documentation
[UART](https://infineon.github.io/psoc6pdl/pdl_api_reference_manual/html/group__group__scb__uart.html)
## Device configurator
For this setup, we will use pin **P5[0]** and **P5[1]** for UART communication.
![[UART_pin.png]]
![[UARTP5[0].png]] 
![[UARTP5[1].png]]
### Peripheral Configuration

After setting up the pins, configure the UART peripheral as shown below:
![[UART_peripherals.png]]
![[UART_params.png]]
Save these configurations to finalize the setup in the Device Configurator.
## Main

### Setting Up UART in the Code

In your `main.c`, include the initialization code to enable UART functionality:
```c
	/* UART context variable */
	cy_stc_scb_uart_context_t UART_context;
	/* Configure and enable the UART */
	Cy_SCB_UART_Init(UART_HW, &UART_config, &UART_context);
	Cy_SCB_UART_Enable(UART_HW);

```


This ensures the UART is ready to use in your main program.
example : 

```c
Cy_SCB_UART_PutString(UART_HW, buffer);
```