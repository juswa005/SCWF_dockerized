# Solve Crypto With Force (SCWF)

SCWF is a CTF tool for identifying, brute-forcing, and decoding various ciphers, obfuscations, and encodings. 

This project is designed to be **offline-first**, meaning all core cryptographic tools and cipher identifications work natively in the browser without any Internet connectivity.

## Requirements

* Docker
* Docker Compose

## Quick Start

```bash
git clone https://github.com/DaWouw/SCWF.git
cd SCWF
docker compose up -d
```

Then visit the application at:

```text
http://localhost:8081
```

## Stop

```bash
docker compose down
```

## Rebuild

```bash
docker compose build --no-cache
docker compose up -d
```

## Offline Usage

Once the Docker image has been built, SCWF's core functionality does not require Internet access. You can completely disconnect your machine from the network and continue to identify, decode, and score various ciphers in your CTFs.

### Optional Legacy Functionality
A PHP backend container is included for legacy functionality involving API proxies to third-party cipher cracking websites (e.g., quipqiup, quinapalus). By default, the application runs entirely in offline-mode. If you wish to enable the online tools (when Internet access is available), change `force_fully_offline = false;` in `UserSettings.js`. Note that this sends encrypted text to external third-party services.

## Management Scripts
Convenience scripts are provided in the `scripts/` directory:
- `./scripts/start.sh`
- `./scripts/stop.sh`
- `./scripts/rebuild.sh`
- `./scripts/test.sh`

## License

This software is released under the GNU General Public License v3 (GPLv3). See the `LICENSE` file for more details.
