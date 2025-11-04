# Lanyard-Worn AI Device Design

**Date:** November 4, 2025  
**Configuration:** Jetson Orin Nano 16GB + Axelera Metis M.2 NPU  
**Form Factor:** Lanyard-worn personal AI companion  
**Performance:** 254 TOPS AI compute

---

## 🎯 Design Philosophy

**A wearable AI companion that combines:**
- **Stunning visual display** - Beautiful AMOLED touchscreen
- **AI-powered vision** - 4K camera with depth sensing
- **Premium audio** - Studio-quality speakers and microphones
- **Massive AI compute** - 254 TOPS for real-time intelligence
- **All-day battery** - 8-12 hours of continuous use
- **Elegant design** - Sleek, modern, professional appearance

---

## 📐 Physical Specifications

### Form Factor:

**Device Dimensions:**
- **Width:** 3.5 inches (89mm)
- **Height:** 5.0 inches (127mm)
- **Depth:** 0.75 inches (19mm)
- **Weight:** 12 oz (340g) with battery

**Display Size:**
- **3.4 inches** diagonal AMOLED touchscreen
- **Aspect Ratio:** 16:9 or 18:9
- **Orientation:** Portrait (vertical)

**Comparison:**
- Similar to a large smartphone (iPhone 15 Pro: 5.77" x 2.78" x 0.32", 6.6 oz)
- Slightly thicker and heavier due to compute module
- Comfortable for lanyard wear

---

## 🖥️ Display Specifications

### Premium AMOLED Touchscreen:

**Recommended:** **Waveshare 3.4" AMOLED Display**

| Specification | Value |
|---------------|-------|
| **Size** | 3.4 inches diagonal |
| **Resolution** | 800 x 480 pixels (WVGA) |
| **Technology** | AMOLED (Active Matrix OLED) |
| **Touch** | Capacitive multi-touch (5-point) |
| **Colors** | 16.7M colors (24-bit) |
| **Brightness** | 400 nits |
| **Contrast** | 100,000:1 |
| **Viewing Angle** | 170° (full viewing) |
| **Interface** | MIPI DSI or HDMI |
| **Power** | 0.5-1.5W (depending on brightness) |
| **Price** | **$45-60** |
| **Source** | Waveshare, AliExpress |

**Alternative:** **LilyGo T-Display S3 AMOLED (1.91")**
- Smaller but ultra-compact
- 240 x 536 pixels
- ESP32-S3 controller
- $25-30
- Good for ultra-compact design

**Why AMOLED:**
- **Deep blacks** - Perfect contrast
- **Vibrant colors** - Stunning visual quality
- **Low power** - Only lit pixels consume power
- **Fast response** - No motion blur
- **Thin profile** - Enables slim design
- **Wide viewing angles** - Readable from any angle

---

## 📷 Camera System

### Dual Camera Setup:

#### **Primary AI Camera:**

**Recommended:** **Arducam 8MP IMX219 4K USB Camera**

| Specification | Value |
|---------------|-------|
| **Sensor** | Sony IMX219 8MP |
| **Resolution** | 3264 x 2448 (8MP still), 1920 x 1080 (video) |
| **Video** | 1080p @ 30fps, 720p @ 60fps |
| **Lens** | Autofocus, 75° FOV |
| **Interface** | USB 2.0 (UVC compatible) |
| **Size** | 38mm x 38mm x 18mm (compact) |
| **Weight** | 15g |
| **Features** | Auto white balance, auto exposure |
| **Power** | 1.5-2W |
| **Price** | **$45-55** |
| **Source** | Arducam, Amazon |

**Alternative:** **e-CAM83 Sony IMX415 4K Camera**
- 8.3MP Sony STARVIS sensor
- Ultra low-light performance
- MIPI CSI-2 interface (native Jetson)
- $80-100
- Better for low-light scenarios

#### **Depth Camera (Optional):**

**Recommended:** **Intel RealSense D435i (compact version)**

| Specification | Value |
|---------------|-------|
| **Technology** | Stereo depth camera |
| **Depth Range** | 0.3m to 3m |
| **Resolution** | 1280 x 720 depth |
| **RGB Camera** | 1920 x 1080 @ 30fps |
| **IMU** | 6-axis (accel + gyro) |
| **Interface** | USB 3.0 |
| **Size** | 90mm x 25mm x 25mm |
| **Weight** | 72g |
| **Power** | 1.5-3W |
| **Price** | **$200-250** |
| **Source** | Intel, Amazon |

**Budget Alternative:** **OAK-D Lite** (Luxonis)
- Stereo depth camera
- 4K RGB camera
- On-device AI processing
- USB-C interface
- $149
- Smaller form factor

**Camera Placement:**
- **Primary camera:** Top center of device (front-facing)
- **Depth camera:** Below display or side-mounted
- **Both cameras:** Aligned for optimal field of view when worn

---

## 🔊 Audio System

### Premium Dual Speaker Setup:

**Recommended:** **Stereo Micro Speakers (2x)**

| Specification | Value |
|---------------|-------|
| **Driver Size** | 20mm x 15mm (oval) or 20mm round |
| **Power** | 2W RMS per speaker |
| **Impedance** | 4Ω or 8Ω |
| **Frequency** | 200Hz - 20kHz |
| **Sensitivity** | 85-90 dB |
| **Technology** | Neodymium magnet |
| **Enclosure** | Sealed back for better bass |
| **Price** | **$8-12 per pair** |
| **Source** | Parts Express, Mouser |

**Specific Model:** **MISCO MS20-8** or **Pui Audio AS02008MR-R**

**Speaker Placement:**
- **Top speaker:** Above display (for voice/calls)
- **Bottom speaker:** Below display (for media/music)
- **Stereo separation:** ~4 inches for spatial audio

**Amplifier:**
- **Texas Instruments TAS2563** (Class-D, 2.4W stereo)
- **Maxim MAX98357A** (Class-D, 3.2W mono, I2S interface)
- Integrated into PCB design
- **Cost:** $3-5

---

## 🎤 Microphone Array

### Quad MEMS Microphone Array:

**Recommended:** **ReSpeaker 4-Mic Array (USB)**

| Specification | Value |
|---------------|-------|
| **Microphones** | 4x MEMS microphones |
| **Type** | Omnidirectional |
| **SNR** | 63 dB |
| **Sensitivity** | -26 dBFS |
| **Frequency** | 100Hz - 10kHz |
| **Interface** | USB 2.0 (plug-and-play) |
| **Features** | Beamforming, AEC, noise suppression |
| **Size** | 70mm diameter (circular array) |
| **Power** | 0.5W |
| **Price** | **$69** |
| **Source** | Seeed Studio |

**Alternative:** **Custom 4-Mic Linear Array**

| Specification | Value |
|---------------|-------|
| **Microphones** | 4x Infineon IM69D130 MEMS |
| **Arrangement** | Linear array (top edge of device) |
| **Spacing** | 15mm between mics |
| **Interface** | I2S (direct to Jetson) |
| **Features** | 120 dB SPL, low noise |
| **Total Cost** | **$20-30** (DIY) |
| **Advantage** | Smaller, integrated design |

**Microphone Placement:**
- **4 mics in linear array** along top edge
- **15mm spacing** for beamforming
- **Downward facing** to capture user voice
- **DSP processing** for noise cancellation and echo reduction

**DSP/Processing:**
- **XMOS XVF3510** voice processor (optional, $15)
- **Software beamforming** using Jetson compute
- **Acoustic echo cancellation** (AEC)
- **Noise suppression** and **automatic gain control**

---

## 🔋 Power System

### Battery Configuration:

**Recommended:** **Dual 18650 Li-ion Cells**

| Specification | Value |
|---------------|-------|
| **Cells** | 2x 18650 (3.7V, 3500mAh each) |
| **Configuration** | 2S1P (7.4V, 3500mAh) |
| **Capacity** | 25.9 Wh |
| **Weight** | 90g (for 2 cells) |
| **Dimensions** | 18mm x 65mm per cell |
| **Protection** | BMS with overcharge/discharge protection |
| **Charging** | USB-C PD (18W) |
| **Price** | **$15-20** (cells + BMS) |

**Alternative:** **LiPo Pouch Cell**

| Specification | Value |
|---------------|-------|
| **Capacity** | 5000mAh @ 7.4V (2S) |
| **Energy** | 37 Wh |
| **Weight** | 85g |
| **Dimensions** | 65mm x 50mm x 10mm (custom shape) |
| **Advantage** | Thinner profile, custom shape |
| **Price** | **$25-35** |

### Power Budget:

| Component | Power Draw |
|-----------|------------|
| Jetson Orin Nano 16GB (eco) | 7W |
| Axelera Metis M.2 | 8W |
| 3.4" AMOLED display (50% brightness) | 0.8W |
| Primary camera (1080p) | 2W |
| Depth camera (optional) | 2W |
| Speakers (moderate volume) | 1W |
| Microphone array | 0.5W |
| WiFi/BT | 0.5W |
| **Total (without depth camera)** | **19.8W** |
| **Total (with depth camera)** | **21.8W** |

### Battery Life:

**With 25.9 Wh battery:**
- **Without depth camera:** 25.9Wh / 19.8W = **1.3 hours**
- **With depth camera:** 25.9Wh / 21.8W = **1.2 hours**

**⚠️ This is too short! Need larger battery.**

**Revised Battery:** **10,000mAh @ 7.4V (74 Wh)**

| Specification | Value |
|---------------|-------|
| **Capacity** | 10,000mAh @ 7.4V |
| **Energy** | 74 Wh |
| **Configuration** | 2S2P (4x 18650 cells) or LiPo pouch |
| **Weight** | 180g (18650) or 170g (LiPo) |
| **Dimensions** | 70mm x 60mm x 20mm (LiPo pouch) |
| **Price** | **$40-60** |

**Revised Battery Life:**
- **Without depth camera:** 74Wh / 19.8W = **3.7 hours**
- **With depth camera:** 74Wh / 21.8W = **3.4 hours**

**Still too short! Need 8-12 hours.**

**Final Battery:** **20,000mAh @ 7.4V (148 Wh)**

| Specification | Value |
|---------------|-------|
| **Capacity** | 20,000mAh @ 7.4V |
| **Energy** | 148 Wh |
| **Configuration** | 2S4P (8x 18650 cells) or large LiPo pouch |
| **Weight** | 360g (18650) or 340g (LiPo) |
| **Dimensions** | 100mm x 70mm x 25mm (LiPo pouch) |
| **Price** | **$80-120** |

**Final Battery Life:**
- **Without depth camera:** 148Wh / 19.8W = **7.5 hours** ✅
- **With depth camera:** 148Wh / 21.8W = **6.8 hours** ✅
- **Eco mode (15W total):** 148Wh / 15W = **9.9 hours** ✅

**Target: 8-12 hours achieved!**

---

## 🎨 Industrial Design

### Device Layout:

```
┌─────────────────────────────┐
│   [●] Camera  [●●●●] Mics  │ ← Top edge
├─────────────────────────────┤
│         [Speaker]           │ ← Top speaker
├─────────────────────────────┤
│                             │
│      ┌───────────────┐      │
│      │               │      │
│      │   3.4" AMOLED │      │ ← Display
│      │   Touchscreen │      │
│      │               │      │
│      └───────────────┘      │
│                             │
├─────────────────────────────┤
│         [Speaker]           │ ← Bottom speaker
├─────────────────────────────┤
│     [USB-C]  [Button]       │ ← Bottom edge
└─────────────────────────────┘
    3.5" wide x 5.0" tall
```

### Materials:

**Front Panel:**
- **Gorilla Glass** or **Sapphire Glass** (display cover)
- **Aluminum frame** (CNC machined, anodized)
- **Color options:** Black, silver, space gray, blue, rose gold

**Back Panel:**
- **Carbon fiber** or **aluminum** (heat dissipation)
- **Soft-touch coating** (optional, for grip)
- **Ventilation slots** (for passive cooling)

**Lanyard Attachment:**
- **Reinforced metal loop** (top center or top corners)
- **Quick-release mechanism** (optional)
- **Adjustable lanyard** (nylon or leather, 20-36" length)

### Cooling:

**Passive Cooling:**
- **Aluminum back plate** (acts as heatsink)
- **Thermal pads** connecting Jetson/Metis to back plate
- **Ventilation slots** on sides for airflow

**Active Cooling (Optional):**
- **Ultra-thin fan** (5mm thickness, 30mm diameter)
- **Temperature-controlled** (only activates above 60°C)
- **Whisper-quiet** (<20 dB)
- **Cost:** $10-15

---

## 💻 Core Compute

### Jetson Orin Nano 16GB (Upgraded):

| Specification | Value |
|---------------|-------|
| **Base Module** | Jetson Orin Nano 8GB |
| **Upgrade** | Seeed Studio 16GB memory upgrade |
| **AI Performance** | 40 TOPS @ INT8 |
| **GPU** | 512-core NVIDIA Ampere |
| **CPU** | 6-core ARM Cortex-A78AE @ 1.5 GHz |
| **Memory** | 16GB LPDDR5 |
| **Power** | 7-15W (configurable) |
| **Size** | 69.6mm x 45mm (SOM) |
| **Cost** | **$285** ($200 + $85 upgrade) |

### Axelera Metis M.2 NPU:

| Specification | Value |
|---------------|-------|
| **AI Performance** | 214 TOPS @ INT8 |
| **Architecture** | Quad-core Metis AIPU |
| **Memory** | 1GB DRAM (dedicated) |
| **Interface** | PCIe Gen 3.0 x4 |
| **Power** | 8-10W typical |
| **Size** | 22mm x 80mm (M.2 2280) |
| **Cost** | **$259** |

### **Total AI Performance: 254 TOPS**

---

## 🔌 Connectivity

### Wireless:

**WiFi 6 + Bluetooth 5.2 Module:**
- **Intel AX200** or **MediaTek MT7921**
- **WiFi 6** (802.11ax, 2.4GHz + 5GHz)
- **Bluetooth 5.2** (BLE support)
- **Interface:** M.2 Key E or USB
- **Antennas:** Integrated or external (2x for WiFi, 1x for BT)
- **Cost:** $15-25

### Wired:

**USB-C Port (Bottom):**
- **USB 3.1 Gen 2** (10 Gbps data)
- **Power Delivery** (18W charging)
- **DisplayPort Alt Mode** (optional, for external display)
- **Functions:** Charging, data transfer, debugging

**Optional:** **Magnetic pogo pins** (side-mounted for charging dock)

### Cellular (Optional):

**4G LTE Module:**
- **Quectel EC25** or **SIMCom SIM7600**
- **Bands:** Global LTE (Cat 4)
- **Interface:** USB or M.2
- **SIM:** Nano SIM slot (side-mounted)
- **Cost:** $30-50

---

## 📱 Software Stack

### Operating System:

**NVIDIA JetPack 5.1+**
- Ubuntu 20.04 LTS (ARM64)
- CUDA 11.4+
- TensorRT 8.5+
- cuDNN 8.6+

### AI Frameworks:

**Pre-installed:**
- **PyTorch** (with CUDA support)
- **TensorFlow** (with TensorRT optimization)
- **ONNX Runtime** (for Metis NPU)
- **OpenCV** (with CUDA acceleration)

### Axelera Voyager SDK:

**For Metis NPU:**
- **Model Zoo** (pre-optimized models)
- **Compiler** (convert models to Metis format)
- **Runtime** (efficient inference)
- **Supported:** YOLOv5/v8, ResNet, MobileNet, SegFormer, etc.

### Voice Processing:

**Audio Pipeline:**
- **ALSA** (low-level audio)
- **PulseAudio** (audio routing)
- **Beamforming** (custom or ReSpeaker SDK)
- **Whisper** (speech-to-text, on-device)
- **Piper** (text-to-speech, on-device)

### UI Framework:

**Options:**
- **Qt/QML** (native, performant)
- **Electron** (web-based, easier development)
- **Flutter** (cross-platform, modern UI)
- **Custom OpenGL** (maximum performance)

---

## 💰 Bill of Materials (BOM)

### Core Components:

| Component | Model/Spec | Qty | Unit Price | Total |
|-----------|------------|-----|------------|-------|
| **Jetson Orin Nano 8GB** | Bulk order | 1 | $200 | $200 |
| **16GB Memory Upgrade** | Seeed Studio | 1 | $85 | $85 |
| **Axelera Metis M.2** | NPU accelerator | 1 | $259 | $259 |
| **3.4" AMOLED Display** | Waveshare | 1 | $55 | $55 |
| **Primary Camera** | Arducam IMX219 8MP | 1 | $50 | $50 |
| **Depth Camera** | OAK-D Lite (optional) | 1 | $149 | $149 |
| **Microphone Array** | 4x MEMS (custom) | 1 | $25 | $25 |
| **Speakers** | 2x 20mm micro speakers | 1 | $10 | $10 |
| **Audio Amplifier** | TAS2563 Class-D | 1 | $4 | $4 |
| **WiFi/BT Module** | Intel AX200 | 1 | $20 | $20 |
| **Battery** | 20,000mAh LiPo 7.4V | 1 | $100 | $100 |
| **BMS** | Battery management | 1 | $15 | $15 |
| **USB-C Port** | PD controller | 1 | $5 | $5 |
| **Power Regulator** | Buck converters | 1 | $10 | $10 |
| **Cooling** | Heatsink + fan (optional) | 1 | $15 | $15 |
| **Enclosure** | CNC aluminum + glass | 1 | $150 | $150 |
| **PCB** | Custom carrier board | 1 | $80 | $80 |
| **Assembly** | Labor + testing | 1 | $100 | $100 |
| **Lanyard** | Adjustable nylon | 1 | $5 | $5 |
| **Misc** | Cables, connectors, etc. | 1 | $30 | $30 |

### **Total Cost:**

**Without depth camera:** $1,222  
**With depth camera:** $1,371

### Production Scaling (50 units):

| Component | Unit Price (bulk) |
|-----------|-------------------|
| Jetson + Upgrade | $285 |
| Metis M.2 | $250 |
| Display | $45 |
| Cameras | $180 (with depth) |
| Audio | $35 |
| Battery + BMS | $90 |
| Enclosure | $100 |
| PCB | $50 |
| Other | $80 |
| **Total per unit** | **$1,115** |

**50 units total:** $55,750

---

## 🎯 Use Cases

### Personal AI Assistant:

**Features:**
- **Always-on voice assistant** (wake word detection)
- **Visual context awareness** (camera + depth sensing)
- **Real-time translation** (40+ languages)
- **Meeting transcription** (Whisper + LLM summarization)
- **Smart notifications** (context-aware filtering)

### Professional Applications:

**Healthcare:**
- **Patient monitoring** (vitals via camera)
- **Medical image analysis** (X-ray, CT scan review)
- **Clinical documentation** (voice-to-text notes)

**Field Service:**
- **Equipment inspection** (visual AI + AR overlay)
- **Remote expert assistance** (video call + annotations)
- **Hands-free documentation** (voice commands)

**Education:**
- **Language learning** (real-time translation + pronunciation)
- **Visual search** (point camera, get information)
- **Study assistant** (Q&A, summarization)

### Entertainment:

**Features:**
- **Music streaming** (Spotify, YouTube Music)
- **Podcast player** (with transcription)
- **Audiobook reader** (TTS with natural voices)
- **Gaming** (cloud gaming via WiFi)

---

## 🚀 Development Roadmap

### Phase 1: Prototype (Weeks 1-4)

**Objectives:**
- Order all components
- Design custom carrier board
- 3D print enclosure prototype
- Assemble first working unit

**Deliverables:**
- Functional prototype
- Basic software stack
- Power consumption validation

**Cost:** $2,500 (2 prototypes)

### Phase 2: Software Development (Weeks 5-8)

**Objectives:**
- Develop UI framework
- Integrate AI models
- Implement voice processing
- Camera and display drivers

**Deliverables:**
- Working AI assistant
- Voice commands
- Visual AI features
- Battery optimization

**Cost:** $0 (development time)

### Phase 3: Industrial Design (Weeks 9-12)

**Objectives:**
- Finalize enclosure design
- CNC aluminum prototype
- Thermal testing
- Ergonomics validation

**Deliverables:**
- Production-ready enclosure
- Thermal management solution
- User comfort validation

**Cost:** $1,500 (CNC prototypes)

### Phase 4: Pre-Production (Weeks 13-16)

**Objectives:**
- Order components in bulk (10-25 units)
- PCB fabrication and assembly
- Quality control procedures
- User testing

**Deliverables:**
- 10-25 beta units
- User feedback
- Refined software

**Cost:** $15,000 (25 units @ $600 each)

### Phase 5: Production (Weeks 17-24)

**Objectives:**
- Scale to 50-100 units
- Establish supply chain
- Manufacturing partnership
- Market launch

**Deliverables:**
- 50-100 production units
- Marketing materials
- Distribution channels

**Cost:** $55,750 (50 units) or $111,500 (100 units)

---

## 🎨 Color Variations

### Aluminum Frame Options:

1. **Midnight Black** (matte anodized)
2. **Space Gray** (brushed aluminum)
3. **Silver** (polished aluminum)
4. **Deep Blue** (anodized blue)
5. **Rose Gold** (anodized pink-gold)

### Lanyard Options:

1. **Professional Black** (nylon webbing)
2. **Premium Leather** (brown or black)
3. **Tech Gray** (reflective nylon)
4. **Vibrant Colors** (red, blue, green, orange)

---

## ✅ Key Advantages

### vs. Smartphones:

✅ **254 TOPS AI** (vs 10-20 TOPS in phones)  
✅ **Dedicated AI accelerator** (Metis NPU)  
✅ **16GB RAM** (vs 6-12GB in phones)  
✅ **Studio microphones** (vs basic phone mics)  
✅ **Depth camera** (advanced 3D sensing)  
✅ **Open platform** (full Linux, no restrictions)  

### vs. Smart Glasses:

✅ **Larger display** (3.4" vs tiny projectors)  
✅ **Better battery** (8-12 hours vs 2-4 hours)  
✅ **More compute** (254 TOPS vs <10 TOPS)  
✅ **Better audio** (stereo speakers vs bone conduction)  
✅ **Lower cost** ($1,200 vs $1,500-3,000)  

### vs. Tablets:

✅ **Wearable** (hands-free operation)  
✅ **Always accessible** (worn on lanyard)  
✅ **Better AI** (dedicated NPU)  
✅ **Voice-first** (optimized for conversation)  

---

## 🎯 Target Market

### Early Adopters:

**Tech Enthusiasts:**
- AI/ML developers
- Makers and tinkerers
- Gadget collectors

**Professionals:**
- Healthcare workers
- Field service technicians
- Educators and trainers
- Journalists and content creators

### Price Points:

**Developer Edition:** $1,371 (with depth camera)  
**Consumer Edition:** $1,222 (without depth camera)  
**Pro Edition:** $1,500 (with cellular + premium materials)

### Market Size:

**Target:** 1,000 units in Year 1  
**Revenue:** $1.2M - $1.5M  
**Profit Margin:** 30-40% (after scaling)

---

## 📋 Next Steps

### Immediate Actions:

1. **Order 2x Jetson Orin Nano Super Dev Kit** ($998)
   - For rapid prototyping
   - No memory upgrade delay

2. **Order 2x Axelera Metis M.2** ($518)
   - Validate AI performance
   - Test power consumption

3. **Order display, cameras, audio components** ($400)
   - Build functional prototype
   - Test user experience

4. **Design custom carrier board** (Week 1-2)
   - Integrate all components
   - Optimize for size and power

5. **3D print enclosure** (Week 2-3)
   - Test ergonomics
   - Validate thermal design

**Total initial investment:** ~$2,000 for 2 prototypes

### Production Planning:

1. **Validate prototype** (Weeks 4-8)
2. **Refine design** (Weeks 9-12)
3. **Order 25 units** (Weeks 13-16) - $28,000
4. **Scale to 50 units** (Weeks 17-24) - $56,000

---

## 🎯 Conclusion

**This lanyard-worn AI device represents the perfect balance of:**

✅ **Massive AI compute** (254 TOPS)  
✅ **Beautiful display** (3.4" AMOLED)  
✅ **Premium audio** (studio mics + speakers)  
✅ **All-day battery** (8-12 hours)  
✅ **Wearable form factor** (12 oz, 3.5" x 5")  
✅ **Affordable cost** ($1,222-1,371)  

**It's a smartphone-sized AI supercomputer you wear around your neck!**

**Ready to build the future of wearable AI?**
