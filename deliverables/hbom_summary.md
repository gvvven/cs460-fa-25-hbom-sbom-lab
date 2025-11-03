Component 1: ESP32-Sc
This component is a SoC / Wi-Fi and Bluetooth microcontroller.
Manufacturer: Espressif systems
Part: ESP32 - S3 (or ESP32-S3FNB)
Known Vulnerabilites: The first issue is an issue with the Espressif's ESP-IDF SDK ecosystem with one of the main vulnerabilites being a wifi/bluetooth stack bug. This can cause someone to compromise the firmaware which can lead to remote code execution, persistence or total device control.
Mitigation: One way to mitigate such risks is to enable secure boot, verify all OTA images are cryptogaphically signed and track Expressif advisories and NVD for new CVE's.

Component 2: ST7789V2
This component is a LCD controller / display driver.
Manufacturer: Sitronix Technology
Part: ST7789V2 TFT - LCD controller
Vulnerabilties: The firware initialization code can have buffer overflows or timing errors which an attacker can take advantage of. This can lead to a lot of reliability issues.
Mitigation: One way to mitigate this is to test initiazliation sequence to see if it is working as intended.

Component 3: SPM1423
This component is a PDM MEMS Microphone
Manufacturer: Lnowles Electronics
Part: SPM1423 digital MEMS microphone
Vulnerabilties: One is that the microphones can capture sensitive audio or be used for eavesdropping if the firmware streams data in an insecure way. this can lead a very large privacy issue and also data handling.
Mitigation: Restrict microphone access in the firmware could help with this issue as well as encrypting audo in transit so that no on in the middle can intercept it.

Hardware dependencies realy define the foudnation of firmware security and vulnerabilties easily propogate into the devices firmware. Even components without CVE's can introduce through counterfeit substitution, unstable drivers, or other ways. Maintaining an HBOM alongside an SBOM enables easy tracebiltiy since you can link each firware comopnent to the actual hardware it runs on, you can identify whether the sdks or toolchains have advisories and prioritize mitigations such as sucure goot, signed firmware and others.