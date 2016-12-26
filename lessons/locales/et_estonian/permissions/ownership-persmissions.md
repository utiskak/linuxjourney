﻿# Omandiõigused

## Tunni sisu

Lisaks ligipääsuõigustele, saab muuta ka faili omanikku: kasutajat ja gruppi.

<b>Omanik-kasutaja muutmine</b>

<pre>
$ sudo chown peeter minufail
</pre>

See muudab faili omanikuks Peetri.

<b>Omanik-grupi muutmine</b>

<pre>
$ sudo chgrp vaalad minufail
</pre>

See muudab faili grupiks vaalad.

<b>Kasutaja ja grupi üheaegne muutmine</b>

Kui lisada kasutaja järgi koolon ning grupinimi, saab neid üheaegselt muuta.

<pre>
$ sudo chown peeter:vaalad minufail
</pre>

## Harjutus

Muuta mõne testfaili omanikku, kasutajad ja gruppi. Pärast aga vaadata õigusi käsuga *ls -l*.

## Küsimus

Millise käsuga saab muuta faili omanikku?

## Vastus

chown