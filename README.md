# Automated Temperature Data Acquisition and Control System

A LabVIEW-based virtual instrumentation system for real-time temperature threshold monitoring, automated actuation and continuous data logging.

Course project - Measurement & Instrumentation Laboratory, Vellore Institute of Technology (VIT), 5th semester. Faculty guide: Prof. Uma Sathyakam P.

## Problem statement

- Manual/analog temperature monitoring in lab and industrial environments is discontinuous, operator-dependent and prone to human error.
- No instant, threshold-triggered alerts, which raises the risk of equipment damage from overheating or under-cooling.
- Conventional thermometry has no built-in continuous data logging, hindering trend analysis and audit traceability.
- Sensing, decision-making and actuation are typically disjointed subsystems, increasing response latency.

## Approach

- A simulated temperature sensor sub-VI generates continuous DBL data emulating an RTD/thermocouple analog output.
- Comparator logic classifies the reading in real time: HIGH above 35 °C, LOW below 14 °C, and a bounded MODERATE band (15-34 °C) via an AND of two comparators.
- Threshold crossings directly drive front-panel LED indicators and actuate the COOLING FAN (on HIGH) and HEATER (on LOW) outputs, with no manual intervention.
- A While Loop with a 500 ms Wait function sets a fixed real-time sampling rate.
- The live signal is routed in parallel to a Waveform Chart for trend visualization and to the Write To Measurement File Express VI for timestamped, Excel-compatible logging.

## Key features

- Real-time three-zone temperature classification with LED indication
- Automated fan/heater actuation from threshold-crossing events
- Continuous, timestamped data logging to an Excel-compatible file
- Virtual front panel: colour-coded analog dial, digital readout, fill-slide sensor indicator and chart recorder
- Thresholds, sampling rate and control logic fully reconfigurable in software

## Results

- Comparator logic correctly asserted HIGH TEMP / COOLING FAN above 35 °C and LOW TEMP / HEATER below 14 °C; the MODERATE indicator activated only within the 15-34 °C band.
- Logged entries confirmed a consistent ~500 ms sampling interval over the full continuous run.
- The Waveform Chart captured clear zone transitions, including dips near -5 °C and peaks approaching 45 °C.

## Files

- `Automated_Temperature_DAQ_Control_Report.pdf` - full project report (problem statement, theory, methodology, block diagram, front panel, results)
- LabVIEW source (`.vi`) files - to be added

## Future work

- PID control loop for finer regulation
- IoT-based remote monitoring
- Migration from the simulated sensor to a physical sensor/actuator interface
