# Qwerky BOM

This is the working bill of materials for one full split keyboard, based on the
current Ergogen/KiCad files. Supplier links are intentionally left blank until
the BOM is confirmed and sourcing starts.

## Already Acquired

| Item | Quantity | Status | Notes |
| --- | ---: | --- | --- |
| nice!nano MCU | 2 | Acquired | One per half. |
| nice!view display | 2 | Acquired | One per half. |
| Key switches | 48 | Acquired | Board has 24 switch positions per half. |
| Keycaps | 48 | Acquired | Board has 24 key positions per half. |
| Batteries | 2 | Acquired | One per half. |
| Large battery option | 2 | Acquired / candidate | 3.7V 750mAh 403450 rechargeable lithium battery. |
| Small battery option | 2 | Acquired / candidate | 3.7V 110mAh 301230 rechargeable lithium battery. |
| Male-to-male header pins | As supplied | Acquired | Came with the nice!nanos/nice!views, but the current plan is to use female headers on the PCB for socketing. |

## To Source

| Item | Quantity | Footprint / size | Status | Notes | Supplier link |
| --- | ---: | --- | --- | --- | --- |
| SMD switching diode | 48 | SOD-123 | Need to source | Footprint is `ceoloide:diode_tht_sod123`; intended for `1N4148W`-style diodes. Buy extras. | TBD |
| Choc hot-swap socket | 48 | Kailh Choc PG1350/PG1353 compatible | Need to source | Footprint is `ceoloide:switch_choc_v1_v2`; configured for Choc v1/v2 hot-swap. | TBD |
| Power slide switch | 2 | SMD side-actuated | Need to source | Footprint comments name Alps `SSSS811101`; also expected to be compatible with `PCM12SMTR`-style parts. | TBD |
| Reset button | 2 | SMD side-actuated momentary | Need to source | Footprint comments name Panasonic `EVQ-PUC02K` family. | TBD |
| Battery connector | 2 | JST PH 2.0mm, 2-pin, through-hole | Need to source | Footprint is `ceoloide:battery_connector_jst_ph_2`; intended for `S2B-PH-K` style connector. | TBD |
| Battery positive PTC fuse | 2 | 0603 imperial / 1608 metric | Need to source | Fits the modified battery connector jumper pads. Target one resettable PTC suitable for both battery options: about 150mA hold / 300mA trip, voltage rating >= 6V, low resistance. This leaves margin above the nice!nano default 100mA charge current while staying low enough to react to battery/board faults. | TBD |
| Battery ground jumper / 0 ohm resistor | 2 | 0603 imperial / 1608 metric | Need to source | Fits the modified battery connector jumper pads. | TBD |
| Standard female socket header for nice!nano | 4 x 12-pin rows | 2.54mm pitch | Need to source | Two 12-pin female rows per MCU, four rows total for the split. Use standard-height headers so the smaller 301230 battery can fit under the MCU. | TBD |
| Standard female socket header for nice!view | 2 x 5-pin rows | 2.54mm pitch | Need to source | One 5-pin female row per display. Match the standard header style used for the nice!nano. | TBD |
| M2 case screws | 10+ | M2 | Need to source | PCB has five 2.2mm plated mounting holes per half. Final screw length depends on the 3D printed case stack height. | TBD |
| M2 heat-set inserts | 10+ | M2, for 3D printed plastic | Need to source | One insert per PCB mounting point, plus extras for installation loss/testing. Exact outer diameter and length should be chosen during case design. | TBD |
| Low-profile tripod threaded insert | 2 | 1/4-20 UNC | Need to source | Standard camera tripod thread is 1/4-20 UNC. Use one low-profile heat-set or embedded threaded insert on the back of each half to minimize case thickness. | TBD |

## PCB-Derived Counts

| Footprint | Per half | Full split |
| --- | ---: | ---: |
| `ceoloide:switch_choc_v1_v2` | 24 | 48 |
| `ceoloide:diode_tht_sod123` | 24 | 48 |
| `ceoloide:mcu_nice_nano` | 1 | 2 |
| `ceoloide:display_nice_view` | 1 | 2 |
| `ceoloide:battery_connector_jst_ph_2` | 1 | 2 |
| `ceoloide:power_switch_smd_side` | 1 | 2 |
| `ceoloide:reset_switch_smd_side` | 1 | 2 |
| `ceoloide:mounting_hole_plated` | 5 | 10 |

## Open Decisions Before Sourcing

- Final M2 screw length and heat-set insert dimensions, to be chosen after the 3D printed case geometry is drafted.

## Header Notes

- Use standard 2.54mm female headers for MCU and display socketing.
- Standard headers are preferred over machine-pin sockets to leave room for the smaller 301230 battery under the MCU and to work with common square header pins.
- Confirm installed header height against the 301230 battery thickness during case design.

## Case Hardware Notes

- The planned case is 3D printed and should use M2 hardware.
- The PCB has five 2.2mm plated mounting holes per half, so the full split needs ten M2 mounting points.
- Add M2 heat-set inserts for the printed case.
- Add a low-profile 1/4-20 UNC threaded insert or heat-set insert for a standard tripod mount on the back of each half.

## Fuse Notes

- Fuse type is resettable PTC/polyfuse.
- Battery options are 3.7V 750mAh 403450 and 3.7V 110mAh 301230 lithium cells.
- The nice!nano default charge current is 100mA. The boost solder jumper changes charging to about 500mA and is only recommended for batteries above 500mAh; do not enable boost for the 110mAh battery option.
- The limiting case is the 110mAh cell. A 150mA hold / 300mA trip PTC is the first target because it should tolerate the default 100mA charger without nuisance trips while still reacting to battery/board faults.
- Do not use a 100mA hold PTC here unless testing shows it does not nuisance trip during charging; its hold current is too close to the nice!nano default charge current.
