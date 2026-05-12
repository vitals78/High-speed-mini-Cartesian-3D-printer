# High-speed-mini-Cartesian-3D-printer
High‑speed mini Cartesian 3D printer with a 120 mm carbon build plate.
![Printer](Images/011.jpg)

This project is best suited for people who have plenty of free time, a spare Flying Bear Ghost 5 printer, and access to a CNC milling machine for manufacturing frame parts, motor mounts, and printhead components.

The printer turned out to be quite successful — it is capable of fast, high-quality printing while also being convenient to use and maintain.

However, there are still some unresolved drawbacks. One of the main issues is the Z-axis dropping when the motors are disabled. This problem was partially mitigated by adding a magnetic spring that prevents the axis from falling to the lowest position and pressing against the Z endstop. My preferred long-term solution would be to use a geared motor for the Z-axis.

The printer currently uses a heated bed from the Voron 0 Heated Bed 100x100mm. Due to the very low thermal conductivity of carbon fiber, the bed effectively heats only a 100×100 mm area. Ideally, a 120×120 mm Polyimide Film Heater should be used instead, which would allow utilizing the full bed surface.

With the current Voron 0 heater setup:

120×120 mm printing area is suitable only for PLA
For ABS and PETG, the effective heated area is limited to 100×100 mm

Using a Polyimide Film Heater would also reduce bed weight and eliminate another weakness of the design — insufficient bed base rigidity. The bed base should ideally be made from 4–5 mm carbon fiber instead of 3 mm.

The printer has additional potential for higher print speeds. By using higher-quality components (instead of parts sourced from Flying Bear), the available Z-axis height provides enough clearance for a hotend with a larger melt zone. There is also enough room to install more powerful motors on the X and Y axes.

The CAD files include an alternative printhead design using a 5015 part-cooling fan. While this configuration is not ideal for maximum print speed, it makes the project somewhat more affordable.

All printed parts were manufactured using PCTG filament from various manufacturers. I chose this material because of its exceptional layer adhesion and very low shrinkage. Some printer components require extremely high dimensional accuracy, so filament shrinkage calibration and slicer compensation are strongly recommended.

A heat-resistant spacer should be installed between the X-axis motor and the "Guide rail and motor mounts" part, or alternatively this component should be printed from ABS or ASA.

Cooling for the BTT Manta M5P controller board is provided by a Foxconn PVB080G12H fan powered through a 5V DC-DC converter. If this fan is unavailable, the mounting system will need to be redesigned for an alternative fan model.

The printer uses an auto power-off system based on an Arduino relay module. Because of this, the power button must be held for approximately 10–15 seconds during startup until the relay receives a GPIO signal. If this behavior is undesirable, an alternative power control relay solution can be implemented.

The printer also uses a Klicky Probe PCB, which ultimately turned out to be unnecessary due to the small bed size and the absence of significant thermal bed deformation (assuming you were lucky enough to get a flat carbon fiber plate). In practice, the bed probing system can be omitted entirely.

In the printer.cfg configuration, the X and Y motor currents are tuned for fast Benchy printing. For normal operating conditions, it is recommended to reduce the current by 200 mA to lower motor heating. Additionally, change the microsteps from 16 to 32 — this will reduce noise and VFA at low printing speeds.
