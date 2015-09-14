#Leírás
#OpenWrt
A projekt egy OpenWrt az eszközünkre való telepítésével kezdődik.
(Támogatott eszközök listája:http://wiki.openwrt.org/toh/start , 
Telepítéshez tartozó általános leírás: http://wiki.openwrt.org/hu/doc/howto/generic.flashing )
	Az eszközünk WEB felületét, a '192.168.1.1' címen érhetjük el(konfigurálás előtt).
     Az OpenWrt néhány beállítását('root' jelszó , az eszköz ip-címe, gateway, alhálózati maszk, dns szerver) a WEB felületén keresztül(LuCi) könnyedén elvégezhetjük.
![Alt text](https://github.com/mZoltan05/freewifi/blob/master/OpenWrt.png "LuCi")
SSH-n keresztül elérhetjük az eszközünket, ahová "root" felhasználónévvel és a LuCi-n beállított 
jelszóval léphetünk be.

Egy opkg csomagkezelővel való frissítés után fel is telepíthetjük a nekünk kellő programot, a NoDogSplash-t.

( https://github.com/nodogsplash/nodogsplash , http://wiki.openwrt.org/doc/howto/wireless.hotspot.nodogsplash)

![Alt text](https://github.com/mZoltan05/freewifi/blob/master/sshOpenWrt.png "sshnopenwrt")
#NoDogSplash
A NoDogSplash-t a(z) "/etc/nodogsplash" könyvtárban szabhatjuk személyre.
A Config fájlban bő leírás van. A(z) "/etc/nodogsplash/htdocs/" könyvtárban lévő "splash.html" fog minket belépéskor fogadni.

![Alt text](https://github.com/mZoltan05/freewifi/blob/master/nodogsplash.png "nodogsplash")

Ha jelszóhoz akarjuk kötni a belépést, akkor a jelszót a config fájlban kell beállítanunk

![Alt text](https://github.com/mZoltan05/freewifi/blob/master/nodogsplashpw.png "nodogsplashpw")

A splash.html kódjának pedig valami hasonló képp kell kinéznie:

![Alt text](https://github.com/mZoltan05/freewifi/blob/master/nodogsplashauth.png "nodogsplashauth")

A(z) "/etc/init.d/nodogsplash start" parancssal elindíthatjuk a NoDogSplash-t.
A(z) "/usr/bin/ndsctl status" paranccsal kérhetjük le a NoDogSplash státuszát.
![Alt text](https://github.com/mZoltan05/freewifi/blob/master/ndsctl.png "ndsctl")

A splash lapot a böngészőben a router hálózati IP-címén és a "nodogsplash.conf"-ban beállított porton érhetjük el.
pl: 192.168.1.2:2050





