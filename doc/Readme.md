# Documentation for Using

# Hardware
- 3S to 10S Lipo
- 300A (10sec)
- 150A Dauer (estimated)
- 2x watercooling necessary (Plus und Phases)
- Watercooling Minus is optional

## SD Card
- Fat32
- Folder/Subfolder are not used but accepted
- no min. Size

## USB
- Serial COM Port
- Used for BlHeli32_Suite/AM32 Config Tool
- Used for Debuggig and Development
- HW 1.0 comes without USB Port (external USB-Serial Converter)

## Servo Cable
- Digital and Analog Port 

### Analog Servo Input
- Servosignal 1000µs - 2000µs
- Calibration necessary

### Digital Port
- Telemetry Port
- SBUS/SBUS2
- Jeti ExBus
- Hott
- S.Port (planed)
- Jeti EX (not possible?
- Channel Selection (planed)

## BEC
- einstellbar von 4,5 bis 7,5V
- Abweichung bis zu 0,5V
- Kalibrierung (geplant)
- 2A Dauer
- 3A Kurzzeitig (10sek)

# ESC Funktionen
## Bluetooth
- Verfügbar bei USB und Lipospannung
- Verbindung ist nur möglich wenn Servosignal = Aus
- Bestehende Verbindungen werden gehalten
- BlControl App (Android)
- BlHeli32_App (Android)

## SD Karte
- nur aktiv bei Lipospannung
- Enthält die Logdatein -> Lesbar mit Logview Studio und Dataexplorer

## Udate
- Update Datei muss in "update.bin" umbenennt werden
- "update.bin" auf die SD Karte kopieren
- SD Karte in den ESC stecken
- unbedingt mit Lipo/Netzteil starten (USB ist zu instabil)

# App
- Berechtigung für Standort -> Bluetooth
- Berechtigung für Foto/Datei -> Logs Speichern
- Bluetooth muss aktiviert sein

## Connect Bildschirm
- Liste aller ESC's in Reichweite
- Links: die MAC-Adresse
- Mitte: Name
- Rechts Empfangsstärke
- connect durch klick auf Liste

## Menü Bildschirm
- HW Version -> Hardware Version des ESC
- FW Version -> Firmware Version vom ESC (Update durch SD Karte)
- App Version -> App Version auf Smartphone (Update durch .Apk)

## Settings
- BEC Voltage -> BEC Spannung
- Telemetry Mode -> Telemetrieprotokoll

### Limits
- Over Current Limit -> Stromlimit 
- Under Voltage Limit -> Lipo Unterspannungsschutz
- Over Temperature Limit -> Übertemperaturschutz
- ERPM Limit -> Drehzahl Limit (elektrische Drehzahl)
- Mode None -> Aus (wirklich aus)
- Mode Hard -> 20%
- Mode Soft -> 60%
- Mode Limit -> dynamische Regelung

### Logging Start/Stop
- Mode None -> Kein Logging
- Mode Throttle -> Servosignal Start/Stop
- Mode ERPM -> Drehzahl Start/Stop (elektrische Drehzahl)
- Mode Current -> Strom Start/Stop
- Mode Time -> Zeit Start/Stop
- Zeit Start kann nur einmal loggen
- Alle anderen Modes können mehrfach loggen
- Start Value sollte größer sein als Stop Value (außer Zeit)
- Log Start Value = 5 sek -> Start 5sek nach den Boot Prozess
- Log Stop Value = 20 sek -> Stop 20sek nach Start (max 255 sek = 4 min 15 sek)
- Log Stop Value = 0 sek -> niemals stoppen
- Log Start Value = 20 % -> Servoposition größer 20% (1200µs) = Start
- Log Stop Value = 5 % -> Servoposition kleiner 5% (1050µs) = Stop
- Log Stop Value = 0 % -> niemals stoppen
- Log Start Value = 20 A -> Strom größer 20A = Start
- Log Stop Value = 5 A -> Strom kleiner 5A = Stop
- Log Stop Value = 0 A -> niemals stoppen
- Log Start Value = 20 ERPM -> Dehzahl größer 20.000 ERPM = Start
- Log Stop Value = 5 ERPM -> Drehzahl kleiner 5.000 ERPM = Stop
- Log Stop Value = 0 ERPM -> niemals stoppen

## Motor
- ohne Funktion
- zukünftiger Ersatz zur BlHeli32_App

## Live Monitor
- Zeigt alle Live Werte an, wie sie auch im beim Loggen gespeichert werden
- Spannung = Lipospannung
- Temperatur = ESC Temperatur
- Drehzahl = elektrische Umdrehungen pro Minute
- Strom = Lipo Strom
- Spannung BEC = eingestellte Spannung (berechnet, nicht gemessen)
- Spannung Gate = Steuerspannung der Mosfets (sollte immer ~ 12V sein)
- Throttle = Servosignal Ausgang (für BlHeli32)
- Error = Aktueller Errorcode

## Read Logs
- Dropdown -> zeigt die letzten 10 gespeicherten Logdatein auf dem Regler (SD Karte) an
- Read Log -> Läd die ausgewählte Log Datei vom ESC herunter
- Stop -> Stoppt den Download
- Der Download kann mehrere Minuten dauern
- Alle gespeicherten Logs auf dem Smartphone werden in einer Liste angezeigt
- Mit dem klick auf den Log erscheind die Grafik zum Auswerten (in Arbeit)
- Alle Logs werden im externen Speicher unter Log_Files gespeichert
- Die Log Files können mit Logview Studio und Dataexplorer gelesen werden
- Der Errorlog kann nur vom Support gelesen werden -> weiterleiten per Email

## Debug
- alles was der Regler an Informationen ausgibt
- Befehle senden
- noch in entwicklung

## Factory
- Nur für Wartungszwecke!
- Nur wenn Messwerte Abweichen
- Nur in Rücksprache mit dem Support
- Reset to Factory -> Alle Einstellungen auf Werkeinstellung (Logcount auf 1) -> Unbedingt die SD Karte löschen
- Read ErrorLog -> lädt den Fehlerspeicher vom ESC herunter
### Kalibrierung
1. die VRef (in mV) einstellen bis der Live Wert = Lipospannung (Multimeter)
2. Bei ausgeschalteten Motor (Strom = 0A) den Strom-Raw Wert in die Offset Spalte eintragen (Offsetabgleich)
3. Strom-Gain nur anpassen wenn der gemessene Motorstom != echter Motorstrom (geprüft durch Unilog o.ä.)

- Read Cal. -> Gespeicherte Kalibrierung lesen
- Test Cal. -> geänderte Kalibrierung testen -> Live Werte sind kalibriert
- Save Cal. -> Kalibrierung auf dem ESC Speichern

# Logs Verarbeiten
- Die Logdatein sind als OpenFormatZero geschrieben
- kompatiben zu Dataexplorer, Logview Studio,
- teilwese unterstützt von dataexplorer App
- inkompatibel zu Logview V2
- 
## App intern
- nur Spannung,Strom,Temperatur,Drehzahl
- in Arbeit

## Dataexplorer App (Android)
- die Dataexplorer App kann keine Mehrfach Logs auswerten
- daher müssen alle Logs ohne Stop gestartet werden
- oder ZeitStop

## Dataexplorer 
- Dataexplorer öffnen
- Gerät/Port auswählen -> ZeroAdapter
- importiere Daten -> Log Datei von Sd Karte oder Smartphone auswählen

## LogView Studio
- Logview Studio öffnen
- Neues Projekt anlegen (oder bestehendes öffnen)
- Devise auswählen -> OpenFormat Zero Sensor
- Source auswählen -> File -> Log Datei von Sd Karte oder Smartphone auswählen
- Logging auswählen -> Chart
