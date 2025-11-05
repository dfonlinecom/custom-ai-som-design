# Flip-Down Projection Panel Design

**Date:** November 4, 2025  
**Feature:** A flip-down panel that covers the AMOLED screen and serves as a dedicated projection surface for the laser projector.  
**Target Model:** Entry Level Plus Plus (and a new "Pro" model)

---

## 🎯 Design Concept

A spring-loaded panel, seamlessly integrated into the device's chassis, that flips down with the press of a button. This provides a perfect, always-available screen for the laser projector, enhancing usability and creating a "wow" factor.

### **Mechanism:**

```mermaid
graph TD
    A[Closed Position] -->|Push Button| B(Panel Flips Down);
    B --> C{Open Position @ 110°};
    C -->|Laser Projector ON| D[Projects onto Panel];
    D -->|User Interaction| D;
    C -->|Push Panel Up| E(Clicks Shut);
    E --> A;

    subgraph Device
        direction LR
        subgraph Case
            direction TB
            Screen(3.4" AMOLED Screen);
            Panel(Flip-Down Panel) -- covers --> Screen;
            Hinge(Spring Hinge) -- attaches --> Panel;
            Laser(Laser Projector) -- projects to --> Panel;
        end
    end
```

1.  **Closed:** The panel sits flush, protecting the AMOLED screen. It's held in place by a magnetic latch.
2.  **Activation:** A small, tactile button on the side of the device releases the latch.
3.  **Deployment:** A custom spring-loaded hinge smoothly swings the panel down to a pre-set angle of 110 degrees, optimal for viewing when worn on a lanyard.
4.  **Projection:** The laser projector automatically turns on and projects a 4-inch diagonal image onto the panel.
5.  **Stowing:** The user simply pushes the panel up until it clicks back into its magnetic housing.

---

## 📐 Specifications

### **Panel:**
-   **Projection Surface:** 4.0-inch diagonal (3.5" x 2.0")
-   **Material:** Rigid, lightweight polymer substrate.
-   **Coating:** Screen Goo "Digital Grey Lite" formula for high contrast and brightness with low-lumen pico projectors.
-   **Backing:** Microfiber cloth to clean and protect the AMOLED screen when closed.

### **Hinge & Latch:**
-   **Hinge:** Custom-designed, miniature spring-loaded friction hinge. Provides smooth motion and holds the panel securely at the desired angle.
-   **Latch:** Neodymium magnetic latch for a secure, satisfying click closure.

### **Case Integration:**
-   **Overall Thickness:** The device thickness will increase from 1.25" to **1.4 inches** (35.5mm) to accommodate the panel and mechanism.
-   **Bezel:** A minimal bezel around the screen will house the hinge and latch mechanism, keeping the design sleek.

---

## 💰 Cost Analysis

This feature will be exclusive to the highest tiers, justifying the added cost and complexity.

| Component | Cost @ 100 units | Notes |
|---|---|---|
| Custom Spring Hinge | $8.50 | Miniature, durable, smooth action |
| Projection Panel (Substrate + Coating) | $12.00 | High-gain material is crucial |
| Magnetic Latch Mechanism | $2.50 | Neodymium magnets + housing |
| Microfiber Backing | $1.50 | Protects the main display |
| Additional Assembly Labor | $5.50 | Requires precise alignment |
| **TOTAL ADDITIONAL COST** | **$30.00** | **Wholesale cost increase per unit** |

---

## 💡 Product Tier Integration

This feature creates a new top-tier product, further segmenting the market and providing a clear upgrade path.

### **New "Pro" Tier:**

-   **Device:** Jetson Orin Nano 16GB + **Flip-Down Panel** (No Metis, No Laser)
-   **Purpose:** A premium version of the "Entry Level" model with a focus on display protection and a unique mechanical feature.

### **Renamed "Ultimate" Tier (was "Plus Plus"):**

-   **Device:** Jetson + Metis + Laser Projector + **Flip-Down Panel**
-   **Purpose:** The absolute best-of-the-best, combining maximum AI power with the futuristic projection system.

This creates a clear distinction: The flip-down panel is the hallmark of the premium models.
