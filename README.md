# Embedded-System-for-Real-Time-Sensor-Monitoring

 Description:
This project involves designing and developing a real-time embedded system to monitor and process sensor data using a microcontroller (e.g., ARM Cortex or Arduino). The system includes interfacing with multiple peripherals like UART, SPI, and I2C for communication and data transfer.

Key Features:

Microcontroller Core Architecture: Programmed and configured an ARM Cortex-M-based microcontroller.
Peripheral Interfaces: Used UART for serial communication, I2C for sensor integration, and SPI for external memory.
Bare-Metal Development: Implemented functionality without an OS for lightweight and fast performance.
Debugging and Optimization: Used tools like JTAG for debugging and performance tuning.
Optional RTOS Integration: Explored real-time task scheduling using FreeRTOS.

Embedded C programming and assembly language.
Strong grasp of microcontroller architecture (ARM Cortex preferred).
Peripheral programming (UART, I2C, SPI).
Debugging and optimization skills for embedded systems.
Board bring-up experience, if applicable (e.g., configuring power-up sequences).

#include <stdio.h>
#include <stdint.h>

// Mock functions to simulate UART, I2C, and SPI behavior
void UART_SendString(const char *str) {
    printf("%s", str); // Simulate sending a string over UART by printing to console
}

uint8_t I2C_ReadByte(uint8_t device_addr, uint8_t reg_addr) {
    // Simulate reading a byte from a device (returning a mock temperature value)
    return 25; // Example: returning a mock temperature of 25°C
}

void SPI_WriteByte(uint8_t data) {
    // Simulate writing data via SPI (printing to console)
    printf("SPI Write: %d\n", data);
}

void read_temperature_data(void) {
    uint8_t temp_data = I2C_ReadByte(0x48, 0x00); // Example device address and register
    char buffer[20];
    
    sprintf(buffer, "Temp: %d°C\n", temp_data);   // Format temperature data into string
    UART_SendString(buffer);                       // Send temperature data over "UART"
    SPI_WriteByte(temp_data);                      // Log temperature data via "SPI"
}

int main(void) {
    while (1) {
        read_temperature_data(); // Continuously read and process sensor data
        break; // Break after one iteration for demonstration purposes
    }
    
    return 0;
}

![image](https://github.com/user-attachments/assets/29c56f1a-3c40-4d6b-95c3-611376242e97)
