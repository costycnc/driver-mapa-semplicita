
# 🔌 Driver + MAPPA — The hidden truth about Arduino and the digital world

[![YouTube Video](https://img.shields.io/badge/YouTube-Watch%20Demo-red?logo=youtube)](https://www.youtube.com/shorts/ZcSXHUBY7dc)
[![License: CC0 1.0](https://img.shields.io/badge/License-CC0%201.0-lightgrey)](https://creativecommons.org/publicdomain/zero/1.0/)
[![GitHub Pages](https://img.shields.io/badge/GitHub-Pages-blue?logo=github)](https://costycnc.github.io/driver-mapa-semplicita/)

> **Drivers are not magic. They are just MAP + basic instructions.**  
> `sbi 4,5` and `sbi 5,5` on Arduino prove it. 2 instructions. 4 numbers. One LED. That's all.

---

## 📖 The core idea

Every driver, every peripheral, from Arduino LEDs to car engine control units, works the same way:  
**write a bit in a register, read a status, turn on a LED**. That's it.

This repository explains the concept with the **simplest possible example**:

```assembly
.org 0
    sbi     4, 5        ; Drawer 4, bit 5 = 1 (pin 13 as OUTPUT)
    sbi     5, 5        ; Drawer 5, bit 5 = 1 (LED ON)
halt:
    rjmp    halt        ; Stop here - LED stays on
```

---

## 🏠 The wardrobe metaphor

Imagine a big **cabinet** with numbered drawers. Each drawer number is fixed:

| Drawer | Technical name | Address | What it controls |
|--------|----------------|---------|------------------|
| **4** | DDRB | 0x24 | Configures pins (input/output) |
| **5** | PORTB | 0x25 | Sets pins (on/off) |
| **3** | PINB | 0x23 | Reads pin states |

- **MAP** = the document that says "drawer 4 bit 5 controls pin 13 configuration, drawer 5 bit 5 turns the LED on/off"  
- **DRIVER** = someone who knows the map and writes/reads those drawers

---

## 📹 See it in action

[![Driver + MAP demo](https://img.youtube.com/vi/ZcSXHUBY7dc/0.jpg)](https://www.youtube.com/shorts/ZcSXHUBY7dc)

▶️ **[Watch the 60-second video proof](https://www.youtube.com/shorts/ZcSXHUBY7dc)** — a real Arduino, real assembly, real LED turning on.

---

## 🚀 Try it yourself (2 minutes, no install)

1. Connect Arduino UNO/Nano to your computer via USB
2. Open **[costycnc.it/avr1/compiler.html](https://costycnc.it/avr1/compiler.html)** (works in browser, Web Serial API)
3. Copy the code above
4. Click **Assemble**, then **Upload**, select your port
5. **Watch the LED on pin 13 turn on** 💡

✅ **You just wrote a real driver.** No libraries. No frameworks. Just pure register access.

---

## 🌍 Why this matters

Smartphones, computers, washing machines, cars, TVs... **they all work exactly like this**.  
They have thousands of drawers instead of 64, but the principle is IDENTICAL:

- **MAP** = documentation (datasheet) saying "register X controls Y"
- **DRIVER** = software that reads/writes those registers

This is the **hidden truth** that nobody teaches, but everyone should know.

---

## 📚 Related resources on CostyCNC

| Resource | Description |
|----------|-------------|
| [🔧 AVR Assembly Compiler](https://costycnc.it/avr1/compiler.html) | Program ATmega328 in Assembly from browser |
| [📘 Start Here - AVR Tutorial](https://costycnc.it/avr1/start-here.html) | The only lesson you need to understand Arduino |
| [💥 Crash ASM: Stack Disasters](https://costycnc.it/avr1/crash-asm/) | Ethical lesson with real examples (Boeing, Ariane, Therac-25) |
| [🔌 Serial Port Communication](https://costycnc.it/avr1/serial-port/) | HTML + JS + Web Serial API step-by-step |
| [⚙️ Stepper Motor in AVR Assembly](https://costycnc.it/avr1/motore-passo-passo-assembly/) | Drive 28BYJ-48 with ULN2003 in pure assembly |
| [🔄 Servo G90 360 in Assembly](https://costycnc.it/avr1/servo-g90-assembly/) | From stop to rotation with r17 register |
| [❓ Why ATmega328?](https://costycnc.it/avr1/perche-atmega328.html) | The perfect microcontroller to learn Assembly |
| [📖 Read Flash Memory](https://costycnc.it/avr1/read-flash/) | Read ATmega328 Flash via Web Serial |
| [🔥 Flash Memory Modification](https://costycnc.it/avr1/flash-tutorial/) | Complete guide to write AVR assembly and modify flash |

---

## 📊 How many people know this?

**Out of 100 programmers:**
- 95 don't know what a register is
- 4 have heard of it but never used it
- 1 has written a driver at least once
- **0.1 truly understands the whole chain**

**You are now part of the 0.1%.**  
You've seen behind the curtain. You understand that under all complexity lies childlike simplicity.

---

## 🎯 Now you know

You've seen the truth. You can:
- **Ignore it** (like 99% of people do)
- **Use it** (and never fear technology again)
- **Teach it** (show the obvious to those who have eyes)

---

## 📁 Repository contents

| File | Description |
|------|-------------|
| [`index.html`](https://costycnc.github.io/driver-mapa-semplicita/index.html) | English version (main) |
| [`it.html`](https://costycnc.github.io/driver-mapa-semplicita/it.html) | Italian version |
| `README.md` | This file |

---

## 🌐 Live pages

- **English**: [costycnc.github.io/driver-mapa-semplicita/index.html](https://costycnc.github.io/driver-mapa-semplicita/index.html)
- **Italian**: [costycnc.github.io/driver-mapa-semplicita/it.html](https://costycnc.github.io/driver-mapa-semplicita/it.html)

---

## 📜 License

This work is dedicated to the public domain under [CC0 1.0 Universal](https://creativecommons.org/publicdomain/zero/1.0/).  
No copyright. No rights reserved. Spread it. Teach it. Show the obvious.

---

## 👤 Author

Created by [**Costel Boboaca — CostyCNC**](https://costycnc.it/about/en.html)  
- Main site: [costycnc.it](https://costycnc.it)  
- AVR portal: [costycnc.it/avr1](https://costycnc.it/avr1)  
- YouTube: [@costycnc](https://www.youtube.com/shorts/ZcSXHUBY7dc)

---

> **sbi 4,5**  
> **sbi 5,5**  
> This is a driver. Everything else is just layers.
