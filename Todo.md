

Als Erstes könnte man herausfinden, was für Hardware man braucht: Kann ein günstiger Computer (Raspberry Pi 3) 4 USB-Mikrophone mit genug Leistung versorgen? Wenn nicht, hilft ein USB-Hub mit eigener Stromversorgung.

Kann ein Raspi die Signale der 4 Mikrophone schnell genug hintereinander auslesen?: Der Schall ist ca. 334m/s schnell. D.h. er braucht nur (1/334)s also ca. 3ms um den 1m zw. 2 Mikrofonen zurück zu legen. Nach dem Nyquist-Theorem muss der Computer in dieser Zeit die Mikrophone mindestens zweimal auslesen. Um Schallquellen wieder erkennen zu können, muss er die Mikrophone deutliche häufiger auslesen, vielleicht 100mal in 3ms.

Man kann auch Analog-Mikrophone nehmen. Hat der Raspi 4 Analog-Digital-Wandler, und kann er die schnell genug auslesen? Wie ist deren Auflösung (z.B. 12Bit).
Wenn der Raspi nur einen AD-Wandler hat, könnte man die Mikrophonen nacheinander daran anschließen. Das könnte eine elektronische Schaltung sehr schnell machen (multiplexing chip (MUX). Kann sie es schnell genug?

DSPs Digital Signal Processors sind Spezial-Chips die helfen könnten.

FPGAs könnten auch helfen, sind aber schwer zu programmieren.

Wenn ein Raspi nicht reicht, braucht man vielleicht einen PC mit einer schnellen Soundcard mit 4 Anschlüssen für Mikrophone. Man kann Musiker fragen. Die nehmen manchmal mit 4 Mikrofonen gleichzeitig auf, z.B. bei einer Band mit 4 Instrumenten.
@jwolpers123
jwolpers123 15 minutes ago Owner

Update 17.09.2020

Also Arduino ist laut diesem Geschwindigkeitstest noch die beste Option:
http://netmf-tutorial.de/reaktionszeit-raspberry-pi-windows-10-gegen-net-micro-framework-gegen-arduino/

Leider sind alle Arduinos gleich getaktet, dass heißt für unsere Zwecke zu langsam. Wir müssen also selbst was zusammenlöten. Dafür bräuchten wir einen Experten :-)
