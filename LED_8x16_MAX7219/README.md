Na desce jsou použity 2x řadiče MAX7219 a modul 8x8 LED ze [stavenice](https://www.laskakit.cz/stavebnice-8x8-cervena-led-matice-smd-max7219/), které jsou zapojeny v daisy-chain zapojení - viz. schéma.

Několik postřehů:
* Je vhodné využít blok SPI komunikace - viz. časování v DS:
  * Rámec začíná CS = 0
  * Přenáší se 16-bitové slovo, pro jednoduchost jako 2 8-bitová po sobě (i když SPI na STM32 umí 16-bitový režim)
  * Případně další 16b slova
  * Na konci CS = 1
* Příkazy pro "druhý" řadič přeposílá ten první až po přijetí "svých" 16 bitů, proto je vhodné jako první poslat povel NOP - viz. DS - "Table 2"
* Ověřená inicializace:
  * 0x0f00 = display test - normal operation - viz. Table 10
  * 0x0b07 = scan limit - 8 digits/lines - viz. Table 8
  * 0x0900 = decode mode - no decode - viz. Table 4
  * 0x0c01 = shutdown register - normal op. - viz. Table 3
  * 0x0a08 = intensity - 17/32 - viz. Table 7

