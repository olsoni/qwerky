# Qwerky Assembly Guide

This guide is for one full split keyboard. Repeat the PCB assembly steps for
both halves.

The current PCB has the controller, display, reset switch, and power switch on
the front side. The JST battery connector can be assembled on either side,
depending on the battery and case layout, and its 0603 fuse/ground jumper parts
should go on the opposite side from the connector. The Choc hot-swap sockets
are on the back side. The diode footprints have SOD-123 pads and orientation
silkscreen on both sides; for this build, install the diodes on the back side
with the hot-swap sockets so the keycap/switch side stays clear. Build from
lowest profile to tallest, and test after each major stage so mistakes are
still easy to reach.

## Before Soldering

- Keep the battery unplugged until the very end.
- Do not install switches or keycaps until all electrical tests pass.
- Confirm diode orientation before soldering. The stripe on each diode is the
  cathode; align it with the diode stripe/bar marking on the PCB footprint.
- Confirm the battery connector polarity against the PCB `+` and `-` markings
  before plugging in a battery.
- If using the 110 mAh battery option, do not bridge the nice!nano charge boost
  jumper. The default charge current is the safer choice for that cell.
- Use flux, a clean tip, and enough heat for quick joints. For SMD parts, tack
  one pad first, align the part, then solder the remaining pads.

Recommended tools:

- Fine-tip temperature-controlled iron
- Leaded solder or thin lead-free solder
- Flux pen or paste flux
- Tweezers
- Solder wick
- Multimeter with continuity mode
- Kapton tape or low-tack tape for holding sockets/connectors

## Assembly Order

### 1. Battery connector side and opposite-side jumpers

Choose the JST battery connector side before soldering this area. The connector
may go on the front or back depending on whether the final build uses the large
or small battery and how the case routes the battery lead.

Install the 0603 jumper parts on the opposite side of the PCB from the JST
connector. Do these before soldering the connector, because the connector body
can make the nearby pads harder to reach.

- Solder one 0603 PTC fuse on the positive battery jumper pads.
- Solder one 0603 0 ohm resistor on the ground battery jumper pads.

Tips:

- The PTC fuse is not polarized.
- The 0 ohm resistor is not polarized.
- If the JST connector will be on the front, solder the fuse and 0 ohm resistor
  on the back. If the JST connector will be on the back, solder the fuse and
  0 ohm resistor on the front.
- After soldering, check continuity from the JST positive pin pad to `BAT_P`
  through the fuse, and from the JST ground pin pad to `GND` through the
  resistor.
- Check that `BAT_P` and `GND` are not shorted.

### 2. Back-side diodes

Install the SOD-123 diodes: 24 per half, 48 total for the full split.

Tips:

- Orientation matters. Align the diode stripe with the diode stripe/bar on the
  same side of the PCB where you are soldering.
- Install the diodes on the back side unless your case design requires the
  back side to be completely flat. The pads exist on both sides, but front-side
  diodes can sit on the same side as the switches and keycaps.
- Solder one pad, slide the diode into alignment while reheating that pad, then
  solder the other pad.
- Reflow the first pad after the second pad is done so both ends sit flat.
- Inspect for tombstoning, cold joints, and solder bridges.
- After each half, use continuity mode or a diode-test mode spot check several
  matrix positions before continuing.

### 3. Front-side reset button and power switch

Install the reset button and power slide switch next.

Tips:

- These side-actuated switches need to sit flat and square. Tack one mechanical
  pad first, align the actuator with the board edge/cutout direction, then
  solder the rest.
- For the power switch, add enough solder to the anchor pads for mechanical
  strength, but avoid flooding the signal pins.
- Verify the power switch with a multimeter: in the ON position, `BAT_P` should
  connect to `RAW`; in the OFF position, it should not.
- Verify the reset switch momentarily connects `RST` to `GND` when pressed.

### 4. JST battery connector

Install the right-angle JST PH battery connector on the side selected in step 1,
after the opposite-side battery jumper parts are done.

Tips:

- Match the connector side to the battery and case plan before soldering. It is
  much easier to change now than after the connector is installed.
- Seat the connector flush before soldering both through-hole pins.
- Solder one pin first, reheat it while pressing the connector square, then
  solder the second pin.
- Do not plug the battery in yet.
- After soldering, verify connector polarity one more time. Battery connector
  polarity mistakes can destroy the controller or battery.

### 5. Back-side Choc hot-swap sockets

Flip the PCB over and install the Kailh Choc hot-swap sockets: 24 per half,
48 total for the full split.

Tips:

- The hot-swap sockets go on the back side of the PCB.
- Install these after the back-side diodes so the larger sockets do not block
  access to diode pads.
- Make sure every socket is fully seated and matches the footprint outline.
- Tack one pad first, confirm the socket is flat, then solder the other pad.
- Use enough solder to wet both the socket tab and PCB pad. These joints take
  mechanical force when switches are inserted.
- Do not overheat a socket. If the plastic starts to soften, stop and let it
  cool.
- After this step, insert a few switches temporarily to confirm the socket
  orientation and fit, then remove them again until final assembly.

### 6. nice!nano PCB sockets

Install the female machine sockets for the nice!nano on the PCB. Do not solder
the nice!nano directly to the PCB.

Tips:

- Use the Typeractive EZ-Solder machine sockets/headers if available.
- Keep both socket rows parallel and vertical. The nice!nano should plug in
  without forcing the pins inward or outward.
- A good alignment method is to plug the male headers into the female sockets,
  place the assembly through the PCB, tape or fixture it square, then solder the
  PCB-side sockets. Remove the nice!nano/module before applying unnecessary heat
  if your header system allows it.
- Solder only one pin on each socket row first, check alignment, then finish the
  rest.
- Inspect for bridges between adjacent header pins.

### 7. nice!view socket

Install the 5-pin socket for the nice!view after the nice!nano socket rows are
straight and verified.

Tips:

- The nice!view footprint overlaps the nice!nano in XY, so the display sits
  above the controller.
- Keep the 5-pin socket vertical. A tilted socket can make the display collide
  with the controller stack or case.
- If using Typeractive 5 mm sockets, the display should sit around 7 mm above
  the PCB after its pins are installed.
- Do not install the display permanently until the controller and keyboard
  matrix have been tested.

### 8. Headers on the nice!nanos and nice!views

Prepare the socketed modules off the PCB.

Tips:

- Solder the matching male headers to each nice!nano, keeping the controller
  square to the headers.
- Solder pins/headers to each nice!view so they match the PCB socket orientation.
- Use the PCB sockets as an alignment jig only if you can avoid heating the
  already-installed PCB sockets excessively.
- Clean flux residue before plugging modules into sockets.

### 9. Electrical checks before installing modules

Before plugging in the nice!nanos or displays:

- Check there is no short between `VCC` and `GND`.
- Check there is no short between `RAW` and `GND`.
- Check there is no short between `BAT_P` and `GND`.
- Check battery connector polarity at the JST pins.
- Check the power switch opens/closes `BAT_P` to `RAW`.
- Check reset connects `RST` to `GND` only while pressed.
- Check several diode orientations with diode-test mode.

Fix any issue before installing the expensive modules.

### 10. Install and test the nice!nanos

Plug in the nice!nanos without the battery connected.

Tips:

- Power each half from USB first.
- Confirm the board enumerates and can be flashed.
- Test reset from the reset button.
- Use tweezers or a switch to short individual key positions and confirm the
  matrix works before installing all switches.
- If a row or column is dead, stop and inspect the relevant header pins and
  diode orientation before continuing.

### 11. Install and test the nice!views

Plug in the nice!views after the controller works over USB.

Tips:

- Confirm the display socket orientation before insertion.
- Do not force the display pins. If it does not seat cleanly, remove it and
  inspect pin alignment.
- Power from USB and confirm the display initializes before using battery power.

### 12. Battery and final mechanical assembly

Only connect the battery after USB-powered testing passes.

Tips:

- Confirm the battery plug polarity matches the JST connector and PCB marking.
- Turn the power switch OFF before plugging in the battery.
- Plug in the battery, turn the switch ON, and confirm the controller powers up.
- Install the PCB in the case with M2 hardware after electrical testing.
- If using the small 301230 battery under the nice!nano, check physical
  clearance before closing the case.
- If using the larger 403450 battery, make sure the case provides a supported
  pocket and no pressure points on the cell.
- Install switches by supporting the hot-swap sockets from behind when possible.
  Press straight down so the switch pins enter the sockets instead of bending.
- Install keycaps last.

## Troubleshooting Notes

- One key does not work: inspect that key's diode orientation and both hot-swap
  socket joints.
- A full row or column does not work: inspect the relevant nice!nano socket pin,
  then check for a solder bridge or open joint.
- Board works over USB but not battery: check JST polarity, the PTC fuse, the
  0 ohm ground jumper, and the power switch.
- Display does not work: check the nice!view socket orientation, pin alignment,
  and the `VCC`, `GND`, `SCK`, `MOSI`, and `CS` connections.
- Reset does not work: check that the reset button shorts `RST` to `GND` only
  while pressed.
