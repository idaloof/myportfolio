---
Title: PHP
Description: A page about PHP.
Template: technology
---

PHP
==================

PHP är ett populärt skriptspråk som främst används för att skapa webbplatser med dynamiskt innehåll. PHP är det mest använda server-side programmeringsspråk på webben med uppåt 80% av alla webbplatser som använder det.

PHP är ett objekt-orienterad programmeringsspråk, som med senare versioner kan vara hård typat och till och med JIT.

Ett program som skriver ut alla jämna siffror mellan 1 och 100 kan se ut på följande sätt i PHP:

<pre><span class="pl-ent">&lt;?php</span>
for (<span class="pl-s1"><span class="pl-c1">$</span>i</span> = <span class="pl-c1">1</span>; <span class="pl-s1"><span class="pl-c1">$</span>i</span> &lt;= <span class="pl-c1">100</span>; <span class="pl-s1"><span class="pl-c1">$</span>i</span>++) {
    <span class="pl-k">if</span> (!(<span class="pl-s1"><span class="pl-c1">$</span>i</span> % <span class="pl-c1">2</span>)) {
        print(<span class="pl-s1"><span class="pl-c1">$</span>i</span>);
    }
}</pre>