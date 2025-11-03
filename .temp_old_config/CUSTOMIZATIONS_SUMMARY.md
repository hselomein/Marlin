# Ender 5 Plus Configuration Customizations Summary
## Firmware Version: bugfix-2.1.x (November 2, 2025)

## Machine Identity
- **Author**: Corey Davis, Ender-5 Plus
- **Machine Name**: Ender 5 Plus - SKRMiniE3V3
- **UUID**: 2b117734-6f34-421f-a189-e9d70cd08eaa

## Hardware
- **Motherboard**: BOARD_BTT_SKR_MINI_E3_V3_0
- **Serial**: Port 2, Baudrate 115200
- **Serial Port 2**: -1 (USB) enabled
- **Display**: CR10_STOCKDISPLAY + BTT TFT35 (dual mode)

## Stepper Drivers
- **All axes**: TMC2209 (X, Y, Z, E0)

## Motion Configuration
### Steps per Unit
- X: 80, Y: 80, Z: 800, E: 136.616 (calibrated)

### Max Feedrates
- X: 750, Y: 750, Z: 10, E: 75 mm/s
- **LIMITED_MAX_FR_EDITING**: Enabled
- Edit limits: X: 1000, Y: 1000, Z: 25, E: 150 mm/s

### Acceleration
- Printing: 750 mm/s²
- Retract: 1000 mm/s²
- Travel: 1000 mm/s²
- Max acceleration: X: 5000, Y: 5000, Z: 200, E: 500

### Jerk
- X: 20.0, Y: 20.0, Z: 0.3, E: 10.0

## Bed & Build Volume
- **Bed Size**: 350 x 350 mm
- **Z Max**: 405 mm
- **Y Min**: -1
- **X Home Dir**: 1 (Max)
- **Y Home Dir**: 1 (Max)
- **Axis Inversions**: X and Z inverted

## Endstops & Homing
- **Endstop Interrupts**: Enabled
- **Endstop Noise Threshold**: 4
- **Z Clearance for Homing**: 10 mm
- **Z After Homing**: 17 mm
- **Homing Feedrate**: X: 90*60, Y: 90*60, Z: 15*60 mm/min
- **Z Safe Homing**: Enabled

## Probe Configuration (BLTouch)
- **Probe Type**: BLTouch
- **Use Probe for Z Homing**: Enabled
- **Nozzle to Probe Offset**: X: -44, Y: -9, Z: -2.0
- **Probing Margin**: 20 mm
- **XY Probe Feedrate**: 200*60 mm/min
- **Z Probe Fast**: 12*60 mm/min
- **Multiple Probing**: 2
- **Z Clearance Deploy**: 3 mm
- **Z After Probing**: 17 mm
- **Repeatability Test**: Enabled (M48)

## Bed Leveling
- **Type**: AUTO_BED_LEVELING_BILINEAR
- **Grid Points**: 5x5
- **Restore Leveling After G28**: Enabled
- **Preheat Before Leveling**: Enabled (120°C nozzle, 50°C bed)
- **LCD Bed Leveling**: Enabled
- **LCD Probe Z Range**: 8 mm
- **LCD Bed Tramming**: Enabled
- **Bed Tramming Insets**: L:25, F:38, R:63, B:53 (mm)
- **Bed Tramming Use Probe**: Enabled
- **Bed Tramming Tolerance**: 0.1 mm

## Temperature Control
### Hotend PID (Auto-tuned)
- Kp: 42.7089
- Ki: 5.5037
- Kd: 82.8552

### Bed PID
- **PID Enabled**: Yes
- Kp: 129.4981
- Ki: 11.7299
- Kd: 953.1061

### Other Temp Settings
- **Extrude Min Temp**: 180°C
- **PID Functional Range**: 10°C
- **PID Autotune Menu**: Enabled
- **Thermal Protection Chamber**: Disabled

## Preheat Profiles
### Profile 1 (PLA)
- Hotend: 195°C
- Bed: 60°C

### Profile 2 (PETG)
- Hotend: 240°C
- Bed: 80°C

## Advanced Features
### Filament Management
- **Filament Runout Sensor**: Enabled
- **Advanced Pause Feature**: Enabled
- **Nozzle Park**: Front left position (X:10, Y:9, Z:20)
- **Filament Change (M600)**: Enabled
- **Purge Length**: 150 mm
- **Purge Feedrate**: 3 mm/s

### Linear Advance
- **Enabled**: Yes
- **K-Factor**: 0.056 (calibrated)

### Babystepping
- **BABYSTEPPING**: Enabled
- **BABYSTEP_XY**: Enabled
- **BABYSTEP_INVERT_Z**: Enabled (intuitive control)
- **DOUBLECLICK_FOR_Z_BABYSTEPPING**: Enabled
- **BABYSTEP_DISPLAY_TOTAL**: Enabled
- **BABYSTEP_ALWAYS_AVAILABLE**: Enabled
- **BABYSTEP_WITHOUT_HOMING**: Enabled
- **EP_BABYSTEPPING**: Enabled (M293/M294 support)

### Communication & Buffers
- **EMERGENCY_PARSER**: Enabled
- **ADVANCED_OK**: Enabled (buffer status reporting)
- **BUFSIZE**: 16 (command buffer)
- **BLOCK_BUFFER_SIZE**: 16 (motion planner buffer)
- **TX_BUFFER_SIZE**: 32 bytes (transmit buffer)
- **RX_BUFFER_SIZE**: 128 bytes (receive buffer)
- **SERIAL_OVERRUN_PROTECTION**: Enabled

### Progress & Time Display
- **SET_PROGRESS_MANUALLY**: Enabled (M73 support)
- **SET_REMAINING_TIME**: Enabled
- **SHOW_REMAINING_TIME**: Enabled on LCD

### Storage & Transfer
- **EEPROM Settings**: Enabled
- **EEPROM Init Now**: Enabled
- **SD Card Support**: Enabled
- **BINARY_FILE_TRANSFER**: Enabled
- **CUSTOM_FIRMWARE_UPLOAD**: Enabled

### Other Features
- **Individual Axis Homing Menu**: Enabled
- **E0 Auto Fan**: FAN1_PIN (hotend cooling)

## NeoPixel LEDs
- **Enabled**: Yes
- **Type**: NEO_GRB
- **Pixel Count**: 18
- **Startup Test**: Enabled
- **Case Light**: Enabled (turns on white at startup)
- **Case Light Menu**: Enabled (LCD control)

## Display Settings
- **Character Set**: WESTERN (instead of JAPANESE)

## Compilation Info
- **Last Successful Build**: November 3, 2025
- **Flash Usage**: ~46% (237KB / 516KB)
- **RAM Usage**: ~13% (19KB / 147KB)
- **Build Environment**: STM32G0B1RE_btt_xfer

## Notes
- Tramming sanity check disabled in source code (menu_bed_tramming.cpp) - physically verified probe reaches all points
- E-steps calibrated from 142 to 136.616 (~3.8% reduction)
- Buffer sizes optimized for TFT touch mode stability
- All settings tested and verified on hardware
