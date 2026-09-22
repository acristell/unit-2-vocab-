
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Unit 2 Science Vocabulary Flashcards</title>
  <script src="https://cdn.tailwindcss.com"></script>
  <link href="https://fonts.googleapis.com/css2?family=Fredoka:wght@400;500;600;700&family=Nunito:wght@400;600;700;800&display=swap" rel="stylesheet">
  <style>
    body {
      font-family: 'Nunito', sans-serif;
      background-color: #f0f4f8;
    }
    .font-heading {
      font-family: 'Fredoka', sans-serif;
    }
    /* Perspective for 3D flip card effect */
    .perspective-1000 {
      perspective: 1000px;
    }
    .transform-style-3d {
      transform-style: preserve-3d;
      transition: transform 0.6s cubic-bezier(0.4, 0, 0.2, 1);
    }
    .backface-hidden {
      backface-visibility: hidden;
      -webkit-backface-visibility: hidden;
    }
    .rotate-y-180 {
      transform: rotateY(180deg);
    }
    /* Card specific themes matching Canva slides */
    .card-theme-blue {
      background: linear-gradient(135deg, #e6f3ff 0%, #d4e9ff 100%);
      border: 3px solid #7cb9e8;
    }
    .card-theme-green {
      background: linear-gradient(135deg, #e8f8f2 0%, #d1f2e4 100%);
      border: 3px solid #52be80;
    }
    .card-theme-yellow {
      background: linear-gradient(135deg, #fefde8 0%, #fff9c4 100%);
      border: 3px solid #f4d03f;
    }
    .card-theme-cyan {
      background: linear-gradient(135deg, #e0f7fa 0%, #b2ebf2 100%);
      border: 3px solid #26c6da;
    }
    .card-theme-orange {
      background: linear-gradient(135deg, #fff3e0 0%, #ffe0b2 100%);
      border: 3px solid #ff9800;
    }

    .badge-teal {
      background-color: #00838f;
      color: white;
    }

    /* Custom scrollbars */
    ::-webkit-scrollbar {
      width: 8px;
      height: 8px;
    }
    ::-webkit-scrollbar-track {
      background: #f1f1f1;
    }
    ::-webkit-scrollbar-thumb {
      background: #888;
      border-radius: 4px;
    }
    ::-webkit-scrollbar-thumb:hover {
      background: #555;
    }
  </style>
</head>
<body class="min-h-screen text-slate-800 flex flex-col justify-between">

  <!-- TOP BANNER HEADER (Matching Canva Theme) -->
  <header class="bg-gradient-to-r from-teal-700 via-cyan-600 to-teal-800 text-white shadow-lg sticky top-0 z-50">
    <div class="max-w-6xl mx-auto px-4 py-3 flex flex-col md:flex-row justify-between items-center gap-3">
      <div class="flex items-center space-x-3">
        <!-- Bulb / Atom Icon -->
        <div class="bg-yellow-400 p-2.5 rounded-2xl text-teal-900 shadow-md">
          <svg class="w-8 h-8" fill="currentColor" viewBox="0 0 24 24">
            <path d="M12 2C8.13 2 5 5.13 5 9c0 2.38 1.19 4.47 3 5.74V17c0 .55.45 1 1 1h6c.55 0 1-.45 1-1v-2.26c1.81-1.27 3-3.36 3-5.74 0-3.87-3.13-7-7-7zm-1 18h2v1h-2v-1zm-3-1h8v1H8v-1z"/>
          </svg>
        </div>
        <div>
          <div class="flex items-center gap-2">
            <span class="bg-teal-900 text-teal-200 text-xs font-bold px-2 py-0.5 rounded-full tracking-wider uppercase">Unit 2 Science</span>
            <span class="text-xs text-teal-100 font-medium hidden sm:inline">Energy in Action & Conservation</span>
          </div>
          <h1 class="text-2xl md:text-3xl font-extrabold tracking-tight font-heading">Interactive Science Flashcards</h1>
        </div>
      </div>

      <!-- Mode Toggles -->
      <div class="flex items-center bg-teal-900/60 p-1.5 rounded-xl border border-teal-500/30">
        <button id="btn-mode-flashcard" onclick="setMode('flashcard')" class="px-3 py-1.5 rounded-lg text-xs font-bold transition-all bg-white text-teal-900 shadow">
          🎴 Single Card
        </button>
        <button id="btn-mode-grid" onclick="setMode('grid')" class="px-3 py-1.5 rounded-lg text-xs font-bold text-teal-100 hover:text-white transition-all">
          🖼️ Grid View
        </button>
        <button id="btn-mode-quiz" onclick="setMode('quiz')" class="px-3 py-1.5 rounded-lg text-xs font-bold text-teal-100 hover:text-white transition-all">
          🧠 Self Quiz
        </button>
      </div>
    </div>
  </header>

  <!-- MAIN CONTAINER -->
  <main class="max-w-5xl mx-auto px-4 py-6 flex-grow w-full">

    <!-- CONTROLS & FILTER BAR -->
    <div class="bg-white rounded-2xl p-4 shadow-sm border border-slate-200 mb-6 flex flex-wrap items-center justify-between gap-4">
      <!-- Filter dropdown -->
      <div class="flex items-center space-x-2">
        <label for="lesson-select" class="text-xs font-bold uppercase tracking-wider text-slate-500">Select Lesson:</label>
        <select id="lesson-select" onchange="filterCards()" class="bg-slate-100 border border-slate-300 rounded-xl px-3 py-2 text-sm font-bold text-slate-700 focus:outline-none focus:ring-2 focus:ring-teal-500">
          <option value="ALL">All Lessons (39 Cards)</option>
          <option value="2.05">Lesson 2.05: Energy in Action</option>
          <option value="2.06">Lesson 2.06: Conservation & Systems</option>
          <option value="2.07">Lesson 2.07: Gravitational Potential Energy</option>
          <option value="2.08">Lesson 2.08: Elastic Potential Energy</option>
          <option value="2.09">Lesson 2.09: Chemical Potential & Reactions</option>
          <option value="2.10">Lesson 2.10: Molecules in Motion</option>
          <option value="2.11">Lesson 2.11: Conduction & Thermal</option>
          <option value="2.12">Lesson 2.12: Convection & Heat Transfer</option>
          <option value="2.13">Lesson 2.13: Radiation & EM Waves</option>
        </select>
      </div>

      <!-- Quick Stats & Actions -->
      <div class="flex items-center space-x-3 text-xs font-semibold">
        <button onclick="shuffleCards()" class="flex items-center gap-1.5 bg-slate-100 hover:bg-slate-200 text-slate-700 px-3 py-2 rounded-xl transition border border-slate-200">
          🔀 Shuffle
        </button>
        <button onclick="resetProgress()" class="flex items-center gap-1.5 bg-slate-100 hover:bg-slate-200 text-slate-700 px-3 py-2 rounded-xl transition border border-slate-200">
          🔄 Reset Marks
        </button>
        <div class="bg-teal-50 text-teal-800 px-3 py-2 rounded-xl border border-teal-200 flex items-center gap-2">
          <span>Mastered: <strong id="mastered-count" class="text-teal-700 font-extrabold">0</strong></span>
        </div>
      </div>
    </div>

    <!-- FLASHCARD SINGLE VIEW MODE -->
    <div id="view-flashcard" class="flex flex-col items-center">
      
      <!-- Progress Bar -->
      <div class="w-full max-w-2xl flex items-center justify-between text-xs font-bold text-slate-500 mb-2 px-1">
        <span id="card-indicator">Card 1 of 39</span>
        <span id="lesson-badge-top" class="bg-teal-700 text-white px-2.5 py-0.5 rounded-full font-bold">Lesson 2.05</span>
      </div>
      <div class="w-full max-w-2xl bg-slate-200 h-2.5 rounded-full overflow-hidden mb-6">
        <div id="progress-bar" class="bg-gradient-to-r from-teal-500 to-cyan-500 h-full transition-all duration-300" style="width: 2.5%;"></div>
      </div>

      <!-- FLIP CARD CONTAINER -->
      <div class="w-full max-w-2xl h-[420px] sm:h-[460px] perspective-1000 cursor-pointer group" onclick="flipCurrentCard()">
        <div id="card-inner" class="relative w-full h-full transform-style-3d rounded-3xl shadow-xl transition-transform duration-500">
          
          <!-- FRONT SIDE (Word + Picture graphic) -->
          <div id="card-front" class="absolute inset-0 w-full h-full backface-hidden rounded-3xl p-6 flex flex-col justify-between items-center text-center border-4 card-theme-blue shadow-inner">
            <!-- Header Tag -->
            <div class="w-full flex justify-between items-center">
              <span id="front-lesson-badge" class="badge-teal text-xs px-3 py-1 rounded-full font-bold uppercase tracking-wider">Unit 2 | Lesson 2.05</span>
              <span class="text-xs text-slate-500 font-bold flex items-center gap-1">
                <svg class="w-4 h-4" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M15 15l-2 5L9 9l11 4-5 2zm0 0l5 5M7.188 2.239l.777 2.897M5.136 7.965l-2.898-.777M13.95 4.05l-2.122 2.122m-5.657 5.656l-2.12 2.122"/></svg>
                Click to flip
              </span>
            </div>

            <!-- Title Word -->
            <h2 id="front-word" class="text-3xl sm:text-4xl font-extrabold text-slate-800 font-heading tracking-wide my-1">
              Energy Transfer
            </h2>

            <!-- Visual Graphic Container -->
            <div id="front-graphic" class="w-full max-w-[280px] h-48 sm:h-56 bg-white/80 backdrop-blur-sm rounded-2xl border border-white/60 shadow-sm flex items-center justify-center p-3 my-2 overflow-hidden">
              <!-- SVG graphic injected dynamically -->
            </div>

            <!-- Footer Hint -->
            <p class="text-xs font-semibold text-slate-500 flex items-center gap-1">
              💡 <span id="front-hint">Look closely at how energy moves between objects</span>
            </p>
          </div>

          <!-- BACK SIDE (Definition + Example) -->
          <div id="card-back" class="absolute inset-0 w-full h-full backface-hidden rotate-y-180 rounded-3xl p-6 flex flex-col justify-between items-center text-left border-4 card-theme-blue bg-white shadow-inner">
            <!-- Header -->
            <div class="w-full flex justify-between items-center border-b pb-2 border-slate-200">
              <span id="back-word-title" class="text-lg font-bold text-teal-800 font-heading">Energy Transfer</span>
              <span class="text-xs text-slate-400 font-semibold">DEFINITION & EXAMPLE</span>
            </div>

            <!-- Definition Box -->
            <div class="w-full my-auto space-y-4">
              <div>
                <span class="text-xs font-extrabold uppercase tracking-wider text-teal-600">Definition:</span>
                <p id="back-definition" class="text-slate-800 text-lg sm:text-xl font-bold leading-relaxed mt-1">
                  Movement of energy from one object to another.
                </p>
              </div>

              <!-- Example Box -->
              <div class="bg-amber-50 border-l-4 border-amber-400 p-3.5 rounded-r-xl">
                <span class="text-xs font-extrabold uppercase tracking-wider text-amber-700 block">Real-World Example:</span>
                <p id="back-example" class="text-amber-900 text-sm sm:text-base font-semibold mt-0.5">
                  Energy (heat) moves from the hot cup to the cold cup.
                </p>
              </div>
            </div>

            <!-- Bottom Action controls -->
            <div class="w-full flex justify-between items-center pt-2 border-t border-slate-100" onclick="event.stopPropagation()">
              <button id="btn-mastered" onclick="toggleMastered(event)" class="text-xs font-bold px-3 py-1.5 rounded-xl border transition flex items-center gap-1.5 bg-slate-100 text-slate-600 border-slate-300 hover:bg-emerald-50 hover:text-emerald-700">
                <span>Check</span> Mark as Mastered
              </button>
              <span class="text-xs text-slate-400">Press <strong>Space</strong> or Click to flip back</span>
            </div>

          </div>

        </div>
      </div>

      <!-- NAVIGATION BUTTONS -->
      <div class="flex items-center space-x-4 mt-6">
        <button onclick="prevCard()" class="bg-white hover:bg-slate-100 text-slate-700 border border-slate-300 font-bold px-5 py-2.5 rounded-2xl shadow-sm transition flex items-center gap-2">
          ⬅️ Prev
        </button>
        <button onclick="flipCurrentCard()" class="bg-teal-600 hover:bg-teal-700 text-white font-bold px-6 py-2.5 rounded-2xl shadow-md transition flex items-center gap-2">
          🔄 Flip Card
        </button>
        <button onclick="nextCard()" class="bg-teal-700 hover:bg-teal-800 text-white font-bold px-5 py-2.5 rounded-2xl shadow-md transition flex items-center gap-2">
          Next ➡️
        </button>
      </div>

      <p class="text-xs text-slate-400 mt-4">Tip: Use <strong>Left / Right Arrows</strong> to navigate, <strong>Spacebar</strong> to flip card.</p>
    </div>

    <!-- GRID VIEW MODE -->
    <div id="view-grid" class="hidden">
      <div id="grid-cards-container" class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-6">
        <!-- Grid card items populated dynamically -->
      </div>
    </div>

    <!-- QUIZ MODE -->
    <div id="view-quiz" class="hidden flex flex-col items-center">
      <div class="w-full max-w-xl bg-white rounded-3xl p-6 shadow-md border border-slate-200">
        <div class="flex justify-between items-center mb-4">
          <span class="text-xs font-bold text-teal-700 uppercase tracking-wide">Self-Assessment Quiz Mode</span>
          <span id="quiz-progress" class="text-xs font-bold text-slate-500">Question 1 of 39</span>
        </div>

        <!-- Question Graphic & Word -->
        <div id="quiz-question-container" class="text-center my-4">
          <div id="quiz-graphic" class="w-48 h-40 mx-auto bg-slate-50 rounded-2xl border border-slate-200 flex items-center justify-center p-2 mb-4"></div>
          <h3 id="quiz-word" class="text-2xl font-extrabold text-slate-800 font-heading">Energy Transfer</h3>
          <p class="text-xs text-slate-500 mt-1">Can you recall the definition and example?</p>
        </div>

        <!-- Reveal Definition Button -->
        <div id="quiz-answer-box" class="hidden bg-slate-50 p-4 rounded-2xl border border-slate-200 my-4 text-left">
          <span class="text-xs font-extrabold uppercase text-teal-600">Definition:</span>
          <p id="quiz-def" class="text-slate-800 font-bold mb-2">Movement of energy from one object to another.</p>
          <span class="text-xs font-extrabold uppercase text-amber-600">Example:</span>
          <p id="quiz-ex" class="text-slate-700 font-semibold text-sm">Energy (heat) moves from the hot cup to the cold cup.</p>
        </div>

        <!-- Action Controls -->
        <button id="btn-quiz-reveal" onclick="revealQuizAnswer()" class="w-full bg-teal-600 text-white font-bold py-3 rounded-2xl shadow-md hover:bg-teal-700 transition my-2">
          Show Definition & Example
        </button>

        <div id="quiz-grading-btns" class="hidden grid grid-cols-2 gap-3 mt-3">
          <button onclick="gradeQuiz(false)" class="bg-red-100 hover:bg-red-200 text-red-700 font-bold py-2.5 rounded-xl border border-red-200 transition">
            ❌ Need Practice
          </button>
          <button onclick="gradeQuiz(true)" class="bg-emerald-100 hover:bg-emerald-200 text-emerald-800 font-bold py-2.5 rounded-xl border border-emerald-300 transition">
            ✅ Got It Right!
          </button>
        </div>
      </div>
    </div>

  </main>

  <!-- FOOTER -->
  <footer class="bg-slate-800 text-slate-400 py-4 text-center text-xs mt-12 border-t border-slate-700">
    <p class="font-semibold">Unit 2 Science Vocabulary • Energy Transfer, Transformation, Conservation & Heat</p>
  </footer>

  <!-- SCRIPT & FLASHCARD DATA -->
  <script>
    // FLASHCARD DATASET FROM THE CANVA SLIDES
    const cardData = [
      // LESSON 2.05
      {
        id: 1,
        lesson: "2.05",
        lessonTitle: "Unit 2 | Lesson 2.05",
        word: "Energy Transfer",
        theme: "blue",
        definition: "Movement of energy from one object to another.",
        example: "Energy (heat) moves from the hot cup to the cold cup.",
        hint: "Heat moving from hot mug to cold mug",
        svg: `<svg viewBox="0 0 200 120" class="w-full h-full">
          <!-- Red Mug -->
          <rect x="25" y="45" width="35" height="40" rx="4" fill="#e74c3c"/>
          <path d="M 25 55 C 10 55, 10 75, 25 75" stroke="#e74c3c" stroke-width="4" fill="none"/>
          <!-- Steam -->
          <path d="M 32 38 Q 36 30 32 24" stroke="#ff7675" stroke-width="2.5" fill="none"/>
          <path d="M 42 38 Q 46 30 42 24" stroke="#ff7675" stroke-width="2.5" fill="none"/>
          <path d="M 52 38 Q 56 30 52 24" stroke="#ff7675" stroke-width="2.5" fill="none"/>
          <!-- Heat Arrows -->
          <path d="M 70 60 L 110 60" stroke="#f39c12" stroke-width="6" stroke-linecap="round"/>
          <polygon points="110,53 125,60 110,67" fill="#f39c12"/>
          <!-- Blue Mug -->
          <rect x="135" y="45" width="35" height="40" rx="4" fill="#3498db"/>
          <path d="M 170 55 C 185 55, 185 75, 170 75" stroke="#3498db" stroke-width="4" fill="none"/>
        </svg>`
      },
      {
        id: 2,
        lesson: "2.05",
        lessonTitle: "Unit 2 | Lesson 2.05",
        word: "Energy Transformation",
        theme: "green",
        definition: "Change of energy from one form to another.",
        example: "Chemical energy in the battery transforms into light and thermal energy.",
        hint: "A flashlight converting stored battery power into bright light",
        svg: `<svg viewBox="0 0 200 120" class="w-full h-full">
          <!-- Flashlight Body -->
          <rect x="30" y="45" width="65" height="30" rx="5" fill="#16a085"/>
          <polygon points="95,40 125,30 125,90 95,80" fill="#1abc9c"/>
          <!-- Switch -->
          <rect x="50" y="38" width="15" height="7" rx="2" fill="#2c3e50"/>
          <!-- Light Beam Rays -->
          <polygon points="125,30 190,10 190,110 125,90" fill="#f1c40f" opacity="0.6"/>
          <line x1="125" y1="30" x2="195" y2="5" stroke="#f39c12" stroke-width="2" stroke-dasharray="4"/>
          <line x1="125" y1="90" x2="195" y2="115" stroke="#f39c12" stroke-width="2" stroke-dasharray="4"/>
        </svg>`
      },
      {
        id: 3,
        lesson: "2.05",
        lessonTitle: "Unit 2 | Lesson 2.05",
        word: "Mechanical Energy",
        theme: "blue",
        definition: "Energy of motion and position.",
        example: "A roller coaster has mechanical energy as it moves and when it is at the top of a hill (position).",
        hint: "Kinetic motion + Potential position on a coaster track",
        svg: `<svg viewBox="0 0 200 120" class="w-full h-full">
          <!-- Coaster Track Hill -->
          <path d="M 10 100 Q 80 10 130 70 T 190 100" stroke="#7f8c8d" stroke-width="5" fill="none"/>
          <!-- Supports -->
          <line x1="80" y1="35" x2="80" y2="100" stroke="#bdc3c7" stroke-width="3"/>
          <line x1="130" y1="70" x2="130" y2="100" stroke="#bdc3c7" stroke-width="3"/>
          <!-- Coaster Cart -->
          <rect x="68" y="22" width="24" height="14" rx="3" fill="#e74c3c"/>
          <circle cx="74" cy="38" r="3" fill="#2c3e50"/>
          <circle cx="86" cy="38" r="3" fill="#2c3e50"/>
          <!-- Passengers -->
          <circle cx="74" cy="18" r="3" fill="#34495e"/>
          <circle cx="86" cy="18" r="3" fill="#34495e"/>
        </svg>`
      },
      {
        id: 4,
        lesson: "2.05",
        lessonTitle: "Unit 2 | Lesson 2.05",
        word: "Chemical Energy",
        theme: "yellow",
        definition: "Energy stored in chemical bonds.",
        example: "A battery stores chemical energy that can be released to do work (e.g., power a toy).",
        hint: "Energy stored inside batteries and chemical bonds",
        svg: `<svg viewBox="0 0 200 120" class="w-full h-full">
          <!-- Battery Body -->
          <rect x="70" y="30" width="60" height="75" rx="8" fill="#e67e22"/>
          <rect x="90" y="20" width="20" height="10" rx="2" fill="#7f8c8d"/>
          <!-- Lightning Icon -->
          <polygon points="105,38 88,68 100,68 95,95 112,62 100,62" fill="#f1c40f" stroke="#d35400" stroke-width="1"/>
        </svg>`
      },
      {
        id: 5,
        lesson: "2.05",
        lessonTitle: "Unit 2 | Lesson 2.05",
        word: "Thermal Energy",
        theme: "blue",
        definition: "Energy related to heat.",
        example: "A fire has thermal energy, which moves from the hotter object to the cooler surroundings.",
        hint: "Heat energy emitted from burning wood",
        svg: `<svg viewBox="0 0 200 120" class="w-full h-full">
          <!-- Logs -->
          <rect x="50" y="85" width="100" height="14" rx="4" fill="#795548" transform="rotate(-10 100 90)"/>
          <rect x="50" y="85" width="100" height="14" rx="4" fill="#5d4037" transform="rotate(10 100 90)"/>
          <!-- Flame Outer -->
          <path d="M 100 20 C 130 50, 130 85, 100 85 C 70 85, 70 50, 100 20 Z" fill="#ff5722"/>
          <!-- Flame Inner -->
          <path d="M 100 40 C 118 60, 118 85, 100 85 C 82 85, 82 60, 100 40 Z" fill="#ffeb3b"/>
        </svg>`
      },

      // LESSON 2.06
      {
        id: 6,
        lesson: "2.06",
        lessonTitle: "Unit 2 | Lesson 2.06",
        word: "Conservation of Energy",
        theme: "cyan",
        definition: "The principle that energy cannot be created or destroyed, only transformed from one form to another.",
        example: "Energy is always conserved in a closed system!",
        hint: "Energy cannot be created or destroyed, only converted",
        svg: `<svg viewBox="0 0 200 120" class="w-full h-full">
          <!-- Recycling Circle Arrows -->
          <path d="M 100 20 A 40 40 0 0 1 140 60" fill="none" stroke="#2980b9" stroke-width="8" stroke-linecap="round"/>
          <polygon points="145,65 140,50 130,60" fill="#2980b9"/>
          
          <path d="M 140 60 A 40 40 0 0 1 80 98" fill="none" stroke="#27ae60" stroke-width="8" stroke-linecap="round"/>
          <polygon points="73,95 85,102 85,88" fill="#27ae60"/>

          <path d="M 80 98 A 40 40 0 0 1 100 20" fill="none" stroke="#f39c12" stroke-width="8" stroke-linecap="round"/>
          <polygon points="100,12 92,26 106,26" fill="#f39c12"/>
          
          <text x="100" y="64" text-anchor="middle" font-size="10" font-weight="bold" fill="#2c3e50">CONSERVED</text>
        </svg>`
      },
      {
        id: 7,
        lesson: "2.06",
        lessonTitle: "Unit 2 | Lesson 2.06",
        word: "Potential Energy",
        theme: "blue",
        definition: "Stored energy due to position or condition.",
        example: "A rock at the top of a hill has gravitational potential energy.",
        hint: "Energy stored at a high position before motion occurs",
        svg: `<svg viewBox="0 0 200 120" class="w-full h-full">
          <!-- Cliff Ledge -->
          <polygon points="10,110 80,40 120,40 120,110" fill="#7f8c8d"/>
          <!-- Rock on Ledge -->
          <ellipse cx="90" cy="28" rx="16" ry="12" fill="#34495e"/>
          <!-- Motion Arrow Down -->
          <path d="M 125 35 L 125 75" stroke="#e74c3c" stroke-width="4" stroke-dasharray="4"/>
          <polygon points="125,82 120,70 130,70" fill="#e74c3c"/>
        </svg>`
      },
      {
        id: 8,
        lesson: "2.06",
        lessonTitle: "Unit 2 | Lesson 2.06",
        word: "Kinetic Energy",
        theme: "yellow",
        definition: "Energy of motion.",
        example: "A moving soccer ball has kinetic energy.",
        hint: "Energy of anything that is actively moving",
        svg: `<svg viewBox="0 0 200 120" class="w-full h-full">
          <!-- Speed Lines -->
          <line x1="20" y1="40" x2="80" y2="40" stroke="#bdc3c7" stroke-width="3" stroke-linecap="round"/>
          <line x1="10" y1="60" x2="90" y2="60" stroke="#bdc3c7" stroke-width="4" stroke-linecap="round"/>
          <line x1="30" y1="80" x2="75" y2="80" stroke="#bdc3c7" stroke-width="3" stroke-linecap="round"/>
          <!-- Flying Soccer Ball -->
          <circle cx="130" cy="60" r="28" fill="#ffffff" stroke="#2c3e50" stroke-width="3"/>
          <polygon points="130,42 142,50 138,65 122,65 118,50" fill="#2c3e50"/>
        </svg>`
      },
      {
        id: 9,
        lesson: "2.06",
        lessonTitle: "Unit 2 | Lesson 2.06",
        word: "System",
        theme: "cyan",
        definition: "A set of objects we study together.",
        example: "The contents of the beaker are the system.",
        hint: "The specific group of objects under scientific observation",
        svg: `<svg viewBox="0 0 200 120" class="w-full h-full">
          <!-- Glass Beaker -->
          <rect x="65" y="30" width="70" height="70" rx="4" fill="none" stroke="#34495e" stroke-width="4"/>
          <!-- Liquid Inside -->
          <rect x="68" y="55" width="64" height="42" fill="#3498db" opacity="0.6"/>
          <!-- Label Inside -->
          <rect x="75" y="65" width="50" height="20" rx="4" fill="#ffffff"/>
          <text x="100" y="79" text-anchor="middle" font-size="11" font-weight="bold" fill="#2c3e50">System</text>
        </svg>`
      },

      // LESSON 2.07
      {
        id: 10,
        lesson: "2.07",
        lessonTitle: "Unit 2 | Lesson 2.07",
        word: "Gravitational Potential Energy (GPE)",
        theme: "blue",
        definition: "The energy an object has due to its position in a gravitational field.",
        example: "A ball at the top of a cliff has more gravitational potential energy than the same ball on the ground.",
        hint: "Stored energy proportional to height and mass",
        svg: `<svg viewBox="0 0 200 120" class="w-full h-full">
          <!-- Cliff -->
          <rect x="20" y="50" width="70" height="60" fill="#7f8c8d"/>
          <!-- Ball on cliff -->
          <circle cx="55" cy="38" r="12" fill="#e67e22"/>
          <!-- Arrow Down -->
          <path d="M 100 40 L 100 90" stroke="#2980b9" stroke-width="4" stroke-dasharray="4"/>
          <polygon points="100,98 95,86 105,86" fill="#2980b9"/>
        </svg>`
      },
      {
        id: 11,
        lesson: "2.07",
        lessonTitle: "Unit 2 | Lesson 2.07",
        word: "Mass",
        theme: "green",
        definition: "The amount of matter in an object.",
        example: "This object has a mass of 5 kilograms.",
        hint: "Measured in kilograms (kg) or grams",
        svg: `<svg viewBox="0 0 200 120" class="w-full h-full">
          <!-- Weight Stand -->
          <rect x="60" y="90" width="80" height="10" fill="#34495e"/>
          <!-- Weight Block -->
          <path d="M 80 45 L 120 45 L 130 85 L 70 85 Z" fill="#7f8c8d" stroke="#2c3e50" stroke-width="2"/>
          <circle cx="100" cy="35" r="10" fill="none" stroke="#2c3e50" stroke-width="4"/>
          <text x="100" y="70" text-anchor="middle" font-size="16" font-weight="bold" fill="#ffffff">5 kg</text>
        </svg>`
      },
      {
        id: 12,
        lesson: "2.07",
        lessonTitle: "Unit 2 | Lesson 2.07",
        word: "Height",
        theme: "blue",
        definition: "The vertical distance from a reference point.",
        example: "The ball is 10 meters above the ground (reference point).",
        hint: "Vertical elevation above reference baseline",
        svg: `<svg viewBox="0 0 200 120" class="w-full h-full">
          <!-- Vertical Height Arrow -->
          <line x1="100" y1="20" x2="100" y2="100" stroke="#e74c3c" stroke-width="4"/>
          <polygon points="100,12 94,24 106,24" fill="#e74c3c"/>
          <polygon points="100,108 94,96 106,96" fill="#e74c3c"/>
          <!-- Label -->
          <rect x="110" y="50" width="55" height="22" rx="4" fill="#ffffff" stroke="#e74c3c"/>
          <text x="137" y="65" text-anchor="middle" font-size="12" font-weight="bold" fill="#c0392b">Height</text>
        </svg>`
      },
      {
        id: 13,
        lesson: "2.07",
        lessonTitle: "Unit 2 | Lesson 2.07",
        word: "Joule (J)",
        theme: "yellow",
        definition: "The unit used to measure energy.",
        example: "Energy is measured in joules (J).",
        hint: "Standard SI unit for work and energy",
        svg: `<svg viewBox="0 0 200 120" class="w-full h-full">
          <!-- Blue Badge Tile -->
          <rect x="55" y="20" width="90" height="80" rx="16" fill="#2980b9"/>
          <text x="100" y="68" text-anchor="middle" font-size="44" font-weight="extrabold" fill="#ffffff" font-family="sans-serif">J</text>
          <text x="100" y="88" text-anchor="middle" font-size="11" font-weight="bold" fill="#ecf0f1" tracking="2">JOULE</text>
        </svg>`
      },
      {
        id: 14,
        lesson: "2.07",
        lessonTitle: "Unit 2 | Lesson 2.07",
        word: "Reference Point",
        theme: "cyan",
        definition: "A chosen starting position from which height is measured.",
        example: "In most cases, the ground is used as the reference point (0 meters).",
        hint: "Baseline starting height position (0 m)",
        svg: `<svg viewBox="0 0 200 120" class="w-full h-full">
          <!-- Cliff diagram -->
          <rect x="30" y="30" width="50" height="60" fill="#95a5a6"/>
          <circle cx="55" cy="20" r="8" fill="#e67e22"/>
          <!-- Ground Baseline Dashed -->
          <line x1="20" y1="90" x2="180" y2="90" stroke="#2c3e50" stroke-width="4" stroke-dasharray="6"/>
          <text x="110" y="82" text-anchor="start" font-size="11" font-weight="bold" fill="#2c3e50">Reference Point (0m)</text>
        </svg>`
      },

      // LESSON 2.08
      {
        id: 15,
        lesson: "2.08",
        lessonTitle: "Unit 2 | Lesson 2.08",
        word: "Elastic Potential Energy",
        theme: "blue",
        definition: "The energy stored in an object when it is stretched or compressed.",
        example: "A stretched archer's bow or a compressed metal spring stores elastic energy.",
        hint: "Energy stored in stretched rubber bands or squeezed springs",
        svg: `<svg viewBox="0 0 200 120" class="w-full h-full">
          <!-- Bow -->
          <path d="M 40 20 Q 20 60 40 100" stroke="#795548" stroke-width="6" fill="none"/>
          <line x1="40" y1="20" x2="40" y2="100" stroke="#bdc3c7" stroke-width="2"/>
          <!-- Spring compressed -->
          <path d="M 120 30 Q 140 35 120 40 Q 140 45 120 50 Q 140 55 120 60 Q 140 65 120 70 Q 140 75 120 80" stroke="#34495e" stroke-width="4" fill="none"/>
          <path d="M 130 18 L 130 26" stroke="#e74c3c" stroke-width="3"/>
          <polygon points="130,28 126,22 134,22" fill="#e74c3c"/>
          <path d="M 130 92 L 130 84" stroke="#e74c3c" stroke-width="3"/>
          <polygon points="130,82 126,88 134,88" fill="#e74c3c"/>
        </svg>`
      },
      {
        id: 16,
        lesson: "2.08",
        lessonTitle: "Unit 2 | Lesson 2.08",
        word: "Deformation",
        theme: "green",
        definition: "The change in shape of an object when a force is applied.",
        example: "Squeezing or squishing a pink eraser alters its original shape.",
        hint: "Physical change in shape caused by force",
        svg: `<svg viewBox="0 0 200 120" class="w-full h-full">
          <!-- Normal Eraser -->
          <rect x="50" y="25" width="100" height="25" rx="5" fill="#ff7675"/>
          <text x="100" y="42" text-anchor="middle" font-size="10" font-weight="bold" fill="#ffffff">Before (Original)</text>
          <!-- Deformed Eraser -->
          <path d="M 50 75 Q 100 95 150 75 L 145 95 Q 100 105 55 95 Z" fill="#d63031"/>
          <text x="100" y="90" text-anchor="middle" font-size="10" font-weight="bold" fill="#ffffff">After (Deformed)</text>
        </svg>`
      },
      {
        id: 17,
        lesson: "2.08",
        lessonTitle: "Unit 2 | Lesson 2.08",
        word: "Spring Constant",
        theme: "blue",
        definition: "A measure of how stiff a spring is.",
        example: "A stiff spring with a large spring constant is harder to stretch.",
        hint: "Stiffness rating ($k$) of a spring",
        svg: `<svg viewBox="0 0 200 120" class="w-full h-full">
          <!-- Loose Spring -->
          <path d="M 50 20 Q 70 30 50 40 Q 70 50 50 60 Q 70 70 50 80 Q 70 90 50 100" stroke="#3498db" stroke-width="3" fill="none"/>
          <text x="60" y="112" text-anchor="middle" font-size="9" font-weight="bold" fill="#2980b9">Small k (Easier)</text>
          <!-- Stiff Spring -->
          <path d="M 140 20 Q 160 25 140 30 Q 160 35 140 40 Q 160 45 140 50 Q 160 55 140 60 Q 160 65 140 70 Q 160 75 140 80 Q 160 85 140 90 Q 160 95 140 100" stroke="#2c3e50" stroke-width="6" fill="none"/>
          <text x="150" y="112" text-anchor="middle" font-size="9" font-weight="bold" fill="#2c3e50">Large k (Harder)</text>
        </svg>`
      },
      {
        id: 18,
        lesson: "2.08",
        lessonTitle: "Unit 2 | Lesson 2.08",
        word: "Hooke's Law",
        theme: "yellow",
        definition: "A law stating that the force needed to stretch a spring is proportional to the distance it is stretched.",
        example: "Formula: F = kx, where F is force (N), k is spring constant (N/m), and x is distance (m).",
        hint: "Formula: F = kx",
        svg: `<svg viewBox="0 0 200 120" class="w-full h-full">
          <rect x="30" y="30" width="140" height="60" rx="12" fill="#fff9c4" stroke="#f1c40f" stroke-width="3"/>
          <text x="100" y="68" text-anchor="middle" font-size="28" font-weight="extrabold" fill="#2c3e50">F = kx</text>
          <text x="100" y="82" text-anchor="middle" font-size="9" font-weight="bold" fill="#7f8c8d">F = force | k = spring constant | x = stretch</text>
        </svg>`
      },

      // LESSON 2.09
      {
        id: 19,
        lesson: "2.09",
        lessonTitle: "Unit 2 | Lesson 2.09",
        word: "Chemical Potential Energy",
        theme: "blue",
        definition: "Energy stored in chemical bonds between atoms and molecules.",
        example: "A battery stores chemical potential energy.",
        hint: "Stored energy inside atomic chemical bonds",
        svg: `<svg viewBox="0 0 200 120" class="w-full h-full">
          <!-- Molecule bonds -->
          <circle cx="60" cy="60" r="16" fill="#e74c3c"/>
          <circle cx="140" cy="60" r="16" fill="#3498db"/>
          <line x1="76" y1="60" x2="124" y2="60" stroke="#f1c40f" stroke-width="8"/>
          <text x="100" y="52" text-anchor="middle" font-size="10" font-weight="bold" fill="#d35400">BOND</text>
        </svg>`
      },
      {
        id: 20,
        lesson: "2.09",
        lessonTitle: "Unit 2 | Lesson 2.09",
        word: "Chemical Reaction",
        theme: "green",
        definition: "Process where substances change into different substances.",
        example: "In a chemical reaction, the atoms rearrange into new substances.",
        hint: "Atoms rearranging to form brand new chemical compounds",
        svg: `<svg viewBox="0 0 200 120" class="w-full h-full">
          <!-- Flask 1 -->
          <path d="M 40 40 L 55 75 A 10 10 0 0 1 45 90 L 25 90 A 10 10 0 0 1 15 75 Z" fill="#3498db"/>
          <!-- Arrow -->
          <path d="M 70 65 L 110 65" stroke="#2ecc71" stroke-width="5"/>
          <polygon points="110,58 122,65 110,72" fill="#2ecc71"/>
          <!-- Flask 2 bubbling -->
          <path d="M 155 40 L 170 75 A 10 10 0 0 1 160 90 L 140 90 A 10 10 0 0 1 130 75 Z" fill="#e67e22"/>
          <circle cx="150" cy="50" r="3" fill="#e67e22"/>
          <circle cx="155" cy="38" r="4" fill="#e67e22"/>
        </svg>`
      },
      {
        id: 21,
        lesson: "2.09",
        lessonTitle: "Unit 2 | Lesson 2.09",
        word: "Reactants",
        theme: "blue",
        definition: "Starting materials in a chemical reaction.",
        example: "Wood and oxygen are reactants in a combustion reaction.",
        hint: "The starting chemical ingredients before a reaction",
        svg: `<svg viewBox="0 0 200 120" class="w-full h-full">
          <!-- Wood Logs -->
          <rect x="30" y="60" width="50" height="15" rx="4" fill="#795548"/>
          <rect x="30" y="80" width="50" height="15" rx="4" fill="#5d4037"/>
          <text x="55" y="110" text-anchor="middle" font-size="10" font-weight="bold" fill="#5d4037">Wood</text>
          <!-- Plus -->
          <text x="100" y="75" text-anchor="middle" font-size="22" font-weight="bold" fill="#2c3e50">+</text>
          <!-- Oxygen Molecules -->
          <circle cx="135" cy="70" r="10" fill="#e74c3c"/>
          <circle cx="152" cy="70" r="10" fill="#e74c3c"/>
          <text x="144" y="110" text-anchor="middle" font-size="10" font-weight="bold" fill="#c0392b">Oxygen (O₂)</text>
        </svg>`
      },
      {
        id: 22,
        lesson: "2.09",
        lessonTitle: "Unit 2 | Lesson 2.09",
        word: "Products",
        theme: "yellow",
        definition: "Materials formed in a chemical reaction.",
        example: "Carbon dioxide and water are products of the combustion reaction.",
        hint: "The final resulting substances created by a reaction",
        svg: `<svg viewBox="0 0 200 120" class="w-full h-full">
          <!-- CO2 -->
          <circle cx="50" cy="50" r="12" fill="#2c3e50"/>
          <circle cx="30" cy="50" r="8" fill="#e74c3c"/>
          <circle cx="70" cy="50" r="8" fill="#e74c3c"/>
          <text x="50" y="80" text-anchor="middle" font-size="10" font-weight="bold" fill="#2c3e50">CO₂</text>
          
          <!-- H2O -->
          <circle cx="140" cy="50" r="12" fill="#e74c3c"/>
          <circle cx="126" cy="62" r="7" fill="#ecf0f1" stroke="#bdc3c7"/>
          <circle cx="154" cy="62" r="7" fill="#ecf0f1" stroke="#bdc3c7"/>
          <text x="140" y="80" text-anchor="middle" font-size="10" font-weight="bold" fill="#2c3e50">H₂O</text>
        </svg>`
      },
      {
        id: 23,
        lesson: "2.09",
        lessonTitle: "Unit 2 | Lesson 2.09",
        word: "Exothermic",
        theme: "cyan",
        definition: "Reaction that releases energy (usually in the form of heat or light).",
        example: "Burning wood is an exothermic reaction because it releases heat and light.",
        hint: "Releases heat outward (Ex = Exit)",
        svg: `<svg viewBox="0 0 200 120" class="w-full h-full">
          <!-- Fire Center -->
          <circle cx="100" cy="70" r="20" fill="#ff5722"/>
          <!-- Outward Heat Arrows -->
          <path d="M 100 40 L 100 15" stroke="#e74c3c" stroke-width="4"/>
          <polygon points="100,8 94,18 106,18" fill="#e74c3c"/>
          
          <path d="M 130 70 L 155 70" stroke="#e74c3c" stroke-width="4"/>
          <polygon points="162,70 152,64 152,76" fill="#e74c3c"/>

          <path d="M 70 70 L 45 70" stroke="#e74c3c" stroke-width="4"/>
          <polygon points="38,70 48,64 48,76" fill="#e74c3c"/>
        </svg>`
      },
      {
        id: 24,
        lesson: "2.09",
        lessonTitle: "Unit 2 | Lesson 2.09",
        word: "Endothermic",
        theme: "green",
        definition: "Reaction that absorbs energy (usually in the form of heat).",
        example: "An instant cold pack is endothermic because it absorbs heat from its surroundings.",
        hint: "Absorbs heat inward (En = Enter)",
        svg: `<svg viewBox="0 0 200 120" class="w-full h-full">
          <!-- Cold Pack Center -->
          <rect x="65" y="35" width="70" height="50" rx="6" fill="#00bcd4"/>
          <text x="100" y="65" text-anchor="middle" font-size="10" font-weight="bold" fill="#ffffff">COLD PACK</text>
          <!-- Inward Arrows -->
          <path d="M 30 60 L 55 60" stroke="#00838f" stroke-width="4"/>
          <polygon points="58,60 48,54 48,66" fill="#00838f"/>

          <path d="M 170 60 L 145 60" stroke="#00838f" stroke-width="4"/>
          <polygon points="142,60 152,54 152,66" fill="#00838f"/>
        </svg>`
      },

      // LESSON 2.10
      {
        id: 25,
        lesson: "2.10",
        lessonTitle: "Unit 2 | Lesson 2.10",
        word: "Molecules",
        theme: "blue",
        definition: "Tiny particles that make up matter.",
        example: "Water is made of H₂O molecules.",
        hint: "Microscopic groups of bonded atoms",
        svg: `<svg viewBox="0 0 200 120" class="w-full h-full">
          <!-- Molecule Cluster -->
          <circle cx="70" cy="50" r="14" fill="#e74c3c"/>
          <circle cx="55" cy="62" r="8" fill="#ecf0f1" stroke="#bdc3c7"/>
          <circle cx="85" cy="62" r="8" fill="#ecf0f1" stroke="#bdc3c7"/>

          <circle cx="140" cy="70" r="14" fill="#e74c3c"/>
          <circle cx="125" cy="82" r="8" fill="#ecf0f1" stroke="#bdc3c7"/>
          <circle cx="155" cy="82" r="8" fill="#ecf0f1" stroke="#bdc3c7"/>
        </svg>`
      },
      {
        id: 26,
        lesson: "2.10",
        lessonTitle: "Unit 2 | Lesson 2.10",
        word: "Temperature",
        theme: "yellow",
        definition: "Measure of average molecular motion.",
        example: "Higher temperature means faster molecular motion.",
        hint: "Average kinetic speed of molecules",
        svg: `<svg viewBox="0 0 200 120" class="w-full h-full">
          <!-- Cold Thermometer -->
          <rect x="50" y="20" width="12" height="70" rx="6" fill="#ecf0f1" stroke="#3498db" stroke-width="2"/>
          <circle cx="56" cy="85" r="12" fill="#3498db"/>
          <rect x="53" y="60" width="6" height="25" fill="#3498db"/>

          <!-- Hot Thermometer -->
          <rect x="140" y="20" width="12" height="70" rx="6" fill="#ecf0f1" stroke="#e74c3c" stroke-width="2"/>
          <circle cx="146" cy="85" r="12" fill="#e74c3c"/>
          <rect x="143" y="30" width="6" height="55" fill="#e74c3c"/>
        </svg>`
      },
      {
        id: 27,
        lesson: "2.10",
        lessonTitle: "Unit 2 | Lesson 2.10",
        word: "Equilibrium",
        theme: "cyan",
        definition: "When temperatures balance between objects.",
        example: "Eventually, both objects reach the same equal temperature.",
        hint: "Balanced temperature state between two contacting objects",
        svg: `<svg viewBox="0 0 200 120" class="w-full h-full">
          <!-- Red Mug -->
          <rect x="35" y="45" width="35" height="40" rx="4" fill="#e74c3c"/>
          <!-- Blue Mug -->
          <rect x="130" y="45" width="35" height="40" rx="4" fill="#3498db"/>
          <!-- Equalizing Curved Arrows -->
          <path d="M 75 50 Q 100 35 125 50" stroke="#f39c12" stroke-width="4" fill="none"/>
          <path d="M 125 80 Q 100 95 75 80" stroke="#f39c12" stroke-width="4" fill="none"/>
        </svg>`
      },

      // LESSON 2.11
      {
        id: 28,
        lesson: "2.11",
        lessonTitle: "Unit 2 | Lesson 2.11",
        word: "Conduction",
        theme: "blue",
        definition: "The transfer of thermal energy between objects through direct contact.",
        example: "Thermal energy moves from hot coffee to a metal spoon by direct contact.",
        hint: "Direct physical contact heat transfer",
        svg: `<svg viewBox="0 0 200 120" class="w-full h-full">
          <!-- Mug -->
          <rect x="50" y="40" width="60" height="60" rx="6" fill="#009688"/>
          <!-- Metal Spoon -->
          <path d="M 80 20 L 75 80" stroke="#95a5a6" stroke-width="6" stroke-linecap="round"/>
          <!-- Heat Transfer squiggles -->
          <path d="M 70 50 Q 75 45 70 40" stroke="#e74c3c" stroke-width="3" fill="none"/>
          <path d="M 80 50 Q 85 45 80 40" stroke="#e74c3c" stroke-width="3" fill="none"/>
        </svg>`
      },
      {
        id: 29,
        lesson: "2.11",
        lessonTitle: "Unit 2 | Lesson 2.11",
        word: "Conductor",
        theme: "blue",
        definition: "A material that easily transfers thermal energy.",
        example: "Metals like aluminum and copper are good conductors.",
        hint: "Materials (like metals) that pass heat quickly",
        svg: `<svg viewBox="0 0 200 120" class="w-full h-full">
          <!-- Metal Cooking Pot -->
          <rect x="45" y="45" width="90" height="45" rx="4" fill="#7f8c8d"/>
          <rect x="135" y="55" width="35" height="8" rx="2" fill="#2c3e50"/>
          <!-- Heat Arrows -->
          <path d="M 135 50 L 160 30" stroke="#e74c3c" stroke-width="4"/>
          <polygon points="165,26 154,30 160,38" fill="#e74c3c"/>
        </svg>`
      },
      {
        id: 30,
        lesson: "2.11",
        lessonTitle: "Unit 2 | Lesson 2.11",
        word: "Insulator",
        theme: "yellow",
        definition: "A material that poorly transfers thermal energy.",
        example: "Materials like rubber, wood, and fabric oven mitts are good insulators.",
        hint: "Materials (like rubber or wool) that block heat flow",
        svg: `<svg viewBox="0 0 200 120" class="w-full h-full">
          <!-- Oven Mitt -->
          <path d="M 70 25 C 100 25, 120 40, 120 70 L 120 95 L 60 95 L 60 60 C 60 40, 50 35, 70 25 Z" fill="#00acc1"/>
          <!-- Thumb -->
          <path d="M 60 60 C 40 60, 40 80, 60 85 Z" fill="#00acc1"/>
        </svg>`
      },

      // LESSON 2.12
      {
        id: 31,
        lesson: "2.12",
        lessonTitle: "Unit 2 | Lesson 2.12",
        word: "Convection Cell",
        theme: "blue",
        definition: "A complete loop of rising warm fluid and sinking cool fluid.",
        example: "Warm fluid rises, cool fluid sinks, creating a continuous convection cycle.",
        hint: "Warm rises, cool sinks loop in fluids/gases",
        svg: `<svg viewBox="0 0 200 120" class="w-full h-full">
          <!-- Boiling Pot -->
          <rect x="40" y="30" width="120" height="70" rx="6" fill="#34495e" opacity="0.3"/>
          <!-- Warm Up Arrow (Red) -->
          <path d="M 75 80 L 75 45" stroke="#e74c3c" stroke-width="5"/>
          <polygon points="75,37 68,48 82,48" fill="#e74c3c"/>
          <!-- Cool Down Arrow (Blue) -->
          <path d="M 125 45 L 125 80" stroke="#3498db" stroke-width="5"/>
          <polygon points="125,88 118,77 132,77" fill="#3498db"/>
        </svg>`
      },
      {
        id: 32,
        lesson: "2.12",
        lessonTitle: "Unit 2 | Lesson 2.12",
        word: "Particles",
        theme: "blue",
        definition: "Tiny pieces of matter that make up everything.",
        example: "All matter is made of particles that are always in continuous motion.",
        hint: "Tiny moving building blocks of matter",
        svg: `<svg viewBox="0 0 200 120" class="w-full h-full">
          <circle cx="40" cy="30" r="8" fill="#3498db"/>
          <circle cx="100" cy="40" r="8" fill="#3498db"/>
          <circle cx="160" cy="30" r="8" fill="#3498db"/>
          <circle cx="70" cy="80" r="8" fill="#3498db"/>
          <circle cx="130" cy="85" r="8" fill="#3498db"/>
        </svg>`
      },
      {
        id: 33,
        lesson: "2.12",
        lessonTitle: "Unit 2 | Lesson 2.12",
        word: "Circulation",
        theme: "yellow",
        definition: "Continuous movement in a circular pattern.",
        example: "In convection, fluid circulates continuously as warm rises and cool sinks.",
        hint: "Continuous circular motion pattern",
        svg: `<svg viewBox="0 0 200 120" class="w-full h-full">
          <path d="M 100 20 A 35 35 0 1 1 99 20" fill="none" stroke="#e74c3c" stroke-width="8" stroke-dasharray="25 10"/>
          <polygon points="110,22 100,10 100,30" fill="#e74c3c"/>
        </svg>`
      },
      {
        id: 34,
        lesson: "2.12",
        lessonTitle: "Unit 2 | Lesson 2.12",
        word: "Temperature Gradient",
        theme: "cyan",
        definition: "The difference in temperature between two areas.",
        example: "Larger temperature differences cause faster convection rates.",
        hint: "Temperature difference scale between warm and cold zones",
        svg: `<svg viewBox="0 0 200 120" class="w-full h-full">
          <!-- Gradient Bar -->
          <defs>
            <linearGradient id="tempGrad" x1="0" y1="0" x2="0" y2="1">
              <stop offset="0%" stop-color="#e74c3c" />
              <stop offset="100%" stop-color="#3498db" />
            </linearGradient>
          </defs>
          <rect x="85" y="20" width="30" height="80" rx="6" fill="url(#tempGrad)"/>
          <text x="125" y="35" font-size="11" font-weight="bold" fill="#e74c3c">Warmer</text>
          <text x="125" y="90" font-size="11" font-weight="bold" fill="#3498db">Cooler</text>
        </svg>`
      },

      // LESSON 2.13
      {
        id: 35,
        lesson: "2.13",
        lessonTitle: "Unit 2 | Lesson 2.13",
        word: "Radiation",
        theme: "blue",
        definition: "Transfer of energy through electromagnetic waves.",
        example: "The Sun transfers energy through space to Earth via radiation.",
        hint: "Heat transfer through empty space by waves",
        svg: `<svg viewBox="0 0 200 120" class="w-full h-full">
          <!-- Sun -->
          <circle cx="35" cy="60" r="22" fill="#f1c40f"/>
          <!-- Wavy Rays -->
          <path d="M 65 40 Q 80 30 95 40 T 125 40" stroke="#e67e22" stroke-width="3" fill="none"/>
          <path d="M 65 60 Q 80 50 95 60 T 125 60" stroke="#e67e22" stroke-width="3" fill="none"/>
          <path d="M 65 80 Q 80 70 95 80 T 125 80" stroke="#e67e22" stroke-width="3" fill="none"/>
          <!-- Earth -->
          <circle cx="160" cy="60" r="18" fill="#2980b9"/>
        </svg>`
      },
      {
        id: 36,
        lesson: "2.13",
        lessonTitle: "Unit 2 | Lesson 2.13",
        word: "Electromagnetic Waves",
        theme: "blue",
        definition: "Energy that travels through space without needing a medium.",
        example: "Electromagnetic waves can travel through empty space (like vacuum of space).",
        hint: "Light and heat waves that don't require matter to travel",
        svg: `<svg viewBox="0 0 200 120" class="w-full h-full">
          <!-- Sine Wave -->
          <path d="M 20 60 Q 45 20 70 60 T 120 60 T 170 60" stroke="#9b59b6" stroke-width="5" fill="none"/>
          <!-- Wavelength arrow -->
          <line x1="45" y1="20" x2="95" y2="20" stroke="#2c3e50" stroke-width="2"/>
          <text x="70" y="15" text-anchor="middle" font-size="9" font-weight="bold" fill="#2c3e50">Wavelength</text>
        </svg>`
      },
      {
        id: 37,
        lesson: "2.13",
        lessonTitle: "Unit 2 | Lesson 2.13",
        word: "Infrared Radiation",
        theme: "yellow",
        definition: "Heat waves we can't see but can feel.",
        example: "A TV remote control gives off infrared radiation rays.",
        hint: "Invisible thermal heat waves",
        svg: `<svg viewBox="0 0 200 120" class="w-full h-full">
          <!-- Remote -->
          <rect x="120" y="40" width="30" height="60" rx="4" fill="#2c3e50"/>
          <circle cx="135" cy="48" r="3" fill="#e74c3c"/>
          <!-- Heat Waves -->
          <path d="M 100 50 Q 110 40 100 30" stroke="#e74c3c" stroke-width="3" fill="none"/>
          <path d="M 85 55 Q 95 40 85 25" stroke="#e74c3c" stroke-width="3" fill="none"/>
          <!-- Hand -->
          <path d="M 40 60 C 30 50 40 30 50 40" stroke="#f39c12" stroke-width="6"/>
        </svg>`
      },
      {
        id: 38,
        lesson: "2.13",
        lessonTitle: "Unit 2 | Lesson 2.13",
        word: "Absorption",
        theme: "cyan",
        definition: "The process of taking in radiant energy.",
        example: "A black shirt absorbs more radiant energy than a white shirt.",
        hint: "Taking in or soaking up heat energy",
        svg: `<svg viewBox="0 0 200 120" class="w-full h-full">
          <!-- Black Shirt -->
          <path d="M 70 35 L 90 35 L 100 45 L 110 35 L 130 35 L 140 55 L 125 60 L 125 95 L 75 95 L 75 60 L 60 55 Z" fill="#2c3e50"/>
          <!-- Inward Rays -->
          <path d="M 25 50 L 55 50" stroke="#e74c3c" stroke-width="4"/>
          <polygon points="58,50 48,44 48,56" fill="#e74c3c"/>
        </svg>`
      },
      {
        id: 39,
        lesson: "2.13",
        lessonTitle: "Unit 2 | Lesson 2.13",
        word: "Emission",
        theme: "green",
        definition: "The process of giving off radiant energy.",
        example: "A campfire emits radiant energy as heat and light.",
        hint: "Giving off or releasing heat waves outward",
        svg: `<svg viewBox="0 0 200 120" class="w-full h-full">
          <!-- Bonfire -->
          <polygon points="100,40 115,80 85,80" fill="#e67e22"/>
          <!-- Outward Radiation Rays -->
          <line x1="100" y1="35" x2="100" y2="15" stroke="#e74c3c" stroke-width="3"/>
          <line x1="120" y1="45" x2="140" y2="30" stroke="#e74c3c" stroke-width="3"/>
          <line x1="80" y1="45" x2="60" y2="30" stroke="#e74c3c" stroke-width="3"/>
        </svg>`
      }
    ];

    // APPLICATION STATE
    let activeCards = [...cardData];
    let currentIndex = 0;
    let isFlipped = false;
    let masteredIds = new Set();
    let currentMode = 'flashcard';

    // INITIALIZATION
    window.onload = () => {
      renderCurrentCard();
      updateStats();
      setupKeyboardNav();
    };

    // FILTER CARDS BY LESSON
    function filterCards() {
      const selected = document.getElementById('lesson-select').value;
      if (selected === 'ALL') {
        activeCards = [...cardData];
      } else {
        activeCards = cardData.filter(c => c.lesson === selected);
      }
      currentIndex = 0;
      isFlipped = false;
      renderCurrentCard();
      if (currentMode === 'grid') renderGridView();
      if (currentMode === 'quiz') renderQuizView();
    }

    // SHUFFLE CARDS
    function shuffleCards() {
      for (let i = activeCards.length - 1; i > 0; i--) {
        const j = Math.floor(Math.random() * (i + 1));
        [activeCards[i], activeCards[j]] = [activeCards[j], activeCards[i]];
      }
      currentIndex = 0;
      isFlipped = false;
      renderCurrentCard();
    }

    // RENDER SINGLE CARD VIEW
    function renderCurrentCard() {
      if (activeCards.length === 0) return;
      const card = activeCards[currentIndex];

      // Reset flip state
      const cardInner = document.getElementById('card-inner');
      cardInner.classList.remove('rotate-y-180');
      isFlipped = false;

      // Theme classes
      const frontElem = document.getElementById('card-front');
      const backElem = document.getElementById('card-back');
      frontElem.className = `absolute inset-0 w-full h-full backface-hidden rounded-3xl p-6 flex flex-col justify-between items-center text-center border-4 card-theme-${card.theme} shadow-inner`;
      backElem.className = `absolute inset-0 w-full h-full backface-hidden rotate-y-180 rounded-3xl p-6 flex flex-col justify-between items-center text-left border-4 card-theme-${card.theme} bg-white shadow-inner`;

      // Front content
      document.getElementById('front-lesson-badge').innerText = card.lessonTitle;
      document.getElementById('front-word').innerText = card.word;
      document.getElementById('front-graphic').innerHTML = card.svg;
      document.getElementById('front-hint').innerText = card.hint;

      // Back content
      document.getElementById('back-word-title').innerText = card.word;
      document.getElementById('back-definition').innerText = card.definition;
      document.getElementById('back-example').innerText = card.example;

      // Progress & Counters
      document.getElementById('card-indicator').innerText = `Card ${currentIndex + 1} of ${activeCards.length}`;
      document.getElementById('lesson-badge-top').innerText = `Lesson ${card.lesson}`;
      const pct = ((currentIndex + 1) / activeCards.length) * 100;
      document.getElementById('progress-bar').style.width = `${pct}%`;

      // Mastered button status
      updateMasteredBtnUI(card.id);
    }

    // FLIP CARD FUNCTION
    function flipCurrentCard() {
      const cardInner = document.getElementById('card-inner');
      isFlipped = !isFlipped;
      if (isFlipped) {
        cardInner.classList.add('rotate-y-180');
      } else {
        cardInner.classList.remove('rotate-y-180');
      }
    }

    // NAVIGATION
    function nextCard() {
      if (currentIndex < activeCards.length - 1) {
        currentIndex++;
        renderCurrentCard();
      } else {
        currentIndex = 0; // Loop back
        renderCurrentCard();
      }
    }

    function prevCard() {
      if (currentIndex > 0) {
        currentIndex--;
        renderCurrentCard();
      } else {
        currentIndex = activeCards.length - 1;
        renderCurrentCard();
      }
    }

    // MASTERED TRACKING
    function toggleMastered(e) {
      if (e) e.stopPropagation();
      const currentId = activeCards[currentIndex].id;
      if (masteredIds.has(currentId)) {
        masteredIds.delete(currentId);
      } else {
        masteredIds.add(currentId);
      }
      updateMasteredBtnUI(currentId);
      updateStats();
    }

    function updateMasteredBtnUI(id) {
      const btn = document.getElementById('btn-mastered');
      if (masteredIds.has(id)) {
        btn.className = "text-xs font-bold px-3 py-1.5 rounded-xl transition flex items-center gap-1.5 bg-emerald-600 text-white border-emerald-700 shadow";
        btn.innerHTML = "✓ Mastered";
      } else {
        btn.className = "text-xs font-bold px-3 py-1.5 rounded-xl border transition flex items-center gap-1.5 bg-slate-100 text-slate-600 border-slate-300 hover:bg-emerald-50 hover:text-emerald-700";
        btn.innerHTML = "Mark as Mastered";
      }
    }

    function updateStats() {
      document.getElementById('mastered-count').innerText = masteredIds.size;
    }

    function resetProgress() {
      masteredIds.clear();
      updateStats();
      renderCurrentCard();
    }

    // VIEW MODES SWITCHING
    function setMode(mode) {
      currentMode = mode;
      document.getElementById('view-flashcard').classList.add('hidden');
      document.getElementById('view-grid').classList.add('hidden');
      document.getElementById('view-quiz').classList.add('hidden');

      // Toggles button styles
      ['flashcard', 'grid', 'quiz'].forEach(m => {
        const btn = document.getElementById(`btn-mode-${m}`);
        if (m === mode) {
          btn.className = "px-3 py-1.5 rounded-lg text-xs font-bold transition-all bg-white text-teal-900 shadow";
        } else {
          btn.className = "px-3 py-1.5 rounded-lg text-xs font-bold text-teal-100 hover:text-white transition-all";
        }
      });

      if (mode === 'flashcard') {
        document.getElementById('view-flashcard').classList.remove('hidden');
        renderCurrentCard();
      } else if (mode === 'grid') {
        document.getElementById('view-grid').classList.remove('hidden');
        renderGridView();
      } else if (mode === 'quiz') {
        document.getElementById('view-quiz').classList.remove('hidden');
        renderQuizView();
      }
    }

    // RENDER GRID VIEW
    function renderGridView() {
      const container = document.getElementById('grid-cards-container');
      container.innerHTML = activeCards.map((card) => `
        <div class="bg-white rounded-2xl border-2 border-slate-200 p-4 shadow-sm hover:shadow-md transition flex flex-col justify-between">
          <div>
            <div class="flex justify-between items-center mb-2">
              <span class="text-[10px] font-bold uppercase tracking-wider text-teal-700 bg-teal-50 px-2 py-0.5 rounded-md">Lesson ${card.lesson}</span>
              ${masteredIds.has(card.id) ? '<span class="text-xs text-emerald-600 font-bold">✓ Mastered</span>' : ''}
            </div>
            <h3 class="text-xl font-extrabold text-slate-800 font-heading mb-2">${card.word}</h3>
            <div class="w-full h-32 bg-slate-50 rounded-xl p-2 border border-slate-100 flex items-center justify-center my-2">
              ${card.svg}
            </div>
            <p class="text-xs text-slate-600 font-semibold mt-2">${card.definition}</p>
          </div>
          <div class="mt-3 pt-2 border-t border-slate-100 text-[11px] text-amber-800 bg-amber-50 p-2 rounded-lg font-medium">
            <strong>Ex:</strong> ${card.example}
          </div>
        </div>
      `).join('');
    }

    // RENDER QUIZ VIEW
    function renderQuizView() {
      const card = activeCards[currentIndex];
      document.getElementById('quiz-progress').innerText = `Question ${currentIndex + 1} of ${activeCards.length}`;
      document.getElementById('quiz-word').innerText = card.word;
      document.getElementById('quiz-graphic').innerHTML = card.svg;
      document.getElementById('quiz-def').innerText = card.definition;
      document.getElementById('quiz-ex').innerText = card.example;

      document.getElementById('quiz-answer-box').classList.add('hidden');
      document.getElementById('quiz-grading-btns').classList.add('hidden');
      document.getElementById('btn-quiz-reveal').classList.remove('hidden');
    }

    function revealQuizAnswer() {
      document.getElementById('quiz-answer-box').classList.remove('hidden');
      document.getElementById('quiz-grading-btns').classList.remove('hidden');
      document.getElementById('btn-quiz-reveal').classList.add('hidden');
    }

    function gradeQuiz(isCorrect) {
      if (isCorrect) {
        masteredIds.add(activeCards[currentIndex].id);
      }
      updateStats();
      nextCard();
      renderQuizView();
    }

    // KEYBOARD NAVIGATION CONTROLS
    function setupKeyboardNav() {
      document.addEventListener('keydown', (e) => {
        if (currentMode !== 'flashcard') return;
        if (e.code === 'Space') {
          e.preventDefault();
          flipCurrentCard();
        } else if (e.code === 'ArrowRight') {
          nextCard();
        } else if (e.code === 'ArrowLeft') {
          prevCard();
        }
      });
    }
  </script>
</body>
</html>
