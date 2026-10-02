# 🎙️ voice-activated-room-light

> A hardware-based voice activation pipeline to control room lighting via custom wake-word detection.

![Project Demo Placeholder](images/demo.gif)

---

Highlights

* **Wake-Word Detection:** Activated by the "Hey Jarvis" command.
* **Custom Hardware Stack:** Built using a microchip and modular microphone routing.
* **Ambient Integration:** Designed to integrate into a modern desktop environment to control local illumination.
* **3D-Printed Enclosure:** Form-fitted, custom CAD-designed housing to cleanly conceal the prototyping board and mic.

---

## ℹ️ Overview

**voice-activated-room-light** is a physical, voice-activated assistant designed to bridge the gap between custom hardware prototyping and everyday smart-home utility. Instead of relying on privacy-invasive commercial smart speakers, this project utilizes a dedicated hardware pipeline to process voice commands locally and trigger immediate spatial reactions—like killing the lights at your desk with a single phrase.

The project was co-developed as a summer engineering sprint, focusing on efficient hardware wiring, custom enclosure fabrication, and software trigger calibration.

### 🛠️ The Hardware Stack
As seen in the initial prototype layout below, the system utilizes a dedicated microphone breakout board wired directly into a central microcontroller unit, all mounted on a custom prototyping board.

![Hardware Prototype Layout](images/hardware-prototype.png)
*(This will show your prototype board image once uploaded!)*

---

## 🚀 How It Works

1.  **Acoustic Input:** The high-sensitivity microphone module continuously samples environmental audio.
2.  **Wake-Word Match:** The onboard processing pipeline listens specifically for the localized audio signature of *"Hey Jarvis"*.
3.  **Action Trigger:** Upon validation, a signal is dispatched to toggle the target electrical circuit (e.g., desk lighting).

---

## 📐 Mechanical Design (CAD)

To transform this from an open-board prototype into a clean desktop accessory, a custom-molded enclosure was designed to house the components safely and optimize microphone positioning.

![CAD Assembly Model](images/cad-enclosure.png)
*(Placeholder for your CAD screenshots!)*

---

## 💻 Technical Implementation

The core logic handles continuous audio stream monitoring and executes the corresponding callback functions when thresholds are crossed.

```cpp
// Example logic loop for trigger handling
if (wakeWordDetected && command == "turn the light off") {
    triggerLightRelay(LOW);
}
