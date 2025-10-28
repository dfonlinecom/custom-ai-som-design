# Project Requirements & Specifications

## Project Goals

Design and develop a custom System-on-Module (SOM) for AI inference that:
1. Provides high AI performance at low cost
2. Maintains low power consumption for edge deployment
3. Uses readily available laptop CPU components
4. Supports modular carrier board architecture
5. Enables easy manufacturing through online PCB services

## Functional Requirements

### Performance Requirements

| Requirement | Target | Rationale |
|------------|--------|-----------|
| **AI Performance** | 70+ TOPS total | Competitive with Jetson Orin Nano (40 TOPS) |
| **CPU Performance** | 8-12 cores | Sufficient for AI preprocessing and system tasks |
| **Memory Bandwidth** | 100+ GB/s | Required for AI model loading and inference |
| **Power Consumption** | 15-25W typical | Suitable for fanless or small fan cooling |
| **Operating Temperature** | 0°C to 70°C | Standard commercial temperature range |

### Interface Requirements

**Required Interfaces:**
- PCIe Gen 3/4 (for AI accelerator and NVMe storage)
- USB 3.2 Gen 2 (multiple ports)
- Gigabit Ethernet or 2.5GbE
- DisplayPort or HDMI (from integrated GPU)
- GPIO for general purpose I/O
- I2C, SPI, UART for peripheral communication
- MIPI CSI-2 for camera input (optional)

### Form Factor Requirements

- **Connector**: 260-pin SO-DIMM (1.27mm pitch)
- **SOM Dimensions**: Similar to Jetson Orin Nano (69.6mm x 45mm target)
- **Mounting**: Compatible with standard SO-DIMM sockets
- **Thermal Interface**: Exposed thermal pad for heatsink attachment

## Technical Specifications

### CPU Specifications

**Recommended: AMD Ryzen AI 300 Series**

- Architecture: Zen 5
- Process: 4nm
- Cores: Up to 12 cores
- Integrated GPU: RDNA 3.5 (Radeon 800M series)
- Integrated NPU: XDNA 2 (50+ TOPS)
- Memory Support: DDR5
- TDP: Configurable (15W-28W range)

### AI Accelerator Specifications

**Recommended: Hailo-8 M.2 Module**

- Performance: 26 TOPS
- Interface: PCIe Gen 3 x4 (M-key) or x2 (B+M key)
- Power: <5W typical
- Temperature: -40°C to 85°C
- Framework Support: TensorFlow, PyTorch, ONNX, Keras

### Memory Specifications

- Type: DDR5 SO-DIMM
- Capacity: 8GB, 16GB, or 32GB options
- Speed: DDR5-4800 or higher
- Configuration: Single or dual channel

### Storage Specifications

- Primary: eMMC 5.1 (32GB-128GB) soldered on SOM
- Secondary: M.2 NVMe via carrier board (optional)

## Design Constraints

### PCB Design Constraints

| Parameter | Specification |
|-----------|---------------|
| **Layer Count** | 10-16 layers |
| **Board Thickness** | 1.6mm ±10% |
| **Min Trace Width** | 4mil (0.1mm) |
| **Min Spacing** | 4mil (0.1mm) |
| **Via Size** | 0.2mm minimum |
| **BGA Pitch** | 0.4mm minimum |
| **Impedance Control** | ±10% (50Ω, 90Ω, 100Ω) |

### Power Requirements

**Power Rails:**
- 5V input (main power)
- 3.3V (I/O and peripherals)
- 1.8V (I/O and memory)
- 1.2V (CPU core)
- 1.0V (CPU core)
- 0.9V (memory)

**Power Budget:**
- CPU: 15-25W
- Memory: 3-5W
- AI Accelerator: 3-5W
- Peripherals: 2-3W
- **Total**: 25-40W maximum

### Thermal Requirements

- Maximum junction temperature: 95°C
- Thermal solution: Heatsink with thermal pad
- Airflow: Passive or active (small fan)

## Manufacturing Requirements

### PCB Manufacturing

**Manufacturer Capabilities Required:**
- High layer count (10+ layers)
- HDI with microvias
- Fine-pitch BGA assembly (0.4mm pitch)
- Controlled impedance
- X-ray inspection for BGA
- AOI (Automated Optical Inspection)

**Recommended Manufacturer:** PCBWay

### Component Sourcing

**Critical Components:**
- AMD Ryzen AI CPU (may require direct sourcing)
- DDR5 memory chips
- Hailo-8 M.2 module
- Power management ICs
- SO-DIMM connector (260-pin)

**Component Availability:**
- Standard components: DigiKey, Mouser, Arrow
- Specialized components: Direct from manufacturer or authorized distributors
- Alternative sourcing: Alibaba for volume production

## Quality & Testing Requirements

### Electrical Testing

- Power-on self-test (POST)
- Memory testing (MemTest86)
- CPU stress testing
- AI accelerator validation
- Interface connectivity testing

### Thermal Testing

- Thermal imaging under load
- Temperature monitoring at critical points
- Thermal cycling tests

### Reliability Testing

- Burn-in testing (48-72 hours)
- Vibration testing (for mobile applications)
- ESD testing
- EMI/EMC compliance testing

## Compliance & Certifications

**Required Certifications:**
- CE marking (Europe)
- FCC (United States)
- RoHS compliance
- REACH compliance

**Optional Certifications:**
- UL listing
- Military standards (MIL-STD) for rugged applications

## Software Requirements

### Operating System Support

- Linux (Ubuntu, Debian, Yocto)
- Windows 11 (with AI PC features)
- Custom embedded Linux distributions

### AI Framework Support

- TensorFlow / TensorFlow Lite
- PyTorch
- ONNX Runtime
- OpenVINO
- Hailo SDK

### Driver Requirements

- CPU drivers (AMD chipset drivers)
- GPU drivers (AMD RDNA drivers)
- NPU drivers (AMD XDNA drivers)
- Hailo-8 drivers and SDK

## Documentation Requirements

**Required Documentation:**
- Schematic diagrams
- PCB layout files
- Bill of Materials (BOM)
- Assembly drawings
- User manual
- Software development guide
- Thermal design guide

## Timeline & Milestones

| Phase | Duration | Deliverables |
|-------|----------|--------------|
| **Research & Planning** | 2-4 weeks | Component selection, design guide |
| **Schematic Design** | 4-6 weeks | Complete schematics, BOM |
| **PCB Layout** | 6-8 weeks | PCB layout, Gerber files |
| **Prototype** | 4-6 weeks | First prototypes, bring-up |
| **Testing & Validation** | 4-6 weeks | Test reports, design refinements |
| **Production** | 2-4 weeks | Production-ready design |

**Total Estimated Timeline:** 6-8 months from concept to production

## Budget Considerations

### Prototype Costs (Estimated)

- PCB fabrication: $500-1,000 per board (5-10 units)
- Component costs: $300-500 per unit
- Assembly: $200-400 per unit
- Testing equipment: $1,000-2,000 (one-time)
- **Total per prototype**: $1,000-1,900

### Production Costs (Estimated, 100+ units)

- PCB fabrication: $50-100 per board
- Component costs: $250-400 per unit
- Assembly: $50-100 per unit
- **Total per unit**: $350-600

## Risk Assessment

| Risk | Impact | Mitigation |
|------|--------|------------|
| Component availability | High | Multiple sourcing options, design alternatives |
| Thermal management | Medium | Early thermal simulation, prototype testing |
| Signal integrity issues | High | Professional PCB design, simulation tools |
| Manufacturing defects | Medium | Choose experienced manufacturer, thorough testing |
| Software compatibility | Medium | Early driver validation, community support |

## Success Criteria

The project will be considered successful when:
1. Prototype boots and runs operating system
2. AI inference performance meets or exceeds 70 TOPS
3. Power consumption stays within 25-40W range
4. Thermal performance allows for passive or small fan cooling
5. All interfaces function correctly
6. Manufacturing cost targets are met
7. Design is reproducible by online PCB manufacturers

---

**Document Version:** 1.0  
**Last Updated:** October 2025  
**Status:** Draft
