For motors and ESCs, there are no end of manufacturers - below I've chosen popular hobbyist level components that are readily available. That doesn't mean that these are necessarily the best but they're a good starting point.

### Flight controller

PX4 (the people who, among other things, develop the Pixhawk schematics) maintain a [list](https://docs.px4.io/v1.11/en/flight_controller/) of Pixhawk flight controllers.

At the time of writing, the standard supported Pixhawk flight controllers include:

| FMU version | Model |
| FMUv3 | [ProfiCNC Cube (purple with mini carrier board)](http://www.proficnc.com/all-products/180-the-cube.html) |
| FMUv3 | [CUAV Pixhack V3X](https://store.cuav.net/index.php?id_product=8&controller=product) |
| FMUv4-PRO | [Drotek Pixhawk 3 Pro](https://store-drotek.com/821-pixhawk-pro-autopilot.html) |
| FMUv5 | [Holybro Pixhawk 4](https://shop.holybro.com/pixhawk-4beta-launch_p1089.html) |
| FMUv5 | [Holybro Pixhawk 4 Mini](https://shop.holybro.com/pixhawk4-mini_p1120.html) |

I've just some of the major models that fall within the hobbyist price range, there are many more expensive variants and variants that aren't considered standard by PX4.

The [FMU version](https://docs.px4.io/v1.11/en/flight_controller/pixhawk_series.html#fmu_versions) is the version of the open schematic produced by PX4, with the various models being mostly proprietary implementations of these schematics from various manufacturers.

The original Pixhawk (now retroactively called the Pixhawk 1) was manufactured by a company called 3DR that has pivoted several times since and no longer produces flight controllers.

Until recently, you used to be able to buy Pixhawk 1 clones from numerous no name Chinese manufacturers. Now these are becoming rarer and rarer but there are still some available on sites like Banggood:

* [Pixhawk 1 - 2.4.6](https://www.banggood.com/New-Pixhawk-PX4-Autopilot-PIX-2_4_6-32Bits-ARM-Flight-Controller-p-971381.html?ID=224)
* [Pixhawk 1 - 2.4.8](https://www.banggood.com/Pixhawk-PX4-2_4_8-Flight-Controller-32-Bit-ARM-PX4FMU-PX4IO-Combo-for-Multicopters-p-1040416.html)

These really are clones of the original 3DR Pixhawk model with no information about who really manufactured them. Also the version number of the second is just made up - PX4 published various [revisions](https://github.com/pixhawk/Hardware/tree/master/FMUv2) of the FMUv2 schematics, the last of which was 2.4.6 - so what version 2.4.8 might be is anyones guess.

In addition to the clones, other manufacturers (in addition to 3DR) produced their own variants which are still available:

* [mRo Pixhawk 2.4.6](https://store.mrobotics.io/Genuine-PixHawk-Flight-Controller-p/mro-pixhawk1-minkit-mr.htm)
* [Holybro Pix32](https://shop.holybro.com/pix32quotpixhawkquot-flight-controller_p1020.html)

As you can see, version numbering in the Pixhawk world is completely erratic. The model numbers _tend_ to be one behind the schematic version, e.g. the Holybro Pixhawk 4 is based on the FMUv5 schematic. But this isn't consistent, e.g. Holybro refer to their Pix32 as a Pixhawk 2 model while all other producer of models based on the FMUv2 schematic called their models either Pixhawk 1 or just plain Pixhawk. Then schematic revisions add to the confusion, e.g. the 2.4.6 revision number seen above in the mRo Pixhawk model name. To add to the confusion some people use the name PX4 to refer to the flight controller - the Pixhawk is the flight controller hardware and you can choose to run either PX4 or ArduCopter on this hardware, there is no device called the PX4. This becomes even more confusing now that there is a Pixhawk 4 - some people refer to this as a PX4 but these people are just confused.

From a layout point of view the major distinguishing features between models are:

* The ports are either on top or at one end of the device.
* The three rows of pins which, among other things, control the ESCs are built in or external.

As far as I'm aware the Holybro Pixhawk 4 is the only model where these ESC related pins are external (technically this also applies to the cube designs from ProfiCNC and CUAV but they connect directly to a carrier board that has these pins).

For me, at the moment, the choice _for a hobbyist drone_ comes down to choosing between the Pixhawk 4 and the Pixhawk 4 Mini. Holybro is a well known name in this space and the Pixhawk 4 seems to be the most popular of the post Pixhawk 1 designs and has been picked up by a lot of distributors. The Pixhawk 4 Mini has a more traditional arrangement with the ESC pins being part of the device but I quite like the Pixhawk 4 design that allows these pins to be hidden away in the same place where one wires up the ESCs for power.

Final choice: [Holybro Pixhawk 4 & M8N GPS combo - Banggood.com](https://www.banggood.com/HolyBro-Pixhawk-4-Autopilot-Flight-Controller-M8N-GPS-Module-Combo-p-1302123.html?ID=534790)

### Flight controller damping

Damping platforms used to be considered essential, by many people, e.g.:

* [Banggood anti-vibration set](https://www.banggood.com/APM2_5-2_6-KK-MWC-Glass-Fiber-Shock-Absorber-Anti-vibration-Set-p-914546.html)
* [HobbyKing damping platform](https://hobbyking.com/en_us/apm-flight-controller-damping-platform.html) (discontinued).

But nowdays the flight controllers generally include some form of internal damping for the relevant components and they ship with simple damping foam that's usually considered enough. If you need to buy this kind of foam, there are no end of fairly random products (usually _claiming_ to be 3M based). ArduPilot suggest [mRo PixHawk damping foams](https://store.mrobotics.io/product-p/mro-pxfoams-mr.htm) (at $23, they're fairly expensive). For more see [here](https://ardupilot.org/copter/docs/common-vibration-damping.html).

### ESCs

Oddly, the processors used in modern ESCs are more powerful than those used in the first ArduPilot flight controllers. Currently, the most popular firmware for ESCs is BLHeli. This firmware used to be open source until they switched to ARM 32-bit MCUs. I had hoped a community would develop around the last open source BLHeli release and continue developing it but this hasn't happened. So instead one should just accept the closed source nature and find a suitable modern BLHeli_32 ESC.

Final choice: [Racerstar Tattoo 30A - Banggood](https://www.banggood.com/4-PCS-Racerstar-Tattoo-30A-BLheli_32-2-4S-Brushless-ESC-Dshot1200-for-Racing-Drone-p-1219847.html) (see **update** below).

See also the Racerstar [product page](https://www.racerstar.com/Racerstar-Tattoo-30A-BLheli_32-STM32F051-DShot1200-ESC-p-200.html) for these ESCs.

Alternatives: [HAKRC 35A - Banggood](https://www.banggood.com/4X-HAKRC-BLHeli_32-Bit-35A-2-5S-ESC-Built-in-LED-Support-Dshot1200-Multishot-for-FPV-RC-Drone-p-1280430.html) (these are also sold by GetFPV as their budget ESCs in the 30A range).

Questions:

* Is opto coupling relevant to connecting just signal to PM07? I don't think so.
* Do these ESCs support telemetry so that one can e.g. see current and information needed for [notch filters](https://ardupilot.org/copter/docs/common-imu-notch-filtering.html)?

**Update:** it seems, within the 30A range, Racerstar only has telemetry out on their [PG30 ESCs - Banggood](https://www.banggood.com/4X-Racerstar-PG30-BLHeli_32-30A-3-4S-Proshot-Ready-Brushless-ESC-for-RC-FPV-Racing-Drone-p-1279815.html) (the blue wire in the photos).

TODO: lookup how the telemetry cables are wired into the Pixhawk. To wire up a connector it's probably easiest to use an already wired JST-GH connector and tin the wires from the ESCs to those of the connector. Alternatively one could buy housings:

* [JST-GH housings - ApiExpress](https://www.aliexpress.com/item/4000492364443.html)
* [pre-crimped wires for JST-GH connectors - ApiExpress](https://www.aliexpress.com/item/4000585046133.html)

#### ArduPilot BLHeli setup

[ArduCopter - BLHeli_32 pass-through support](https://ardupilot.org/copter/docs/common-blheli32-passthru.html)

[icantfly - how to change brushless motor direction using BLHeli](https://icantfly.xyz/how-to-change-brushless-motor-direction-using-blheli/)

Note: according to one of the Banggood reviews, they couldn't set up the the Racerstar Tattoo 30A ESCs with pass-through. Googling finds lots of confused people using pre-BLHeli_32 configurators and the like, so it's hard to tell if this is an issue.

### 60a 4in1 ESCs

An interesting alternative to individual ESCs might be a 4in1. Most of these have fairly low amp limits but two that support 60A or more are:

* [HolyBro Tekko32F3 Metal 4in1 65A ESC - Banggood](https://www.banggood.com/Upgrade-30_5x30_5mm-Holybro-Tekko32F3-Metal-65A-BLheli_32-4-6S-4in1-ESC-DShot1200-w-or-F3-MCU-and-Current-Sensor-for-RC-Drone-FPV-Racing-p-1414818.html)
* [Racerstar Metal 60A 4in1 60A ESC - Banggood](https://www.banggood.com/Racerstar-Metal-60A-Blheli_32-3-8S-4-IN-1-Brushless-ESC-w-or-Current-sensor-DShot1200-CNC-IP65-Waterproof-24g-for-RC-Drone-p-1453469.html?ID=228)

While these are only around 60A and the combined ampage of four of the ESCs is about twice that, some of the DJI ESCs that they used to recommend for use with their F450 frame were around 15A each.

### Capacitors

This [GetFPV page](https://www.getfpv.com/learn/new-to-fpv/all-about-multirotor-fpv-drone-electronic-speed-controller/) notes that ESCs used to often come with capacitors but in the race to reduce size they've been removed even though the need for them still remains. My DJI 420 Lite ESCs use Rubycon 330&micro;F 25V - like [these](https://www.digikey.ch/products/en/capacitors/aluminum-electrolytic-capacitors/58?pv2049=u330%C2%B5F&pv2079=u25V&s=33170) from Digikey.

Oscar Liang explains why you want [capacitors for cleaning up noise](https://oscarliang.com/capacitors-mini-quad/). One can choose between cleaning up the noise with capacitors or preventing the noise getting to your FPV equipment with an LC filter. In general, Oscar (as he notes [here](https://oscarliang.com/connect-vtx-fpv-camera/)) and others seem to feel its better to clean up the noise, i.e. choose capacitors over LC filters.

**Note:** Oscar says you should cut the legs as short as possible (to minimize ESR issues) before soldering.

Given Oscar Liang's recommendations, the following would seem perfect:

* [Panasonic FM 470&micro;F 25V](https://www.reichelt.com/elko-radial-470-uf-25-v-105-c-low-esr-fm-a-470u-25a-p200052.html)
* [Panasonic FM 470&micro;F 35V](https://www.reichelt.com/elko-radial-470-uf-35-v-105-c-low-esr-fm-a-470u-35-p200054.html)
* [Panasonic FM 330&micro;F 25V](https://www.reichelt.com/elko-radial-330-uf-25-v-105-c-low-esr-fm-a-330u-25a-p200044.html)

These all have 5mm spacing (matching Oscar's recommendations). You can also get narrower but longer variants with 3.5mm spacing that are slightly cheaper (but have slightly different characteristics, e.g. compare ripple currents).

Note: 25V should be enough for 4S batteries (as noted by Oscar Liang, you'd move up to 35V for 5S and 6S batteries, although he later qualifies this by saying things can spike up above 25V for 4S batteries).

If you put capacitors across the ESCs power terminals then cover the entire ESC with heat shrink as you can't just heat shrink the terminals.

**TODO:** is there any guide to what size capacitors one should use for a given ampage ESC? I don't have an answer but my impression is that 1000&micro;F are _huge_ and only necessary if you're planning to just use one capacitor (soldered across the battery connector), 470&micro;F should be more than enough (in this [video](https://youtu.be/oDFclImvl6M) they're used with 35A ESCs, not that that's definitive) and 330&micro;F seem to be enough for most racing setups even for larger 7" vehicles, i.e. 300mm wheelbase.

### Motors

6mm screws:

* [4 x Racerstar BR2212 980KV - Banggood](https://www.banggood.com/4X-Racerstar-Racing-Edition-2212-BR2212-980KV-2-4S-Brushless-Motor-For-350-380-400-Frame-Kit-p-1083199.html)
* [4 x Racerstar BR2312 960KV - Banggood](https://www.banggood.com/4X-Racerstar-Racing-Edition-2312-BR2312-960KV-2-4S-Brushless-Motor-For-350-380-400-Frame-Kit-p-1083204.html)
* [4 x Racerstar BR2212 920KV - Banggood](https://www.banggood.com/4X-Racerstar-Racing-Edition-2212-BR2212-920KV-2-4S-Brushless-Motor-For-350-380-400-Frame-Kit-p-1083198.html)
* [4 x Racerstar BR2216 810KV- Banggood](https://www.banggood.com/4X-Racerstar-Racing-Edition-2216-BR2216-810KV-2-4S-Brushless-Motor-For-350-380-400-450-Frame-Kit-p-1083207.html)
* [Emax MT2216 810KV (plus 6mm adapter and propeller) - Banggood](https://www.banggood.com/EMAX-MT-2216-KV810-Brushless-Motor-With-1045-Propeller-for-RC-Drone-FPV-Racing-p-925679.html?ID=521309)
* [DYS BX2212 920KV - Banggood](https://www.banggood.com/1-PCS-DYS-BX2212-920KV-Brushless-Motor-CWCCW-For-RC-Drone-FPV-Racing-Drone-Airplane-Aircraft-p-936355.html)
* [B2212 920KV for DJI Phantom - Banggood](https://www.banggood.com/B2212-920KV-CWCCW-Brushless-Motor-For-DJI-Phantom-1-Phantom-2-Phantom-3-p-1166424.html?ID=49005) (do not appear to be DJI original parts)
* [Holybro 2216 880KV](https://shop.holybro.com/motor2216-880kv-1pc_p1154.html)
* [SunnySky X2212 980KV](https://sunnyskyusa.com/collections/other-multirotor-motors/products/sunnysky-x2212-brushless-motors-new)
* [Lumenier FM2216 900KV - GetFPV](https://www.getfpv.com/fm2216-11-900kv.html)

The Holybro motor looks like it might be a rebranded SunnySky X2216 880KV (right KV value) or the SunnySky X2212 980KV (right screw size).

Note: the numbers like 2212, 2216 and 2312 refer to stator diameter and height, e.g. 2212 means 22mm in diameter and 12mm high.

SunnySky has an [offical store](https://edge-china.en.alibaba.com/) on Alibaba.

Motors provided in popular F450-style kits:

* The DJI E305 motors were 800KV 2312.
* The Hexsoon EDU450 motors are 2216 880KV.
* The Holybro S500 motors are 2216 880KV.

Final choice: Racerstar BR2216 810KV or BR2212 920KV with [Realacc motor grip pliers - Banggood](https://www.banggood.com/Realacc-Motor-Grip-Pliers-For-RC-Models-p-1053444.html)

For a less budget motor, I'd buy the SunnySky X2216 880KV motors with 6mm adapters (see below).

---

Motors with prop adapters:

* [SunnySky V2216 800 and 900KV models](https://sunnyskyusa.com/collections/other-multirotor-motors/products/sunnysky-v2216-motors?variant=15989441691742)
* [SunnySky X2216 880KV](https://sunnyskyusa.com/products/sunnysky-x2216-brushless-motors)
* [SunnySky X2212 980KV](https://sunnyskyusa.com/products/sunnysky-x2212-brushless-motors?variant=44592207951)
* [SunnySky X2212 980KV - Banggood](https://www.banggood.com/4-X-SunnySky-X2212-KV980-Brushless-Motor-p-954481.html)
* [Lumenier FX2216 900KV - GetFPV](https://www.getfpv.com/fx2216-11-900kv-v2.html)

For these kind of motors you need a 6mm prop adapter with 3 screw holes (there are variants for 4 screw holes for other types of motors):

* [Team BlackSheep 6mm adapters](https://www.team-blacksheep.com/products/prod:stpa_ccw)
* [small parts CNC - SunnySky X22 6mm adapter](http://smallpartscnc.com/index.php?route=product/product&product_id=191)

GetFPV also sell various M6 adapters - see [here](https://www.getfpv.com/catalogsearch/result/index/?dir=asc&order=price&q=m6+adapter) (and look at the models shown with 3 bolts rather than 4).

Various AliExpress stores also sell considerably cheaper X22 adapters:

* [CyberModel - SunnySky X22 6mm adapter](https://www.aliexpress.com/item/10000356078885.html)
* [XDRC - SunnySky X22 6mm adapter](https://www.aliexpress.com/item/33010374401.html)
* [Flying Your Dream - SunnySky X22 6mm adapter](https://www.aliexpress.com/item/32779379043.html)

ThanksBuyer also sell [adapter pairs](https://www.thanksbuyer.com/3-12-self-locking-quick-release-cnc-aluminum-propeller-base-cw-ccw-1pair-for-9443-9450-propeller-40632) (you'd need two pairs).

### Propellers

Various people produce suitable self-tightening propellers:

* [DJI 9450 CW & CCW pair - Banggood](https://www.banggood.com/9450-Plastic-Self-tightening-Propeller-1CWand1CCW-For-DJI-Phantom-3-UPair-Chase-p-990157.html)
* [SunnySky 9045 propellers CW & CCW pair](https://sunnyskyusa.com/collections/other-multirotor-motors/products/sunnysky-multirotor-9450-propellers-cw-ccw-rotation-pair-fit-a2212-x2212-multirotor-motors)
* [HolyBro 1045 full set (4 propellers) - Banggood](https://www.banggood.com/2-Pairs-Holybro-S500-V2-Frame-Kit-Spare-Part-10-Inch-1045-10x4_5x2-Propeller-CW-CCW-p-1542886.html)
* [Gemfan 9450 CW & CCW pair (carbon fiber) - Banggood](https://www.banggood.com/Gemfan-9_4x5-9450-Carbon-Fiber-Multirotor-Self-Lock-Propellers-CWCCW-p-974634.html?rmmds=search&cur_warehouse=CN)
* [Tarot 9" CW & CCW pair](http://www.tarotrc.com/Product/Detail.aspx?Lang=en&Id=9e7e5502-18de-444a-ae82-c11068a5a030)

Note the sizes, e.g. the SunnySky propellers are 9045, i.e. slightly smaller than the typical 9450 propellers, and the HolyBro ones are 1045, i.e. slightly bigger.

There are various other variants available on Banggood, just search for "9450 propeller" or "phanton propeller".

Interesting folding alternatives:

* [Rcgeek 3-blade CW & CCW pair (carbon fiber) - Banggood](https://m.banggood.com/4PCS-Carbon-Fiber-Noise-Reduction-Self-locking-Folding-3-blade-Propeller-for-DJI-Phantom-1-or-2-or-3-p-1345792.html)
* [Gemfan 9450 CW & CCW pair - AliExpress](https://www.aliexpress.com/i/32755280913.html) (requires connector and screw-down spinner).

Final choice: DJI 9450 CW & CCW pair or HolyBro 1045 full set.

### S500 frame

DJI used to produce an extremely popular quadcopter frame called the F450 and many other manufacturers produces clones and variants of this frame. However, now nearly everyone is focusing on the smaller racing drone frames.

In the F450 space, the most easily available frame of this style is the S500. It's available from a number of manufacturers:

* [HolyBro - S500 with skids](https://shop.holybro.com/s500-v2-frame-kit_p1139.html)
* [ReadyToSky - S500 with skids or 4 legs](http://www.readytosky.com/e_products/330mm-and-bigger-Quadcopter-Frame-18-107.html)
* [HobbyKing - S500 with 4 leg landing gear](https://hobbyking.com/en_us/s500-glass-fiber-quadcopter-frame-480mm-integrated-pcb-version.html)

The text etc. on the top and bottom plates seems to be identical for all three. So, rather than straight clones (which is common in this space even for name brands), I suspect there's only one manufacturer and the others resell them under their brand.

Generally, the flight controller is placed on the top plate and the battery is slung under the bottom plate between the two legs, but it is possible to build the S500 without legs (as shown [here](https://www.rcgroups.com/forums/showpost.php?p=40228017&postcount=2730)) but this requires a suitably slim flight controller (with ports for GPS etc. at one end rather than on top).

The PX4 people have instructions for building the S500 with the Pixhawk 4 [here](https://docs.px4.io/master/en/frames_multicopter/holybro_s500_v2_pixhawk4.html). HolyBro, oddly, have just printed this build log as a PDF and used this as their official manual.

### Classic F450-style frame

Various manufacturers have discontinued their F450-style frames, e.g.:

* [Hobbyking - Q450](https://hobbyking.com/en_us/q450-v3-glass-fiber-quadcopter-frame-450mm-integrated-pcb-version.html)
* [Hobbyking - SK450](https://hobbyking.com/en_us/hobbyking-sk450-glass-fiber-quadcopter-frame-450mm.html)
* [Diatone Q450 - Banggood](https://www.banggood.com/Diatone-Q450-Quad-450-V3-PCB-Quadcopter-Frame-Kit-450mm-p-942100.html)

The Diatone Q450 and the Hobbyking Q450 look like they were the same thing.

Still available F450-style frames include:

* [Tarot - FY450 (TL2749-05)](http://www.tarotrc.com/Product/Detail.aspx?Lang=en&Id=39ad11bb-423e-4a26-b0bf-8accac72b7c3)
* [Readytosky - F450](http://www.readytosky.com/e_productshow/?419-Readytosky-F450-4-Axis-Quadcopter-Frame-419.html)

The Tarot top plate looks quite like the original DJI F450 top plate while the bottom plate is quite dissimilar. With the Readytosky its the opposite - the bottom plate looks similar but the top plate looks dissimilar (in particular it has more holes, including a large center hole).

Banggood and AliExpress have various models that all _look_ like the Readytosky F450:

* [F450 with extended feet - Banggood](https://www.banggood.com/Upgrade-F450-450mm-Wheelbase-Frame-Kit-with-Highten-Landing-Gear-for-RC-Drone-p-1414811.html)
* [U-Angel-1988 - F450 - AliExpress](https://www.aliexpress.com/item/32926442641.html)
* [Soulload FPV - F450 - AliExpress](https://www.aliexpress.com/item/32911454049.html)
* [Magic Power - F450 - AliExpress](https://www.aliexpress.com/item/4000182267455.html)

**Warning:** for the AliExpress stores, it's fairly unclear what you're buying - in particular at the Magic Power store, it's very unclear that all options except the first one relate to the smaller F330 rather than the F450.

### Hexsoon EDU450

An interesting recently released frame is the Hexsoon EDU450. The pedigree of this frame is a little unclear, it's been produced in cooperation between ArduPilot and ProfiCNC as a [reference frame](https://ardupilot.org/copter/docs/reference-frames.html). The manufacturing side of ProfiCNC is called Hex but the actual frame seems to have been developed for them by [DonSoon](http://www.donsoon.com/product/450mm-multi-rotor-UAV.html) (with the Hexsoon product name being an amalgamation of both the Hex and DonSoon names). As usually with these kind of Chinese companies it's impossible to tell what kind of relationship there is between the two.

It's only available in [packs of 5](http://www.proficnc.com/all-products/200-pixhawk2-suite.html) from the ProfiCNC store but individual frames are available from various sites, e.g. [Unmanned Tech](https://www.unmannedtechshop.co.uk/product/hexsoon-edu-450-drone-development-platform/) in the UK.

Hexsoon EDU450 resources:

* The ArduPilot Hexsoon EDU450 [documentation page](https://ardupilot.org/copter/docs/reference-frames-hexsoon-edu450.html).
* ArduPilot Discourse [Hexsoon EDU450 thread](https://discuss.ardupilot.org/t/auwsume-hexsoon-edu-450/52275).
* Hexsoon EDU450 [build log](https://rotorbuilds.com/build/24081) (the link to this log was found in the ArduPilot Discourse thread).
* Hexsoon EDU450 [unboxing video](https://www.youtube.com/watch?v=-YwU8w9Rho0&feature=youtu.be&t=58) (worth watching for negative feedback).
* The Hexsoon EDU450 [in-action video](https://www.youtube.com/watch?v=BhU3ly_wkx8) (being used with a 3D camera for positioning rather than GPS).

Note that the unboxing video and the ArduPilot Discourse thread are rather discouraging - there definitely seem to have been QA issues. At this price point, there's little excuse for poor finishing on the carbon fiber parts. Hopefully, things will improve on this front or already have.

At the moment, at about twice the price, it looks rather pricey compared to the [HolyBro S500 ARF V2 frame kit](https://shop.holybro.com/s500-arf-v2-frame-kit_p1216.html) that also has motors, ESCs, propellers etc. The S500 has plastic arms (reinforced with steel rods), while the EDU450 is made from carbon fiber and has a larger central space for mounting equipment. However, I'm not sure that's enought to justify the price difference.

### Large frames

Tarot produce a whole range of large frames such as the [Tarot Ironman 650 (Banggood)](https://www.banggood.com/Tarot-Full-Folding-Carbon-Fiber-4-Axis-IRON-MAN-650-TL65B01-Rack-p-89713.html).

Readytosky have [various frames](http://www.readytosky.com/e_products/330mm-and-bigger-Quadcopter-Frame-18-107.html) including the [ZD550](http://www.readytosky.com/e_productshow/?425-Ready-ZD550-Carbon-Fiber--Quadcopter-Frame-Kit-with-carbon-fiber-landing-skidtosky-425.html).

Lumenier produce a number of large frames that are in the premium hobbyist price range:

* The [QAV-RXL 2](https://www.getfpv.com/lumenier-qav-rxl-2-8-fpv-quadcopter-frame.html).
* The [QAV400](https://www.lumenier.com/commercial/qav400).

The TBS Discovery (PDF manual [here](https://www.team-blacksheep.com/tbs-discovery-manual.pdf)) seems to have finally been discontinued (as has the Diatone [White Sheep](https://www.rcgroups.com/forums/showthread.php?2134571-Diatone-White-Sheep-PCB-Version-FPV-Quadcopter-Frame-Kit-Banggood) clone).

Random large-ish frames:

* [Diatone - GT Tyrant 530 (Banggood)](https://www.banggood.com/Diatone-2018-GT-Tyrant530-530mm-Wheelbase-5mm-Arm-Normal-X-FPV-Racing-Frame-Kit-p-1345009.html)
* [HobbyKing Super-H 600](https://hobbyking.com/en_us/hobbyking-super-h-600-quadcopter-kit.html)
* [Daya 680 (AliExpress)](https://www.aliexpress.com/item/32886038214.html)

### Smaller frames

The classic step down in size from the F450-style frames is the no longer available DJI F330. However, clones of the F330 are still available:

* [F330 (Banggood)](https://www.banggood.com/F330-4-Axis-RC-Quadcopter-Frame-Kit-RC-Drone-Support-KK-MK-MWC-p-943370.html)
* [Readytosky Q330](http://www.readytosky.com/e_productshow/?405-Readytosky-Q330-PCB-Quadcopter-Frame-405.html) - a slightly stretched version of the F330.

Readytosky also have the slightly larger [Q380](http://www.readytosky.com/e_productshow/?406-Readytoaky-Q380-Quadcopter-Frame-Kit-406.html). 

A much more modern racing style frame is the [HolyBro QAV250](https://shop.holybro.com/qav250-fpv-frame_p1140.html) (they also sell this as a [kit](https://shop.holybro.com/qav250-kit_p1125.html) with the Pixhawk 4 Mini).

HolyBro is probably just reselling the [HSKRC QAV250](https://www.banggood.com/HSKRC-QAV250-V3-250mm-Wheelbase-5-Inch-3-or-4mm-Arm-Frame-Kit-Carbon-Fiber-for-RC-Drone-FPV-Racing-p-1466481.html). There's also a very similar frame called the [ZMR250](https://www.banggood.com/ZMR250-V2-Carbon-Fiber-Frame-Kit-4-0mm-Arm-Thickness-Support-1806-2204-2206-Power-p-1010702.html) (also listed on some sites as the H250).

These all seem to be clones of no longer available Lumenier [QAV250](https://www.lumenier.com/products/legacy/qav250).

PX4 have a nice [build guide](https://docs.px4.io/master/en/frames_multicopter/lumenier_qav250_pixhawk_mini.html) for the original Lumenier QAV250 in combination for the Pixhawk Mini.

Similar slightly larger frames include:

* [Realacc Martian IV - 300mm (Banggood)](https://www.banggood.com/Realacc-Martian-IV-7-Inch-300mm-Wheelbase-4mm-Arm-Carbon-Fiber-FPV-Racing-Frame-Kit-p-1295851.html)
* [GEPRC Crocodil (AKA LC7) - 315mm (Banggood)](https://www.banggood.com/GEPRC-GEP-LC7-315mm-Wheelbase-6-7-Inch-5mm-Arm-Carbon-Fiber-Frame-Kit-153g-for-RC-Drone-FPV-Racing-p-1438745.html) (there's also a [kit version](https://www.banggood.com/GEPRC-GEP-Crocodil-GEP-LC7-PRO-315mm-7-Inch-6S-RC-FPV-Racing-Drone-Betaflight-F4-50A-Runcam-Micro-Swift-p-1414014.html) with the Runcam 2 and various other [configurations](https://geprc.com/product-category/drones/6inch-8inch-drone/)).
* [GEPRC Mark2-7 - 300mm (Banggood)](https://www.banggood.com/Geprc-Mark2-7-7-Inch-300mm-4mm-Arm-Carbon-Fiber-FPV-Racing-Frame-Kit-w-5V12V-PDB-for-RC-Drone-p-1275422.html)
* [iFlight XL7 V4 - 295mm (Banggood)](https://www.banggood.com/IFlight-XL7-V4-True-X-7-inch-Long-Range-Freestyle-Frame-Kit-Arm-4mm-for-FPV-Racing-Drone-p-1361609.html)

Oscar Liang has a nice 7" quadcopter [build guide](https://oscarliang.com/7-inch-long-range-fpv-drone-build/) - he uses the Mode 2 Shredder 7" frame (a frame that doesn't seem to be very readily available) but he also mentions the Martian IV (implicitly as his second choice).

Quote from this build guide:

> When we are talking about the size of a racing drone, we normally refer to the maximum propeller size it can take. In this case, a 7" frame means it can take 7" propellers. 7" frame typically have a wheelbase of around 300mm, sometimes also known as motor to motor distance.

When talking about non-racing drones, referring to the wheelbase, i.e. the distance from the center of one motor to the center of the diagonally opposite motor, seems to be more common.

### Transmitter

The lower end of the FrSky range now consists of 3 models:

* Taranis X9 Lite - entry level ~US$70
* Taranis Q X7 - solid first transmitter ~US$110
* Taranis X9D Plus - the classic FrSky transmitter ~US$180

The X9D is FrSky's classic transmitter and the basic styling hasn't changed for years, the Q X7 was introduced as a solid slightly cheaper transmitter and the X9 Lite is the newest entry - it's substantially cheaper and is competing with basic entry level models from other manufacturers (FrSky largely dominates the premium end of the market).

I prefer the dials of the Q X7 for menu navigation (rather than the buttons of the X9D). The Q X7 does have fewer switches, than the X9D, but this is unlikely to be a factor except in very complicated setups.

**Important:** you should buy the transmitter version suitable for your region, i.e. FCC for America and many other counties and LBT for the EU (although this is _probably_ switchable via firmware). The same goes for your receiver.

The older Taranis Q X7 **ACCST** model has been extremely popular on Banggood. Oddly, the newer [ACCESS model](https://www.banggood.com/FrSky-Taranis-Q-X7-ACCESS-2_4GHz-24CH-Mode2-Transmitter-Supports-Spectrum-Analyzer-Function-for-RC-Drone-p-1650441.html) doesn't seem to have accumulated many reviews yet. A slightly more expensive bundle, the ACCESS model with R9M long range module, seems to have sold better (or has simply been available longer).

With the newer ACCESS models you get support for the new ACCESS protocol and the existing ACCST D16 protocol but you lose the support that the pre-2020 Q X7 had for the D8 protocol. D8 isn't even legal in the EU and is mainly found on [Whoop-style](https://oscarliang.com/best-tiny-whoop/) drones - and these days such drones generally also support D16.

Cases:

* [FrSky Q X7S case](https://www.banggood.com/Frsky-EVA-Handbag-Hard-Case-for-Taranis-Q-X7S-or-X9D-Plus-SE-Radio-Transmitter-p-1251902.html?ID=533009)
* [Realacc Taranis case](https://www.banggood.com/Realacc-Handbag-Backpack-Bag-Case-with-Sponge-for-Frsky-Taranis-X9D-PLUS-SE-Q-X7-Transmitter-for-RC-Drone-p-1158382.html) - slightly cheaper but so-so foam lining.

From HorusRC:

* [Taranis Q X7 ACCESS](https://www.horusrc.com/en/frsky-2-4ghz-taranis-q-x7-access-transmitter.html).
* [FrSky Q X7S case](https://www.horusrc.com/en/frsky-taranis-q-x7s-eva-case.html)

HorusRC seems to have somewhat better pricing than Banggood. Note that the regional stores (US, EU etc.) carry a very limited range - just use the global store.

#### Transmitter batteries

For the newer transmitter models you need two 18650 li-ion batteries, e.g. [NCR18650B 3400mAH (Banggood)](https://www.banggood.com/2pcs-NCR18650B-3400mAH-3_7-V-Unprotected-Rechargeable-Lithium-Battery-p-87078.html). These batteries cost ~US$7 from Banggood, which is about the right price, they're cheaper from the [18650BatteryStore](https://www.18650batterystore.com/Panasonic-18650-p/panasonic-ncr18650b.htm), at around $5. Something similar - the Samsung INR18650 30Q - from [Conrad](https://www.conrad.ch/de/p/samsung-inr18650-30q-spezial-akku-18650-flat-top-hochstromfaehig-li-ion-3-6-v-3000-mah-1558875.html) is about US$8. Reichelt have a two pack of suitable [Samsung batteries](https://www.reichelt.com/industriezelle-18650-3-6-v-3450-mah-ungeschuetzt-2er-pack-sam-18650-35e-p261044.html) for about US$10. Whether the ones from Banggood are genuine is another matter - it's not clear either way.

**TODO:** it doesn't make sense to quote Reichelt prices in dollars - use Euros instead.

There are also button-top variants of these batteries - the transmitter seems to take either button top or non-button top (the manual doesn't specify one or the other and you can see Painless360 using [button-less ones](https://www.youtube.com/watch?v=8cA-qQMRsdQ&feature=youtu.be&t=279) and in other videos you can see people using button-top ones).

The manual confirms that the batteries "can be balance charged via the Mini USB interface," so you don't need a separate charger.

#### Transmitter batteries for older models

The [NiMH battery pack](https://www.banggood.com/Frsky-ACCST-Taranis-Q-X7-Transmitter-Spare-Part-7_2V-AA-2000mAh-NiMH-Battery-for-RC-Drone-FPV-Racing-p-1153564.html) has a 3-pin female connector (with the middle pin left unconnected). A 3-pin connector is a _2S_ connector, for an extension cable one would use:

* [2S balance cable - 10cm (Banggood)](https://www.banggood.com/JSTXH-LiPo-Balance-Wire-10CM-2S-3S-4S-5S-6S-p-925209.html?ID=512939)
* [2S balance cable - 20cm (Banggood)](https://www.banggood.com/Li-Po-Battery-Balance-Charging-Extension-Wire-Cable-20cm-2S-3S-4S-6S-for-RC-Drone-Lipo-Battery-p-951866.html?ID=512939)
* [2S balance cable - 30cm (Banggood)](https://www.banggood.com/Lipo-Battery-Charger-Silicone-Wire-Balance-Extension-Cable-2S-3Pin-3S-4Pin-4S-5Pin-8S-9Pin-2_54XH-30cm-p-1022456.html?ID=47891)

The FrSky FCX07 NiMH charger seems to be discontinued but you can still buy it from places like [GetFPV](https://www.getfpv.com/frsky-taranis-q-x7-fcx07-li-nimh-dual-mode-charger.html) (and also as a [bundle](https://www.getfpv.com/frsky-fcx07-charger-with-2000mah-nimh-battery-for-q-x7-x7s-combo-kit.html) with the NiMH battery).

### Receiver (RX)

For this kind of project, there are basically two interesting FrSky receivers:

* [Archer RS](https://www.frsky-rc.com/product/archer-rs/)
* [Archer R4](https://www.frsky-rc.com/product/archer-r4/)

The RS has everything we need, so what's interesting about the R4 and R8 PRO with there unneeded PWM output pins that take up a lot of space? Unlike the RS, they have connectors so you don't have to solder down wires for SBUS and S.PORT. However, the R4 connector isn't for something standard, like a [servo connector](https://www.pololu.com/product/1924). It does though come with a cable where the S.PORT pins are broken out to a servo connector and remaining SBUS related pins are broken out to individual jumper wire style female connectors.

There's also the [Archer M+](https://www.frsky-rc.com/archer-m/) - it is almost idenical to the RS, except that it doesn't support receiver redundancy (an irrelevant feature for most hobbyist setups) and it just has one antenna (unlike the RS, R4 etc. which have two for [antenna diversity](https://en.wikipedia.org/wiki/Antenna_diversity)).

Note: this [video](https://youtu.be/38SEKpScwvU?t=405) is interesting in how it shows soldering up the Archer RS receiver wires but **it also makes clear how fidly this is (some of the holes are right beside components on the PCB)**. If you really want a small size then simply cutting the PWM pins off the R4 might be a simpler alternative.

The Archer series receivers are very new and only supported by the latest 2020 FrSky transmitters. For receivers using the D16 protocol that has broader support across transmitters from different manufacturers there are the older equivalent X-series receivers:

* [R-XSR](https://www.frsky-rc.com/product/r-xsr/)
* [RX4R](https://www.frsky-rc.com/product/rx4r/)
* [X8R](https://www.frsky-rc.com/product/x8r/)

Protocol aside, the R-XSR and RX4R are very similar to the Archer RS and Archer R4 respectively. Note that you can reflash the firmware on the R-XSR and RX4R (but not the X8R) for ACCESS support (but having to do this initial flashing somewhat negates the whole supposed ease of setup aspect of ACCESS). There is a XM+ which looks similar to the Archer M+ but, unlike the Archer version, the XM+ doesn't support telemetry.

So why include the X8R here but not the similar Archer R8 above? The X8R has even more unneeded PWM output pins but the extra size means they can fit in servo connector for SBUS and S.PORT which is quite convenient - you can use standard servo cables to connect it up. The Archer R8 also has a servo connector for SBUS but a non-standard S.PORT connector so isn't quite so convenient in this respect.

#### F.PORT

The Archer series feature F.PORT, which is SBUS and S.PORT rolled into a single wire, and continue to support SBUS and S.PORT broken out onto seprate wires. According to the ArduPilot [documentation](https://ardupilot.org/copter/docs/common-FPort-receivers.html) F.PORT support will not be available until version 4.1, there's no ETA for 4.1 but minor releases tend to come out once a year and 4.0.0 came out at the end of 2019.

F.PORT version 1 just supported a direct connection between receiver and flight controller with only the flight controller being capable of feeding the receiver with S.PORT style data. In June 2020, F.PORT version 2 came out where you can add in the usual S.PORT capable sensors like the [FLVSS](https://www.frsky-rc.com/product/flvss/). It's only version 2 that's of interest for our setup. See more details from [Oscar Liang](https://oscarliang.com/setup-frsky-fport/).

#### RX antennas

An alternative to taping the antennas to the quadcopter arms is an atenna mount:

* [antenna mount](https://www.banggood.com/FrSky-2_4G-Receiver-Antenna-Fixing-Seat-QAV-Receiver-Antenna-Fixing-Seat-Transparent-p-986935.html)
* [antenna mount](https://www.banggood.com/CC3D-RC-Antenna-Pedestal-Antenna-Box-For-RC-Mutirotors-p-971903.html)

Antennas are quite complex, there are various factors affecting length etc., see [Oscar Liang](https://oscarliang.com/repair-2-4ghz-antenna-rx/) for more details on 2.4GHz receiver antennas (see the section on how the lengths vary even across the X-series receivers).

HorusRC sell a whole range of [antennas](https://www.horusrc.com/en/accessories/radio-receiver-antennas) suitable for FrSky receivers. Banggood also have antennas, e.g. [this](https://www.banggood.com/FRSKY-Upgraded-Version-Smaller-Antenna-for-X4R-SB-X4R-XSR-Receiver-p-1096739.html) and [this](https://www.banggood.com/Frsky-2_4G-IPEX-V4-Antenna-150mm-For-X4R-X4RSB-XM+-S6R-S8R-F30-F3OP-F40-F4OP-Receiver-p-1167847.html) standard wire antennas and [this](https://www.banggood.com/FrSky-PCB-Antenna-For-X8R-X6R-Receiver-p-991728.html) PCB-style antenna but it's less clear than with HorusRC as to exactly what you're getting.

Molex and Taoglas (only by Mouser) produce various suitable PCB antennas with all kinds of connectors - unfortunately they're poorly categorized by Digikey and Mouser or mis-categorized (e.g. the Molex atennas on Mouser all seem to be categorized as having solder connectors):

* [Mouser antenna](https://eu.mouser.com/Passive-Components/Antennas/_/N-8w0fa)
* [Digikey antenna](https://www.digikey.ch/products/en/rf-if-and-rfid/rf-antennas/875)

### Video transmitter (VTX)

Oscar Liang maintains a [best VTX](https://oscarliang.com/top-5-best-vtx-mini-quad/) page. His cheapest choice is the Eachine TX526 which has been around for years (and which I bought back in 2017, along with the massive TX832).

As of late 2020, his best value transmitter is the [TX805 (Banggood)](https://www.banggood.com/Eachine-TX805-5_8G-40CH-25-or-200-or-600-or-800mW-FPV-Transmitter-TX-LED-Display-Support-OSD-or-Pitmode-or-Smart-Audio-p-1333984.html) (see Oscar's [review](https://oscarliang.com/eachine-tx805-vtx/)).

As pointed out in his review, you can mount this VTX on top of a standard 30x30 stack (as shown [here](https://oscarliang.com/ctt/uploads/2019/03/Eachine-TX805-Video-Transmitter-mini-quad-stack.jpg)).

### Configuring the VTX

On a massive old style VTX like the TX832, it's easy enough to set things up via the buttons on the device itself. This all gets a bit more fiddly with smaller VTXs, e.g. on the TX805 everything has to be done with a single button and you have to interpret what's happening via an array of tiny blue and red LEDs.

An alternative is to use VTX telemetry (AKA SmartAudio or Tramp). DroneTrest have a nice [blog entry](https://blog.dronetrest.com/smart-audio-vtx/) discussing this technology.

Oscar Liang has a [guide](https://oscarliang.com/vtx-control/) to configuring things so you can configure your VTX thru the OSD of your FPV goggles or via your TX. However, both these approaches work via BetaFlight.

There is an [open MR](https://github.com/ArduPilot/ardupilot/pull/15174) that's actively being worked on (mid-October, 2020) and a corresponding discussion [thread](https://discuss.ardupilot.org/t/is-there-a-way-to-get-smartaudio-working/29025/58) but at the moment there is no SmartAudio support in ArduPilot.

#### VTX notes

In this [page](https://oscarliang.com/choose-video-transmitter-fpv-mini-quad/) he also discusses why adjusting your VTX to maximum power may actually have negative consequences in terms of heat, multipath interference and interference with others. He notes that you should use 25mW indoors and that many races mandate 25mW and recommends 200mW as "a conservative option that provides the best of both worlds [i.e. 25mW and 600mW]" for outdoor flying. He also notes that 600mW isn't so dramatically better than 25mW due to the diminishing returns implied by the inverse square aspect of things. Note that at 25mW the VTX will be uncomfotably hot and at 200mW and above it'll be too hot to touch - air flow cools it down so, in general, avoid running it when not in movement.

Aside: see [PAL vs NTSC](https://oscarliang.com/pal-ntsc-fpv-quadcopter/) - basically its a choice between better image quality (PAL) and more frames-per-second (NTSC) and there's no clear choice one way or the other.

#### VTX antennas

The TX805 features an MMCX connector which is viewed as a big improvement over the older SMA connectors (which was subject to being torn off the VTX during crashes). However, the SMA connectors had the advantage of providing a stable mounting point. If you use the TX805's MMCX to SMA adapter then you'll also need a mount like [this](https://www.banggood.com/Eachine-Wizard-X220HV-FPV-Racing-RC-Drone-Spare-Part-Antenna-Fixing-Seat-Mount-3D-Printing-p-1392505.html) (which can be used as shown [here](https://imgaz.staticbg.com/customers_images/newlarge/c6/9a/2020051913320129-1392505.jpg) or even nicer, handling both VTX and RX antennas, as shown [here](https://imgaz.staticbg.com/customers_images/newlarge/c6/4f/2019111617283117-1392505.jpg)).

Alternatively, one can buy a pure MMCX antenna like this [Realacc UXII](https://www.banggood.com/Realacc-UXII-5_8G-1_6dBi-MMCX-StraightMMCX-90-Degree-RHCP-FPV-Antenna-p-1256003.html) (available in 90&deg; and straigh variants) or this [Foxeer Pagoda Pro](https://www.banggood.com/Foxeer-Pagoda-Pro-5_8GHz-2dBi-RHCP-FPV-Antenna-86mm-MMCX-BlackRedOrange-p-1241973.html) (straight only). Both Realacc and Foxeer seem to be well regarded so it's hard to say one is generally considered better than the other. Of course, this style simply leads to different mounting issues.

Note: 90&deg; sounds odd but the idea is if, for whatever reason, you want to mount the VTX sideways (as shown in [this video](https://youtu.be/NaMwoDO_pCk?t=692)).

As usual, Oscar Liang has a nice [overview](https://oscarliang.com/best-fpv-antenna/) of VTX antennas.

#### More antenna options

Two popular antenna styles at the moment are pagoda and stubby/lollipop. The Realacc UXII, mentioned above is a stubby antenna, and the Foxeer Pagoda Pro is obviously a pagoda. Both seem to be excellent antennas (and not just the ones that happen to be on Banggood). On the whole Foxeer seems to produce more premium priced products than Realacc.

Realacc have a pagoda - but it only comes with SMA - it's actually the [best selling antenna](https://www.banggood.com/Realacc-Pagoda-RHCP-Antenna-65mm-5_8G-5dBi-Panel-Plate-Omni-Directional-FPV-Short-Antenna-RC-Drone-p-1174479.html?ID=224523628) on Banggood (actually the linked to antenna comes second after its cheaper variant without a protective case around the PCB disks).

The SMA [Foxeer Lollipop](https://www.banggood.com/2pcs-Foxeer-5_8G-Lollipop-3-2_5DBi-Omni-FPV-Antenna-RHCP-SMA-or-RP-SMA-for-RC-Drone-Airplane-p-1472198.html) are the third best selling VTX atenna on Banggood (after the two Realacc pagoda variants). The Foxeer Lollipop has an MMCX variant - it's not currently on sale on Banggood but can be found on the [Foxeer site](https://www.foxeer.com/foxeer-lollipop-3-5-8g-2-5dbi-high-gain-omni-fpv-antenna-g-230). Note: in true Banggood style the video at the top of product description for the SMA Foxeer Lollipop is actually for the _Micro_ Lollipop, which is a different product (and also available on Banggood).

Interestingly, Foxeer also produce a [version](https://www.banggood.com/2pcs-Foxeer-5_8G-Lollipop-3-2_5DBi-Stubby-Omni-FPV-Antenna-LHCPRHCP-for-RC-Drone-Airplane-p-1472193.html) of their Lollipop (which they confusingly call a _stubby_ Lollipop) that comes with no feed line, i.e. you could attach it to an MMCX to SMA converter without adding additional length (but why not just buy an MMCX antenna then?).

As usual with this kind of thing, there's no clear information saying Lollipops are better than Pagodas or vice-versa (which is odd as the Lollipops are more expensive). Oscar Liang doesn't come down clearly one way or another in his [round up](https://oscarliang.com/best-fpv-antenna/) of antennas. My impression is that the Pagodas _may_ be technically better but their PCBs are easily knocked out of alignment and that the Lollipops are far more robust (which is important when racing).

### Camera

For combined FPV and HD video the current best option seems to be the RunCam Split 3 Micro (there's also an even smaller Nano variant but in choosing it seems a better choice to choose the improved image quality that comes with the larger lens of the only slightly larger Micro model). Oscar's review is [here](https://oscarliang.com/runcam-split-3-camera/).

You can find the current RunCam recoding cameras [here](https://shop.runcam.com/fpv-hd-recording-camera/) on their site. As pointed out in Oscar's review, there's now also a Split 4 but this is a HD Micro only camera - paying even just slightly extra for HD with such a tiny lens seems pointless.

#### Pure HD camera

An alternative to the Split is a pure HD camera, like the [RunCam 5](https://shop.runcam.com/runcam-5-orange/) or the [RunCam 2](https://shop.runcam.com/runcam2/) (see RunCam's [action camera](https://shop.runcam.com/action-camera/) and [HD camera](https://shop.runcam.com/fpv-hd-recording-camera/) sections). These can be connected up to a VTX and power using [this cable](https://shop.runcam.com/tv-out-and-power-cable-for-runcam-2/).

These cameras have much betters lenses than the smaller Split and the higher latency for live-video via the VTX isn't an issue (it is if you're planning to race). However, they're both fairly large and come with their own batteries (it's convenient to keep the number of batteries to a minimum - keeping track of them and particularly whether they're charged or not can get frustrating). You can remove the batteries and provide them with 5V via the USB adapter. The battery compartment is a noticeable part of the camera's size and the battery is a noticeable part of its cost - both are essentially unnecessary.

Note: you'd need a step-down voltage regulator that can output 5V for the USB power supply. You can get combination regulators that can output 12V for the VTX and 5V for the camera.

#### Pure FPV camera (with recorder)

Another alternative, if you're not interested in HD recorded footage, is simply a basic FPV camera like the [RunCam Swift 2](https://shop.runcam.com/runcam-swift-2/). This is far cheaper than something like the RunCam 5 or 2 or the Split. And it's far smaller - it has neither the large battery compartment of the RunCam 5 or 2 nor the secondary PCB of the Split. And its much lower power consumption means it can be powered directly off the VTX (most have a 5V output for the camera that's generally capable of fairly limited amps).

The RunCam Swift 2 is a "full size" camera (see [here](https://oscarliang.com/best-fpv-camera-quadcopter/) for details of the standard camera sizes), i.e. noticeably larger than the camera portion of the Split Micro (28mm wide vs 19mm), so it _should_ actually have room for better optics (not that this is probably relevant once encoding into NTSC or PAL and lossy transmission are taken into account).

Note: you can actually combine a pure FPV camera like the Swift with a tiny on-board recorder like [this](https://shop.runcam.com/runcam-mini-fpv-dvr/) from RunCam. You will, of course, be recording a classic analogue TV signal rather than 1080p but it won't suffer from the interference seen if recording the transmitted signal.

### VTX power consumption

It's remarkably hard to find power consumption data for VTXs. This [post](https://fpvlab.com/forums/showthread.php?30580-Vtx-output-power-relationship-to-consumed-power&s=538b86b105aa90cbe388b40a5fe84ef5&p=516843&viewfull=1#post516843) gives the following numbers (derived from ImmersionRC and Fatshark specs) - the left being the power output and the right being the power consumed by the VTX:

* 25mW = 0.72W
* 250mW = 2.44W
* 600mW = 3.36W

[Here](https://www.immersionrc.com/fpv-products/tramp-hv-5-8ghz-video-transmitter/) ImmersionRC reports:

* 200mW = 1.9W
* 600mW = 4W

In this [video](https://youtu.be/kzIJug7nBv8?t=52) they actually measure the power consumption, with these results:

* 25mW = 1.2W
* 200mW = 3.2W
* 600mw = 5.2W

The Eachine TX805 [product page](https://www.eachine.com/Eachine-TX805-5_8G-40CH-25-or-200-or-600-or-800mW-FPV-Transmitter-TX-LED-Display-Support-OSD-or-Pitmode-or-Smart-Audio-RP-SMA-Female-p-1234.html) lists:

* 25mW = 1.4W
* 200mW = 2.4W
* 600mW = 3.6W
* 800mW = 4.2W

This [product page](https://www.eachine.com/EACHINE-TXC23-VTX-5_8Ghz-48CH-25-or-200-or-600-or-800mW-FPV-Mini-Transmitter-Pitmode-ISM-Band-Simulation-for-Micro-Drone-RC-Racing-Aircraft-RP-SMA-Female-p-1762.html) for the TXC23 list similar slightly lower values.

So assuming a pessimistic 6W at maximum power consumption then that's **0.5A at 12V**.

And given that we've determined elsewhere that you should probably run at at-most 200mW, you're probably never going to come close to this level of power consumption.

Interestingly, the amount of power the VTX can provide to the camera depends on what power output the VTX is set to (I guess this has something to do with how the switching power supply works). So with a 12V input, the TX805 can supply the following current at 5V depending on its current output setting:

* 25mW = 120mA
* 200mW = 200mA
* 600mW = 300mA
* 800mW = 350mA

So at 25mW it provides less than the 130mA needed for something like the RunCam Swift 2 (a pure FPV camera that needs 130A@5V) but enough for some cameras such as the RunCam Racer 4. And even at 800mW it's far short of the 640mA@5V that the RunCam Split 3 Micro requires.

At 12V the RunCam Split 3 Micro requires 270mA.

**Conclusions:** so with a very power heavy setup (with the VTX running at maximum and a power hungry camera, like the RunCam Split 3 Micro, with HD recording) you end up with:

* VTX = 0.5A@12V
* Camera = 0.27A@12V

So a 12V regulator capable of 1A should be more than enough to supply both (and in reality, if you only use the VTX at 200mW or less, you'll probably never use more than 0.6A).

### 12V / 5V step-down voltage regulator

The camera and VTX need a step-down voltage regulator - the VTX typically needs 12V and, in turn, provides a 5V output for the camera. However, the Split draws more power than a typical camera and more than most VTXs are happy supplying (see elsewhere here for more details). The Split can though take 12V, so it seems best to power them both via the same regulator.

The Pololu [12V/1A step-down voltage regulator](https://www.pololu.com/product/2834) can provide more than enough power for both.

Alternatives from Banggood (all are available in 12V and 5V variants):

* [BlueSky 3A BEC](https://www.banggood.com/DC-DC-Converter-Step-Down-Module-UBEC-3A-5V-or-12V-BEC-For-RC-Airplane-FPV-for-RC-Drone-FPV-Racing-p-981978.html) (with wires and covered in heat shrink).
[Diatone 2A BEC](https://www.banggood.com/Diatone-Mini-2A-BEC-V2-0-Version-3-3V-5V-12V-For-RC-Multirotors-p-1032859.html) - available in 5V and 12V variants.
[Matek 1.5A BEC](https://www.banggood.com/5V-12V-Adjustable-Voltage-Dual-BEC-Output-Board-Only-1g-p-1031884.html) - 5V (but can be coverted to 12V by connecting two solder tabs).

Note: I thought the rated current should depend on the selected voltage, e.g. that switching the Matek from 5V to 12V should reduce the supported 1.5A, but this doesn't seem to be the case (see [specifications](http://www.mateksys.com/?portfolio=mbec2a#tab-id-2)). All the above BECs list a single current value, irrespective of selected voltage.

If you have lower current requirements, you can use something like the [Diatone 500mA BEC](https://www.banggood.com/Diatone-Micro-BEC-5V-6V-12V-500mA-Module-For-RC-Multirotors-78-Series-Regulation-Chip-p-1027492.html) (also available in 5V and 12V variants) but this doesn't seem to save much or anything in terms of price or size (but _may_ be more efficient for that given current).

**TODO:** the consensus seems to be that you shouldn't connect the VTX directly to the battery voltage even though many VTXs can handle the stated voltage. The VTX has a step-down voltage regulator, why does adding another in-between it and the battery make everything OK? Is it simply that a regulator like the Pololu one is more substantial and capable? If so, why not sell VTXs without regulators, leaving it instead to something like the Pololu board or why not sell VTXs with a regulator that matches the Pololu one and is suitable for direct connection to the battery?

#### Combined 12V and 5V PDBs

It doesn't seem possible to get BECs that can handle both 12V and 5V simultaneously - the best you can do are PDBs like this [Matek 36x36mm hub](http://www.mateksys.com/?portfolio=hub5v12v) ([here](https://www.banggood.com/Matek-Mini-Power-Hub-Power-Distribution-Board-PDB-With-BEC-5V-And-12V-for-RC-Drone-FPV-Racing-p-1005549.html) from Banggood). They also have a [larger hub](http://www.mateksys.com/?portfolio=pdb-xt60) ([here](https://www.banggood.com/Matek-Systems-PDB-XT60-W-or-BEC-5V-and-12V-2oz-Copper-for-RC-Drone-FPV-Racing-Multi-Rotor-p-1049051.html) from Banggood) for 6 ESCs where the main board is the same size but the power connector is pushed out (and has holes for an XT60 connector) to make more room for the ESC pads.

While it may seem odd to buy a PDB just for its voltage regulators, remember that there's no wasted circuitry in this setup - the rest of the PDB is simply providing a connection between the battery and the ESC pads. So the only real wasted space are just the the solder pads that you don't use.

Having said that the 36x36mm form factor means they didn't have to pack in the components. If you combined a similarly capable 12V board and a 5V board from Pololu you'd use half that space (at a dramatically higher price, it has to be said).

### Plates and parts for Split and VTX stack

For a base for the VTX and the HD component of the Split that could be stuck down to the frame one could use a 30x30mm plate:

* [GEPRC 30x30mm clear plate](https://www.banggood.com/5-PCS-Geprc-20x20mm-Or-30_5x30_5mm-Flight-Controller-ESC-Insulation-Plate-Short-Circuit-Protection-p-1216854.html) - 5 pack.
* [LDARC 30x30mm FC mount](https://www.banggood.com/Kingkong-Flight-Controller-Fix-Mount-for-CC3D-NAZE32-p-1042350.html) (flip it so its legs face upwards).
* [Clear 30x30mm plate](https://www.banggood.com/10-PCS-20x20mm-30_5x30_5mm-Insulation-Board-Short-Circuit-Protection-for-F3-F4-F7-Flight-Controller-ESC-RC-Drone-FPV-Racing-p-1479182.html) - 10 pack.
* [3D printed 30x30mm plate](https://www.banggood.com/TPU-3D-Printed-30_5x30_5mm-20x20mm-Hole-Insulation-Plate-1mm-for-Flight-Controller-Brushlesss-ESC-RC-FPV-Racing-Drone-p-1528607.html)

There are also carbon fiber plates (like [this](https://www.banggood.com/Flight-Controller-Protection-Cover-Plate-Damping-Plate-Controller-Board-for-Martian-Series-frames-for-RC-Drone-p-1102552.html) and [this](https://www.banggood.com/Realacc-RFX185-RFX160-FPV-Racing-Frame-Spare-Part-1_5mm-Middle-Plate-Carbon-Fiber-p-1101174.html)) but it seems best to stick clear of electrically conductive materials.

Spacers:

* [M3](https://www.banggood.com/Suleve-M3NH1-M3-Nylon-Screw-Black-Hex-Screw-Nut-Nylon-PCB-Standoff-Assortment-Kit-300pcs-p-984310.html)
* [M2](https://www.banggood.com/Suleve-M2NH4-M2-Nylon-Screw-Black-Hex-Screw-Nut-Nylon-PCB-Standoff-Assortment-Kit-300Pcs-p-1377786.html)

A more compact alternative to spacers is to combine bolts with washers like these [M3 3mm thick ones](https://www.banggood.com/Suleve-M3NW2-Flat-Nylon-Washer-Black-Round-Spacer-Waser-OD-8mm-for-M3-Screws-50pcs-p-1001703.html) or these [1mm thick washers](https://www.banggood.com/Suleve-MXNW3-100pcs-M2-M3-M4-M5-Black-Nylon-Washer-Gasket-Thickness-1mm-p-1280764.html) available in M2 and M3 variants.

Bolts:

* [M3](https://www.banggood.com/160Pcs-Metric-M3-Black-Nylon-Phillips-Pan-Head-Screw-Nut-Assortment-Set-p-973441.html)
* [M2](https://www.banggood.com/20-pcs-M2-Black-Round-Nylon-Screws-Phillips-Plastic-Round-Head-Screws-Bolt-p-1004241.html) (don't seem to be available as a box set).

You'd also need [M2 or M3 nuts](https://www.banggood.com/Suleve-MXHN2-50Pcs-Black-Nylon-Nuts-Hex-Plastic-Nut-Washer-Hexagonal-Nuts-M2-M3-M4-M5-M6-p-1272568.html) to go with these.

My impression is that M3 is more commonly used than M2. However, the RunCam Split 3 comes with a set of M2 spacers - I _presume_ it can also accommodate M3 but I can't confirm.

For the camera damping balls _might_ be useful.

Damping balls:

* [M3 6mm high](https://www.banggood.com/Diatone-Flight-Controller-Damping-Rubber-Ring-Blue-10-PCS-for-RC-Drone-FPV-Racing-Multi-Rotor-p-1188743.html)
* [M3 4.6mm high](https://www.banggood.com/4PCS-M3-Damping-Ball-For-M3-Mounting-Hole-Flight-Controller-ESC-RC-Multirotors-p-1150360.html)
* [M3 12.5mm high](https://www.banggood.com/5PCS-Gimbal-Camera-Anti-Vibration-Rubber-Dumping-Ball-for-250-Series-RC-Drone-FPV-Racing-p-1022203.html)

Also popular (in fact more popular) are these Realacc [M3*7+4.5mm damping screws](https://www.banggood.com/4-PCS-Realacc-M3+7+4_5-Flight-Controller-Anti-Vibration-Fixed-Screws-for-RC-Drone-FPV-Racing-p-1135527.html) (although from the photos, it's hard to see how they damp anything).

### Micro camera mounts

There are surprisingly few free standing micro mounts, this [one](https://www.banggood.com/RunCam-Micro-Swift-Camera-Bracket-Fixed-Mount-Holder-p-1170444.html) and [this](https://www.banggood.com/Runcam-Micro-Swift-Micro-Swift-2-Camera-Mount-Holder-30_530_5mm-Mounting-Distance-For-FPV-Racer-p-1156801.html) seem to be it on Banggood. Presumably such cameras are usually attached directly to the frame.

### Action camera mounts

The RunCam 5 has the same dimensions as the GoPro Session cameras, i.e. 38x38x36mm.

#### GoPro style mounts

By GoPro style, I mean mounts with an adjustable angle. Mounts suitable for the RunCam 5 from AliExpress:

* [Mount A](https://www.aliexpress.com/item/32839419942.html)
* [Mount B](https://www.aliexpress.com/item/4000076836617.html)
* [Mount C](https://www.aliexpress.com/item/1000007756487.html)
* [Aluminium mount](https://www.aliexpress.com/item/4000182813606.html)
* [Low-profile mount](https://www.aliexpress.com/item/33011717807.html)

Mounts A, B and C (there's no other obvious names to give them) seem to be clones of the original mount sold by GoPro. The low-profile looks interesting, it could be flipped out forward for flight and then parked nicely, i.e. flipped back, when not in use.

[Adjustable GoPro style mount](https://www.banggood.com/RunCam2-Camera-Mount-Support-GoPro-Action-Camera-p-1031391.html) for the RunCam 2 (although it's not clear from the Banggood listing, RunCam list this product on their site, i.e. it's not a third-party product).

#### Fixed FPV style mounts

By FPV style, I mean mounts with a fixed angle (typically 30&deg;):

* [Mount A](https://www.banggood.com/Eachine-Wizard-X220S-FPV-Racer-Spare-Part-30-Camera-Mount-for-Gopro-Session-or-Runcam-3-RC-Drone-FPV-Racing-p-1166269.html)
* [Mount B](https://www.banggood.com/3D-Printed-25-Degree-Inclined-Fixed-Mount-Holder-Seat-for-Gopro-Session-4-or-5-Runcam-3-RunCam-3S-Camera-FPV-RC-Drone-p-1205394.html)
* [Mount C](https://www.banggood.com/IFlight-Nazgul5-227mm-4S-6S-FPV-Racing-Drone-Spare-Part-for-Camera-Mount-for-Gopro-Hero-4-or-5-Session-TPU-3D-Printed-Protection-ND8-Filter-p-1552693.html)
* [Mount D](https://www.banggood.com/Eachine-Wizard-X220HV-RC-Drone-Spare-Part-Camera-Mount-30-Supports-Runcam-3-3S-for-Gopro-Session-p-1393230.html)

Mount A is the best selling, is flexible (as shown in [this photo](https://imgaz.staticbg.com/customers_images/newlarge/e5/1b/2020052712030844-1166269.jpg)) and looks like the obvious choice for this style of mount.

#### Mounts for classic style GoPro cameras

By classic style, I mean the classic wide, i.e. non-cube, style of GoPro action camera:

* [Adjustable mount](https://www.banggood.com/GEPRC-FPV-Camera-Adjustable-Fix-Mount-for-Gopro-Runcam-GEP150-GEP180-GEP210-Frame-Kit-p-1058697.html)
* [FPV-style fixed mount](https://www.banggood.com/GE-FPV-TPU-30-3D-Printed-Soft-Camera-Mount-for-XIAOYIGopro-p-1180977.html)

### Liquid electrical tape

An interesting alternative to electrical tape is liquid electrical tape (described [here](https://oscarliang.com/tool-spare-multirotors-quadcopter-equipment/)). In the US the main brands for this seems to be Star Brite and Plasti Dip.

**Important:** liquid electrical tape seems to be very unpleasant stuff - only use it wearing disposable _latex_ gloves in a very well ventilated space. Really!

The Plasti Dip black [liquid electrical tape](https://plastidip.com/our-products/liquid-tape/) is easily available from Amazon.com and other US suppliers. In Europe, it's a little harder to come but you can buy it direct from their European distributer [here](https://plastidip-sale.com/Plasti-Dip-Liquid-Electrical-Tape-schwarz-118ml-4oz-black) (despite the name, they seem to be a distributer rather than a subsidiary). This distributer also sells via the EU Amazon sites. There's also a [spray variant](https://plastidip-sale.com/Plasti-Dip-Liquid-Tape-Spray-175-ml-Schwarz-Aerosol-6-oz-Black).

Confusingly, Plasti Dip products are also labelled with the Performix brand - Performix seems to be the parent company and Plasti Dip a brand for solutions intended for home use.

In Europe, a brand called Mibenco seems to be more easily available (and comes in far more colors that Plasti Dip), e.g. here from Conrad:

* [Matt black paint](https://www.conrad.com/p/mibenco-pur-liquid-rubber-coating-colour-black-matt-72829005-175-g-1297872)
* [Matt black spray](https://www.conrad.com/p/mibenco-liquid-rubber-coating-spray-colour-black-matt-71429005-400-ml-1297810)

Oddly, Conrad doesn't sell the paint form from their .ch store and incorrectly classify the spray as a silicone sealant.

**Important:** silicone sealants are popular for home repairs but they're not suitable for use with electronics - in sealant form they release acetic acid which is corrosive for electronics (although there do also appear to be _neutral cure_ silicone sealants that are suitable when installing things like AC units).

### Heat shrink tubing

Banggood doesn't seem to be a great source for heat shrink tubing for things thicker than cables, there's this:

* [30mm-to-19mm tubing](https://www.banggood.com/2M-Flat-29_5MM-18_5MM-PVC-Heat-Shrink-Tubing-For-18650-18500-Battery-p-954761.html)
* [50mm or 80mm (pre-shrinking size) tubing](https://www.banggood.com/50mm80mm-PVC-Transparent-Heat-Shrink-Tube-for-2-4S-Lipo-Battery-p-1382110.html)

There don't seem to be many sellers providing a range of sizes under a single listing. There is this [one](https://www.banggood.com/1m-PVC-Heat-Shrink-Tubing-Black-30-or-40-or-46-or-50-or-60-or-70-or-86mm-Wide-For-Lipo-Battery-p-1092332.html) selling black heat shrink in sizes 30mm to 86mm.

Ebay seems to be a better source. E.g. these 2 EU based sellers:

* [Seller A](https://www.ebay.co.uk/itm/PVC-Heat-Shrink-Tubing-Wrap-RC-Battery-Pack-17mm-150mm-LiPO-NiMH-NiCd-UK/361275492238)
* [Seller B](https://www.ebay.co.uk/itm/Lay-Flat-PVC-Heat-Shrink-Tubing-Wrap-Battery-Pack-10-5mm-320mm-LiPO-NiMH-NiCd/252484196073)

Or these China based sellers:

* [Seller A](https://www.ebay.co.uk/itm/1-Meter-PVC-Heat-Shrink-Tubing-Wrap-RC-Battery-Pack-7mm-450mm-LiPO-NiMH-NiCd/401355403468)
* [Seller B](https://www.ebay.co.uk/itm/Clear-7mm-300mm-PVC-Heat-Shrink-Tubing-RC-Battery-Sleeving-Wrap-LiPO-NiMH-NiCd/324025422489)
* [Seller C](https://www.ebay.co.uk/itm/PVC-Heat-Shrink-Tubing-Wrap-RC-Battery-Pack-9-200mm-Flat-Size-Black-Blue-Clear/124263669316)

Reichelt sell 200mm lengths of heat shrink that shrinks to 4.8mm, 6.4mm and 9.5mm (as well as the usual smaller sizes) - see [here](https://www.reichelt.com/de/en/heat-shrink-in-pieces-c5749.html).

Conrad sell heat shrink over a [far wider range](https://www.conrad.com/o/heat-shrink-tubes-0200231) of sizes (though in their filtering they often seem to have confused pre and post shink size).

### Video receivers

Oddy, the ROTG01 PRO lists for less than the plain ROTG01 on [Eachine's site](https://www.eachine.com/FPV-TRANSMITTER-&-RECEIVER-c-156.html).

[ROTG02 OTG FPV Receiver - Part 1 - Full Walkthrough & Configuration - YouTube](https://www.youtube.com/watch?v=mYITNilUaHc&feature=youtu.be&t=431)

[Eachine ROTG02 UVC OTG 5.8G 150CH Dual Antenna Audio FPV Receiver for Android Tablet Smartphone](https://www.eachine.com/Eachine-ROTG02-UVC-OTG-5_8G-150CH-Dual-Antenna-Audio-FPV-Receiver-for-Android-Tablet-Smartphone-p-1063.html)

For whatever reason, Eachine no longer list the R051 (the ROTG range is for Android, the R051 was for iOS) and it's no longer available on Banggood.

### Telemetry radio

[Transceiver Telemetry Radio Set V3,433MHz](https://shop.holybro.com/transceiver-telemetry-radio-set-v3_p1103.html)

[Holybro V3 Telemetry Radio 100mW 433MHz Receiver for RC Drone - $39.00 Free Shipping|GearBest.com](https://www.gearbest.com/receiver-transmitter/pp_009301755850.html)

[Holybro 100mW Transceiver Telemetry Radio Set V3 (433Mhz)](https://www.getfpv.com/holybro-100mw-transceiver-telemetry-radio-set-v3-433mhz.html)

[HolyBro 433Mhz 915Mhz 100mW Transceiver Radio Telemetry Set V3 for PIXHawk 4 Flight Controller Sale - Banggood.com](https://www.banggood.com/HolyBro-433Mhz-915Mhz-100mW-Transceiver-Radio-Telemetry-Set-V3-for-PIXHawk-4-Flight-Controller-p-1325021.html?ID=554541)

[Holybro 433Mhz 915Mhz 500mW Transceiver Radio Telemetry Set V3 for PIXHawk 4 Flight Controller Sale - Banggood.com](https://www.banggood.com/Holybro-433Mhz-915Mhz-500mW-Transceiver-Radio-Telemetry-Set-V3-for-PIXHawk-4-Flight-Controller-p-1325025.html?ID=554541)

### Sensors

[FrSky Smart Port Lipo Sensor FLVSS - US$18.99](https://www.banggood.com/FrSky-Smart-Port-Lipo-Sensor-FLVSS-p-929070.html)

### GPS

[Mini GPS Folding Antenna Base/Silver](https://hobbyking.com/en_us/mini-gps-folding-antenna-base-silver.html)

[Mini GPS Folding Antenna Base Set/Black](https://hobbyking.com/en_us/mini-gps-folding-antenna-base-set-black.html)

[GPS Seat Folding Bracket Mounting Set Holder Folding Antenna Base For Radio Remote Controller Aircraft Model Rc Toys-in Parts & Accessories from Toys & Hobbies on Aliexpress.com | Alibaba Group](https://www.aliexpress.com/item/GPS-Seat-Folding-Bracket-Mounting-Set-Holder-Folding-Antenna-Base-For-Radio-Remote-Controller-Aircraft-Model/32838863518.html)

### Parallel charging

[LiPo Battery Parallel Charging Tutorial - Oscar Liang](https://oscarliang.com/parallel-charging-multiple-lipo/)

[Lumenier paraguard xt60 plug 4 port safe parallel charging board for 1-6s lipo battery Sale - Banggood.com](https://www.banggood.com/Lumenier-ParaGuard-XT60-Plug-4-Port-Safe-Parallel-Charging-Board-for-1-6S-Lipo-Battery-p-1700339.html)

[Power genius pg parallel charging board supports 5 packs of 2-6s lipo battery xt60 t plug Sale - Banggood.com](https://www.banggood.com/Power-Genius-PG-Parallel-Charging-Board-Supports-5-Packs-of-2-6S-Lipo-Battery-XT60-T-Plug-p-1141232.html?ID=510961)

[Amass v3 xt60 plug lipo parallel charger board for imax b6 charger Sale - Banggood.com](https://www.banggood.com/Amass-V3-XT60-Plug-Lipo-Parallel-Charger-Board-p-1031262.html)

### Dischargers

[3 in 1 diy resistor discharger for draining disposing battery Sale - Banggood.com](https://www.banggood.com/3-in-1-DIY-Resistor-Discharger-for-Draining-Disposing-Battery-p-1418862.html)

[An effective variable load automatic LiPo discharger - Page 26 - RC Groups](https://www.rcgroups.com/forums/showthread.php?2406395-An-effective-variable-load-automatic-LiPo-discharger/page26)

[Aokoda cellmeter 8 150w discharge module set with battery voltage tester buzzer Sale - Banggood.com](https://www.banggood.com/AOKoda-CellMeter-8-150W-Discharge-Module-Set-with-Battery-Voltage-Tester-Buzzer-p-1196807.html)

[Aokoda cellmeter 8 150w discharge module set with lipo battery balancer Sale - Banggood.com](https://www.banggood.com/AOKoda-CellMeter-8-150W-Discharge-Module-Set-with-Lipo-Battery-Balancer-p-1196376.html)

[Aokoda cellmeter 8 150w battery discharge module set for aokoda discharger Sale - Banggood.com](https://www.banggood.com/AOKoda-CellMeter-8-150W-Discharge-Module-Set-for-AOKoda-Discharger-p-1196377.html)

[Uruav ur4 0v / 3.0v-4.0v 6 grade lipo killer discharger for 1-6s lipo battery rc drone fpv racing Sale - Banggood.com](https://www.banggood.com/URUAV-UR4-0V-3_0V-4_0V-6-Grade-Lipo-Killer-Discharger-for-1-6S-Lipo-Battery-RC-Drone-FPV-Racing-p-1393759.html)

[Review: URUAV Lipo Killer | Put Charged Batteries in Storage - Oscar Liang](https://oscarliang.com/uruav-lipo-killer/)

[The Perfect Lipo discharge tool? URUAV Lipo Discharger how to Hack DIY | IntoFPV Forum](https://intofpv.com/t-the-perfect-lipo-discharge-tool-uruav-lipo-discharger-how-to-hack-diy)

[DIY Resistor Discharger for Draining/Disposing Batteries - Oscar Liang](https://oscarliang.com/resistor-discharger-lipo/)

[0v lipo killer discharger for lipo battery with xt60 & xt30 plug rc drone fpv racing Sale - Banggood.com](https://www.banggood.com/0V-Lipo-Killer-Discharger-for-Lipo-Battery-with-XT60-XT30-Plug-RC-Drone-FPV-Racing-p-1387952.html)

### Connecting ESCs to motors

[Image](https://cdn.shopify.com/s/files/1/0076/7098/8859/t/6/assets/description_image_pre_soldered_jpg) showing what you're aiming for when soldering bullet connectors between motors and ESCs (unfortunately the image is served as `application/octet-stream` so it downloads and can't be displayed inline).

[328pcs 2:1 Polyolefin Halogen-Free Heat Shrink Tube Sleeving 5 Color 8 Size - US$3.39](https://www.banggood.com/Soloop-328pcs-21-Polyolefin-Halogen-Free-Heat-Shrink-Tube-Sleeving-5-Color-8-Size-p-969574.html)

[127pcs 7Sizes Polyolefin Halogen-Free Heat Shrink Tubing Tube Sleeving Kit - US$2.99](https://www.banggood.com/DANIU-127pcs-7Sizes-Polyolefin-Halogen-Free-Heat-Shrink-Tubing-Tube-Sleeving-Kit-p-1169515.html)

[10x 3.5mm Gold Plated Bullet Banana Connector Plug For ESC Battery Motor - US$1.99](https://www.banggood.com/Wholesale-10x-3_5mm-Gold-Bullet-Banana-Connector-Plug-For-ESC-Battery-Motor-p-51435.html)

[2 Meter Black Silicone Wire Cable 10/12/14/16/18/20/22AWG Flexible Cable - US$1.50](https://www.banggood.com/DANIU-2-Meter-Black-Silicone-Wire-Cable-10121416182022AWG-Flexible-Cable-p-1170287.html?ID=517601))

[Typical wire gauge for connecting ESCs, Motors, Batteries - RC Groups](https://www.rcgroups.com/forums/showthread.php?2132883-Typical-wire-gauge-for-connecting-ESCs-Motors-Batteries)

[Electrical Wires and Connectors for Quadcopter - Oscar Liang](https://oscarliang.com/wire-awg-chart-quadcopter-rc/)

The MR30 connector seems to be specifically for connecting ESCs to motors. The MR30 is the standard connector while the MR30PB is suitable for soldering directly to a board rather than to wires. Note that that if you buy a set of MR30PB connectors, you'll also need a set of plain MR30 connectors as neither the male nor female MR30PB connectors are designed to take wires.

[5 Pairs Amass MR30 Connector Plug With Sheath Female & Male Sale - Banggood.com](https://www.banggood.com/5-Pairs-Amass-MR30-Connector-Plug-With-Sheath-Female-Male-p-1040876.html)

[5 Pairs Amass MR30PB Connector Plug Female & Male Sale - Banggood.com](https://www.banggood.com/5-Pairs-Amass-MR30PB-Connector-Plug-Female-Male-p-1040874.html)

[5 Pair 2mm Gold Bullet Connectors Banana Plugs For RC Car/Drone Lipo Battery Sale - Banggood.com](https://www.banggood.com/5-Pair-2mm-Gold-Bullet-Connectors-Banana-Plugs-For-RC-CarDrone-Lipo-Battery-p-1046104.html)

### Skids

[4PCS Landing Skid Gear Frame Anti-vibration M3 Sponge for 210 220 250 RC Drone FPV Racing Multi Rotor Sale - Banggood.com](https://www.banggood.com/4PCS-Landing-Skid-Gear-Frame-Anti-vibration-M3-Sponge-for-ZMR250-QAV250-QAV210-RC-Multirotor-p-1063891.html?ID=224)

[4pcs landing skid gear frame anti-vibration m3 sponge for 210 220 250 rc drone fpv racing multi rotor Sale - Banggood.com](https://www.banggood.com/4PCS-Landing-Skid-Gear-Frame-Anti-vibration-M3-Sponge-for-210-220-250-RC-Drone-FPV-Racing-Multi-Rotor-p-1063891.html?ID=224)

[Realacc 50pcs landing skid gear frame anti-vibration m3 sponge for zmr250 qav250 210 rc drone fpv racing Sale - Banggood.com](https://www.banggood.com/Realacc-50PCS-Landing-Skid-Gear-Frame-Anti-vibration-M3-Sponge-for-ZMR250-QAV250-210-RC-Drone-FPV-Racing-p-1081168.html?ID=224)

### Gimbals

Feiju comes with session adapter (I think) but exposes no control pins - [FeiyuTech Feiyu WG2X Splash-proof 3-axis Wearable Gimbal Stabilizer For GoPro He - US$177.58](https://www.banggood.com/FeiyuTech-Feiyu-WG2X-Splash-proof-3-axis-Wearable-Gimbal-Stabilizer-For-GoPro-Hero-7-6-5-4-Session-Sony-RX0-YI-4K-Sport-Camera-p-1560183.html)

[tarot gimbal - Buy tarot gimbal with free shipping | Banggood.com](https://www.banggood.com/search/tarot-gimbal.html)

[Feiyu tech wg gimbal replace board adapter mount for aee xiaomi yi sj camera rc drone Sale - Banggood.com](https://www.banggood.com/Feiyu-Tech-WG-Gimbal-Replace-Board-Adapter-Mount-for-AEE-XiaoMi-Yi-SJ-Camera-p-990563.html)

[Walkera g-2d brushless gimbal metal version for ilook/gopro hero 3 camera on walkera qr x350 pro rc Sale - Banggood.com](https://www.banggood.com/Walkera-G-2D-Brushless-Gimbal-Metal-Version-For-iLookGoPro-Hero-3-Camera-on-Walkera-QR-X350-Pro-RC-p-1192161.html)

[2 axis brushless action camera gimbal with controller support remote control for gopro fpv racing rc drone Sale - Banggood.com](https://www.banggood.com/2-Axis-Brushless-Action-Camera-Gimbal-with-Controller-Support-Remote-Control-for-GoPro-FPV-Racing-RC-Drone-p-908068.html)

[3 axis brushless camera gimbal cnc metal with controller support 3-4s 180g light for gopro osmo action cameras fpv rc drone Sale - Banggood.com](https://www.banggood.com/3-Axis-Brushless-Camera-Gimbal-CNC-Metal-With-Controller-Support-3-4S-180g-Light-for-GoPro-OSMO-Action-Cameras-FPV-RC-Drone-p-1030046.html)

[100% New Gimbal With Camera For Mi Drone 4K Camera with Gimbal Accessories For RC Quadcopter Camera Drone FPV Racer Spare Parts|Parts & Accessories| - AliExpress](https://www.aliexpress.com/item/4000168115330.html)

Fr. 50 - [Eken](https://www.eken.com/action-camera) - the current model is the [H9R](https://www.banggood.com/EKEN-H9R-Sport-Camera-Action-4K-Ultra-HD-2_4G-Remote-WiFi-170-Degree-Wide-Angle-p-1057866.html?ID=227).

Fr. 144 - Xiami has the [Mi Action 4K](https://www.digitec.ch/de/s1/product/xiaomi-mi-action-4k-30p-4k-actionkamera-10295624)

GoPro and DJI have action cameras starting in the Fr. 200+ range.

### Gimbal controller

[ENSYS SToRM32 V3.3 Board (Beta) – ENSYS](https://www.ensys.lt/product/ensys-storm32-v3-3-board-beta/)

[OlliW's Bastelseiten » STorM32 BGC: 3-Achsen STM32 Brushless Gimbal Controller](http://www.olliw.eu/2013/storm32bgc/)

[Getting Started - STorM32-BGC Wiki](http://www.olliw.eu/storm32bgc-wiki/Getting_Started)

### Helping hands

[Metal Base Universal 4 Flexible Arms Soldering Station PCB Fixture Helping Hands - US$34.99](https://www.banggood.com/Metal-Base-Universal-4-Flexible-Arms-Soldering-Station-PCB-Fixture-Helping-Hands-Four-Hand-p-1282415.html)

[Helping Hands - Page 1](https://www.eevblog.com/forum/projects/helping-hands/msg1129221/#msg1129221)

[QuadHands Helping Hands Soldering Third Hand Tool | 4 Flexible Metal Arms Are Easy to Position | Rotating Stainless Steel Clamps | Made in USA - Professional Grade - Power Soldering Accessories - Amazon.com](https://www.amazon.com/QuadHands-Helping-Hands-Third-Soldering/dp/B00GIKVP5K/)

[Amazon.com: QuadHands Workbench Helping Hands Soldering Third Hand Vise | 4 Magnetic Based Flexible Metal Arms Can Be Mounted Anywhere on The 6" x 9" Solid Steel Base | Designed and Made in The USA: Arts, Crafts & Sewing](https://www.amazon.com/dp/B01MTWLF2Q/ref=emc_b_5_i)

[Helping Hands - McPappy Racing](http://www.mcpappyracing.com/store/products/Helping-Hands.html)

[Third-Hand with Soldering Station, Standard Double - GRS](https://grs.com/product/third-hand-with-soldering-station-standard-double/)

[Tarot tl3t02 t-3d iv 3 axis brushless gimbal for hero 4 session camera for rc drone fpv airplane Sale - Banggood.com](https://www.banggood.com/Tarot-TL3T02-T-3D-IV-3-Axis-Brushless-Gimbal-for-Hero-4-SESSION-Camera-for-RC-Drone-FPV-Airplane-p-1090577.html)

### Battery top plate

TL65B03:

* [Tarot 4 axis Battery Plate Tarot 650 TL65B03|tarot 650|battery platetarot plate - AliExpress](https://www.aliexpress.com/item/902919319.html)
* [F05551 Tarot 3K Carbon Battery Mount Plate TL65B03 For FY 650 Folding Main Frame set Quadcopter|plate battery|plate mountplate set - AliExpress](https://www.aliexpress.com/item/32531530328.html)
* [Tarot 3K Carbon Battery Mount Plate TL65B03 For FY 650 Folding Main Frame Kit DIY RC Drone Quadcopter F05551|mount license plate|mount platemounting base plate - AliExpress](https://www.aliexpress.com/item/32591758023.html)
* [F05551 Tarot 3K Carbon Battery Mount Plate TL65B03 For FY 650 Folding Main Frame set Quadcopter|mount license plate|mount platemounting base plate - AliExpress](https://www.aliexpress.com/item/32340638585.html)

![mounted battery plate](https://imgaz.staticbg.com//images/upload/2012/chenjianwei/SKU092984.114.jpg) (from product page for [Tarot IRON MAN 650 FRAME TL65B01](http://www.tarotrc.com/Product/Detail.aspx?Lang=en&Id=dd90dfdb-4679-4d70-a302-98da3040465d)).

Potential plates for mounting on top plate, with battery underneath and Pixhawk 4 on top:

* [TL15T01 113x68mm plate](http://www.tarotrc.com/Product/Detail.aspx?Lang=en&Id=2bb91d82-4c95-495b-80ae-1a2e9e185c5a)
* [TL65B03 125x65mm plate](http://www.tarotrc.com/Product/Detail.aspx?Lang=en&Id=926d7b7b-aa85-4444-a9f7-a38bcc3d853e)

You'd need standoffs to go with these plates, see standoffs section below.

The Pixhawk 4 is 84x44x12mm - the TL65B03 has bolt holes at its corners and looks best if one is planning to drill holes in the top plate (and doesn't want to use slots that are really meant for battery cables).

Although the TL65B03 might also be good as the S500 has a slot running top to bottom and one running left to right which matches the orientation of the bolt holes on the TL65B03 (whereas the TL65B03 has bolt holes in its corners which would require drilling holes).

Both of these plates may actually be a bit too large for the S500 top - the top plate is about 120x120mm but the sides curve in to give a central area that's only 100x100mm.

The bottom plate is more substantial - it's 100mm wide (with no curving in) and 200mm long.

### Battery plate bottom

The alternative idea would be to create a space under the bottom plate, e.g. with a TL68B14 at front and back, essentially creating a landing surface.

* [TL68B14 100x44mm plate](http://www.tarotrc.com/Product/Detail.aspx?Lang=en&Id=7ca67b46-ff40-428a-b4e7-2a28c09d2de8)
* [Tarot fy680 6 axis aircraft flip battery rack tl68b14 Sale - Banggood.com](https://www.banggood.com/Tarot-FY680-6-Axis-Aircraft-Flip-Battery-Rack-TL68B14-p-91550.html)

And then either the 65mm or 40mm damping set:

* [Tarot X8 metal silicone damping Seat TL8X007 Tarot Multirotor Parts Free Shipping with Tracking|tarot x8|metal tracks - AliExpress](https://www.aliexpress.com/item/32285695166.html)
* [Tarot TL8X006 lengthened metal silicone damping Seat for TL65S01 tarot 650 sport Free Shipping with Tracking|metal tracks|tarot 650 sporttarot 650 - AliExpress](https://www.aliexpress.com/item/32221799366.html)

FlyingTech also has the [TL8X006](https://www.flyingtech.co.uk//frames-props-parts-accessories/tarot-shock-absorbing-tube-clamp-10-12mm-2pcs-tl8x006) and the [TL8X007](https://www.flyingtech.co.uk//frames-props-parts-accessories/tarot-shock-absorbing-tube-clamp-10-12mm-2pcs-tl8x007).

Note: The TL8X017 plate that I was considering as a bottom plate is far to big for the S500 at 198x154mm.

### Helicopter skids

Yet another idea would be to use helicopter skids:

[Tarot 450 pro rc helicopter parts landing gear set tl45050-02 Sale - Banggood.com](https://www.banggood.com/Tarot-450PRO-RC-Helicopter-Parts-Landing-Gear-Set-TL45050-02-p-937919.html)

[Alzrc landing skid for t-rex 450 pro devil 450 465 480 helicopter Sale - Banggood.com](https://www.banggood.com/ALZRC-Landing-Skid-For-T-REX-450-Pro-Devil-450-465-480-p-990767.html?ID=226)

### Standoffs

[Online Shopping Fasteners at best prices in Banggood](https://www.banggood.com/Wholesale-Attribute-Fasteners-c-12093-s-5500v51047-5049v47892.html)

[Search results for: 'aluminium spacer'](https://hobbyking.com/en_us/catalogsearch/result/?q=aluminium%20spacer#q=aluminium%20spacer&idx=hbk_live_magento_en_us_products_hbk_price_stock_7_group_0_asc)

### Miscellaneous

[2M PVC Heat Shrink Tubing For 18650 18500 Battery Flat Wide 29.5MM Round 18.5MM - US$2.08](https://www.banggood.com/2M-Flat-29_5MM-18_5MM-PVC-Heat-Shrink-Tubing-For-18650-18500-Battery-p-954761.html?ID=3153)

[Turnigy Heat Shrink Tube 25mm Clear (1m)](https://hobbyking.com/en_us/turnigy-heat-shrink-tube-25mm-x-1mtr-clear.html)

[RJX HOBBY Magic Tape Tie Down Strap for RC Battery Sale - Banggood.com](https://www.banggood.com/RJX-HOBBY-Magic-Tape-Tie-Down-Strap-for-RC-Battery-p-1134012.html?ID=513344529789)

[XT60 Male Plug 12AWG 10cm With Wire - US$1.99](https://www.banggood.com/XT60-Male-Plug-10AWG-10cm-With-Wire-p-77537.html)

[Suleve™ ZT03 100pcs 100X2.5mm Nylon Zip Tie Black White for Cable Core Wire S - US$1.69](https://www.banggood.com/100pcs-100X2_5mm-Nylon-Cable-Core-Wire-Zip-Tie-Strap-BlackWhite-p-988026.html?ID=233)

[Suleve™ ZT01 900pcs 100x2mm Self Locking Nylon Cable Wire Zip Ties 6 Colors - US$9.99](https://www.banggood.com/900pcs-100x2mm-Self-Locking-Nylon-Cable-Wire-Zip-Ties-6-Colors-p-1057854.html)

[6mm Braided Expandable Auto Wire Cable Sleeving High Density Sheathing - US$0.94](https://www.banggood.com/6mm-Braided-Expandable-Auto-Wire-Cable-Sleeving-High-Density-Sheathing-p-985853.html?ID=45763)

[4mm Braided Expandable Auto Wire Cable Gland Sleeving High Density Sheathing - US$1.11](https://www.banggood.com/4mm-Braided-Expandable-Auto-Wire-Cable-Sleeving-High-Density-Sheathing-p-934355.html?ID=45763)

[Battery Silicon Anti-Slip Mat 90x35x1.5mm (Black)](https://hobbyking.com/en_us/battery-silicon-anti-slip-mat-90x35x1-5mm-black.html)

[NanoPi NEO Core and NEO Core2 Allwinner H3/H5 Systems-on-Module Launched for $7.99 and Up](https://www.cnx-software.com/2017/12/13/nanopi-neo-core-and-neo-core2-allwinner-h3-h5-systems-on-module-launched-for-7-99-and-up/)

### 200mm table ties

[10pcs 200mm Self-locking Nylon Wire Tie Cable Strap for RC Helicopter Parts Sale - Banggood.com](https://www.banggood.com/Self-Locking-Nylon-Wire-Tie-Cable-Strap-for-RC-Helicopter-Parts-p-1179970.html?ID=521800)

[500pcs Milk White Nylon Cable Ties Zip Ties 150mm 200mm - US$6.20](https://www.banggood.com/500pcs-Milk-White-Nylon-Cable-Ties-Zip-Ties-4x150mm200mm-p-922054.html)

[100 Pcs White Nylon Cable Zip Ties Nylon Cable Ties Wraps Zip Tie - US$2.29](https://www.banggood.com/100-Pcs-White-Nylon-Cable-Zip-Ties-Nylon-Cable-Ties-Wraps-Zip-Tie-p-1318085.html?ID=49640)

### Setting expo in Ardupilot

[Copter: acro throttle and yaw expo and smoother manual throttle by rmackay9 · Pull Request #4973 · ArduPilot/ardupilot](https://github.com/ArduPilot/ardupilot/pull/4973)

[Acro Mode — Copter documentation](https://ardupilot.org/copter/docs/acro-mode.html)

### Cases

[Series: G-Mixerbag - Gator Cases](https://www.gatorcases.com/g-mixerbag/)

[Gator G-MIXERBAG-2123 Padded Mixer And Equipment Bag | Gear4music](https://www.gear4music.ch/de/PA-DJ-and-Lichttechnik/Gator-G-MIXERBAG-2123-Padded-Mixer-And-Equipment-Bag/2ABM)

[Gator G-MIXERBAG-1818 Padded Mixer And Equipment Bag | Gear4music](https://www.gear4music.ch/de/PA-DJ-and-Lichttechnik/Gator-G-MIXERBAG-1818-Padded-Mixer-And-Equipment-Bag/2AAM)

[B&W Outdoor Case Typ 7800 2 Rollen günstig kaufen | Koffermarkt](https://www.koffermarkt.com/b-w-outdoor-case-typ-7800-2-rollen/)

### Uncategorized

[arf-drone/parts.md at master · george-hawkins/arf-drone](https://github.com/george-hawkins/arf-drone/blob/master/parts.md)

[MissionPlanner issue - it and Mono will never work on 64bit](https://github.com/ArduPilot/MissionPlanner/issues/2244#issuecomment-627098395)

[Ulanzi Tripod Mount Cell Phone Clipper Vertical Bracket Clip Holder 360 Degree Adapter Sale - Banggood.com](https://www.banggood.com/Ulanzi-Tripod-Mount-Cell-Phone-Clipper-Vertical-Bracket-Clip-Holder-360-Degree-Adapter-p-1139977.html)

[standoff - Buy standoff with free shipping | Banggood.com](https://www.banggood.com/search/standoff/0-0-0-1-4-60-0-price-0-0_p-1.html)

[Rjxhobby 6mmx5m expandable braided cable wire sleeve cable sheath mesh Sale - Banggood.com](https://www.banggood.com/RJXHOBBY-6mmX5m-Expandable-Braided-Cable-Wire-Sleeve-Cable-Sheath-Mesh-p-1607988.html?ID=6269620)

[18" x 22" Mixer Case-G-MIX-L 1822 - Gator Cases](https://www.gatorcases.com/products/mixer/lightweight-polyfoam-mixer-cases/gl-mixer/18-x-22-mixer-case-g-mix-l-1822/)

[9455 carbon fiber low noise foldable 2-blade propeller props for dji phantom 1/2/3 rc drone Sale - Banggood.com](https://www.banggood.com/9455-Carbon-Fiber-Low-Noise-Foldable-2-blade-Propeller-Props-for-DJI-Phantom-123-RC-Drone-p-1351516.html)

[Tarot camera mount suspension hook tl68a0 for multi rotor part Sale - Banggood.com](https://www.banggood.com/Tarot-Camera-Mount-Suspension-Hook-TL68A0-For-Multi-Rotor-Part-p-90162.html)

[⁣Tarot 680 Pro Carbon Fibre Battery Mount - 10mm Clips | Flying Tech](https://www.flyingtech.co.uk/frames-props-parts-accessories/tarot-680-pro-carbon-fibre-battery-mount-10mm-clips)

Interesting alternatives to ArduPilot for indoor autonomous flight:

[STEM ranging bundle – Bitcraze Store](https://store.bitcraze.io/products/stem-ranging-bundle)

[ArduBee Is a Small 3” Quadrotor Drone Equipped with ArduPilot - Hackster.io](https://www.hackster.io/news/ardubee-is-a-small-3-quadrotor-drone-equipped-with-ardupilot-a3a14f30547a)

### Stereo cameras

[OpenCV AI Kit by OpenCV — Kickstarter](https://www.kickstarter.com/projects/opencv/opencv-ai-kit/description)

[Intel RealSense T265 — Copter documentation](https://ardupilot.org/copter/docs/common-vio-tracking-camera.html)

[Intel RealSense T265 + ArduPilot (No GPS) - YouTube](https://www.youtube.com/watch?v=BhU3ly_wkx8)

[OpenCV AI Kit (OAK) - ROS Projects - ROS Discourse](https://discourse.ros.org/t/opencv-ai-kit-oak/15406/15)

### GPS for smaller quads

[How to Setup GPS in Betaflight / Mini Quad - Oscar Liang](https://oscarliang.com/gps-mini-quad/)

[Thiner BN-880Q](https://beitian.en.made-in-china.com/product/oCYmyFlrMsWb/China-Beitian-Compass-Qmc5883L-AMP2-6-Pix4-Pixhawk-Flight-Control-Glonass-GPS-Module-Bn-880q.html)

### Pixhawk 4 PDB solutions - I'm no longer sure what I was aiming for here

[1m PVC Heat Shrink Tubing Black 30/40/46/50/60/70/86mm Wide For Lipo Battery Sale - Banggood.com](https://www.banggood.com/1m-PVC-Heat-Shrink-Tubing-Black-30404650607086mm-Wide-For-Lipo-Battery-p-1092332.html?ID=522617)

[Turnigy Heat Shrink Tube 100mm Clear (1m)](https://hobbyking.com/en_us/turnigy-100mm-heat-shrink-tube-1m-clear.html)

[FreeCAD/FreeCAD: This is the official source code of FreeCAD, a free and opensource multiplatform 3D parametric modeler](https://github.com/FreeCAD/FreeCAD)

[openscad/openscad: OpenSCAD - The Programmers Solid 3D CAD Modeller](https://github.com/openscad/openscad)

[digital caliper - Buy Cheap digital caliper - From Banggood](https://www.banggood.com/buy/digital-caliper/0-0-0-1-4-44-0-price-0-0_p-1.html)

[Tutorial on how to use OpenSCAD for 3D printing.](https://www.sculpteo.com/blog/2015/09/12/using-openscad-for-3d-printing-is-awesome/)

[Suleve™ M3NH2 M3 Nylon Screw Black Hex Screw Nut Nylon PCB Standoff Assortment - US$6.19](https://www.banggood.com/260pcs-M3-Nylon-Black-Hex-Screw-Nut-M-F-Stand-off-Set-Assortment-Kit-Box-p-998983.html)

[Suleve™ M3NH8 M3 Nylon Screw White Hex Screw Nut Nylon PCB Standoff Assortment - US$6.39](https://www.banggood.com/150pcs-M3-White-Hex-Spacers-Nylon-Screw-Nut-Washer-Assortment-Standoff-Kit-Stand-off-Plastic-p-1000332.html)

[10 x 15cm 60 Cores Servo Extension Wire Cable For Futaba JR - US$2.49](https://www.banggood.com/10-x-15cm-60-Cores-Servo-Extension-Wire-Cable-For-Futaba-JR-p-909171.html)

[5 Pairs 100mm 10cm JST Male And Female Plug Connector Cable ESC Extension Cable Sale - Banggood.com](https://www.banggood.com/5-Pairs-200mm-20cm-JST-Male-And-Female-Plug-Connector-Cable-ESC-Extension-Cable-p-1125803.html)

[DIY JST Male Female Connector-plug WIth Cables for RC LIPO Battery FPV Drone Quadcopter Sale - Banggood.com](https://www.banggood.com/DIY-JST-Male-Female-Connector-Plug-WIth-Cables-for-RC-LIPO-Battery-FPV-Drone-Quadcopter-p-1080392.html)

[LS-300 220V 300W DIY Electric Heat Shrink Gun Power Tool Hot Air Temperature Gun - US$11.11](https://www.banggood.com/DANIU-220V-300W-DIY-Electric-Heat-Shrink-Gun-Power-Tool-Hot-Air-Temperature-Gun-with-Supporting-Seat-Plastic-FIMO-p-1025199.html)

[DIY Receiver Mount and Protection Board 45 x 45mm Mounting](https://hobbyking.com/en_us/diy-receiver-mount-and-protection-board-45-x-45mm-mounting-2.html)

[DIY Receiver Mount and Protection Board 45 x 45mm Mounting](https://hobbyking.com/en_us/diy-receiver-mount-and-protection-board-45-x-45mm-mounting.html)

[LCD 150mm Electronic Digital Vernier Caliper - US$13.49](https://www.banggood.com/Wholesale-LCD-150mm-Electronic-Digital-Vernier-Caliper-p-63179.html)

[HobbyKing™ Digital Vernier Calipers 150mm](https://hobbyking.com/en_us/hobbykingtm-digital-vernier-calipers-150mm.html)

[Cable Ties 160mm x 2.5mm White (100pcs)](https://hobbyking.com/en_us/cable-ties-160mm-x-2-5mm-white-100pcs.html)

### Random

[Suleve™ M3NR1 M3 Nylon Screw White Nylon Screws Bolt & Nuts Assortment Kit 160 - US$5.99](https://www.banggood.com/160pcs-M3-White-Nylon-Screws-8-Sizes-Assortment-Stand-off-Bolt-Nuts-Kit-p-1000807.html)

[Suleve™ M3CH3 M3 Carbon Steel Allen Bolt 4-25mm Button Head Hex Socket Cap Scr - US$6.55](https://www.banggood.com/240pcs-M3-DIN912-Hex-Socket-Head-Cap-Screw-Nut-Assorted-Kits-4-25mm-p-1074609.html)

[OpenMV | Small - Affordable - Expandable](https://openmv.io/)

[Pixhawk 4 Wiring Quickstart · PX4 User Guide](https://docs.px4.io/en/assembly/quick_start_pixhawk4.html)

[Issues · ArduPilot/ardupilot · GitHub](https://github.com/ArduPilot/ardupilot/labels/ChibiOS)

[ChibiOS: Missing Features · Issue #8109 · ArduPilot/ardupilot · GitHub](https://github.com/ArduPilot/ardupilot/issues/8109)

---

JST related products (the red two pin connectors found on smaller batteries):

* [pair of JST pigtails - one male, one female](https://www.banggood.com/Wholesale-2-Pairs-15cm-JST-Connector-Plug-With-Connect-Cable-For-RC-BEC-ESC-Battery-p-50769.html)
* [JST to bullet connector (for charger)](https://www.banggood.com/AMASS-JST-Plug-Connector-20AWG-30cm-Charging-Cable-Wire-p-1001690.html)
* [JST female to male 2S balance connector](https://hobbyking.com/en_us/2s-xh-balance-plug-to-2-pin-jst-adapter-2pcs.html)
* [JST female to 5 JST male splitter](https://www.banggood.com/Wholesale-3_7V-Li-Po-Battery-JST-Plug-1-to-5-Charging-Cable-For-V959-V212-V222-p-67575.html)
* [JST male to 2 JST female splitter](https://www.banggood.com/JST-Plugs-2-Male-1-Female-3-Plugs-Connector-p-77544.html)
* [JST extension cable with on/off switch](https://www.banggood.com/On-or-off-Switch-With-JST-Plug-For-RC-Car-Model-DIY-Parts-p-922670.html)
* [Another JST extension cable with on/off switch](https://www.banggood.com/OnOff-Switch-Connector-Plug-JST-Male-Female-Wire-For-RC-Li-po-Battery-p-77399.html)
