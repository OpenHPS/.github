<h1 align="center">
  <img alt="OpenHPS" src="https://openhps.org/images/logo_text-512.png" width="40%" />
</h1>

## About OpenHPS
OpenHPS (Open Source Hybrid Positioning System) is a powerful framework for building positioning systems that are **interoperable, scalable, and discoverable**. It provides a flexible architecture for processing positioning data across multiple domains.

- 📡 **Supports RF-based positioning** (Wi-Fi, BLE, RFID, UWB)
- 📷 **Enables computer vision-based localization**
- 🧭 **Integrates IMU-based navigation** (sensor fusion, SLAM)
- 🌍 **Handles geospatial and relative positioning**

## Features
- 2D, 3D, and geographical positioning
- Extensible data processing pipeline
- Support for multiple positioning algorithms (trilateration, triangulation, fingerprinting, SLAM...)
- Modular add-ons for advanced functionality
- Open source and community-driven

## Add-ons
### Positioning Algorithms
- **[@openhps/imu](https://github.com/OpenHPS/openhps-imu)** - IMU sensor fusion
- **[@openhps/rf](https://github.com/OpenHPS/openhps-rf)** - RF signal processing
- **[@openhps/fingerprinting](https://github.com/OpenHPS/openhps-fingerprinting)** - Fingerprinting-based localization
- **[@openhps/opencv](https://github.com/OpenHPS/openhps-opencv)** - Computer vision integration

### Data Services
- **[@openhps/mongodb](https://github.com/OpenHPS/openhps-mongodb)** - MongoDB storage
- **[@openhps/rdf](https://github.com/OpenHPS/openhps-rdf)** - RDF data export
- **[@openhps/solid](https://github.com/OpenHPS/openhps-solid)** - Solid PODs for data storage

## Getting Started
Install OpenHPS Core with:
```bash
npm install @openhps/core --save
```

Create a simple model:
```typescript
import { ModelBuilder } from '@openhps/core';

ModelBuilder.create()
    .build().then(model => {
         // Use the model
    });
```

## Documentation
- 📘 [Getting Started](https://openhps.org/docs/getting-started)
- 📜 [API Reference](https://openhps.org/docs/core)
- 🏗️ [Examples](https://openhps.org/docs/examples)

## Contributing
Contributions are welcome! See our [contributing guidelines](https://github.com/OpenHPS/openhps-core/blob/main/CONTRIBUTING.md) for more information.

## License
OpenHPS is licensed under the Apache License 2.0. See the full license [here](https://www.apache.org/licenses/LICENSE-2.0).

