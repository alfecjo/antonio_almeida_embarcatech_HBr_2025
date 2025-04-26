## ⚠️ Important Note:
You may need to adjust the `CMakeLists.txt` file according to your development environment, as each setup might differ based on the developer's system configuration. Without these adjustments, the code may not behave as expected.

---

### 🚀 **Assignment**

### 📌 Countdown Timer with Event Logging via Interrupts

---

# 🧠 Project006 – Hybrid C/C++ Embedded App with OOP Enhancements

## 🖥️ Platform
Raspberry Pi Pico W / [BitDogLab](https://github.com/BitDogLab/BitDogLab)

## 📦 Description
A modular and object-oriented embedded application designed to:
- Read internal temperature from the RP2040’s ADC
- Convert it to Celsius and voltage
- Display the readings on an **OLED display** and via **serial terminal**
- Execute this process **periodically using a hardware timer**

---

## 💡 Features

- ✅ Hybrid C/C++ application
- ✅ Modular architecture using C++ classes
- ✅ Repeating timer interrupt (every 5 seconds)
- ✅ OLED display via I2C
- ✅ Serial debug output

---

## 🛠️ Logic Explanation

## Step-by-Step Logic

### 1. **Reading the Internal Temperature Sensor**

The RP2040 includes a built-in temperature sensor, which is connected to **ADC channel 4**. To read this temperature:

- The ADC is initialized using `adc_init()`.
- The internal sensor is enabled with `adc_set_temp_sensor_enabled(true)`.
- The ADC input is set to channel 4 using `adc_select_input(4)`.

The raw ADC value is read using `adc_read()` and then converted to a voltage using the following formula:

![Read Temperature](./assets/code.jpg)

### 🖼️ Hardware Setup

This section illustrates the hardware used in this project to help replicate the setup accurately.

### 🔧 Components Used

- Raspberry Pi Pico W or [BitDogLab](https://github.com/BitDogLab/BitDogLab)
- SSD1306 OLED Display (I2C)
- USB cable (for power and programming)

---

### 📝 **The code was written in Hybrid C/C++ and tested using the [BitDogLab](https://github.com/BitDogLab/BitDogLab) platform.**

---

### 🔧 **Status**

✅ Tested – Working properly 🟢

---

### 📋 **Checklist of Test Cases That Supported Project Development**

- 🟢 Test 001 – Success! Time-based.

---

### 🖼️ Hardware Setup

![Final tested project](./assets/project006.gif)

---

## 🐳 Run in a Containerized Environment

Tired of manual setups and toolchain installations? Want to skip the setup and run the projects in a ready-to-use development environment?

🚀 **Launch all projects using our custom Docker image with full Pico SDK support!**  
The image includes build tools, dependencies, and sample projects — all pre-configured.

👇 Visit the repository and get started now:  

<p align="center">
  <a href="https://github.com/alfecjo/rp2040-container">
    <img src="https://github.com/alfecjo/antonio_almeida_embarcatech_HBr_2025/raw/main/picodevbox.png" alt="PicoDevBox" width="200"/>
  </a>
</p>

- 💡 Use this container to compile, test, and develop your Raspberry Pi Pico and [BitDogLab](https://github.com/BitDogLab/BitDogLab) projects instantly — no manual installations needed!
- 🛠️ Created and maintained by the author of this project to simplify and accelerate development.

---

## 👤 Author
**[Antonio Almeida](https://alfecjo.github.io/) Student**

![HBr](./assets/hbr.jpg)

Have suggestions or found a bug?
Feel free to contribute or open an [issue](https://github.com/alfecjo/antonio_almeida_embarcatech_HBr_2025/issues). 🚀

---

- ## Return to the main page
  [![HBr 2025 Project](https://img.shields.io/badge/HBr_2025_Project-000000?style=for-the-badge&logo=github&logoColor=white)](https://github.com/alfecjo/antonio_almeida_embarcatech_HBr_2025)
