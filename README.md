# STM32F446RE Bare-Metal I2C 16x2 LCD Driver

A register-level Bare-Metal C implementation for driving an HD44780-based 16x2 character LCD via PCF8574 I2C adapter on the STM32F446RE microcontroller without using HAL libraries.

---

## 📌 Technical Highlights

* **Pure Bare-Metal C:** Written entirely using register-level manipulation (Direct Memory Access / Memory Mapped Registers).
* **I2C Peripheral Driver:** Manual configuration of STM32 I2C1 peripheral operating at 100 kHz Standard Mode.
* **PCF8574 I2C Adapter Driver:** Implementation of 4-bit mode HD44780 LCD control commands (Nibble shifting, Enable bit toggling, Backlight control).
* **GPIO Alternate Function Mapping:** Configured `PB8` (SCL) and `PB9` (SDA) pins with Open-Drain and Internal Pull-Up logic.

---

## 🛠 Driver Configuration

* **Microcontroller:** STM32F446RE (ARM Cortex-M4)
* **Peripherals:** GPIOB, I2C1, RCC
* **I2C Address:** `0x4E` (PCF8574 8-bit Write Address format: `0x27 << 1`)
* **Pin Mapping:**
  * `PB8` -> I2C1_SCL (AF4, Open-Drain, Pull-Up)
  * `PB9` -> I2C1_SDA (AF4, Open-Drain, Pull-Up)
