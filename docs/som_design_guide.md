# Custom AI Inference SOM Design Guide

## Introduction

This document provides a comprehensive guide for designing a custom System on Module (SOM) for AI inference, based on your requirements for a low-cost, low-power solution using laptop CPUs with integrated graphics and dedicated AI accelerators. This guide draws inspiration from the NVIDIA Jetson Orin Nano's form factor while leveraging the cost-effectiveness and performance of modern x86 processors.

## 1. CPU Selection: Intel vs. AMD

Choosing the right CPU is the most critical decision for your SOM design. Both Intel and AMD offer compelling options with integrated graphics and Neural Processing Units (NPUs) for AI acceleration. The table below provides a comparison of their latest mobile processor series.

| Feature                 | Intel Core Ultra (Series 2)                                                              | AMD Ryzen AI 300 Series                                                                      |
| ----------------------- | ---------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------- |
| **Architecture**        | Arrow Lake                                                                               | Zen 5                                                                                        |
| **Process Node**        | Intel 4                                                                                  | 4nm                                                                                          |
| **Max Cores**           | Up to 24 cores (8 P-cores + 16 E-cores)                                                    | Up to 12 cores                                                                               |
| **Integrated GPU**      | Intel Arc Graphics                                                                       | AMD RDNA 3.5 (Radeon 800M Series)                                                            |
| **Integrated NPU**      | Intel AI Boost                                                                           | AMD XDNA 2                                                                                   |
| **NPU Performance**     | 13 TOPS (Int8)                                                                           | Up to 50+ TOPS                                                                               |
| **Total AI Performance**| Up to 33 TOPS (CPU + GPU + NPU)                                                          | Not explicitly stated, but NPU alone is significantly higher                                 |
| **Power Consumption**   | Mobile variants available with lower TDPs                                                | Designed for ultrathin laptops, with a focus on power efficiency                             |
| **AI Frameworks**       | OpenVINO, WindowsML, DirectML, ONNX RT, WebNN                                              | Not explicitly listed, but expected to support major frameworks through drivers and libraries |

**Recommendation:**

For a low-power, high-performance AI inference SOM, the **AMD Ryzen AI 300 Series** appears to be the more suitable choice. The significantly higher NPU performance (50+ TOPS vs. 13 TOPS) provides a substantial advantage for AI-focused workloads. Additionally, the Zen 5 architecture and 4nm process node suggest excellent power efficiency, which is a key requirement for your project.

## 2. External AI Accelerator Selection

While the integrated NPUs in modern CPUs are powerful, you may want to add a dedicated AI accelerator for even greater performance or to offload specific tasks. The most common options are Google's Coral Edge TPU and Hailo's AI accelerators. They are available in M.2 form factors, making them easy to integrate into a carrier board.

| Feature             | Google Coral Edge TPU                                                              | Hailo-8 AI Accelerator                                                                     |
| ------------------- | ---------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------ |
| **Performance**     | 4 TOPS per chip (8 TOPS for dual-chip module)                                      | Up to 26 TOPS (Hailo-8) or 13 TOPS (Hailo-8L)                                              |
| **Power Efficiency**| 2 TOPS per watt                                                                    | Best-in-class power efficiency                                                             |
| **Form Factor**     | M.2 (A+E or B+M key), Mini PCIe, USB                                                 | M.2 (M, B+M, or A+E key)                                                                   |
| **Interface**       | PCIe Gen2 x1 per TPU                                                               | PCIe Gen3 (2 or 4 lanes)                                                                   |
| **Software Support**| TensorFlow Lite only                                                               | TensorFlow, TensorFlow Lite, ONNX, Keras, PyTorch                                          |
| **Maturity**        | Older technology (released ~2019) with a large community                           | Newer technology with better performance and broader framework support                     |

**Recommendation:**

The **Hailo-8 AI Accelerator** is the clear winner for a new design. It offers significantly higher performance, better power efficiency, and broader AI framework support compared to the aging Google Coral TPU. The availability of different performance tiers (Hailo-8 and Hailo-8L) also provides flexibility for cost and power optimization.

## 3. SOM Design and Form Factor

For your custom SOM, we recommend adopting a form factor similar to the NVIDIA Jetson Orin Nano, which uses a **260-pin SO-DIMM connector**. This approach offers several advantages:

*   **Industry Standard:** SO-DIMM connectors are widely available and cost-effective.
*   **High Pin Count:** The 260 pins provide ample I/O for connecting to the carrier board, including high-speed interfaces like PCIe, USB, and display outputs.
*   **Modularity:** The SOM can be easily replaced or upgraded without redesigning the carrier board.
*   **Proven Design:** This form factor is well-established in the embedded systems market.

**Key Design Considerations:**

*   **High-Speed Design:** The layout of a SOM with a modern x86 processor is a complex task that requires careful attention to signal integrity. This includes proper impedance control, length matching for high-speed differential pairs (like PCIe and USB), and a well-designed power delivery network (PDN).
*   **DDR Memory:** The routing for DDR4 or DDR5 memory is particularly challenging and requires precise length matching and impedance control to ensure stable operation.
*   **Power Management:** A robust power management solution is essential for a low-power design. This includes selecting efficient voltage regulators and implementing proper power sequencing for the CPU and other components.

## 4. Manufacturing Recommendations

Given the complexity of an x86-based SOM, you will need a PCB manufacturer with advanced capabilities. While JLCPCB is a popular choice for simpler boards, their 
economic service is not suitable for this type of design. You will need a manufacturer that can handle high layer counts, fine-pitch BGAs, and controlled impedance.

**PCBWay** is a better option for this project, as they offer advanced capabilities that are well-suited for complex designs:

*   **High Layer Count:** Up to 64 layers.
*   **HDI and Microvias:** Support for High-Density Interconnect (HDI) with staggered and stacked microvias.
*   **Fine-Pitch BGA:** Support for BGA pitches down to 0.4mm, which is necessary for modern CPUs and memory.
*   **Advanced Materials:** A wide range of high-frequency and high-speed materials from Rogers, Taconic, and others.
*   **Quality Control:** Comprehensive quality control processes, including UL, ISO9001, and TS16949 certifications.

**Recommendation:**

For a project of this complexity, we recommend using a manufacturer with a strong track record in advanced PCBs, such as **PCBWay**. While their services may be more expensive than some budget-oriented manufacturers, the quality and reliability are essential for a successful x86 SOM design.

## 5. Conclusion

Designing a custom AI inference SOM based on a laptop CPU is an ambitious but achievable goal. By carefully selecting the right components and following best practices for high-speed design, you can create a powerful and cost-effective solution. Here is a summary of our recommendations:

*   **CPU:** **AMD Ryzen AI 300 Series** for its superior NPU performance and power efficiency.
*   **External Accelerator:** **Hailo-8 AI Accelerator** for its high TOPS, power efficiency, and broad framework support.
*   **Form Factor:** **260-pin SO-DIMM** for its industry-standard, high-density, and modular design.
*   **Manufacturer:** **PCBWay** for their advanced capabilities in high-layer-count, HDI, and BGA assembly.

We recommend starting with a small prototype run to validate your design before committing to a larger production volume. Good luck with your project!

## References

1.  [Intel® Core™ Ultra Processors](https://www.intel.com/content/www/us/en/products/details/processors/core-ultra.html)
2.  [AMD Ryzen™ AI 300 Series Processors](https://www.amd.com/en/partner/articles/ryzen-ai-300-series-processors.html)
3.  [Hailo-8 M.2 AI Acceleration Module](https://hailo.ai/products/ai-accelerators/hailo-8-m2-ai-acceleration-module/)
4.  [Google Coral Edge TPU](https://coral.ai/products/)
5.  [How to Design a PCB for a System-on-Module](https://resources.pcb.cadence.com/blog/how-to-design-a-pcb-for-a-system-on-module)
6.  [NVIDIA Jetson Orin Nano Developer Kit](https://developer.nvidia.com/embedded/learn/jetson-orin-nano-devkit-user-guide/hardware_spec.html)
7.  [JLCPCB PCB Assembly Capabilities](https://jlcpcb.com/capabilities/pcb-assembly-capabilities)
8.  [PCBWay Advanced PCB Capabilities](https://www.pcbway.com/advanced-pcb-capabilities.html)
