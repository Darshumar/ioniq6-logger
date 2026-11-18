# Ioniq 6

Web-App für den Hyundai Ioniq 6, als App installierbar unter Windows (Edge/Chrome) und Android (Chrome):
https://darshumar.github.io/ioniq6-logger/

- **Live** (`index.html`): verbindet sich per Web Bluetooth mit dem Vgate-OBD2-Adapter (ELM327, BLE),
  zeigt Akku- und Fahrdaten live und zeichnet sie als CSV auf (gleiches Format wie die Logs des
  ESP32-Displays). Aufzeichnungen bleiben auf dem Gerät (IndexedDB).
- **Logs** (`logs.html`): zeigt Fahrten als Diagramme: Aufzeichnungen dieses Geräts, geöffnete CSV-Dateien
  und die ESP-Logs aus dem privaten Repo `Darshumar/Ioniq6-logs` (`logs/esp32`, bis 18.11.2026 in `Ioniq6_obd`). Dafür braucht die App einen
  Fine-grained Token mit „Contents: Read-only“ nur für dieses Repo; er wird nur im Browser gespeichert.
- **Laden** (`logs.html#laden`): nur die Ladevorgänge aus allen Logs (Zustand 3 = Laden, bei alten Logs ohne
  diese Spalte: Akku nimmt Leistung auf und der Motor steht). Je Ladung: AC/DC, Ladestand von–bis, kWh in den Akku
  und von der Säule, Spitzen- und Mittelleistung, Dauer, Zeit 10 (20) → 80 %, Akkutemperatur und -heizung, dazu
  die Ladekurve (kW über Ladestand) mit früheren Ladungen gleicher Art zum Vergleich. Die Liste wird einmal aus
  allen Logs gesucht und auf dem Gerät gemerkt; danach lädt die App nur neue oder geänderte Logs nach.

Installieren unter Windows: Seite in Edge öffnen → Menü „…“ → Apps → „Diese Website als App installieren“
(in Chrome: Symbol rechts in der Adressleiste). Danach startet „Ioniq 6“ aus dem Startmenü im eigenen Fenster.

Die Umrechnung der Rohwerte spiegelt `esp32/ioniq6_display/decode.cpp` aus dem Projekt `ioniq6_obd`.
Ein Teil der Zuordnungen stammt aus [OBDb Hyundai-IONIQ-6](https://github.com/OBDb/Hyundai-IONIQ-6) (CC BY-SA 4.0).
