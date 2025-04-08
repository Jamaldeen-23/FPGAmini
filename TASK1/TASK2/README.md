# UART RGB LED Controller (FPGA Verilog)

This project implements a UART-based RGB LED controller using Verilog for FPGA devices (Lattice ICE40).  
It demonstrates UART transmission, internal clock generation, and RGB LED control using PWM.

---

## Features
- Internal High-Frequency Oscillator (HFOSC)
- UART Transmitter (8N1 protocol) with state machine
- RGB LED control (PWM)
- Frequency counter (for clock division or delay)
- Loopback UART (for testing purposes)

---

## File Structure


---

## Module Details

### Top Module (`top.v`)

| Port       | Direction | Description                 |
|------------|-----------|-----------------------------|
| led_red    | Output    | Red LED Control             |
| led_green  | Output    | Green LED Control           |
| led_blue   | Output    | Blue LED Control            |
| uarttx     | Output    | UART TX Output              |
| uartrx     | Input     | UART RX Input               |
| hw_clk     | Input     | External Clock (optional)   |

- Generates internal clock using `SB_HFOSC`.
- UART transmit line (`uarttx`) connected to receive line (`uartrx`) for loopback testing.
- RGB LED driven using `SB_RGBA_DRV` primitive.
- Frequency counter increments on every clock edge.

---

### UART Transmitter (`uart_tx_8n1`)

Implements a UART transmitter with:
- 1 Start bit
- 8 Data bits (LSB first)
- 1 Stop bit

#### State Machine:
| State        | Description            |
|--------------|------------------------|
| IDLE         | Wait for send trigger  |
| STARTTX      | Send start bit (LOW)   |
| TXING        | Send 8 data bits       |
| TXDONE       | Send stop bit (HIGH)   |

---

## Requirements

- Lattice ICE40 FPGA
- Verilog Compiler (Yosys / IceStorm Toolchain)
- UART Terminal (for testing output)

---

