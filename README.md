# web-serial-projection-interface
Built a browser-based control system that synchronizes 3D projection mapping with physical hardware.
This project uses projection mapping to create a "forced perspective" illusion of a robotic arm emerging from a wall to turn on a light. The system synchronizes this digital animation with physical hardware using the Web Serial API, allowing the holographic hand to "physically" turn on a real-world LED light at the exact moment of contact.

⚡ Features
Web-to-Hardware Bridge: Direct communication between a web browser and Arduino using Web Serial (no local server required).

Projection Mapping: Built with Maptastic.js to warp the video output onto any physical surface (doorframe, box, wall).

State Machine Logic: Custom JavaScript handling for precise timing (Idle -> Running -> Trigger LED -> Reset).

Forced Perspective: Uses high-contrast, black-background video loops to create a naked-eye 3D hologram effect.

🛠️ Hardware Requirements
Microcontroller: Arduino Nano (or compatible like DFRduino), Uno, or ESP32.

Output: Projector (connected to computer via HDMI).

Circuit:

1x LED (connected to Pin 2).

1x 220Ω Resistor.

Breadboard & Jumper wires.

Computer: Laptop/PC running Google Chrome or MS Edge (required for Web Serial API support).

🚀 Installation & Setup
1. Hardware Setup
Circuit: Connect the LED Long Leg (+) to Digital Pin 2 and the Short Leg (-) to GND.

Projector: Connect your projector to the computer.

Tip: Go to your Display Settings and ensure the projector is set to "Extend Display" (not Mirror). This allows you to have the code on your laptop and the projection on the wall.

2. Arduino Setup
Open Arduino IDE.

Open the Arduino/Listener.ino file (or copy the code from the main sketch).

Select your Board (Arduino Nano) and Port.

Troubleshooting: If using a generic Nano, select Processor: ATmega328P (Old Bootloader).

Upload the code. The board is now listening for serial commands (1 for ON, 0 for OFF).

3. Running the Interface
Download this repository.

Ensure your video file (e.g., tunnel.mp4) is in the same folder as index.html.

Open index.html in Chrome or Edge.

Drag the window to your Projector screen and press F11 for Fullscreen.

🔮 Future Improvements / Roadmap
We are planning to expand this project beyond a single surface. Here are some ideas for version 2.0:

📦 Multi-Face Mapping (3D Objects): Currently, we project onto a single flat surface (2D). The next step is to map onto a cube or corner. By adding more \<div> elements in the HTML and initializing Maptastic with multiple IDs (e.g., Maptastic("face1", "face2")), we can project different perspectives of the "engine room" onto different sides of a physical box for a true 3D effect.

🖐️ Sensor/OpenCV Integration: Instead of pressing Space to start, we can add an Ultrasonic Sensor or IR Motion Sensor to the Arduino. The projection would automatically "wake up" and open the portal when a person walks past it. If the projector is upgraded, OpenCV could be integrated to detect when an individual walks into the room or area and activate the projection. 

🔊 Sound Design: Adding spatial audio effects (heavy mechanical sounds, steam hisses) that sync with the video using JavaScript's Audio object.

🕸️ IoT Integration: Replacing the LED with a Relay Module to control high-voltage appliances (like a desk fan or room lamp) for a stronger physical impact.

🤝 Credits
Projection Library: MaptasticJS by Glowbox.
Inspiration: ZakShineman
Video Assets: Generated via AI / Stock footage.

Created by Abdulhamid Daghistani - 2025
