# Custom AI Inference System-on-Module (SOM)

A custom System-on-Module design for AI inference applications, inspired by NVIDIA Jetson Orin Nano but based on low-cost, low-power laptop CPUs with integrated graphics and dedicated NPU/TPU accelerators.

## Project Overview

This project aims to create a cost-effective AI inference SOM that combines:
- **x86 laptop CPU** with integrated NPU and GPU (AMD Ryzen AI 300 Series recommended)
- **External AI accelerator** (Hailo-8 M.2 module recommended)
- **Modular design** using 260-pin SO-DIMM form factor
- **Carrier board architecture** for easy customization and expansion

## Key Features

- **High AI Performance**: 50+ TOPS from integrated NPU + 26 TOPS from Hailo-8 = 76+ TOPS total
- **Low Power**: Optimized for edge AI applications with configurable TDP
- **Modular Design**: Separate SOM and carrier board for flexibility
- **Cost-Effective**: Using laptop CPUs instead of specialized embedded processors
- **Open Architecture**: Designed for customization and expansion

## Project Structure

```
custom-ai-som-design/
├── docs/                      # Documentation
│   └── som_design_guide.md    # Comprehensive design guide
├── research/                  # Research and analysis
│   ├── cpu/                   # CPU research and comparisons
│   ├── accelerators/          # NPU/TPU accelerator research
│   ├── manufacturing/         # PCB manufacturing capabilities
│   └── som-design/            # SOM design considerations
├── hardware/                  # Hardware design files
│   ├── schematics/            # Schematic designs
│   ├── pcb/                   # PCB layout files
│   └── bom/                   # Bill of materials
├── software/                  # Software and drivers
└── tools/                     # Development and research tools
```

## Component Recommendations

### Primary Components

| Component | Recommendation | Rationale |
|-----------|---------------|-----------|
| **CPU** | AMD Ryzen AI 300 Series | 50+ TOPS NPU, excellent power efficiency, Zen 5 architecture |
| **External Accelerator** | Hailo-8 M.2 (26 TOPS) | Best-in-class performance, broad framework support |
| **Form Factor** | 260-pin SO-DIMM | Industry standard, high pin count, proven design |
| **Memory** | DDR5 SO-DIMM | High bandwidth for AI workloads |

### Manufacturing

| Aspect | Recommendation | Notes |
|--------|---------------|-------|
| **PCB Manufacturer** | PCBWay | 64-layer support, HDI, fine-pitch BGA |
| **Layer Count** | 10-16 layers | Required for complex x86 routing |
| **Assembly** | Professional PCBA service | BGA assembly, X-ray inspection required |

## Getting Started

### Prerequisites

- PCB design software (Altium Designer, KiCad, or Eagle)
- Component datasheets and reference designs
- Access to PCB manufacturing services
- Understanding of high-speed PCB design

### Development Phases

1. **Research & Planning** ✅ (Current Phase)
   - Component selection
   - Architecture design
   - Manufacturing partner selection

2. **Schematic Design** (Next Phase)
   - CPU and power management
   - Memory interfaces
   - I/O and connectivity
   - AI accelerator integration

3. **PCB Layout**
   - High-speed signal routing
   - Power distribution network
   - Thermal management
   - Mechanical design

4. **Prototype & Testing**
   - First article inspection
   - Bring-up and validation
   - Performance benchmarking
   - Thermal testing

5. **Production**
   - Design for manufacturing (DFM)
   - Production run
   - Quality control

## Research Tools & Methodology

This project uses advanced research methodologies including:
- **Deep Research Agents**: For comprehensive component analysis
- **Web Scraping & Analysis**: For real-time pricing and availability
- **Parallel Research Swarms**: For simultaneous multi-vendor comparisons
- **Automated Documentation**: For maintaining up-to-date specifications

## AI Software Stack

The SOM will support multiple AI frameworks and tools:
- **OpenVINO**: Intel's optimization toolkit
- **TensorFlow / TensorFlow Lite**: Google's ML framework
- **PyTorch**: Facebook's deep learning framework
- **ONNX Runtime**: Cross-platform inference engine
- **Hailo SDK**: For Hailo-8 accelerator optimization

## Use Cases

- Edge AI inference devices
- Computer vision applications
- Robotics and autonomous systems
- Industrial automation
- Smart city infrastructure
- Medical imaging devices
- Retail analytics systems

## Contributing

This is an active development project. Contributions are welcome in the following areas:
- Hardware design and optimization
- Software drivers and frameworks
- Testing and validation
- Documentation improvements

## License

This project is open-source and available under the MIT License.

## Contact & Support

For questions, suggestions, or collaboration opportunities, please open an issue in this repository.

## References

- [Design Guide](docs/som_design_guide.md)
- [Research Notes](research/)
- [AMD Ryzen AI 300 Series](https://www.amd.com/en/partner/articles/ryzen-ai-300-series-processors.html)
- [Hailo-8 AI Accelerator](https://hailo.ai/products/ai-accelerators/hailo-8-m2-ai-acceleration-module/)
- [NVIDIA Jetson Orin Nano](https://developer.nvidia.com/embedded/jetson-orin-nano-developer-kit)

---

**Status**: Research & Planning Phase  
**Last Updated**: October 2025  
**Project Lead**: AI Hardware Development Team
