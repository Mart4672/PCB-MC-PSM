# PCB-MC-PSM
Modular/Configurable Power Supply Module (PSM) Board. This PCB works as a standalone PSM that also has high current connections for servos and mosfets.

## Modular/Configurable PSM Board "Version-A" Features
- Power Supply Module board that supports power, servos, and mosfets
    - all high current devices should be managed by this board
- Supports a battery input voltage range that covers 6 to 16.8V
    - This voltage range ensures that 2s to 4s LiPo batteries can be used
- Has a PMIC that outputs a regulated 5V and supports at least 5A continuous
- Has a high current diode rectifier to support a second power input
    - intended for a secondary battery or a power supply for keeping the main PSM battery from discharging
- Has terminal blocks for battery connections

TODO
- 5 Mosfet channels
    - 2 5V channels
    - 3 VBatt channels
    - continuity checking on all channels
        - optionally uses alternative continuity circuit (NFET instead of voltage divider) [1/15/2025]
    - current limiting resistors or fuses on all channels
        - uses a high wattage-rated resistor to limit the current to a level that the traces can handle
- 4 Servo connections
    - uses a screwless terminal block connection
        - ex: TE 1-2834015-4 Buchanan WireMate
    - uses inline PTC fuses for each servo
- Connectors for STEVE board signals
    - Uses screwless terminal block connectors or JST-GH connectors
    - Servo PWM signals (4)
    - Mosfet gate signals (5)
    - Mosfet continuity signals (5)
    - Battery Voltage sensing lines (1)

- import/assign missing 3D part models

## Future Updates

### Future PSM Board Updates
- create additional PSM boards with more/less features depending on desired capability
    - ex: a larger PSM board with a second PMIC to support more servos and mosfets
    - ex: a smaller PSM board with fewer supported servos/mosfets and/or a lower current rating
- use a PMOS mosfet for reverse polarity protection
- current draw sensing that can be reported to the main STEVE board
