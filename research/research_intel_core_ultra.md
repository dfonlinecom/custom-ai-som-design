# Intel Core Ultra Processor Research

## Intel Core Ultra 7 265 Specifications

### CPU Specifications
- **Total Cores**: 20 (8 Performance-cores + 12 Efficient-cores)
- **Total Threads**: 20
- **Max Turbo Frequency**: 5.3 GHz
- **Cache**: 30M Cache
- **Recommended Customer Price**: $384.00-$394.00

### NPU (Neural Processing Unit) Specifications
- **NPU Name**: Intel® AI Boost
- **NPU Peak TOPS (Int8)**: 13 TOPS
- **Sparsity Support**: Yes
- **Windows Studio Effects Support**: Yes
- **AI Software Frameworks**: OpenVINO™, WindowsML, DirectML, ONNX RT, WebNN

### GPU (Integrated Graphics) Specifications
- **GPU Name**: Intel® Graphics
- **Graphics Base Frequency**: 300 MHz
- **Graphics Max Dynamic Frequency**: 1.95 GHz
- **GPU Peak TOPS (Int8)**: 8 TOPS
- **Intel® Deep Learning Boost on GPU**: Yes

### Overall AI Performance
- **Overall Peak TOPS (Int8)**: 33 TOPS (combined CPU + GPU + NPU)

### Product Collection
- Intel® Core™ Ultra Processors (Series 2)
- Code Name: Arrow Lake
- Vertical Segment: Desktop

## Key Observations for SOM Design

1. **Integrated NPU**: Built-in 13 TOPS NPU for AI inference
2. **Integrated GPU**: Intel Arc graphics with 8 TOPS AI performance
3. **Combined AI Performance**: 33 TOPS total (CPU + GPU + NPU)
4. **Power Considerations**: Desktop variant - need to check mobile variants for lower TDP
5. **AI Framework Support**: Comprehensive support for OpenVINO, DirectML, ONNX RT, WebNN


## AMD Ryzen AI 300 Series Specifications

### Key Features
- **Architecture**: Zen 5 architecture on 4nm technology node
- **Cores**: Up to 12 cores
- **Graphics**: AMD RDNA 3.5 integrated graphics (Radeon 800M series)
- **NPU**: AMD XDNA 2 NPU architecture with up to 50+ TOPS
- **Memory**: 50% more on-chip memory than previous generation
- **Connectivity**: WiFi 7 and Bluetooth 5.4

### AI Performance
- **NPU TOPS**: Up to 50+ TOPS (world's best NPU for Windows 11 AI PCs)
- **AI Performance Improvement**: 3X improvement over previous generation
- **Power Efficiency**: 2X power efficiency for AI workloads

### Graphics Performance
- **Integrated GPU**: AMD Radeon 800M Series (fastest in class)
- **Graphics Cores**: 33% more graphics cores than previous generation
- **Architecture**: AMD RDNA 3.5

### Specific Models Mentioned
- **Radeon 890M**: 16 compute units
- **Radeon 880M**: 12 compute units

### Power Characteristics
- Designed for ultrathin x86 laptop devices
- 2X power efficiency across select AI workloads
- Optimized for mobile/laptop form factors

### Comparison Notes
- More high-performance cores than any AMD-powered PC in its class
- Best-in-class CPU, GPU and NPU performance
- Copilot+ PC ready


## Hailo-8 M.2 AI Accelerator Module Specifications

### Performance
- **AI Processor**: Hailo-8 AI processor
- **TOPS**: Up to 26 TOPS (Tera-Operations Per Second)
- **Power Efficiency**: Best-in-class power efficiency
- **Cost Efficiency**: Highest cost-efficiency (TOPS/$) compared with existing solutions

### Form Factor & Interface
- **Form Factor**: NGFF M.2 standard
- **Available Keys**: M, B+M, and A+E keys
- **Dimensions**: 22 x 42 mm (with breakable extensions to 22 x 60 mm and 22 x 80 mm)
- **Interface (M Key)**: PCIe Gen-3.0, 4 lanes (up to 32 Gbps)
- **Interface (B+M Key)**: PCIe Gen-3.0, 2 lanes

### Software Support
- **Supported Frameworks**: TensorFlow, TensorFlow Lite, ONNX, Keras, PyTorch
- **Supported OS**: Linux, Windows
- **Certification**: CE, FCC

### Key Features
- Enabling real-time, low latency, and high-efficiency AI inferencing on edge devices
- Scalable, enabling simultaneous processing of multi-streams & multi-models
- Robust software suite supports state-of-the-art deep learning models & applications out-of-the-box
- Supporting extended temperature range of -40°C to 85°C
- Fast time to market using standard form factor module

### Integration Notes for SOM Design
- Standard M.2 form factor makes it easy to integrate into carrier boards
- PCIe Gen-3.0 interface compatible with most modern processors
- Can be plugged into existing edge device with M.2 socket
- Multiple key options (M, B+M, A+E) provide flexibility for different board designs


## Google Coral Edge TPU Specifications

### Performance
- **TOPS**: 4 TOPS per Edge TPU
- **Power Consumption**: 2 watts (2 TOPS per watt)
- **Dual TPU Version**: 8 TOPS total (M.2 Accelerator with Dual Edge TPU)

### Form Factor Options
- **M.2 Accelerator (Single TPU)**: A+E key or B+M key
- **M.2 Accelerator (Dual TPU)**: 22mm x 30mm x 2.8mm (M.2-2230)
- **USB Accelerator**: USB form factor
- **PCIe Accelerator**: Full-height, half-length PCIe card

### Interface
- **M.2 Version**: PCIe Gen2 x1 interface per TPU
- **Operating Temperature**: -40°C to +85°C

### Software Support
- **Framework**: TensorFlow Lite
- **OS Support**: Linux, Windows (with drivers)

### Comparison with Hailo
- **Coral Edge TPU**: 4 TOPS per chip, 2W power
- **Coral Dual Edge TPU**: 8 TOPS total, ~4W power
- **Hailo-8L**: 13 TOPS
- **Hailo-8**: 26 TOPS

### Notes
- Coral TPU is older technology (released ~2019)
- Hailo offers better TOPS/$ and TOPS/watt ratios
- Coral has good community support but less active development
- TensorFlow Lite only vs Hailo's broader framework support


## SOM Design Considerations

### Building Blocks of a System-on-Module

#### Main Components
1. **Main Processor**: MPU (like Intel Core Ultra or AMD Ryzen AI) or FPGA
2. **Memory**: DDR4/DDR5 RAM chips
3. **Storage**: eMMC or SSD controller
4. **Power Management**: Voltage regulators, power sequencing
5. **Peripherals**: Can be on SOM or carrier board (designer's choice)

#### Connection Methods to Carrier Board
1. **Mezzanine Connectors** (Most Common for High I/O Count)
   - Used on development boards for large processors
   - Supports many interfaces and connections
   - Allows easy module replacement

2. **Edge Connector with Exposed Pins**
   - Very common in modular systems
   - Similar to Jetson Orin Nano form factor
   - Good for standardized interfaces

3. **Castellated Holes** (Less Common)
   - Soldered directly to main board
   - More difficult to change later
   - Permanent connection

### Key Design Considerations

#### High-Speed Signal Design
- **Interfaces to Support**: USB, Ethernet, MIPI (display/camera), PCIe
- **PCB Stackup**: Proper layer stack for signal integrity
- **Power Distribution Network (PDN)**: Critical for stable operation
- **BGA Package Layout**: Proper routing for processor BGA
- **Signal Integrity**: Impedance control, length matching for high-speed signals

#### Modular Design Benefits
- **Risk Reduction**: Spread critical components into one module
- **Future-Proofing**: Only upgrade obsolete module, not entire system
- **Supply Chain**: Easier to manage component availability
- **Cost-Effective**: Reuse carrier board across product generations

#### Design Resources Needed
- Schematics and Bill of Materials (BOM)
- PCB layout files
- 3D models for mechanical integration
- S-parameter/IBIS models for SI simulation
- Design guidelines and application notes


## Nvidia Jetson Orin Nano as Reference Design

### Form Factor
- **Connector**: 260-pin SO-DIMM connector, 1.27mm pitch
- **Interface**: Standard SODIMM form factor
- **Size**: Smallest Jetson form-factor

### Performance Specifications
- **AI Performance**: 40 TOPS (up to 67 TOPS with software update)
- **Power Options**: 5W to 15W
- **GPU**: NVIDIA Ampere architecture with 1024 CUDA cores and 32 tensor cores
- **CPU**: 6-core Arm Cortex-A78AE
- **Memory Bandwidth**: 68 GB/s (up to 102 GB/s with update)

### Connector Details
- **260-pin SO-DIMM**: Industry standard connector
- **Exposes**: Power, ground, high-speed and low-speed I/O
- **Mating Connector**: Available from standard suppliers
- **Reference Design**: Carrier board schematics and design files available

### Design Resources Available
- Concept schematics PDF & design files
- OrCAD schematic design files
- Allegro layout files
- PCB stack-up information
- Gerber files
- Design guidelines and recommendations

### Why This Form Factor Works
- **Industry Standard**: SO-DIMM is well-established
- **Compact**: Small footprint for edge AI applications
- **High Pin Count**: 260 pins support many interfaces
- **Proven**: Used across Jetson product line
- **Supply Chain**: Standard connectors readily available


## Online PCB Manufacturers - JLCPCB

### PCB Assembly Capabilities

#### Economic PCBA Service
- **Assembly Types**: Single sided placement (SMT/Through-hole)
- **PCB Layers**: 2, 4, 6-layers
- **Thickness**: 0.8mm - 1.6mm
- **Dimension**: 
  - Single PCB: 10x10mm - 470x500mm
  - Panel: 10x10mm - 250x250mm
- **Order Volume**: 2 - 50 pcs
- **Minimum Package**: 0402
- **Minimum IC Pin Spacing**: 0.4mm
- **Minimum BGA Spacing**: 0.5mm (center to center)
- **Build Time**: 1 - 3 days
- **Inspection**: AOI, Visual, X-ray (for BGA)

#### Standard PCBA Service
- **Assembly Types**: Single & double sided placement (SMT/Through-hole)
- **PCB Layers**: 1 - 32 layers
- **Thickness**: No limit
- **Dimension**: 
  - Single PCB: 70x70mm - 460x500mm
  - Panel: 70x70mm - 250x250mm
- **Order Volume**: 2 - 80,000 pcs
- **Minimum Package**: 0201
- **Minimum IC Pin Spacing**: 0.35mm
- **Minimum BGA Spacing**: 0.35mm (center to center)
- **Build Time**: ≥ 4 days
- **Special Features**: 
  - Castellated holes support
  - Edge plating support
  - SPI inspection
  - All stack-up options
- **Inspection**: SPI, AOI, Visual, X-ray (for BGA)

### Key Considerations for SOM Design
- **BGA Support**: Yes, with X-ray inspection
- **Component Library**: 440,000+ in-stock components
- **High Layer Count**: Up to 32 layers supported
- **Complex Assembly**: Double-sided SMT supported
- **Quality Control**: Multiple inspection methods
- **Scalability**: From prototype (2 pcs) to production (80,000 pcs)

### Limitations for Complex SOM
- **Economic PCBA**: Limited to 6 layers, may not be suitable for complex x86 SOM
- **Standard PCBA**: Better suited for complex designs with high layer counts
- **Component Sourcing**: May need to provide specialized components (CPUs, high-end DDR5)


## Online PCB Manufacturers - PCBWay

### Advanced PCB Manufacturing Capabilities

#### Layer Count and Complexity
- **Max Layer Count**: 64 layers (as of 2018)
- **HDI Support**: HDI(7+N+7) staggered and stacked vias
- **Buried IC**: Supported
- **Aspect Ratio**: Up to 20:1

#### Board Specifications
- **Max Board Size**: 609mm x 889mm (20" x 35")
- **Board Thickness**: 0.21mm - 6.0mm
- **Min Track/Space**: 2mil inner / 2mil outer (portions)
- **Copper Thickness**: Up to 8oz outer and inner layers

#### Advanced Features
- **Min Hole Size**: 
  - Mechanical: 0.15mm
  - Laser (blind/buried): 0.1mm
- **Min BGA Pitch**: 0.4mm
- **Min BGA Diameter**: 8mil
- **Impedance Control**: ±10%, 50Ω and below: ±5Ω

#### Materials Support
- **Standard FR4**: Shengyi, Kingboard
- **High-Tg Materials**: Up to Tg-220
- **High-Frequency Materials**: Rogers, Taconic, Arlon, PTFE
- **High-Speed Materials**: Support for 1-5G, 5-10G, 10-25G, >25G applications
- **Halogen-Free**: Available

#### Surface Finishes
- ENIG, HASL (leaded/lead-free), OSP, Immersion Ag, Immersion Sn, Gold Plating

#### Quality Certifications
- UL, ISO9001, ISO14000, ROHS, TS16949

### PCB Assembly Capabilities (PCBWay)
- **BGA Assembly**: Supported with proper capabilities
- **Component Sourcing**: Turnkey or consignment
- **Quality Inspection**: AOI, X-ray, visual inspection
- **Production Scale**: Prototype to production volumes

### Suitability for SOM Design
- **Excellent for Complex Designs**: 64-layer support, HDI, high-density
- **High-Frequency Support**: Multiple material options for high-speed signals
- **BGA Support**: Critical for CPU and memory chips
- **Professional Service**: Better suited for complex x86 SOM than JLCPCB economic service
- **Component Sourcing**: May require customer-supplied components for specialized parts
