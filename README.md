# HARDWARE-ACCELERATED-CNN
# 🚀 Hardware-Accelerated CNN Inference on Zynq
### Bharat AI SoC Challenge – ARM India

This repository contains the implementation of a real-time CNN inference accelerator designed for the **PYNQ-Z2 board** using the **Xilinx Zynq-7000 SoC** (ARM Cortex-A9 + FPGA fabric).

The project was developed as part of the **Bharat AI SoC Challenge organized by ARM India**, focusing on hardware/software co-design for Edge AI acceleration.

---

# 🧠 System Architecture

The design follows a **Hardware/Software Co-Design approach** by partitioning tasks between the Processing System (PS) and Programmable Logic (PL).

## Processing System (PS)
- Image preprocessing  
- AXI-DMA configuration and control  
- Data transfer management  
- Post-processing  
- Accuracy computation  

## Programmable Logic (PL)
Hardware accelerator implementing CNN layers:
- Convolution layer
- ReLU activation
- Fully Connected layer

### Communication Interfaces
- **AXI-Lite** – Control and configuration  
- **AXI Master** – Memory access  
- **AXI-DMA** – High-throughput data transfer between PS and PL  

---

# ⚙️ Accelerator Design (Vitis HLS)

The CNN accelerator was designed using **Xilinx Vitis HLS**.

Key design features:

- 3-layer lightweight CNN architecture
- Fixed-point quantization for efficient FPGA implementation
- Loop unrolling for parallel MAC operations
- Pipeline optimization for higher throughput
- BRAM-based on-chip storage for CNN weights
- DSP utilization ≈ 54%

---

# 📊 Performance Results

Evaluation was performed using **100 CIFAR-10 images**.

| Implementation | Throughput |
|---------------|------------|
| ARM CPU (PS only) | 0.88 FPS |
| FPGA Accelerator (PS + PL) | 105 FPS |

🚀 **~120× Speedup compared to CPU-only inference**

---

# ⚖️ Accuracy Considerations

To achieve high performance and resource efficiency, the CNN was implemented using **fixed-point quantization**.

This introduces **accuracy–precision trade-offs**, since the model was deployed **without Quantization-Aware Training (QAT)**.

---

# 🛠 Tools & Technologies

- PYNQ-Z2 Board
- Xilinx Zynq-7000 SoC
- Vitis HLS
- Vivado
- Python (PYNQ environment)
- AXI DMA / AXI Lite Interfaces
- CIFAR-10 Dataset

---

# 🎯 Learning Outcomes

This project provided hands-on experience in:

- Edge AI deployment on embedded SoCs
- FPGA-based CNN acceleration
- High Level Synthesis (HLS) accelerator design
- AXI-based PS–PL integration
- Performance and resource optimization

---

# 👨‍💻 Team

- Lakshmi Nair  
- Gautham P Nair  
- Gaurynandana J  

---

# 🎓 Mentor

Dr. Jagadeesh Kumar P

---

# 🇮🇳 Bharat AI SoC Challenge

This project was developed as part of the **Bharat AI SoC Challenge**, promoting innovation in AI hardware acceleration and indigenous semiconductor ecosystem development in India.

---

# 📌 Keywords

FPGA | Zynq | Edge AI | CNN Accelerator | Embedded Systems | Vitis HLS
