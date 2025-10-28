# Research Summary - Custom AI SOM Design

**Date:** October 28, 2025  
**Research Phase:** Component Selection and Sourcing

---

## Executive Summary

Research swarms have been deployed to gather comprehensive data on CPUs, AI accelerators, and memory components for the Custom AI SOM design. This document summarizes the key findings and recommendations.

---

## 1. CPU Research Results

### AMD Ryzen AI 9 365 ⭐ **RECOMMENDED**

**Key Specifications:**
- **Cores:** 10 Cores / 20 Threads (4x Zen 5 + 6x Zen 5c)
- **NPU Performance:** 50 TOPS (AMD XDNA 2)
- **Total AI Performance:** 73 TOPS (NPU + CPU + GPU)
- **GPU:** AMD Radeon 880M (12 Graphics Cores, 2900 MHz)
- **TDP:** 28W default (configurable 15-54W)
- **Memory:** DDR5/LPDDR5x support
- **Process:** TSMC 4nm FinFET
- **Package:** FP8 (BGA, mobile/soldered)

**Pricing:**
- **Single Unit:** Not available as bare processor
- **System Integration:** $829 (Beelink SER9 Pro Mini PC reference)
- **100 Units:** Requires direct AMD engagement or authorized partners

**Availability:**
- Not sold through DigiKey/Mouser
- Available through AMD embedded partners
- ASRock Industrial 4X4 BOX AI300 Series (Q1 2025)

**Suppliers:**
- AMD Embedded/Partner Channels (direct engagement required)
- ASRock Industrial (https://www.asrockind.com/)
- System Integrators: Ma Labs, ASI

**Reference Designs:**
- AMD Ryzen AI Software platform
- ASRock Industrial 4X4 AI300 Motherboard Series

---

### AMD Ryzen AI 9 HX 370 ⭐ **ALTERNATIVE**

**Key Specifications:**
- **Cores:** 12 Cores / 24 Threads (4x Zen 5 + 8x Zen 5c)
- **NPU Performance:** 50 TOPS (XDNA 2)
- **Total AI Performance:** 80 TOPS
- **GPU:** AMD Radeon 890M (16 Graphics Cores)
- **TDP:** 28W default (configurable 15-54W)
- **Memory:** DDR5 and LPDDR5X
- **Process:** TSMC 4nm FinFET

**Pricing:**
- **Single Unit:** Not available as bare processor
- **Mini-ITX Motherboard:** $899/unit (MOQ 5 pieces)
- **System:** $629 (ACEMAGIC F3A Mini PC)

**Availability:**
- BGA package, not available as discrete component
- Available through industrial motherboard manufacturers

**Suppliers:**
- Shenzhen T.d.s Electronic Technology Co., Limited (Alibaba)
- Mini-PC vendors: Beelink, GEEKOM, GMKtec

---

### Intel Core Ultra 7 258V

**Key Specifications:**
- **Cores:** 8 Cores (4 P-cores, 4 LP E-cores) / 8 Threads
- **NPU Performance:** 47 TOPS (Intel AI Boost NPU 4.0)
- **GPU:** Intel Arc 140V (8 Xe-cores, 64 TOPS)
- **Total AI Performance:** 115 TOPS
- **TDP:** 17W base, 37W max turbo
- **Memory:** Up to 32GB LPDDR5X 8533 MT/s (on-package)
- **Package:** FCBGA-2833

**Pricing:**
- **Single Unit:** $930.34 (Mouser, non-stocked)
- **100 Units:** Requires direct Intel negotiation

**Availability:**
- Listed on Mouser as "Non-Stocked"
- Available through OEM/ODM channels
- Development kits available ($1,199 from Khadas)

**Suppliers:**
- Mouser Electronics (non-stocked)
- Embedded partners: Khadas, Simply NUC, DFI, BVM

**Reference Designs:**
- Intel AI PC Development Kit (Khadas Mind Maker Kit)
- OpenVINO Toolkit and developer resources

---

### Intel Core Ultra 5 228V

**Key Specifications:**
- **Cores:** 8 Cores (4 P-cores, 4 LPE-cores) / 8 Threads
- **NPU Performance:** 40 TOPS (Intel AI Boost)
- **GPU:** Intel Arc 130V (7 Xe-cores, 53 TOPS)
- **Total AI Performance:** 97 TOPS
- **TDP:** 17W base, 37W max turbo
- **Memory:** Up to 32GB LPDDR5X 8533 MT/s (on-package)
- **Package:** FCBGA2833

**Pricing:**
- **Single Unit:** ~$569 (broker/reseller)
- **100 Units:** ~$517 (broker/reseller)

**Availability:**
- Not available on DigiKey/Mouser
- Available through embedded system manufacturers
- AAEON UP Xtreme ARL developer board available

**Suppliers:**
- AAEON, ASRock Industrial, Innodisk
- Broker: Verified Electronics

---

## 2. AI Accelerator Research Results

### Hailo-8 M.2 Module ⭐ **RECOMMENDED**

**Key Specifications:**
- **AI Performance:** 26 TOPS
- **Power:** 2.5W typical, 8.65W maximum
- **Interface:** PCIe Gen3 (2-lane or 4-lane)
- **Form Factor:** M.2 2280/2260/2242 (Key M, B+M, or A+E variants)
- **Temperature:** -40°C to 85°C

**Framework Support:**
- TensorFlow, TensorFlow Lite, ONNX, Keras, PyTorch
- Hailo Dataflow Compiler and HailoRT runtime
- Linux and Windows support

**Pricing:**
- **Single Unit:** $179.99 - $249.99
- **100 Units:** $198-249 per piece (requires inquiry for volume discount)
- **Best Price:** $179.99 (Waveshare)

**Availability:**
- In stock from multiple distributors
- Lead time: 1-7 days from wholesale suppliers
- MOQ: 1 piece

**Suppliers:**
- **Official:** EBV Elektronik (Avnet), J-Squared Technologies, Macnica DHW
- **Resellers:** Waveshare, AAEON, RobotShop, Jevois Inc., Advantech

---

### Hailo-8L M.2 Module

**Status:** Research did not return results. This is a lower-power variant (13 TOPS) that may be suitable for cost-sensitive applications.

---

### Google Coral M.2 Accelerator (Dual Edge TPU)

**Key Specifications:**
- **AI Performance:** 8 TOPS total (4 TOPS per TPU)
- **Power:** 4W maximum (2 TOPS per watt)
- **Interface:** M.2 E-key with 2x PCIe Gen2 x1
- **Form Factor:** M.2-2230-D3-B (22.0 x 30.0 x 2.8 mm)
- **Temperature:** -40°C to +85°C

**Framework Support:**
- **TensorFlow Lite ONLY**
- Requires model conversion and quantization
- PyCoral API (Python) and libcoral API (C++)

**Pricing:**
- **Single Unit:** $46.99 (Seeed Studio) or $67.32 (Mouser)
- **100 Units:** Likely ≤$46.99 per unit

**Availability:**
- In stock at Seeed Studio (10+ units)
- In stock at RS Components (123 units)

**Suppliers:**
- Seeed Studio, Mouser, RS Components, Newark, Electromaker

**Limitations:**
- TensorFlow Lite only (major limitation)
- Older technology (released ~2019)
- Lower performance than Hailo-8

---

### Intel Movidius Myriad X VPU

**Key Specifications:**
- **AI Performance:** >1 TOPS per VPU
- **Power:** 3.8W typical (single VPU)
- **Interface:** M.2 2230 (Key A+E) or M.2 2280 (Key B+M)
- **Temperature:** -20°C to 60°C

**Framework Support:**
- **Legacy OpenVINO only** (discontinued in 2023.0+)
- TensorFlow, Caffe, MXNet, Kaldi, ONNX (via older OpenVINO)

**Pricing:**
- **Single VPU:** $110-121
- **Dual VPU:** $159
- **100 Units:** Estimated $88-143 (requires inquiry)

**Availability:**
- Available to order from Advantech, Mouser, Newark
- **End-of-life warning:** Intel discontinued support

**Suppliers:**
- Advantech, AAEON/UP, IEI, Mouser, Newark

**Limitations:**
- **Discontinued support** in modern OpenVINO
- Low performance compared to modern alternatives
- **Not recommended for new designs**

---

## 3. Memory Research Results

### DDR5 SO-DIMM 8GB

**Key Findings:**
- **Part Numbers:** Multiple options from Micron, Samsung, SK Hynix
- **Specifications:** DDR5-4800/5600, 1.1V, SO-DIMM form factor
- **Compatibility:** Compatible with AMD Ryzen AI and Intel Core Ultra
- **Pricing:** 
  - Single unit: $40-60
  - 100 units: $30-45 per unit
- **Availability:** In stock from major distributors
- **Suppliers:** DigiKey, Mouser, Crucial, Kingston

---

### DDR5 SO-DIMM 16GB

**Key Findings:**
- **Part Numbers:** Multiple options from major manufacturers
- **Specifications:** DDR5-4800/5600, 1.1V, SO-DIMM form factor
- **Compatibility:** Compatible with AMD Ryzen AI and Intel Core Ultra
- **Pricing:**
  - Single unit: $70-100
  - 100 units: $55-80 per unit
- **Availability:** In stock from major distributors
- **Suppliers:** DigiKey, Mouser, Crucial, Kingston

---

### DDR5 Chips (Soldered) - 8GB Capacity

**Key Findings:**
- **Part Numbers:** Available from Micron, Samsung, SK Hynix
- **Specifications:** DDR5 SDRAM chips for BGA mounting
- **Compatibility:** Requires custom PCB design with proper routing
- **Pricing:** Requires direct manufacturer inquiry
- **Availability:** Available through authorized distributors
- **Suppliers:** Direct from Micron, Samsung, SK Hynix

**Note:** Soldered DDR5 requires advanced PCB design expertise and adds significant complexity.

---

### DDR5 Chips (Soldered) - 16GB Capacity

**Key Findings:**
- Similar to 8GB capacity
- Higher density chips available
- Requires more complex routing
- **Recommendation:** Consider SO-DIMM approach for initial design

---

## Recommendations

### Primary Configuration ⭐

| Component | Recommendation | Rationale |
|-----------|---------------|-----------|
| **CPU** | AMD Ryzen AI 9 365 | Best NPU performance (50 TOPS), excellent power efficiency, 73 TOPS total |
| **AI Accelerator** | Hailo-8 M.2 (26 TOPS) | Best-in-class performance, broad framework support, reasonable pricing |
| **Memory** | DDR5 SO-DIMM 16GB | Simplifies design, readily available, good performance |
| **Total AI Performance** | **99 TOPS** (50 NPU + 26 Hailo + 23 GPU/CPU) | Significantly exceeds Jetson Orin Nano (40 TOPS) |

### Alternative Configuration

| Component | Recommendation | Rationale |
|-----------|---------------|-----------|
| **CPU** | AMD Ryzen AI 9 HX 370 | Higher core count (12 cores), 80 TOPS total |
| **AI Accelerator** | Hailo-8 M.2 (26 TOPS) | Same as primary |
| **Memory** | DDR5 SO-DIMM 16GB | Same as primary |
| **Total AI Performance** | **106 TOPS** | Maximum performance option |

### Budget Configuration

| Component | Recommendation | Rationale |
|-----------|---------------|-----------|
| **CPU** | Intel Core Ultra 5 228V | Lower cost, good availability through brokers |
| **AI Accelerator** | Google Coral Dual TPU | Lowest cost ($47), but TensorFlow Lite only |
| **Memory** | DDR5 SO-DIMM 8GB | Lower capacity for cost savings |
| **Total AI Performance** | **105 TOPS** (40 NPU + 8 Coral + 57 GPU/CPU) | Good performance, lower cost |

---

## Key Insights

### CPU Selection
1. **AMD Ryzen AI 300 Series** offers the best NPU performance (50 TOPS)
2. **Intel Core Ultra** offers higher total TOPS but includes on-package memory (limiting flexibility)
3. **Bare processors are not available** through standard distributors
4. **Sourcing strategy:** Must engage with embedded partners or use industrial motherboards as reference

### AI Accelerator Selection
1. **Hailo-8** is the clear winner for performance and framework support
2. **Google Coral** is budget-friendly but limited to TensorFlow Lite
3. **Intel Movidius** is end-of-life and not recommended

### Memory Selection
1. **SO-DIMM approach** is strongly recommended for initial design
2. **Soldered DDR5** adds significant complexity and should be reserved for production optimization
3. **16GB capacity** provides good balance of performance and cost

### Sourcing Strategy
1. **CPUs:** Must work with AMD embedded partners or ASRock Industrial
2. **AI Accelerators:** Multiple suppliers available, Waveshare offers best pricing
3. **Memory:** Standard distributors (DigiKey, Mouser) have good availability

---

## Next Steps

1. **Engage with AMD Embedded** to discuss CPU sourcing for SOM application
2. **Contact ASRock Industrial** regarding 4X4 AI300 series as reference platform
3. **Order Hailo-8 samples** from Waveshare ($179.99)
4. **Source DDR5 SO-DIMM samples** from DigiKey/Mouser
5. **Begin schematic design** using AMD reference designs
6. **Set up development environment** with AMD Ryzen AI Software and Hailo SDK

---

## Cost Estimate (Preliminary)

### Per-Unit BOM Cost (100 units)

| Component | Estimated Cost |
|-----------|---------------|
| AMD Ryzen AI 9 365 | $300-400 (estimated) |
| Hailo-8 M.2 | $180-200 |
| DDR5 16GB SO-DIMM | $60-80 |
| Power Management | $30-50 |
| Connectors & Passives | $20-30 |
| PCB (bare board) | $50-100 |
| **Subtotal** | **$640-860** |
| Assembly | $50-100 |
| **Total per unit** | **$690-960** |

**Note:** CPU pricing is estimated based on system pricing and requires direct inquiry with AMD.

---

**Research Status:** ✅ Phase 1 Complete  
**Next Phase:** Component Procurement and Schematic Design  
**Last Updated:** October 28, 2025
