# BraunX4-4-Bit-Array-Multiplier(Braun-Multiplier)
BraunX4 is a 4-bit unsigned Braun Array Multiplier designed for efficient binary computation.It combines parallel partial-product generation using AND gates with optimized Half Adder and Full Adder stages to produce a precise 8-bit output, demonstrating combinational logic, modular architecture, and core VLSI design principles for modern systems!
<p align="center">
  <img src="https://img.shields.io/badge/Project-Digital_VLSI-blue"/>
  <img src="https://img.shields.io/badge/Architecture-Braun_Multiplier-purple"/>
  <img src="https://img.shields.io/badge/Multiplier-4--Bit-green"/>
  <img src="https://img.shields.io/badge/Output-8--Bit-orange"/>
</p>

---

## Table of Contents

1. [Project Highlights & Key Specifications](#project-highlights--key-specifications)
2. [Tools and Technologies Used](#tools-and-technologies-used)
3. [Fundamental Logic Gate Design & Simulation](#fundamental-logic-gate-design--simulation)
   - 3.1 NOT Gate (Inverter)
   - 3.2 OR Gate
   - 3.3 NAND Gate
   - 3.4 XOR Gate 
4. [Arithmetic Circuit Design](#arithmetic-circuit-design)
   - 4.1 Half Adder Design
   - 4.2 Full Adder Design
5. [BraunX4 Multiplier Architecture](#braunx4-multiplier-architecture)
   - 5.1 Partial Product Generation
   - 5.2 Adder Array Configuration
   - 5.3 4-Bit Binary Multiplication
6. [Circuit Implementation & Schematic Design](#circuit-implementation--schematic-design)
7. [Simulation Results & Waveform Analysis](#simulation-results--waveform-analysis)
   - 7.1 Half Adder Simulation
   - 7.2 Full Adder Simulation
   - 7.3 BraunX4 Multiplier Simulation
   - 7.4 Functional Verification
8. [Performance Analysis](#performance-analysis)
9. [Applications](#applications)
10. [Future Enhancements](#future-enhancements)
11. [Conclusion](#conclusion)
12. [Acknowledgements](#acknowledgements)

---

## Project Highlights & Key Specifications

| Parameter | Specification / Value |
|:---|:---|
| Project Name | BraunX4 – 4-Bit Array Multiplier |
| Multiplier Architecture | Braun Array Multiplier |
| Multiplication Type | Unsigned Binary Multiplication |
| Input A Width | 4 Bits |
| Input B Width | 4 Bits |
| Output Product Width | 8 Bits |
| Partial Product Generation | 16 Partial Products |
| Partial Product Circuit | AND Gate Logic |
| Arithmetic Components | Half Adders (HA) & Full Adders (FA) |
| Logic Design | Combinational Logic Architecture |
| Design Methodology | Schematic-Based Circuit Design |
| EDA Tool | Cadence Virtuoso |
| Circuit Modules | Inverter, NAND, OR, XOR, Half Adder, Full Adder |
| Main Circuit | 4-Bit Braun Array Multiplier |
| Simulation | Transient Waveform Analysis |
| Verification | Functional Simulation |
| Design Objective | Accurate and Efficient Binary Multiplication |
| Applications | ALUs, DSP Systems, Microprocessors & Embedded Systems |

---

## Tools & Technologies Used

| Category | Tool / Technology |
|:---|:---|
| EDA Platform | Cadence Virtuoso |
| Schematic Design | Cadence Virtuoso Schematic Editor |
| Simulation Environment | Cadence Virtuoso ADE |
| Waveform Analysis | Cadence Visualization & Analysis XL |
| Circuit Simulator | Spectre |
| Design Methodology | Schematic-Based Circuit Design |
| Circuit Architecture | Combinational Logic |
| Logic Components | AND, NAND, OR, XOR, NOT Gates |
| Arithmetic Components | Half Adders & Full Adders |
| Multiplier Architecture | 4-Bit Braun Array Multiplier |
| Simulation Analysis | Transient Analysis |
| Operating Environment | Linux |
| Design Domain | Digital VLSI Design |
| Verification Method | Functional Simulation & Waveform Analysis |

---

---

## 3. Fundamental Logic Gate Design & Simulation

Fundamental logic gates are the essential building blocks of digital electronic systems. As part of the BraunX4 project, basic CMOS logic gate design is explored using Cadence Virtuoso. These circuits establish the foundation for understanding transistor-level implementation, Boolean logic operations, and combinational circuit behavior. The schematic design and simulation provide insights into the operation of fundamental digital building blocks.

### 3.1 NOT Gate (Inverter)

The NOT Gate, also known as an inverter, is a fundamental CMOS logic circuit that performs logical inversion of its input signal. It consists of complementary NMOS and PMOS transistors, producing an output that is the logical opposite of the applied input.

**Boolean Expression:**

Y = A'

**Operating Principle:**
- When input A is LOW (0), output Y becomes HIGH (1).
- When input A is HIGH (1), output Y becomes LOW (0).
- The PMOS transistor acts as the pull-up network.
- The NMOS transistor acts as the pull-down network.

**Truth Table:**

| Input (A) | Output (Y) |
|:---:|:---:|
| 0 | 1 |
| 1 | 0 |

**Schematic Design – Cadence Virtuoso**

![CMOS NOT Gate Schematic](images/inv.png)

---

### 3.2 NAND Gate

The NAND gate is a universal logic gate that performs the complement of the AND operation. It produces a LOW output only when both inputs are HIGH. Its CMOS implementation uses a combination of PMOS and NMOS transistors to achieve the required switching behavior.

**Boolean Expression:**

`Y = (A · B)'`

**Operating Principle:**
- When both inputs are HIGH (1), output Y becomes LOW (0).
- For all other input combinations, output Y remains HIGH (1).
- PMOS transistors form the pull-up network.
- NMOS transistors form the pull-down network.

**Truth Table:**

| A | B | Y |
|:---:|:---:|:---:|
| 0 | 0 | 1 |
| 0 | 1 | 1 |
| 1 | 0 | 1 |
| 1 | 1 | 0 |

**Schematic Design – Cadence Virtuoso**

![NAND Gate Schematic](images/nand.png)

---

### 3.3 OR Gate

The OR gate is a fundamental combinational logic circuit that performs logical addition of two binary inputs. It generates a HIGH output whenever at least one input is HIGH. It is widely used in digital decision-making and control logic circuits.

**Boolean Expression:**

`Y = A + B`

**Operating Principle:**
- When both inputs are LOW, output Y becomes LOW.
- When either or both inputs are HIGH, output Y becomes HIGH.
- The circuit performs logical addition of binary inputs.

**Truth Table:**

| A | B | Y |
|:---:|:---:|:---:|
| 0 | 0 | 0 |
| 0 | 1 | 1 |
| 1 | 0 | 1 |
| 1 | 1 | 1 |

**Schematic Design – Cadence Virtuoso**

![OR Gate Schematic](images/or.png)

---

### 3.4 XOR Gate

The XOR (Exclusive-OR) gate is an essential digital logic circuit that produces a HIGH output when its two binary inputs are different. It plays a significant role in arithmetic operations, particularly in Sum generation within Half Adders and Full Adders.

**Boolean Expression:**

`Y = A ⊕ B`

**Operating Principle:**
- When both inputs are identical, output Y becomes LOW.
- When the inputs are different, output Y becomes HIGH.
- It is a fundamental component of binary addition circuits.

**Truth Table:**

| A | B | Y |
|:---:|:---:|:---:|
| 0 | 0 | 0 |
| 0 | 1 | 1 |
| 1 | 0 | 1 |
| 1 | 1 | 0 |

**Schematic Design – Cadence Virtuoso**

![XOR Gate Schematic](images/xor.png)

---

---

## 4. Arithmetic Circuit Design

Arithmetic circuits are fundamental components of digital computing architectures responsible for performing binary mathematical operations. In BraunX4, Half Adders and Full Adders form the core arithmetic building blocks used for partial product accumulation. Both circuits are designed using CMOS logic and implemented in Cadence Virtuoso to demonstrate efficient combinational arithmetic operations.

### 4.1 Half Adder Design

A Half Adder is a combinational arithmetic circuit that performs the addition of two single-bit binary inputs (A and B). It generates two outputs: Sum and Carry. The Sum output is obtained using an XOR operation, while the Carry output is generated using an AND operation.

**Boolean Expressions:**

- Sum = A ⊕ B
- Carry = A · B

**Truth Table:**

| A | B | Sum | Carry |
|:---:|:---:|:---:|:---:|
| 0 | 0 | 0 | 0 |
| 0 | 1 | 1 | 0 |
| 1 | 0 | 1 | 0 |
| 1 | 1 | 0 | 1 |

**Key Features:**
- Two binary inputs and two outputs.
- XOR-based Sum generation.
- AND-based Carry generation.
- Fundamental building block for binary arithmetic.

**Schematic Design – Cadence Virtuoso**

![Half Adder Schematic](images/ha.png)

---

### 4.2 Full Adder Design

A Full Adder is a combinational arithmetic circuit that performs the addition of three single-bit binary inputs: A, B, and Carry-in (Cin). It generates two outputs, Sum and Carry-out (Cout), enabling multi-bit binary addition and carry propagation across successive arithmetic stages.

**Boolean Expressions:**

- Sum = A ⊕ B ⊕ Cin
- Cout = AB + ACin + BCin

**Truth Table:**

| A | B | Cin | Sum | Cout |
|:---:|:---:|:---:|:---:|:---:|
| 0 | 0 | 0 | 0 | 0 |
| 0 | 0 | 1 | 1 | 0 |
| 0 | 1 | 0 | 1 | 0 |
| 0 | 1 | 1 | 0 | 1 |
| 1 | 0 | 0 | 1 | 0 |
| 1 | 0 | 1 | 0 | 1 |
| 1 | 1 | 0 | 0 | 1 |
| 1 | 1 | 1 | 1 | 1 |

**Key Features:**
- Three binary inputs and two outputs.
- Supports carry-in and carry-out operations.
- XOR-based Sum generation.
- Enables multi-stage binary addition.
- Essential arithmetic component in multiplier architectures.

**Schematic Design – Cadence Virtuoso**

![Full Adder Schematic](images/fa.png)

---
