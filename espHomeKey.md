# ESP HomeKey - Nastavení a konfigurace

Repozitář projektu: [HomeKey-ESP32](https://github.com/rednblkx/HomeKey-ESP32)

## Hardware - Nákupní seznam

1. **ESP32 Development Board**  
   - POZOR: ESP32 má svůj specifický pinout  
   - Koupit zde: [ESP32 Development Board - Dratek.cz](https://dratek.cz/arduino/1581-esp-32s-esp32-esp8266-development-board-2.4ghz-dual-mode-wifi-bluetooth-antenna-module.html?gad_source=1&gclid=Cj0KCQiAo5u6BhDJARIsAAVoDWuEgV5QnQcolHmUXOlUG-lTX0xjY1nzYqNvKiSRJX8wsh1kH4dr1CMaAhEwEALw_wcB)

2. **NFC reader deska PN532**  
   - Koupit zde: [PN532 NFC/RFID čtečka - Laskakit.cz](https://www.laskakit.cz/rfid-ctecka-s-vestavenou-antenou-nfc-rfid-mifare-pn532-cteni-i-zapis/?utm_source=google&utm_medium=cpc&utm_campaign=1_PMax_%5BCZ%5D_Top_tROAS_540&utm_id=18587021915&gad_source=1&gclid=Cj0KCQiAo5u6BhDJARIsAAVoDWtzJJ2XOu-eiKSxxGTD2O7jB5C3pgI4gtqIAwj3JChYHU8raZXyPJwaAtGTEALw_wcB)

## Firmware

1. **Stažení firmwaru**  
   - Soubor: `esp32-firmware_merged.bin`  
   - Odkaz ke stažení: [Releases na GitHubu](https://github.com/rednblkx/HomeKey-ESP32/releases)

2. **Flashování ESP32**
   - Připojte ESP32 k MacBook Air (MBA)
   - Použijte následující příkaz pro nahrání firmware:
     ```bash
     esptool.py write_flash 0x0 esp32-firmware_merged.bin
     ```

## Nastavení WiFi

1. Po flashování ESP vytvoří WiFi síť:
   - **SSID:** `HomeSpan-Setup`  
   - **Heslo:** `homespan`

2. Otevřete tento odkaz pro konfiguraci domácí WiFi:  
   [Konfigurační wizard](http://192.168.4.1/hotspot-detect.html)

3. Uložte nastavení a restartujte zařízení.

## Další detaily a konfigurace (použít chrome v safari nejde)

Podrobnosti naleznete na stránkách projektu:  
[Wiki HomeKey-ESP32](https://github.com/rednblkx/HomeKey-ESP32/wiki/Configuration)

## po nakonfigurování wifi se přihlásit na Ip adresu kterou dostane ESP z DHCP (pouze v chrome)


## Pinout zapojení ESP32 a PN532

| ESP32 Pin          | NFC čtečka PN532 Pin  |
|--------------------|------------------------|
| **VCC/3V3**        | **VCC***              |
| **GND**            | **GND**               |
| **GPIO18 (pin9 = D18)**  | **SCK**               |
| **GPIO19 (pin10 = D19)** | **MISO**              |
| **GPIO23 (pin15 = D23)** | **MOSI**              |
| **GPIO5 (pin8 = D5)**   | **SS**                |

## Deska PN532 nastavit piny na SPI 
### první pin 0 druhý pin 1

Podrobný pinout ESP32 naleznete zde:  
[Pinout dokumentace - Dratek.cz](https://dratek.cz/docs/produkty/0/719/pinout.pdf?_gl=1*1y1myge*_up*MQ..*_gs*MQ..&gclid=Cj0KCQiAo5u6BhDJARIsAAVoDWuEgV5QnQcolHmUXOlUG-lTX0xjY1nzYqNvKiSRJX8wsh1kH4dr1CMaAhEwEALw_wcB)