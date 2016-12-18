﻿# Upstart'i ülevaade

## Tunni sisu

Kuna *Upstart* on Canonical'i välja töötatud, oli see mõnda aega Ubuntu*init*'i teostus. Kaasaegsematel Ubuntudel kasutatakse aga *systemd*'d. *Upstart* loodi selleks, et parandada mõningaid probleeme *Sys V*'ga, näiteks range alglaadimise protsess, tegumite blokeerimine jne. *Upstart*'i sündmustele ja töödele orienteeritud mudel lubab reageerida sündmustele jooksvalt.

Kui kasutajal on süsteemis kataloog */usr/share/upstart* on see päris hea vihje, et kasutusel on *Upstart*.

Tööd on tegevused, mida *Upstart* teostab ja sündmused on teated, mida töödeldakse tööde aktiveerimiseks. Tööde ja nende seadete nimekirja kuvamiseks:

<pre>
pete@icebox:~$ ls /etc/init
acpid.conf                   mountnfs.sh.conf
alsa-restore.conf            mtab.sh.conf
alsa-state.conf              networking.conf
alsa-store.conf              network-interface.conf
anacron.conf                 network-interface-container.conf
</pre>

Nendes seadete failides on informatsioon selle kohta kuidas ja millal töid käivitada.

Näiteks networking.conf failist võiks leida järgmise:
<pre>
start on runlevel [235]
stop on runlevel [0]
</pre>

See tähendab, et võrgundust seatakse üles teenustasemel 2, 3 või 5 ja peatatakse tasemel 0. Seadete faili võib kirjutada mitut moodi, selle tõestamiseks tuleb vaid erinevaid variante uurida.

*Upstart* töötab järgmiselt:

<ol>
<li>Esiteks laetakse töö seadete fail kataloogist */etc/init*</li>
<li>Kui toimub alglaadimise sündmus, käivitatakse selle poolt aktiveeritud töö</li>
<li>Need tööd loovad uusi sündmusi, mis omakorda akviteerivad rohkem töid</li>
<li>*Upstart* toimib kuni kõik valitud tööd on teostatud</li>
</ol>

## Harjutus

Kui arvutis on *Upstart*, uurida */etc/init* sisu. Kas seaded on arusaadavad?

## Küsimus

Millist *init*'i teostust Ubuntus kasutati?

## Vastus

upstart