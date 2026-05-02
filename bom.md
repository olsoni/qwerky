# Qwerky BOM

This is the working bill of materials for one full split keyboard, based on the
current Ergogen/KiCad files.

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
| SMD switching diode | 48 | SOD-123 | Need to source | Footprint is `ceoloide:diode_tht_sod123`; intended for `1N4148W`-style diodes. Buy extras, e.g. 60-100 total. | [DigiKey: SMC Diode Solutions `1N4148W`](https://www.digikey.com/en/products/detail/smc-diode-solutions/1N4148W/6022450) |
| Choc hot-swap socket | 48 | Kailh Choc PG1350/PG1353 compatible | Need to source | Footprint is `ceoloide:switch_choc_v1_v2`; configured for Choc v1/v2 hot-swap. Buy 50+ total. | [Typeractive: Kailh Hotswap Sockets, choose Choc](https://typeractive.xyz/products/hotswap-sockets); [Kailh manufacturer part `CPG135001S30`](https://www.kailhswitch.com/mechanical-keyboard-switches/box-switches/choc-type-hot-swap-socket.html) |
| Power slide switch | 2 | SMD side-actuated | Need to source | Alps Alpine `SSSS811101`, SPDT, right-angle SMD. Buy extras. | [DigiKey: `SSSS811101`](https://www.digikey.com/en/products/detail/alps-alpine/SSSS811101/19529062) |
| Reset button | 2 | SMD side-actuated momentary | Need to source | Panasonic `EVQ-PUC02K`, side-actuated SMD tactile switch. Buy extras. | [DigiKey: `EVQ-PUC02K`](https://www.digikey.com/en/products/detail/panasonic-electronic-components/EVQ-PUC02K/286336) |
| Battery connector | 2 | JST PH 2.0mm, 2-pin, through-hole | Need to source | JST `S2B-PH-K-S`, right-angle through-hole PH header. Buy extras. | [DigiKey: `S2B-PH-K-S`](https://www.digikey.com/en/products/detail/jst-sales-america-inc/S2B-PH-K-S/926626) |
| Battery positive PTC fuse | 2 | 0603 imperial / 1608 metric | Need to source | Fits the modified battery connector jumper pads. Best found part so far is Eaton `PTS06039V016`: 160mA hold, 400mA trip, 9V, 0603. This leaves margin above the nice!nano default 100mA charge current while staying low enough to react to battery/board faults. | [DigiKey: Eaton `PTS06039V016`](https://www.digikey.com/en/products/detail/eaton-electronics-division/PTS06039V016/15193468) |
| Battery ground jumper / 0 ohm resistor | 2 | 0603 imperial / 1608 metric | Need to source | Fits the modified battery connector jumper pads. Buy extras. | [DigiKey: Bourns `CR0603-J/-000ELF`](https://www.digikey.com/en/products/detail/bourns-inc/CR0603-J-000ELF/3593211) |
| EZ-Solder machine sockets and headers for nice!nano | 2 kits | 2.54mm pitch, 2 x 12-pin socket/header pairs per kit | Need to source | One kit per nice!nano. Solder the male headers to the nice!nano and the sockets to the PCB. Typeractive describes these as tall enough for 301230 batteries underneath while short enough for the nice!view to sit above. | [Typeractive: EZ-Solder Machine Sockets and Headers](https://typeractive.xyz/products/ez-machine-sockets-and-headers) |
| 5-pin sockets for nice!view | 2 sockets | 2.54mm pitch, 5mm socket height | Need to source | One socket per display. Typeractive states these are 5mm tall; with the nice!view's 2mm pins, the display sits at about 7mm, which is intended to fit snugly over a socketed nice!nano. | [Typeractive: 5-Pin Sockets](https://typeractive.xyz/products/5-pin-sockets) |
| M2 case screws | 10+ | M2 x 4mm and M2 x 5mm | Need to source | PCB has five 2.2mm plated mounting holes per half. Buy both 4mm and 5mm lengths until the printed stack height is final. Low-profile heads are preferred if available. | [McMaster: M2 socket head screws](https://www.mcmaster.com/products/socket-head-cap-screws/thread-size~m2/) |
| M2 heat-set inserts | 10+ | M2 x 0.4mm, 3.4-4.1mm installed length | Need to source | One insert per PCB mounting point, plus extras for installation loss/testing. Reasonable case-model target: 3.3mm max hole diameter, 5mm boss OD. | [McMaster: heat-set inserts, choose M2 x 0.4mm](https://www.mcmaster.com/products/heat-set-inserts) |
| Low-profile tripod threaded insert | 2 | 1/4-20 UNC | Need to source | Standard camera tripod thread is 1/4-20 UNC. Use one low-profile heat-set or embedded threaded insert on the back of each half. Reasonable case-model target: 0.300in installed length, 0.319in max hole diameter. | [McMaster: heat-set inserts, choose 1/4-20 x 0.300in](https://www.mcmaster.com/products/heat-set-inserts); [E-Z LOK flush insert option `240-4-BR`](https://www.ezlok.com/ezpress-insert-240-4-BR) |

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

## Open Decisions Before Ordering

- Final M2 screw length, to be chosen after the 3D printed case geometry is drafted. Buying both M2 x 4mm and M2 x 5mm is reasonable.
- Final tripod insert choice. The McMaster 1/4-20 x 0.300in heat-set insert is the lowest-profile target found so far; E-Z LOK press inserts are easier to source individually but are deeper.

## Header Notes

- The nice!view footprint overlaps the nice!nano footprint in XY, so the display must sit above the MCU.
- Use Typeractive EZ-Solder Machine Sockets and Headers for the nice!nanos instead of standard square-pin female headers. They are designed for this exact stack: a 301230 battery under a socketed nice!nano with a nice!view above.
- Use Typeractive 5-pin sockets for the nice!views. Typeractive states the socket is 5mm tall and the nice!view pin adds about 2mm, putting the nice!view at about 7mm.
- This should be lower than the previous 8.51mm standard-header plan while still preserving the intended nice!view-over-nice!nano clearance.
- Confirm installed socket/header height against the 301230 battery thickness during case design.

### Header Alternatives

| Option | Quantity | Estimated part cost | Notes | Supplier link |
| --- | ---: | ---: | --- | --- |
| Typeractive EZ-Solder nice!nano kits | 2 kits | About $18 total | Recommended for convenience. Includes captured male/female machine header pairs for two nice!nanos. | [Typeractive: EZ-Solder Machine Sockets and Headers](https://typeractive.xyz/products/ez-machine-sockets-and-headers) |
| DigiKey Mill-Max loose-pin nice!nano socketing | 4 socket strips + 50 pins | About $10.10 total | Cheaper, but uses loose pins instead of captured male headers. Use 4 x 12-position Mill-Max 310 socket strips plus 48 pins, or 50 pins to allow two spares. | [DigiKey: Mill-Max `310-47-112-41-001000`](https://www.digikey.com/en/products/detail/mill-max-manufacturing-corp/310-47-112-41-001000/7364039), [DigiKey: Mill-Max `3320-0-00-15-00-00-03-0`](https://www.digikey.com/en/products/detail/mill-max-manufacturing-corp/3320-0-00-15-00-00-03-0/4147392) |
| DigiKey captured machine-header style | 4 sockets + 4 headers | About $25.96 total | Not cheaper than Typeractive. Uses 4 x Mill-Max-compatible 12-position sockets and 4 x 12-position 335-series male headers. | [DigiKey: `315-43-112-41-003000`](https://www.digikey.com/en/products/detail/mill-max-manufacturing-corp/315-43-112-41-003000/4455232), [DigiKey: `335-40-112-00-160000`](https://www.digikey.com/en/products/detail/digikey-va/335-40-112-00-160000/4455913) |
| Typeractive nice!view 5-pin sockets | 2 sockets | $1 total | Recommended. DigiKey through-hole alternatives found so far are either taller, lower than the intended 7mm display height, surface-mount, or more expensive. | [Typeractive: 5-Pin Sockets](https://typeractive.xyz/products/5-pin-sockets) |

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
- Current sourced target is Eaton `PTS06039V016`: 160mA hold, 400mA trip, 9V, 0603.
