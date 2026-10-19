# Ioniq 6 Logger

Webseite, die sich per Web Bluetooth direkt mit einem Vgate-OBD2-Adapter (ELM327, BLE)
verbindet, Akku- und Fahrdaten eines Hyundai Ioniq 6 ausliest und als CSV aufzeichnet.

Öffnen: https://darshumar.github.io/ioniq6-logger/ (Chrome auf Android oder Chrome/Edge am PC).

Das CSV-Format entspricht den Logs des ESP32-Displays aus dem (privaten) Projekt
`ioniq6_obd`; `index.html` ist dort eine Kopie von `web/logger.html`.

Ein Teil der Zuordnungen der Messwerte stammt aus
[OBDb Hyundai-IONIQ-6](https://github.com/OBDb/Hyundai-IONIQ-6) (CC BY-SA 4.0).
