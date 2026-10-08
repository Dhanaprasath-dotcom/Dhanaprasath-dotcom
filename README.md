<div align="center">

## 📡 Real-Time Analytics

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 900 380" width="100%" height="380"
     preserveAspectRatio="xMidYMid meet" role="img"
     aria-label="Real-time analytics line graph with axes">

  <defs>
    <linearGradient id="bgGrad" x1="0%" y1="0%" x2="100%" y2="100%">
      <stop offset="0%"   stop-color="#050912"/>
      <stop offset="45%"  stop-color="#0b1530"/>
      <stop offset="100%" stop-color="#050912"/>
    </linearGradient>

    <linearGradient id="areaGrad" x1="0%" y1="0%" x2="0%" y2="100%">
      <stop offset="0%"   stop-color="#00E5FF" stop-opacity="0.45"/>
      <stop offset="55%"  stop-color="#7C4DFF" stop-opacity="0.18"/>
      <stop offset="100%" stop-color="#7C4DFF" stop-opacity="0"/>
    </linearGradient>

    <linearGradient id="lineGrad" x1="0%" y1="0%" x2="100%" y2="0%">
      <stop offset="0%"   stop-color="#00E5FF"/>
      <stop offset="40%"  stop-color="#38BDF8"/>
      <stop offset="72%"  stop-color="#A855F7"/>
      <stop offset="100%" stop-color="#F472B6"/>
    </linearGradient>

    <linearGradient id="ghostGrad" x1="0%" y1="0%" x2="100%" y2="0%">
      <stop offset="0%"   stop-color="#22D3EE"/>
      <stop offset="100%" stop-color="#F472B6"/>
    </linearGradient>

    <linearGradient id="scanGrad" x1="0%" y1="0%" x2="0%" y2="100%">
      <stop offset="0%"   stop-color="#00E5FF" stop-opacity="0"/>
      <stop offset="50%"  stop-color="#00E5FF" stop-opacity="0.30"/>
      <stop offset="100%" stop-color="#00E5FF" stop-opacity="0"/>
    </linearGradient>

    <filter id="glow" x="-60%" y="-60%" width="220%" height="220%">
      <feGaussianBlur stdDeviation="4" result="blur"/>
      <feMerge>
        <feMergeNode in="blur"/>
        <feMergeNode in="SourceGraphic"/>
      </feMerge>
    </filter>

    <clipPath id="plotClip">
      <rect x="70" y="50" width="770" height="240"/>
    </clipPath>

    <marker id="axisArrow" markerWidth="10" markerHeight="10"
            refX="8" refY="3" orient="auto" markerUnits="strokeWidth">
      <path d="M0,0 L8,3 L0,6 Z" fill="#4f7ba8"/>
    </marker>
  </defs>

  <style>
    .grid  { stroke:#1e3a5f; stroke-width:1; opacity:.45; }
    .axis  { stroke:#4f7ba8; stroke-width:1.8; opacity:.95; }
    .tick  { fill:#5f7fa8; font-family:'Segoe UI',Roboto,Helvetica,sans-serif;
             font-size:11px; letter-spacing:.5px; }
    .title { fill:#e2f4ff; font-family:'Segoe UI',Roboto,Helvetica,sans-serif;
             font-size:15px; font-weight:700; letter-spacing:2.4px; }
    .sub   { fill:#6f8fb8; font-family:'Segoe UI',Roboto,Helvetica,sans-serif;
             font-size:10.5px; letter-spacing:1.6px; }
    .axisLabel { fill:#7fa8d4; font-family:'Segoe UI',Roboto,Helvetica,sans-serif;
                 font-size:12px; font-weight:600; letter-spacing:1.2px; }

    .mainLine {
      fill:none;
      stroke:url(#lineGrad);
      stroke-width:3.2;
      stroke-linecap:round;
      stroke-linejoin:round;
      filter:url(#glow);
      stroke-dasharray:1200;
      stroke-dashoffset:1200;
      animation: draw 4.5s ease-out forwards;
    }
    @keyframes draw { to { stroke-dashoffset: 0; } }

    .ghostLine {
      fill:none;
      stroke:url(#ghostGrad);
      stroke-width:1.6;
      stroke-dasharray:6 10;
      opacity:.55;
      animation: dashMove 2.6s linear infinite;
    }
    @keyframes dashMove { to { stroke-dashoffset: -64; } }

    .area { opacity:0; animation: fadeUp 3s ease-out 2s forwards; }
    @keyframes fadeUp {
      from { opacity:0; transform: translateY(16px); }
      to   { opacity:1; transform: translateY(0); }
    }

    .scan { animation: scan 6s linear infinite; }
    @keyframes scan {
      0%   { transform: translateX(0);     opacity:0; }
      8%   { opacity:1; }
      92%  { opacity:1; }
      100% { transform: translateX(770px); opacity:0; }
    }

    .liveDot { animation: blink 1.1s ease-in-out infinite; }
    @keyframes blink { 0%,100% { opacity:1; } 50% { opacity:.12; } }
  </style>

  <!-- BACKGROUND -->
  <rect x="0" y="0" width="900" height="380" rx="18" fill="url(#bgGrad)"/>
  <rect x="0.5" y="0.5" width="899" height="379" rx="18"
        fill="none" stroke="#1b2f4d" stroke-width="1"/>

  <!-- TITLE + LIVE BADGE -->
  <text class="title" x="30" y="27">REAL-TIME ANALYTICS</text>
  <text class="sub"   x="30" y="45" opacity="0.85">CONTRIBUTIONS · COMMITS · LEARNING VELOCITY</text>

  <circle class="liveDot" cx="778" cy="20" r="5.5" fill="#F472B6"/>
  <text class="sub" x="792" y="24" fill="#F472B6">LIVE</text>

  <!-- PLOT AREA BACKGROUND -->
  <rect x="70" y="50" width="770" height="240" rx="4" fill="#07101f" opacity="0.55"/>

  <!-- GRID LAYER -->
  <g class="grid">
    <line x1="70" y1="50"  x2="840" y2="50"/>
    <line x1="70" y1="98"  x2="840" y2="98"/>
    <line x1="70" y1="146" x2="840" y2="146"/>
    <line x1="70" y1="194" x2="840" y2="194"/>
    <line x1="70" y1="242" x2="840" y2="242"/>
    <line x1="70" y1="290" x2="840" y2="290"/>

    <line x1="198.5" y1="50" x2="198.5" y2="290"/>
    <line x1="326.9" y1="50" x2="326.9" y2="290"/>
    <line x1="455.4" y1="50" x2="455.4" y2="290"/>
    <line x1="583.8" y1="50" x2="583.8" y2="290"/>
    <line x1="712.3" y1="50" x2="712.3" y2="290"/>
  </g>

  <!-- AXES -->
  <line class="axis" x1="70" y1="290" x2="850" y2="290" marker-end="url(#axisArrow)"/>
  <line class="axis" x1="70" y1="290" x2="70"  y2="40"  marker-end="url(#axisArrow)"/>

  <!-- X-AXIS TICKS -->
  <g class="axis">
    <line x1="70"  y1="290" x2="70"  y2="296"/>
    <line x1="198.5" y1="290" x2="198.5" y2="296"/>
    <line x1="326.9" y1="290" x2="326.9" y2="296"/>
    <line x1="455.4" y1="290" x2="455.4" y2="296"/>
    <line x1="583.8" y1="290" x2="583.8" y2="296"/>
    <line x1="712.3" y1="290" x2="712.3" y2="296"/>
    <line x1="840" y1="290" x2="840" y2="296"/>
  </g>

  <!-- Y-AXIS TICKS -->
  <g class="axis">
    <line x1="64" y1="50"  x2="70" y2="50"/>
    <line x1="64" y1="98"  x2="70" y2="98"/>
    <line x1="64" y1="146" x2="70" y2="146"/>
    <line x1="64" y1="194" x2="70" y2="194"/>
    <line x1="64" y1="242" x2="70" y2="242"/>
    <line x1="64" y1="290" x2="70" y2="290"/>
  </g>

  <!-- Y LABELS -->
  <text class="tick" x="56" y="54"  text-anchor="end">100</text>
  <text class="tick" x="56" y="102" text-anchor="end">80</text>
  <text class="tick" x="56" y="150" text-anchor="end">60</text>
  <text class="tick" x="56" y="198" text-anchor="end">40</text>
  <text class="tick" x="56" y="246" text-anchor="end">20</text>
  <text class="tick" x="56" y="294" text-anchor="end">0</text>

  <!-- X LABELS -->
  <text class="tick" x="70"   y="314" text-anchor="middle">-60s</text>
  <text class="tick" x="326.9" y="314" text-anchor="middle">-40s</text>
  <text class="tick" x="583.8" y="314" text-anchor="middle">-20s</text>
  <text class="tick" x="840"  y="314" text-anchor="middle" fill="#F472B6">now</text>

  <!-- AXIS TITLES -->
  <text class="axisLabel" x="455" y="338" text-anchor="middle">TIME (s)</text>
  <text class="axisLabel" x="22" y="170" text-anchor="middle"
        transform="rotate(-90 22 170)">ACTIVITY INDEX</text>

  <!-- PLOT LAYER -->
  <g clip-path="url(#plotClip)">

    <!-- AREA FILL -->
    <path class="area" fill="url(#areaGrad)"
      d="M70,242 L129.2,218 L188.5,230 L247.7,182 L306.9,194 L366.2,158 L425.4,170
         L484.6,122 L543.8,134 L603.1,98 L662.3,110 L721.5,74 L780.8,86 L840,50
         L840,290 L70,290 Z"/>

    <!-- SECONDARY DASHED SERIES -->
    <path class="ghostLine"
      d="M70,254 L129.2,230 L188.5,242 L247.7,206 L306.9,218 L366.2,182 L425.4,194
         L484.6,158 L543.8,170 L603.1,134 L662.3,146 L721.5,110 L780.8,122 L840,98"/>

    <!-- MAIN GRADIENT LINE -->
    <path class="mainLine"
      d="M70,242 L129.2,218 L188.5,230 L247.7,182 L306.9,194 L366.2,158 L425.4,170
         L484.6,122 L543.8,134 L603.1,98 L662.3,110 L721.5,74 L780.8,86 L840,50"/>

    <!-- SCANNING BEAM -->
    <rect class="scan" x="70" y="50" width="3" height="240" fill="url(#scanGrad)"/>

    <!-- PULSING DATA POINTS -->
    <circle cx="484.6" cy="122" r="5" fill="#00E5FF" filter="url(#glow)"/>
    <circle cx="484.6" cy="122" r="5" fill="none" stroke="#00E5FF" stroke-width="2">
      <animate attributeName="r" values="5;22" dur="2.4s" repeatCount="indefinite"/>
      <animate attributeName="opacity" values="0.85;0" dur="2.4s" repeatCount="indefinite"/>
    </circle>

    <circle cx="840" cy="50" r="5.5" fill="#F472B6" filter="url(#glow)"/>
    <circle cx="840" cy="50" r="5.5" fill="none" stroke="#F472B6" stroke-width="2">
      <animate attributeName="r" values="5.5;24" dur="2.4s" begin="0.8s" repeatCount="indefinite"/>
      <animate attributeName="opacity" values="0.85;0" dur="2.4s" begin="0.8s" repeatCount="indefinite"/>
    </circle>

    <circle cx="366.2" cy="158" r="4" fill="#A855F7">
      <animate attributeName="r" values="4;14" dur="2.6s" begin="1.4s" repeatCount="indefinite"/>
      <animate attributeName="opacity" values="0.7;0" dur="2.6s" begin="1.4s" repeatCount="indefinite"/>
    </circle>

    <!-- TRAVELLING PULSE -->
    <circle r="6" fill="#00E5FF" filter="url(#glow)">
      <animateMotion dur="7s" repeatCount="indefinite"
        path="M70,242 L129.2,218 L188.5,230 L247.7,182 L306.9,194 L366.2,158 L425.4,170
              L484.6,122 L543.8,134 L603.1,98 L662.3,110 L721.5,74 L780.8,86 L840,50"/>
      <animate attributeName="opacity" values="0;1;1;0" dur="7s"
               repeatCount="indefinite"/>
    </circle>
  </g>

  <!-- LEGEND -->
  <line x1="70"  y1="358" x2="100" y2="358" stroke="#00E5FF" stroke-width="3" stroke-linecap="round"/>
  <text class="sub" x="108" y="362">ACTIVITY INDEX</text>

  <line x1="260" y1="358" x2="290" y2="358" stroke="#A855F7" stroke-width="2"
        stroke-dasharray="6 6" stroke-linecap="round"/>
  <text class="sub" x="298" y="362">LEARNING VELOCITY</text>

  <text class="sub" x="840" y="362" text-anchor="end" fill="#3f5c80">AUTO-REFRESHING VIEW</text>

</svg>

</div>
