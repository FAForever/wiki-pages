---
title: FAF-Development
description: 
published: true
date: 2022-01-18T21:53:56.759Z
tags: 
editor: markdown
dateCreated: 2021-12-24T23:55:37.921Z
---

# **Introductie tot ontwikkeling**

Dit document heeft alleen betrekking op de ontwikkeling van de FAF-infrastructuur.

-   Kijk voor informatie over het in kaart brengen
    [Hier](Map_Editor "wikilink").
-   Voor informatie over modden, kijk dan
    [Hier](Modding "wikilink").

## Broncode & versiebeheer

Forged Alliance Forever is een open source-project. Je kunt alles vinden over de
broncode op [Github](https://github.com/FAForever). zoals de naam
aan geeft, Github gebruikt **git** als versiecontrolesysteem. Als je wilt
deelnemen aan ontwikkeling, moet je git gebruiken en een Github account maken
(het is gratis). Een kleine introductie vind je in onze [Dev
School](FAF_Dev_School_Git "wikilink"). Er zijn ook veel tutorials
op YouTube en andere sites

We raden ten zeerste aan om git aan het begin op de opdrachtregel te gebruiken.
Gebruik de git-tools NIET in uw IDE voordat u de basis van git begrepen hebt, voordat u wat doet.

## Communicatie

Alle ontwikkelaarscommunicatie vindt plaats op Zulip.

Als je mee wilt doen, neem dan contact op met een beheerder/moderator op de
forums of in onze in-client chat (witte namen bovenaan) zodat we u kunnen
uinodigen voor onze Zulip-project.

Sinds medio 2016 hebben we elke 2e maand een conference call geïntroduceerd, waarbij:
ontwikkelaars en moderators praten over de voortgang. Deze oproepen zijn:
gestreamd in onze [YouTube kanaal](https://www.youtube.com/channel/UCkAWiUu4QE172kv-ZuyR42w).

Veel ontwikkelaars praten ook graag met elkaar op de [Faf
Discord](https://discord.gg/2u36D9V) in de ontwikkelingskanalen.
Die kanalen zijn beperkt voor toegang, als je die ontwikkelaars schrijft in een privéchat
zullen ze je waarschijnlijk binnen laten.

## Infrastructuur overzicht

Als je ons hebt opgezocht [Githube pagina](https://github.com/FAForever),
heb je misschien veel subprojecten opgemerkt.

FAF bestaat uit 5 belangrijke projecten, die de basis weerspiegelen van de
architectuur:

-   [Game](https://github.com/FAForever/fa): Forged Alliance gameplay
    files (lua)
    -   Dit is de officieel aanbevolen FAF-mod
    -   Dit is de juiste plek om te werken aan veranderingen in balans, game-lobby
        veranderingen, fixes/verbeteringen van eenheidsgedrag
    -   De game communiceert met de client via het GPGNet-protocol
    
---

-   [Client](https://github.com/FAForever/downlords-faf-client): FAF
    lobby client (java)
    -   Dit is de FAF-client op de website en de hoofdgebruiker
        koppel.
    -   Instructies voor het instellen van de client-ontwikkelomgeving kunnen worden
        gevonden op Youtube: ([Brief](https://www.youtube.com/watch?v=_kJoRehdBcM),        [Detailed](https://www.youtube.com/watch?v=z4cnvh_vNKA))

---

-   [Server](https://github.com/FAForever/server): FAF lobby server
    (python)
    -   De server is verantwoordelijk voor het hosten van games, het berekenen van beoordelingen
        en ladder-matchmaking.

---

-   [Web api](https://github.com/FAForever/faf-java-api): FAF restful
    Web-api server (java)
    -   De api-servers bieden servers aan, aan geverifieerde gebruikers (via
        OAuth2)
    -   Diensten zijn bijvoorbeeld prestaties, kaartupload, bugrapporten.
    -   Omdat het voor iedereen open is, is de service zelf niet beperkt
        aan elke client.

---

-   [db](https://github.com/FAForever/db): FAF sql database (sql)
    -   De database is de backend voor server en api.
    -   Instructies voor het instellen van de db zijn te vinden op:
        [Youtube](https://www.youtube.com/watch?v=3vsRs71vMII)

---

Dan is er de python-client, die de vorige officiële client was:

-   [Client](https://github.com/FAForever/client): FAF lobby client
    (python)
    -   Instructies voor het instellen van de python-clientontwikkelingsomgeving kunnen hier
        gevonden worden: [Hier](FAF_Dev_School_Client "wikilink")

---

FAF werkt aan een java-vervanging voor de server (gestaakt):

-   [Server](https://github.com/FAForever/faf-java-server): FAF java
    server

**Al deze projecten hebben een leesmij met informatie over het gebruik
hiervan.** Vraag voor verdere vragen om hulp in onze Zulip-chat.

## Ontwikkelaarstools

De volgende tools worden sterk aanbevolen voor ontwikkeling (ongeacht
van uw besturingssysteem):

-   [Git](https://www.git-scm.com)
    -   Volg alstublieft ons vertakkingsschema.
    -   Linux-client zou beschikbaar moeten zijn in uw pakketbeheerder
    -   [Windows client](https://git-scm.com/download/win)
    - [Docker](https://www.docker.com/)
-   a good IDE:
    -   Python: [PyCharm](https://www.jetbrains.com/pycharm/) (vrij
        community-editie)
    -   Java: [IntelliJ IDEA](https://www.jetbrains.com/idea/) (vrij
        community-editie)

## Waar te beginnen?

Er zijn veel startpunten voor nieuwe ontwikkelaars:

-   Kies een probleem uit een van de [Git-projects](https://github.com/FAForever) en begin eraan te werken.
    -   We raden aan om te controleren of het probleem nog niet is opgelost.
        Als iemand eraan heeft gewerkt, kun je de commits waarnaar wordt verwezen meestal zien in
        de geschiedenis van het probleem.
    -   Als de situatie onduidelijk is, vraag het dan in Zulip.
-   Kies een suggestie uit de [suggesties-forum](http://forums.faforever.com/viewforum.php?f=42) of
-   Breng elk onderwerp naar voren in Zulip en bied aan om daaraan te werken.
    -   De ontwikkelaars zullen nuttige hints geven over je aanpak en je vertellen
        over mogelijke conflicten.
-   Doe mee met #pair-programmeren in Zulip en werk samen met anderen.

## Dev Notities

[Installing Luajit en Lupa voor bouwen Lupa-package](Dev_Note_Lupa "wikilink")

# **FAF-ontwikkelingsschool**

FAF Development School is een open groep opgericht door Softles om de
ontwikkeling van de codebase van FAForever te promoten.

Hints en tips om bij te dragen aan FAF worden aan de minderen
ervaren mensen gegeven in zowel de forums als de groepschat, **#FAF_Dev_School**

-   Om deel te nemen aan deze chat typ je gewoon: ***/join #FAF_Dev_School***
    in [aeolus](FAF_chat "wikilink").

De lessen tot nu toe zijn hieronder opgenomen ter referentie:.

## Lessen

-   [Sources for FAF (Git and GitHub)](FAF_Dev_School_Git "wikilink")
-   [FAF Client code](FAF_Dev_School_Client "wikilink")
-   [FAF Server code](FAF_Dev_School_Server "wikilink")

## Andere

Bronnen voor het werken aan FA-modding (de spelcode):

1\) [Modding hints](Modding "wikilink")

2\) [AI Modding](AI_Modding "wikilink")

2\) [LUA-Docs](LUA-Docs "wikilink")

3\) [Unit Blueprint Docs](Unit_Blueprint_Docs "wikilink")

## Gids voor de eerste keer

Als je nog niet eerder hebt gecodeerd, of geen idee hebt waar je moet beginnen
dan is dit de gids voor jou!

Het belangrijkste dat we moeten doen als we met de FAF-code willen spelen, is:
krijg een GitHub-account, bekijk de les daarover: [Github for
FAF](FAF_Dev_School_Git "wikilink")

Zodra je een GitHub-account hebt ingesteld, is het volgende wat je moet doen:
kies welke FAF-code u wilt bekijken.

Voor de FAF client-code zie: [FAF Client
code](FAF_Dev_School_Client "wikilink")

Voor de FAF-servercode zie: [FAF Server
code](FAF_Dev_School_Server "wikilink")

Als u op zoek bent naar suggesties, is het misschien het gemakkelijkst om de
Clientcode eerst op te zetten :)