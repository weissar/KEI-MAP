# LED Matrix 16x8 - TM1640 Controller

[Stránka produktu](https://www.laskakit.cz/lilygo-ttgo-led-matrix-displej/) na laskakit.cz

Reálně je to známé jako [LilyGO TTGO 16x8 LED Matrix displej](http://www.lilygo.cn/prod_view.aspx?TypeId=50033&Id=1176)

Řadič TM1640 komunikuje ve stylu pseudo-I2C sběrnice = signály DATA a SCK. Není to ale přímo I2C, proto je potřeba využít podobného kódu jako pro "ruční generování SPI" - signály nutno nastavovat pomocí GPIOWrite.

* Časování signálů - viz. DS kap. VI
* Význam příkazů - viz. DS kap. VII

Max. frekvence hodin je 1MHz (kap. V) - pro takt mikrokontroléru 16MHz se asi nemusí řešit.

![Pohled na shield s vyznačením 0,0](./LED-16x8%20SHIELD.jpg)

Další komponenty:
* akcelerometr [LIS2DE12TR](https://www.st.com/en/mems-and-sensors/lis2de12.html)
* Spínačový [joystick](https://tech.alpsalpine.com/e/products/detail/SKRHABE010/) - zobrazeno zapojení vývodů
