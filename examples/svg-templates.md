# SVG Templates (Claude mode)

Starting points for diagrams Claude draws itself. Copy, then change text, counts and
positions. Keep the colours and sizes so every diagram in a run matches.

**Palette:** normal `#2E9E5B` · disease `#D64545` · treatment `#2F6FD6` · warning `#E8892B` ·
tests `#7B4FC9` · text `#1F2933` · lines `#52606D` · panel `#F5F7FA` · white `#FFFFFF`

**Shared `<defs>`** (put once per SVG):
```svg
<defs>
  <marker id="arr" viewBox="0 0 10 10" refX="9" refY="5" markerWidth="8" markerHeight="8" orient="auto-start-reverse">
    <path d="M0,0 L10,5 L0,10 z" fill="#52606D"/>
  </marker>
  <style>
    .t{font:700 26px system-ui,sans-serif;fill:#1F2933}
    .l{font:600 17px system-ui,sans-serif;fill:#1F2933}
    .s{font:400 15px system-ui,sans-serif;fill:#52606D}
    .w{font:700 18px system-ui,sans-serif;fill:#FFFFFF}
    .f{font:400 12px system-ui,sans-serif;fill:#9AA5B1}
  </style>
</defs>
```
Footer (every diagram, bottom-right):
```svg
<text class="f" x="885" y="590" text-anchor="end">MedLens · Educational use</text>
```

---

## 1. Urgent Action card (landscape)
```svg
<svg viewBox="0 0 900 600" xmlns="http://www.w3.org/2000/svg" role="img">
  <title>Urgent action: STEMI</title>
  <!-- shared defs -->
  <rect width="900" height="600" fill="#FFFFFF"/>
  <rect width="900" height="90" fill="#D64545"/>
  <text class="w" x="450" y="56" text-anchor="middle" style="font-size:32px">⚠ URGENT: STEMI</text>
  <g transform="translate(40,130)">
    <rect width="190" height="190" rx="16" fill="#FDECEC" stroke="#D64545" stroke-width="2"/>
    <circle cx="35" cy="35" r="22" fill="#D64545"/><text class="w" x="35" y="42" text-anchor="middle">1</text>
    <text class="l" x="95" y="120" text-anchor="middle">ABCDE + ECG</text>
  </g>
  <g transform="translate(250,130)">
    <rect width="190" height="190" rx="16" fill="#FDECEC" stroke="#D64545" stroke-width="2"/>
    <circle cx="35" cy="35" r="22" fill="#D64545"/><text class="w" x="35" y="42" text-anchor="middle">2</text>
    <text class="l" x="95" y="120" text-anchor="middle">Call cardiology</text>
  </g>
  <g transform="translate(460,130)">
    <rect width="190" height="190" rx="16" fill="#FDECEC" stroke="#D64545" stroke-width="2"/>
    <circle cx="35" cy="35" r="22" fill="#D64545"/><text class="w" x="35" y="42" text-anchor="middle">3</text>
    <text class="l" x="95" y="120" text-anchor="middle">Antiplatelets</text>
  </g>
  <g transform="translate(670,130)">
    <rect width="190" height="190" rx="16" fill="#FDECEC" stroke="#D64545" stroke-width="2"/>
    <circle cx="35" cy="35" r="22" fill="#D64545"/><text class="w" x="35" y="42" text-anchor="middle">4</text>
    <text class="l" x="95" y="120" text-anchor="middle">Primary PCI</text>
  </g>
  <text class="s" x="450" y="400" text-anchor="middle">Follow local emergency protocols</text>
  <text class="f" x="885" y="590" text-anchor="end">MedLens · Educational use</text>
</svg>
```

## 2. Flowchart (portrait) — diagnosis flow
```svg
<svg viewBox="0 0 600 900" xmlns="http://www.w3.org/2000/svg" role="img">
  <title>Diagnosing CAP</title>
  <!-- shared defs -->
  <rect width="600" height="900" fill="#FFFFFF"/>
  <text class="t" x="300" y="50" text-anchor="middle">Diagnosing CAP</text>
  <rect x="160" y="90" width="280" height="60" rx="12" fill="#F5F7FA" stroke="#52606D"/>
  <text class="l" x="300" y="126" text-anchor="middle">Cough + fever</text>
  <line x1="300" y1="150" x2="300" y2="200" stroke="#52606D" stroke-width="2" marker-end="url(#arr)"/>
  <rect x="160" y="200" width="280" height="60" rx="12" fill="#F3EEFB" stroke="#7B4FC9"/>
  <text class="l" x="300" y="236" text-anchor="middle">Chest X-ray</text>
  <line x1="300" y1="260" x2="300" y2="310" stroke="#52606D" stroke-width="2" marker-end="url(#arr)"/>
  <!-- decision diamond -->
  <polygon points="300,310 420,380 300,450 180,380" fill="#FFF4E8" stroke="#E8892B" stroke-width="2"/>
  <text class="l" x="300" y="386" text-anchor="middle">Consolidation?</text>
  <line x1="180" y1="380" x2="90" y2="380" stroke="#52606D" stroke-width="2"/>
  <line x1="90" y1="380" x2="90" y2="520" stroke="#52606D" stroke-width="2" marker-end="url(#arr)"/>
  <text class="s" x="135" y="370" text-anchor="middle">No</text>
  <rect x="20" y="520" width="140" height="60" rx="12" fill="#F5F7FA" stroke="#52606D"/>
  <text class="l" x="90" y="556" text-anchor="middle">Other cause</text>
  <line x1="300" y1="450" x2="300" y2="520" stroke="#52606D" stroke-width="2" marker-end="url(#arr)"/>
  <text class="s" x="318" y="492">Yes</text>
  <rect x="200" y="520" width="200" height="60" rx="12" fill="#F5F7FA" stroke="#52606D"/>
  <text class="l" x="300" y="556" text-anchor="middle">CURB-65 score</text>
  <line x1="300" y1="580" x2="300" y2="640" stroke="#52606D" stroke-width="2" marker-end="url(#arr)"/>
  <rect x="160" y="640" width="280" height="60" rx="12" fill="#EAF2FD" stroke="#2F6FD6"/>
  <text class="l" x="300" y="676" text-anchor="middle">Treat by severity</text>
  <text class="f" x="585" y="890" text-anchor="end">MedLens · Educational use</text>
</svg>
```
Rules: boxes 60 tall, 50 px vertical gap, decision = diamond in warning colour, test = purple,
treatment = blue. Max 8 boxes.

## 3. Timeline (landscape) — follow-up
```svg
<svg viewBox="0 0 900 600" xmlns="http://www.w3.org/2000/svg" role="img">
  <title>Follow-up</title>
  <!-- shared defs -->
  <rect width="900" height="600" fill="#FFFFFF"/>
  <text class="t" x="450" y="60" text-anchor="middle">Follow-up &amp; prevention</text>
  <line x1="80" y1="260" x2="820" y2="260" stroke="#52606D" stroke-width="4" marker-end="url(#arr)"/>
  <!-- repeat a node per milestone; x = 80 + i*(740/(n-1)) -->
  <circle cx="100" cy="260" r="16" fill="#2E9E5B"/>
  <text class="l" x="100" y="220" text-anchor="middle">Diagnosis</text>
  <circle cx="340" cy="260" r="16" fill="#7B4FC9"/>
  <text class="l" x="340" y="220" text-anchor="middle">48–72 h</text>
  <text class="s" x="340" y="305" text-anchor="middle">Review response</text>
  <circle cx="580" cy="260" r="16" fill="#7B4FC9"/>
  <text class="l" x="580" y="220" text-anchor="middle">6 weeks</text>
  <text class="s" x="580" y="305" text-anchor="middle">Repeat CXR if needed</text>
  <circle cx="800" cy="260" r="16" fill="#2F6FD6"/>
  <text class="l" x="800" y="220" text-anchor="middle">Long term</text>
  <text class="s" x="800" y="305" text-anchor="middle">Vaccination</text>
  <text class="f" x="885" y="590" text-anchor="end">MedLens · Educational use</text>
</svg>
```

## 4. Treatment ladder (portrait)
```svg
<svg viewBox="0 0 600 900" xmlns="http://www.w3.org/2000/svg" role="img">
  <title>Treatment ladder</title>
  <!-- shared defs -->
  <rect width="600" height="900" fill="#FFFFFF"/>
  <text class="t" x="300" y="50" text-anchor="middle">Treatment ladder</text>
  <!-- step i (bottom = 1): y = 760 - i*130, width grows to the right like stairs -->
  <rect x="60"  y="700" width="300" height="90" rx="12" fill="#EAF2FD" stroke="#2F6FD6" stroke-width="2"/>
  <text class="l" x="80" y="752">Step 1 · [therapy]</text>
  <rect x="120" y="570" width="300" height="90" rx="12" fill="#D6E5FB" stroke="#2F6FD6" stroke-width="2"/>
  <text class="l" x="140" y="622">Step 2 · [therapy]</text>
  <rect x="180" y="440" width="300" height="90" rx="12" fill="#B9D2F7" stroke="#2F6FD6" stroke-width="2"/>
  <text class="l" x="200" y="492">Step 3 · [therapy]</text>
  <line x1="540" y1="780" x2="540" y2="450" stroke="#E8892B" stroke-width="4" marker-end="url(#arr)"/>
  <text class="s" x="560" y="620" transform="rotate(-90 560 620)" text-anchor="middle">if not controlled</text>
  <text class="s" x="300" y="840" text-anchor="middle">[Guideline, e.g. NICE NG136]</text>
  <text class="f" x="585" y="890" text-anchor="end">MedLens · Educational use</text>
</svg>
```

## 5. Body map (portrait) — clinical features / complications
```svg
<svg viewBox="0 0 600 900" xmlns="http://www.w3.org/2000/svg" role="img">
  <title>Clinical features</title>
  <!-- shared defs -->
  <rect width="600" height="900" fill="#FFFFFF"/>
  <text class="t" x="300" y="50" text-anchor="middle">Clinical features</text>
  <!-- neutral figure, anterior view; figure's RIGHT is viewer's LEFT -->
  <g fill="#E4E7EB" stroke="#9AA5B1" stroke-width="2">
    <circle cx="300" cy="130" r="48"/>
    <rect x="285" y="176" width="30" height="24"/>
    <path d="M220,200 Q300,185 380,200 L395,470 Q300,490 205,470 Z"/>
    <path d="M220,205 L165,420 L185,428 L240,240 Z"/>
    <path d="M380,205 L435,420 L415,428 L360,240 Z"/>
    <path d="M215,470 L235,800 L275,800 L292,485 Z"/>
    <path d="M385,470 L365,800 L325,800 L308,485 Z"/>
  </g>
  <!-- organs (optional, semi-transparent) -->
  <ellipse cx="265" cy="290" rx="38" ry="62" fill="#D64545" opacity=".25"/>
  <ellipse cx="335" cy="290" rx="38" ry="62" fill="#F5B5B5" opacity=".35"/>
  <!-- callout: dot on site -> line -> label at margin -->
  <circle cx="265" cy="320" r="7" fill="#D64545"/>
  <line x1="265" y1="320" x2="90" y2="320" stroke="#D64545" stroke-width="2"/>
  <text class="l" x="20" y="312">Crackles</text>
  <text class="s" x="20" y="334">R base</text>
  <circle cx="300" cy="215" r="7" fill="#D64545"/>
  <line x1="300" y1="215" x2="470" y2="215" stroke="#D64545" stroke-width="2"/>
  <text class="l" x="478" y="221">Cough</text>
  <circle cx="300" cy="100" r="7" fill="#E8892B"/>
  <line x1="300" y1="100" x2="470" y2="100" stroke="#E8892B" stroke-width="2"/>
  <text class="l" x="478" y="106">Fever</text>
  <text class="f" x="585" y="890" text-anchor="end">MedLens · Educational use</text>
</svg>
```
Rules: labels only in left margin (x < 160) or right margin (x > 470); callout lines
horizontal; symptoms red, signs/complications orange. Remember anatomical left/right.

## 6. Mechanism (landscape) — pharmacology
```svg
<svg viewBox="0 0 900 600" xmlns="http://www.w3.org/2000/svg" role="img">
  <title>Drug mechanism</title>
  <!-- shared defs -->
  <rect width="900" height="600" fill="#FFFFFF"/>
  <text class="t" x="450" y="60" text-anchor="middle">[Drug class]: mechanism</text>
  <!-- drug -->
  <rect x="50" y="230" width="200" height="110" rx="16" fill="#EAF2FD" stroke="#2F6FD6" stroke-width="2"/>
  <text class="l" x="150" y="280" text-anchor="middle">[Example drug]</text>
  <text class="s" x="150" y="306" text-anchor="middle">[class]</text>
  <line x1="250" y1="285" x2="345" y2="285" stroke="#2F6FD6" stroke-width="3" marker-end="url(#arr)"/>
  <!-- target -->
  <circle cx="450" cy="285" r="100" fill="#F5F7FA" stroke="#52606D" stroke-width="2"/>
  <text class="l" x="450" y="280" text-anchor="middle">[Target]</text>
  <text class="s" x="450" y="304" text-anchor="middle">[cell / receptor]</text>
  <line x1="365" y1="225" x2="405" y2="245" stroke="#D64545" stroke-width="5"/>
  <line x1="365" y1="245" x2="405" y2="225" stroke="#D64545" stroke-width="5"/>
  <line x1="550" y1="285" x2="645" y2="285" stroke="#52606D" stroke-width="3" marker-end="url(#arr)"/>
  <!-- effect -->
  <rect x="650" y="230" width="200" height="110" rx="16" fill="#E8F6EE" stroke="#2E9E5B" stroke-width="2"/>
  <text class="l" x="750" y="292" text-anchor="middle">[Effect]</text>
  <!-- why chosen -->
  <rect x="200" y="430" width="500" height="70" rx="12" fill="#F5F7FA" stroke="#2F6FD6" stroke-dasharray="6 4"/>
  <text class="l" x="450" y="472" text-anchor="middle">Why first-line: [≤ 6 words]</text>
  <text class="f" x="885" y="590" text-anchor="end">MedLens · Educational use</text>
</svg>
```

## 7. ECG strip (landscape) — investigations
```svg
<svg viewBox="0 0 900 600" xmlns="http://www.w3.org/2000/svg" role="img">
  <title>ECG: ST elevation</title>
  <!-- shared defs; add grid pattern -->
  <defs>
    <pattern id="g" width="20" height="20" patternUnits="userSpaceOnUse">
      <path d="M20 0 L0 0 0 20" fill="none" stroke="#F8C9C9" stroke-width="1"/>
    </pattern>
  </defs>
  <rect width="900" height="600" fill="#FFFFFF"/>
  <text class="t" x="450" y="60" text-anchor="middle">ECG: ST elevation (lead II)</text>
  <rect x="40" y="140" width="820" height="260" fill="url(#g)" stroke="#F0A0A0"/>
  <!-- one beat: baseline 300; P, QRS, elevated ST, T. Repeat with +260 x offset -->
  <polyline fill="none" stroke="#1F2933" stroke-width="3" points="
    40,300 90,300 100,288 110,300 125,300 132,310 142,190 152,320 160,270 200,262 225,250 245,275 300,300
    300,300 350,300 360,288 370,300 385,300 392,310 402,190 412,320 420,270 460,262 485,250 505,275 560,300
    560,300 610,300 620,288 630,300 645,300 652,310 662,190 672,320 680,270 720,262 745,250 765,275 860,300"/>
  <ellipse cx="180" cy="268" rx="34" ry="22" fill="none" stroke="#7B4FC9" stroke-width="3"/>
  <line x1="180" y1="246" x2="180" y2="110" stroke="#7B4FC9" stroke-width="2"/>
  <text class="l" x="190" y="115" fill="#7B4FC9">ST elevation</text>
  <text class="f" x="885" y="590" text-anchor="end">MedLens · Educational use</text>
</svg>
```

## 8. Lab values vs normal range (landscape) — user's own values
```svg
<svg viewBox="0 0 900 600" xmlns="http://www.w3.org/2000/svg" role="img">
  <title>Lab results</title>
  <!-- shared defs -->
  <rect width="900" height="600" fill="#FFFFFF"/>
  <text class="t" x="450" y="60" text-anchor="middle">Blood results vs normal range</text>
  <!-- row i: y = 130 + i*80. Bar 300→800 = scale; green band = normal range; dot = value -->
  <text class="l" x="60" y="146">CRP</text>
  <rect x="300" y="130" width="500" height="20" rx="10" fill="#F5F7FA"/>
  <rect x="300" y="130" width="40" height="20" rx="10" fill="#2E9E5B" opacity=".5"/>
  <circle cx="620" cy="140" r="12" fill="#D64545"/>
  <text class="l" x="640" y="120" fill="#D64545">↑ 180 mg/L</text>
  <text class="l" x="60" y="226">WCC</text>
  <rect x="300" y="210" width="500" height="20" rx="10" fill="#F5F7FA"/>
  <rect x="380" y="210" width="160" height="20" rx="10" fill="#2E9E5B" opacity=".5"/>
  <circle cx="610" cy="220" r="12" fill="#D64545"/>
  <text class="l" x="630" y="200" fill="#D64545">↑ 16 ×10⁹/L</text>
  <text class="s" x="300" y="560">Green band = reference range (check your lab's range)</text>
  <text class="f" x="885" y="590" text-anchor="end">MedLens · Educational use</text>
</svg>
```
Only plot values that are in the screenshot. Normal = green dot, abnormal = red dot.

## 9. Sequential panels (landscape) — pathogenesis / procedure steps
```svg
<svg viewBox="0 0 900 600" xmlns="http://www.w3.org/2000/svg" role="img">
  <title>How it develops</title>
  <!-- shared defs -->
  <rect width="900" height="600" fill="#FFFFFF"/>
  <text class="t" x="450" y="60" text-anchor="middle">How [disease] develops</text>
  <!-- n panels: width = (820 - (n-1)*30)/n ; here n = 4 -> 182.5 -->
  <g transform="translate(40,110)">
    <rect width="182" height="340" rx="14" fill="#F5F7FA" stroke="#52606D"/>
    <circle cx="30" cy="30" r="20" fill="#2E9E5B"/><text class="w" x="30" y="37" text-anchor="middle">1</text>
    <!-- simple schematic shape inside panel here -->
    <text class="l" x="91" y="310" text-anchor="middle">[Stage 1]</text>
  </g>
  <line x1="222" y1="280" x2="252" y2="280" stroke="#52606D" stroke-width="2" marker-end="url(#arr)"/>
  <g transform="translate(252,110)">
    <rect width="182" height="340" rx="14" fill="#F5F7FA" stroke="#52606D"/>
    <circle cx="30" cy="30" r="20" fill="#E8892B"/><text class="w" x="30" y="37" text-anchor="middle">2</text>
    <text class="l" x="91" y="310" text-anchor="middle">[Stage 2]</text>
  </g>
  <line x1="434" y1="280" x2="464" y2="280" stroke="#52606D" stroke-width="2" marker-end="url(#arr)"/>
  <g transform="translate(464,110)">
    <rect width="182" height="340" rx="14" fill="#F5F7FA" stroke="#52606D"/>
    <circle cx="30" cy="30" r="20" fill="#D64545"/><text class="w" x="30" y="37" text-anchor="middle">3</text>
    <text class="l" x="91" y="310" text-anchor="middle">[Stage 3]</text>
  </g>
  <line x1="646" y1="280" x2="676" y2="280" stroke="#52606D" stroke-width="2" marker-end="url(#arr)"/>
  <g transform="translate(676,110)">
    <rect width="182" height="340" rx="14" fill="#F5F7FA" stroke="#52606D"/>
    <circle cx="30" cy="30" r="20" fill="#D64545"/><text class="w" x="30" y="37" text-anchor="middle">4</text>
    <text class="l" x="91" y="310" text-anchor="middle">[Stage 4]</text>
  </g>
  <text class="f" x="885" y="590" text-anchor="end">MedLens · Educational use</text>
</svg>
```
Panel colour goes green → orange → red as disease progresses.

## 10. Hub-and-spoke (landscape) — causes & risk factors
```svg
<svg viewBox="0 0 900 600" xmlns="http://www.w3.org/2000/svg" role="img">
  <title>Causes and risk factors</title>
  <!-- shared defs -->
  <rect width="900" height="600" fill="#FFFFFF"/>
  <text class="t" x="450" y="60" text-anchor="middle">[Disease]: causes &amp; risk factors</text>
  <circle cx="450" cy="320" r="90" fill="#FDECEC" stroke="#D64545" stroke-width="3"/>
  <text class="l" x="450" y="326" text-anchor="middle">[Disease]</text>
  <!-- spoke i of n: angle = i*360/n; node at (450+230cos, 320+200sin). Orange = modifiable, grey = not -->
  <line x1="450" y1="230" x2="450" y2="140" stroke="#52606D" stroke-width="2"/>
  <rect x="360" y="100" width="180" height="44" rx="22" fill="#FFF4E8" stroke="#E8892B"/>
  <text class="l" x="450" y="128" text-anchor="middle">Smoking</text>
  <line x1="535" y1="290" x2="650" y2="250" stroke="#52606D" stroke-width="2"/>
  <rect x="650" y="228" width="180" height="44" rx="22" fill="#FFF4E8" stroke="#E8892B"/>
  <text class="l" x="740" y="256" text-anchor="middle">Alcohol</text>
  <line x1="365" y1="290" x2="250" y2="250" stroke="#52606D" stroke-width="2"/>
  <rect x="70" y="228" width="180" height="44" rx="22" fill="#EEF0F2" stroke="#9AA5B1"/>
  <text class="l" x="160" y="256" text-anchor="middle">Age &gt; 65</text>
  <text class="f" x="885" y="590" text-anchor="end">MedLens · Educational use</text>
</svg>
```

## 11. Comparison grid (landscape) — differentials / normal vs disease
Columns of equal width: `x = 40 + i*(820/n)`. Header row fill = category colour, body cells
`#F5F7FA`, 2–3 short rows per column. Normal-vs-disease schematic = 2 columns, left green
header "Normal", right red header "[Disease]", same schematic drawn in both with the change
highlighted in red on the right.

---

## HTML artifact shell
```html
<!doctype html>
<html lang="en"><head><meta charset="utf-8">
<meta name="viewport" content="width=device-width,initial-scale=1">
<title>MedLens — [Condition]</title>
<style>
:root{--bg:#fff;--fg:#1F2933;--muted:#52606D;--panel:#F5F7FA;--line:#E4E7EB;--blue:#2F6FD6}
@media (prefers-color-scheme:dark){:root:not([data-theme=light]){--bg:#111418;--fg:#E4E7EB;--muted:#9AA5B1;--panel:#1B2027;--line:#2A313A}}
body{margin:0;background:var(--bg);color:var(--fg);font:16px/1.5 system-ui,sans-serif}
header{position:sticky;top:0;background:var(--bg);border-bottom:1px solid var(--line);padding:12px 16px;display:flex;gap:12px;flex-wrap:wrap;align-items:baseline}
header h1{font-size:20px;margin:0}
.tag{font-size:13px;color:var(--muted)}
main{max-width:960px;margin:0 auto;padding:16px}
section{border:1px solid var(--line);border-radius:14px;padding:16px;margin:0 0 20px}
section h2{font-size:18px;margin:0 0 12px}
svg{width:100%;height:auto;border-radius:10px;background:#fff}
.prompt{background:var(--panel);border-radius:10px;padding:12px;margin-top:12px}
.prompt pre{white-space:pre-wrap;font-size:13px;margin:8px 0 0}
button{border:1px solid var(--line);background:var(--bg);color:var(--fg);border-radius:8px;padding:4px 10px;cursor:pointer}
footer{color:var(--muted);font-size:13px;text-align:center;padding:24px 16px}
</style></head><body>
<header><h1>🩺 MedLens — [Condition]</h1>
<span class="tag">[Mode] · Images [a]–[b] of [N] · Educational use only</span></header>
<main>
  <section id="img-1">
    <h2>1. [Title] · <small>[Category]</small></h2>
    <!-- inline <svg> here -->
    <ul><li>[caption bullet]</li></ul>
    <!-- only for prompt images: -->
    <div class="prompt"><strong>🖼️ Realistic version</strong> — paste into any image generator
      <button onclick="navigator.clipboard.writeText(this.nextElementSibling.textContent)">Copy</button>
      <pre>[full prompt]</pre></div>
  </section>
</main>
<footer>MedLens is for education only. It does not diagnose or prescribe. Always apply clinical
judgement and current local guidelines, and verify doses with an authoritative formulary.</footer>
</body></html>
```
