## ⚠️ Important Note:
You may need to adapt your CMakeLists.txt or build system based on your specific development environment. System-specific configurations (e.g., I2C bus, OLED wiring, SDK path) may require manual setup to ensure proper execution.

---

> **🚀 Assignment:** Implement a function to convert ADC readings to temperature (°C) using Raspberry Pi Pico W.

# 🌡️ ADC to Celsius Conversion on Raspberry Pi Pico W

This project demonstrates how to convert the internal temperature sensor reading of the Raspberry Pi Pico W (using its built-in ADC) into degrees Celsius. It includes both the conversion function and a unit test using the [Unity Test Framework](https://github.com/ThrowTheSwitch/Unity).

---

## 🧪 Description

The Raspberry Pi Pico W features an internal temperature sensor connected to a dedicated ADC channel. The ADC provides a 12-bit value based on the reference voltage (V<sub>ref</sub> = 3.3 V). To obtain the temperature in degrees Celsius, the following formula (from the official RP2040 datasheet) is used:

---

## Temperature (°C) = 27 - (V_sensor - 0.706) / 0.001721

### Where:

- V_sensor = (adc_val / 4095) * Vref
- Vref is assumed to be 3.3 V
- 4095 is the max value for a 12-bit ADC

## ✅ Function Prototype

```C

float adc_to_celsius(uint16_t adc_val);

```
- This function converts the raw ADC value into a floating-point temperature in degrees Celsius.

---

## 🔬 Unit Test

- We use Unity to test the function against a known reference:

- A voltage of 0.706 V corresponds to 27 °C.

- The test accepts a small margin of error (±0.5 °C).

## Test Case 

```C

void test_adc_to_celsius_known_value(void) {
    uint16_t adc_val = (uint16_t)((0.706 / 3.3) * 4095);
    float temperature = adc_to_celsius(adc_val);
    TEST_ASSERT_FLOAT_WITHIN(0.5, 27.0, temperature);
}

```

---

## 🛠️ Build & Run Tests

- To compile and run the test with Unity:


```bash

mkdir build && cd build
cmake ..
make
./test_adc_temp

```

---

## 🚀 Requirements

- Raspberry Pi Pico W

- CMake

- Unity Test Framework

- GCC for ARM (or appropriate cross-compiler)

---

## 📚 Reference

- [RP2040 Datasheet– Temperature Sensor Section](https://datasheets.raspberrypi.com/rp2040/rp2040-datasheet.pdf)
- [Unity Test Framework (C - by ThrowTheSwitch)](https://github.com/ThrowTheSwitch/Unity)

---

## 🐳 Run, Maintain and Deploy the Application in a Docker Containerized EnvironmentRun in a Containerized 

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

[![HBr](./assets/hbr.jpg)](https://hardware.org.br/)

Have suggestions or found a bug?
Feel free to contribute or open an [issue](https://github.com/alfecjo/antonio_almeida_embarcatech_HBr_2025/issues). 🚀

---

- ## Return to the main page
  [![HBr 2025 Project](https://img.shields.io/badge/HBr_2025_Project-000000?style=for-the-badge&logo=github&logoColor=white)](https://github.com/alfecjo/antonio_almeida_embarcatech_HBr_2025)
