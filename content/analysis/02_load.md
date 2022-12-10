---
Title: Load analysis
Description: My load analysis report.
---

Analys av användbarhet och laddningstid
=======================
-----------------------

Syftet med uppgiften är att hitta förslag till förbättrad laddningstid och användbarhet för tre webbplatser genom att analysera webbplatsernas laddningstid.

<h2 class="h2">Urval</h2>
-----------------------

Jag har valt följande tre webbplatser till min analys:

* <a href="https://www.ikea.se">IKEA</a>

* <a href="https://fotbollskanalen.se">Fotbollskanalen</a>

* <a href="https://www.blocket.se">Blocket</a>

Jag har, som i föregående rapport (Colors), valt att analysera tre webbplatser inom olika branscher. Anledningen till att jag väljer dessa webbplatser, med lite olika riktning och syfte, är att jag tycker det kan bli intressant att se om även analysen för dem skiljer sig åt i det här avseendet.

<h2 class="h2">Metod</h2>
-----------------------

Jag har använt mig av <a href="https://developer.chrome.com/docs/devtools/">Chrome dev tools</a> för att mäta sidornas laddningstid och även <a href="https://pagespeed.web.dev/?utm_source=psi&utm_medium=redirect">Pagespeed Insights</a> för att mäta och analysera webbplatsernas laddningstider.

Pagespeed Insights har gett mig information om hur väl webbplatserna lyckas mobilt och desktop på följande parametrar:

* Performance (prestanda)

* Accessibility (användbarhet)

* Best practices (kodhälsa)

* SEO (sökmotoroptimering)

Chrome developer tools har har gett mig information om webbplatsernas antal resurser, totala storlek och laddningstid (både för DOM-trädet och inläsning).

<h2 class="h2">Resultat</h2>
-----------------------

<div class="website-table-load">
    <div class="website-title"><h3>Webbplats</h3></div>
    <div class="ikea"><h3>IKEA</h3></div>
    <div class="fotbollskanalen"><h3>Fotbollskanalen</h3></div>
    <div class="blocket"><h3>Blocket</h3></div>
    <div class="ikea-image"><img src="%base_url%/image/ikea.png?w=300&save-as=jpg"></div>
    <div class="fotbollskanalen-image"><img src="%base_url%/image/fotbollskanalen.png?w=300&save-as=jpg"></div>
    <div class="blocket-image"><img src="%base_url%/image/blocket.png?w=300&save-as=jpg"></div>
</div>

<div class="embed-googlesheet">
    <iframe src="https://docs.google.com/spreadsheets/d/e/2PACX-1vQetyXUZ6JK050eOBamdGVrCPqFrJFRTJR2IsvYIhcfqNfj6u8FIbPhxyjvhZ5p0MKd0YF_quRikIbo/pubhtml?gid=0&amp;single=true&amp;widget=true&amp;headers=false&amp;style=embed&amp;range=a1%3Ag16&amp;chrome=false"></iframe>
</div>

En analys av resultatet följer i nästa avsnitt.


<h2 class="h2">Analys</h2>
-----------------------

Samtliga tre webbplatser har bäst performance-värden för desktop (55, 81 och 69). För mobil lyckas de inte lika bra.

Den som förbättrar sig överlägset bäst procentuellt är Fotbollskanalen (ökning med 179%).

Övriga parametrar är i princip oförändrade för samtliga tre webbplatser.

Vad gäller laddningstiderna lyckas Fotbollskanalen bäst vad gäller DOM-innehållet på webbplatsen, med 450 ms medan sidans laddningstid för Blocket är bäst på 1,02 s. En anledning till det kan vara att Blocket har färst antal resurser (117 st) och det storleken på sidan är minst också (6,8 MB).

Pagespeed insights redovisar, förutom betyg på Performance, Accessibility, Best practice och SEO, en rad förbättringsåtgärder. Nedan ser ni dessa åtgärder för respektive webbplats.

<h3 class="website-analysis">IKEA</h3>
De förbättringsåtgärder, med störst potential till besparing av laddningstid, som föreslås för IKEAs webbplats är (i parentes syns möjlig besparing):

* Properly size images (10,35 s), dvs. de rekommenderas att jobba mer med responsiva bilder. Den bild som laddas och den bild som visas för användaren ska inte skilja sig åt. Detta kan vi åtgärda med hjälp av verktyg som t.ex. CImage, så att vi får olika versioner av samma bild för olika skärmstorlekar.

* Defer offscreen images (9,27 s), dvs. de rekommenderas att låta de bilder som inte syns för besökaren att laddas in först när användaren scrollar förbi dem.

* Serve images in next-gen formats (6,9 s), dvs. de rekommenderas att använda format som WwebP och AVIF istället för PNG och JPEG, vilket innebär snabbare nedladdningar och mindre dataanvändning.

* Reduce unused JavaScript (3,71 s), dvs. spara tid och data på att undvika/ta bort JavaScript-kod som inte används.

Källa: https://developer.chrome.com/docs/lighthouse/performance

<h3 class="website-analysis">Fotbollskanalen</h3>
De förbättringsåtgärder, med störst potential till besparing av laddningstid, som föreslås för Fotbollskanalens webbplats är (i parentes syns möjlig besparing):

* Reduce unused JavaScript (2,55 s), dvs. spara tid och data på att undvika/ta bort JavaScript-kod som inte används.

* Användarens upplevelse försämras dessutom av att det tar 12,4 s (time to interactive, TTI) innan hen kan interagera med sidan fullt ut. Den ser ut att vara färdigladdad, men det går inte att göra allt som ska gå att göra.

* En annan aspekt av Fotbollskanalens webbplats som gör att de får en låg performance-score är att det tar 14,2 s innan det största elementet på webbplatsen har renderats, så kallad Largest Contentful Paint.

Källa: https://developer.chrome.com/docs/lighthouse/performance

<h3 class="website-analysis">Blocket</h3>
De förbättringsåtgärder, med störst potential till besparing av laddningstid, som föreslås för Blockets webbplats är (i parentes syns möjlig besparing):

* Flera av åtgärderna är kopplade till JavaScript, t.ex. reduce unused JavaScript (3,33 s) och minimize main-thread work (7,7 s). Den senare åtgärden innebär att minimera tiden det tar att parse:a, compile:a och utföra JavaScript-kod. Om main-thread är upptagen med att göra allt detta, kan den inte processa användar-events, vilket kan leda till en sämre upplevelse av webbplatsen.

* Webbplatsens Time to Interactive är väldigt långt, 15,6 s och kan vara en anledning till att besökaren av webbplatsen upplever sidan långsammare än vad den skulle kunna vara.

Källa: https://developer.chrome.com/docs/lighthouse/performance

<h3 class="website-analysis">ÖVRIG ANALYS</h3>

I den här analysen tycker jag att Blocket är vinnaren. De lyckas bäst på två av fyra parametrar i PageSpeed Insight testet (Accessibility och SEO (sökmotoroptimisering)).

Slår vi ut antalet resurser och sidans totala storlek på sidans laddningstid, ser vi att även där ligger Blocket bättre till än Ikea och Fotbollskanalen.

Jag tänker att sidorna levererar ok på desktop och anledningen till att sidorna inte lyckas lika bra mobilt är att de även har mobilappar, där de säkert lägger mer av sitt krut (bara en teori).

Jag skulle säga att en absolut laddningstid på max 3 sekunder är acceptabel. Alla tre undersökta webbplatser hamnar under den laddningstiden och kan således, i alla fall av mig, anses vara godkända.

Jag blev nyfiken och googlade efter undersökningar kring laddningstid och kom in på den här sidan --> https://www.matthewedgar.net/how-do-people-perceive-website-speed/

Enligt denna sida uppfattar människor en laddningstid på 5 sekunder som medel till snabb.

![Load time vs perceived Speed](%base_url%/image/matthewedgar.jpg?q=70&w=400)

Intressant är att vi upp till en viss laddningstid beskyller internetleverantören, men sedan skiftar det gradvis mot en ilska mot företaget som tillhandahåller hemsidan.


<h2 class="h2">Referenser</h2>
-----------------------

UNDERSÖKTA WEBBPLATSER:

https://www.ikea.se (Besökt senast xxx)

https://www.fotbollskanalen.se (Besök senast xxx)

https://www.blocket.se (Besökt senast xxx)

ANALYSVERKTYG:

https://developer.chrome.com/docs/devtools/ (Besök senast xxx)

https://pagespeed.web.dev/?utm_source=psi&utm_medium=redirect (Besökt senast xxx)

KÄLLOR:

https://developer.chrome.com/docs/lighthouse/performance

https://www.matthewedgar.net/how-do-people-perceive-website-speed/

<h2 class="h2">Övrigt</h2>
-----------------------

Författare av rapporten: Martin Fooladi
