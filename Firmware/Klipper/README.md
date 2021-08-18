# Klipper configuration for BIQU B1XZ

Quick steps to get Klipper up and running:

1. Get a Raspberry Pi
2. Install Klipper
3. Copy the configuration files
4. Perform bed leveling
5. [Calibrate Extruder Steps/mm](https://mattshub.com/blogs/blog/extruder-calibration)
6. Optional (but recommended): tune [Resonance Compensation](https://www.klipper3d.org/Resonance_Compensation.html)
7. Optional (but recommended): tune [Pressure Advance](https://www.klipper3d.org/Pressure_Advance.html)

For more and complete info refer to [Klipper Documentation](https://www.klipper3d.org/Installation.html)

## Original Toolhead Settings

In order to use the configuration provided without hassle you need to replace the original BLTouch Mount with [This](https://www.thingiverse.com/thing:4564987).

If you want to use the original BLTouch mount you need to change the offsets value in printer.cfg, as well the safe home settings, tilt screw settings and mesh limits.

## Klipper Installation

For Klipper installation refer to [fluiddpi](https://docs.fluidd.xyz/installation/fluiddpi).

## Klipper Configuration

For Kipper configuration specific to the B1 the file **printer.cfg** is self explanatory.
The configuration file is splitted in various files in order 

## Slicer Settings

The general recommendation is to set the **Relative Extrusion**.

### Ultimaker Cura

Change the Start and End Gcode.
Go to Machine settings and set

**Start G-code:**

```
START_PRINT T_BED={material_bed_temperature_layer_0} T_EXTRUDER={material_print_temperature_layer_0}
M82 ;Only set this if you aren't using Relative Extrusion
```

Please note that you have to avoid **M82** command if you set Cura to use Relative Extrusion.

**End G-code:**

```
END_PRINT
```

### Prusa Slicer

Basically you can leave your configuration as is. Set 

**Printer Settings -> Start G-code**

```
START_PRINT T_EXTRUDER=[first_layer_temperature_0] T_BED=[first_layer_bed_temperature]
```

**Printer Settings -> End G-code**

```
END_PRINT

```
