﻿# Protsesside jälgimine: top

## Tunni sisu

Sellel kursusel tutvustatakse, kuidas lugeda ja analüüsida süsteemi ressursside kasutust. Selles peatükis näidatakse häid tööriistu, millega on hea tostada protsesside seiret.

<b>top</b>

*Top*'ist on ka varem juttu olnud kuid seekord süveneme natuke spetsiifilisemalt sellesse, mida täpselt tegelikult kuvatakse. Meenutame, et *top* on tööriist, mis võimaldab kuvada protsesside poolt kasutatavaid ressursse reaalajas:

<pre>
top - 18:06:26 up 6 days,  4:07,  2 users,  load average: 0.92, 0.62, 0.59
Tasks: 389 total,   1 running, 387 sleeping,   0 stopped,   1 zombie
%Cpu(s):  1.8 us,  0.4 sy,  0.0 ni, 97.6 id,  0.1 wa,  0.0 hi,  0.0 si,  0.0 st
KiB Mem:  32870888 total, 27467976 used,  5402912 free,   518808 buffers
KiB Swap: 33480700 total,    39892 used, 33440808 free. 19454152 cached Mem

  PID USER      PR  NI    VIRT    RES    SHR S  %CPU %MEM     TIME+ COMMAND                             
 6675 patty    20   0 1731472 520960  30876 S   8.3  1.6 160:24.79 chrome                             
 6926 patty    20   0  935888 163456  25576 S   4.3  0.5   5:28.13 chrome 
</pre>

Kohe räägime, mida see väljund tähendab. Seda infot ei pea kõike meelde jätma, kui on tarvis võib meenutamiseks siia peatüki juurde hiljem tagasi tulla.

<b>1. rida: See on informatsioon, mida võib näha kui sisestada *uptime* käsk (hiljem rohkem)</b>

Väljad vasakult paremale:
<ol>
<li>Hetke aeg</li>
<li>Süsteemi töötamise aeg</li>
<li>Sisse logitud kasutajate arv</li>
<li>Süsteemi keskmine koormus (hiljem rohkem)</li>
</ol>

<b>2. rida: tegumid, mis töötavad, magavad, on peatatud ja, zombid</b>

<b>3. rida: protsessori informatsioon</b>

<ol>
<li>us: kasutaja protsessori aeg  - Protsent protsessori kasutamise ajast, mis on kulunud mittekenadele protsessidele.</li>
<li>sy: süsteemi protsessori aeg - Protsent protsessori kasutamise ajast, mis on kulunud tuumale ja tuuma protsessidele.</li>
<li>ni: kena protsessori aeg - Protsent protsessori kasutamise ajast, mis on kulunud kenadele protsessidele.</li>
<li>id: protsessori tegevusetu aeg - Protsent, mille jooksul protsessor on olnud tegevusetu.</li>
<li>wa: sisend/väljund ooteaeg - Protsent protsessori kasutamise ajast, mis on kulunud sisendi/väljundi järgi ootamiseks. Kui see väärtus on väike, ei ole probleem ilmselt kettas või võrgu sisendis/väljundis</li>
<li>hi: riistvara katkestused - Protsent protsessori kasutamise ajast, mis on kulunud riistvara poolt saadetud katkestuste teenindamisele.</li>
<li>si: tarkvara katkestused - Protsent protsessori kasutamise ajast, mis on kulunud tarkvara poolt saadetud katkestuste teenindamisele.</li>
<li>st: varastatud aeg - Kui arvutis töötavad virtuaalmasinad, on see protsent protsessori ajast, mis on varasatud teiste tegumite jaoks</li>
</ol>

<b>4. ja 5. rida: Mälu ja saaleala kasutus</b>

<b>Hetkel töötavate protsesside nimekiri</b>

<ol>
<li>PID: protsessi id</li>
<li>USER: kasutaja, kes on protsessi omanik</li>
<li>PR: protsessi prioriteet</li>
<li>NI: kenaduse väärtus</li>
<li>VIRT: protsessori poolt kasutatav virtuaalmälu</li>
<li>RES: protsessi kasutatav füüsiline mälu</li>
<li>SHR: protsessi jagatud mälu</li>
<li>S: Protsessi oleku indikaator: S=magab, R=töötab, Z=zombi,D=ei saa katkestada,T=peatatud</li>
<li>%CPU - protsessori kasutamise protsent </li>
<li>%MEM - RAMi kasutamise protsent</li>
<li>TIME+ - protsessi summaarne tööaeg</li>
<li>COMMAND - protsessi nimi</li>
</ol>

Võib ka täpsustada protsessi ID, kui on huvi mingi kindla protsessi vastu:

<pre>$ top -p 1</pre>

## Harjutus

Uurida *top* käsku. Uurida, millised protsessid kasutavad kõige rohkem ressursse.

## Küsimus

Milline käsk kuvab sama väljundi, kui on *top*'i esimene rida?

## Vastus

uptime