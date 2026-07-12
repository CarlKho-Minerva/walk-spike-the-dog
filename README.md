# Walk Spike the Dog

A metabolic-gated focus architecture that intercepts your computer viewport when your blood glucose spikes, forcing you to walk a virtual dog to unlock your terminal.

Built in-person at **hahahack** (July 12, 2026) at **tiat**, San Francisco, with support from OpenAI.

---

## Causal Mechanism

1. **Ingestion:** The system parses continuous glucose telemetry from a subcutaneous Dexcom Stelo sensor.
2. **Lockout:** When a postprandial hyperglycemic spike is detected (e.g., >140 mg/dL or high rate-of-change velocity), a complete system lockout overlay triggers.
3. **Resolution:** To unlock the viewport, you must move. The system leverages the browser's native `devicemotion` API to measure step frequency.
4. **Physiology:** As you walk, skeletal muscle contraction activates GLUT4 translocation independently of insulin, accelerating systemic glucose clearance. The lockout only disengages when you complete the required pacing count, bringing your blood sugar and "Spike" (the dog) back to baseline.

---

## Technical Stack

- **Frontend:** Lightweight monochrome HTML5 overlay with CSS blend masks.
- **Sensing:** HTML5 Device Orientation & Motion API for real-time mobile step telemetry.
- **Assets:** Smooth preloaded 8-frame walk loop extracted from raw pixel tiles using CSS matrix inversion masks (`clip-path` and `mix-blend-mode`).

---

## Demo Instructions

1. Run a local web server or open `index.html` on your machine.
2. Click **Simulate Spike (184 mg/dL)** to trigger the lockout state.
3. Load the page on an iOS device over HTTPS, tap **Enable Motion Sensor**, and walk or shake the device to count steps. Alternatively, tap the **Spacebar** on your laptop keyboard to simulate steps.
4. Watch the step counter decline to zero to disengage the lockout overlay and restore visibility of the underlying research editorial.
