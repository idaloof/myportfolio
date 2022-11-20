---
Title: JavaScript
Description: A page about JavaScript.
Template: technology
---

JavaScript
==================

JavaScript är ett prototyp-baserat skriptspråk. JavaScript utgör tillsammans med HTML och CSS grunden för webben. JavaScript är dynamiskt, svagt typat och hanterar funktioner som första-klass-objekt.

JavaScript använder sig av C-like syntax, men har annars inget gemensamt med programmeringsspråket Java.

Ett program som skriver ut alla jämna siffror mellan 1 och 100 kan se ut på följande sätt i JavaScript:

<pre><span class="pl-k">for</span> <span class="pl-kos">(</span><span class="pl-k">let</span> <span class="pl-s1">i</span> <span class="pl-c1">=</span> <span class="pl-c1">1</span><span class="pl-kos">;</span> <span class="pl-s1">i</span> <span class="pl-c1">&lt;=</span> <span class="pl-c1">100</span><span class="pl-kos">;</span> <span class="pl-s1">i</span><span class="pl-c1">++</span><span class="pl-kos">)</span> <span class="pl-kos">{</span>
    <span class="pl-k">if</span> <span class="pl-kos">(</span><span class="pl-c1">!</span><span class="pl-kos">(</span><span class="pl-s1">i</span> <span class="pl-c1">%</span> <span class="pl-c1">2</span><span class="pl-kos">)</span><span class="pl-kos">)</span> <span class="pl-kos">{</span>
        <span class="pl-smi">console</span><span class="pl-kos">.</span><span class="pl-en">log</span><span class="pl-kos">(</span><span class="pl-s1">i</span><span class="pl-kos">)</span><span class="pl-kos">;</span>
    <span class="pl-kos">}</span>
<span class="pl-kos">}</span></pre>