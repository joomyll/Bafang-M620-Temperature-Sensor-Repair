# Bafang-M620-Temperature-Sensor-Repair
This repository documents the investigation of a motor temperature sensing fault in the Bafang M620 (Ultra) mid-drive motor.

# Bafang M620 / Ultra – Motor Temperature Sensor Fault (Error 10)

## Investigation and Repair Documentation

This repository documents the investigation of a motor temperature sensing fault in the Bafang M620 (Ultra) mid-drive motor.

The purpose is to identify the original temperature sensor, understand the controller's temperature measurement circuit, and document a reliable repair procedure.

**Status: Work in progress – original sensor type not yet confirmed.**

---

## 1. Initial Symptoms

The motor initially developed an intermittent Error 10 fault.

The observed sequence was:

1. Error 10 (Motor temperature too high) started occurring intermittently.
2. The fault temporarily disappeared and the motor worked normally again.
3. Error 10 returned.
4. Eventually, the fault became permanent, even when the motor was cold.

This behaviour suggests a possible problem with the temperature sensor, its wiring, or the controller's temperature measurement circuit.

The intermittent nature of the original fault is an important observation and may indicate a developing sensor or connection failure.

## 2. Error Codes Observed

| Error code | Description | Observation |
|---|---|---|
| Error 10 | Motor temperature too high | Occurs with the original sensor |
| Error 11 | Motor temperature inside motor / sensor circuit fault | Occurs when the sensor is disconnected |

The different error codes suggest that the controller can distinguish between an open sensor circuit and a resistance interpreted as excessive motor temperature.

## 3. Resistance Measurements and Tests

The following tests have been performed:

| Test condition | Resistance | Controller response |
|---|---:|---|
| Original faulty sensor, room temperature | Approximately 1 kΩ | Error 10 |
| Sensor disconnected | Open circuit | Error 11 |
| Test resistor | 680, 470, 300, 270, 220 Ω | Temperature error disappears |
| Test resistor | 940 Ω | Error 10 |
| Test resistor | 100 Ω | Error 10 |

## 4. Possible Original Sensor: KTY84/130

The KTY84/130 silicon PTC temperature sensor is a candidate worth investigating.

Typical KTY84/130 resistance values:

| Temperature | Resistance |
|---:|---:|
| 0 °C | 498 Ω |
| 20 °C | 581 Ω |
| 25 °C | 603 Ω |
| 40 °C | 672 Ω |
| 60 °C | 773 Ω |
| 80 °C | 882 Ω |
| 90 °C | 940 Ω |
| 100 °C | 1000 Ω |

## 5. Current Conclusions

The observations suggest:

1. Error 10 may be caused by an incorrect temperature measurement rather than actual motor overheating.
2. The controller detects an open sensor circuit and reports Error 11.
3. A 680 Ω resistance is accepted by the controller.
4. A 940 Ω resistance triggers Error 10.
5. The original sensor may be a PTC rather than a conventional NTC.
6. KTY84/130 is a candidate requiring further investigation.

None of these observations alone confirms the original sensor specification.

## 6. Repair Objective

The objective is to identify a suitable replacement sensor and restore the original motor temperature protection.

A permanent fixed resistor is not an acceptable repair because it disables meaningful temperature monitoring and can allow motor overheating without warning.

The final repair procedure will be added after the original sensor type and controller input have been verified.

## 7. Community Contributions

If you have experience with Bafang M620 / Ultra temperature sensor failures, please contribute:

- Original sensor identification.
- Sensor markings and photographs.
- Resistance measurements at known temperatures.
- PCB photographs and verified connector pinouts.
- Successful replacement sensor information.
- Confirmed repair procedures.

Please distinguish measured facts from assumptions when submitting information.

---

**Project status:** Ongoing investigation.

**Platform:** Bafang M620 / Ultra mid-drive motor.

**Main subject:** Motor temperature sensor, Error 10 and Error 11.

**Disclaimer:** Experimental repair research. Incorrect electrical connections can cause fire, component damage, or loss of motor temperature protection.
