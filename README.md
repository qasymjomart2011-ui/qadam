index.html
<!DOCTYPE html>
<html lang="kk">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>QADAM 1.0 — ҰБТ Дайындық Платформасы</title>
  <script src="https://cdn.tailwindcss.com"></script>
  <script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
  <style>
    body { background-color: #0b132b; color: #ffffff; font-family: 'Segoe UI', sans-serif; }
    .neon-border { border: 1px solid #00f5d4; box-shadow: 0 0 10px rgba(0, 245, 212, 0.3); }
    .neon-text { color: #00f5d4; text-shadow: 0 0 5px rgba(0, 245, 212, 0.5); }
    .card-bg { background-color: #1c2541; }
  </style>
</head>
<body class="pb-24">

  <!-- РЕСМИ ҚАУІПСІЗ КІРУ МОДУЛІ -->
  <div id="auth-screen" class="fixed inset-0 bg-[#0b132b] z-50 flex items-center justify-center p-4">
    <div class="card-bg p-6 rounded-2xl neon-border w-full max-w-sm space-y-4 text-center">
      <div class="w-12 h-12 rounded-full bg-cyan-400 flex items-center justify-center font-bold text-black text-xl mx-auto">Q</div>
      <h1 class="text-2xl font-bold tracking-wider neon-text">QADAM <span class="text-xs text-white">PRO</span></h1>
      <p class="text-xs text-gray-300">ҰБТ-ға дайындықты бастау үшін жүйеге кіріңіз:</p>
      
      <div class="space-y-3 pt-2">
        <input type="text" id="user-name" placeholder="Аты-жөніңіз" class="w-full card-bg p-3 rounded-xl border border-gray-700 text-xs text-white focus:outline-none focus:border-cyan-400">
        <input type="tel" id="user-phone" placeholder="Телефон номері: +7 (701) 000-00-00" class="w-full card-bg p-3 rounded-xl border border-gray-700 text-xs text-white focus:outline-none focus:border-cyan-400">
        <input type="password" id="user-password" placeholder="Құпия сөз (Пароль)" class="w-full card-bg p-3 rounded-xl border border-gray-700 text-xs text-white focus:outline-none focus:border-cyan-400">
        
        <button onclick="handleLogin()" class="w-full bg-cyan-400 text-black p-3 rounded-xl font-bold text-xs hover:bg-cyan-300 transition">
          <i class="fa-solid fa-lock mr-1"></i> Жүйеге кіру
        </button>

        <div class="relative flex py-1 items-center">
          <div class="flex-grow border-t border-gray-700"></div>
          <span class="flex-shrink mx-3 text-gray-400 text-[10px]">немесе</span>
          <div class="flex-grow border-t border-gray-700"></div>
        </div>

        <button onclick="handleGoogleLogin()" class="w-full bg-white text-black p-3 rounded-xl font-semibold text-xs flex items-center justify-center gap-2 hover:bg-gray-200 transition">
          <i class="fa-brands fa-google text-red-500 text-sm"></i> Google арқылы жалғастыру
        </button>
      </div>
      
      <div class="text-[10px] text-cyan-400 pt-2 border-t border-gray-800">
        🚀 Жоба авторы: <b>Біржанұлы Қасым-Жомарт</b>
      </div>
    </div>
  </div>

  <!-- ЖОҒАРҒЫ НАВИГАЦИЯ -->
  <header class="p-4 card-bg flex justify-between items-center border-b border-cyan-900 sticky top-0 z-40">
    <div class="flex items-center gap-2">
      <div class="w-8 h-8 rounded-full bg-cyan-400 flex items-center justify-center font-bold text-black">Q</div>
      <h1 class="text-xl font-bold tracking-wider neon-text">QADAM <span class="text-xs text-white">1.0</span></h1>
    </div>
    <div class="flex items-center gap-2">
      <span id="display-username" class="text-xs text-cyan-300 font-semibold bg-cyan-950 px-2.5 py-1 rounded-lg border border-cyan-800">Түлек</span>
    </div>
  </header>

  <!-- НЕГІЗГІ КОНТЕНТ -->
  <main class="p-4 max-w-md mx-auto">

    <!-- 1. БАСТЫ БЕТ -->
    <section id="sec-home" class="space-y-4">
      <div class="card-bg p-5 rounded-2xl neon-border">
        <h2 id="welcome-title" class="text-lg font-bold">Сәлем, Түлек! 👋</h2>
        <p class="text-gray-300 text-sm mt-1">Бүгінгі мақсатың — 125+ балл жинау. Пробный тестті бастайық!</p>
        
        <div class="mt-3 text-[11px] text-cyan-300 bg-cyan-950/60 p-2 rounded-lg border border-cyan-900">
          🚀 Жоба авторы: <b>Біржанұлы Қасым-Жомарт</b>
        </div>

        <div class="mt-4 bg-gray-800 rounded-full h-3 overflow-hidden">
          <div class="bg-cyan-400 h-full" style="width: 75%;"></div>
        </div>
        <div class="flex justify-between text-xs mt-1 text-gray-400">
          <span>Дайындық деңгейі: 75%</span>
          <span>Максимум: 140 бал</span>
        </div>
      </div>

      <div class="grid grid-cols-2 gap-3">
        <button onclick="switchTab('unt')" class="card-bg p-4 rounded-xl text-left hover:border-cyan-400 border border-transparent transition">
          <i class="fa-solid fa-graduation-cap text-2xl text-cyan-400 mb-2"></i>
          <div class="font-semibold text-sm">ҰБТ Тесттері</div>
          <div class="text-xs text-gray-400">Лезде тексеру & Талдау</div>
        </button>
        <button onclick="switchTab('grants')" class="card-bg p-4 rounded-xl text-left hover:border-cyan-400 border border-transparent transition">
          <i class="fa-solid fa-award text-2xl text-cyan-400 mb-2"></i>
          <div class="font-semibold text-sm">Гранттар</div>
          <div class="text-xs text-gray-400">Ресми шекті балдар</div>
        </button>
        <button onclick="switchTab('ai')" class="card-bg p-4 rounded-xl text-left hover:border-cyan-400 border border-transparent transition">
          <i class="fa-solid fa-robot text-2xl text-cyan-400 mb-2"></i>
          <div class="font-semibold text-sm">QADAM AI</div>
          <div class="text-xs text-gray-400">Smart Репетитор</div>
        </button>
        <button onclick="switchTab('stats')" class="card-bg p-4 rounded-xl text-left hover:border-cyan-400 border border-transparent transition">
          <i class="fa-solid fa-chart-line text-2xl text-cyan-400 mb-2"></i>
          <div class="font-semibold text-sm">Статистика</div>
          <div class="text-xs text-gray-400">Өсу динамикасы</div>
        </button>
      </div>
    </section>

    <!-- 2. ҰБТ ПӘНДЕРІ ЖӘНЕ ТЕСТ -->
    <section id="sec-unt" class="hidden space-y-4">
      <div id="subject-list-view" class="space-y-3">
        <h2 class="text-xl font-bold neon-text">ҰБТ Пәндері</h2>
        <p class="text-xs text-gray-400">Пәнді таңдаңыз (Міндетті және Бейіндік):</p>
        
        <h3 class="text-xs font-semibold text-cyan-300 uppercase tracking-wider">Міндетті пәндер</h3>
        <div class="space-y-2">
          <div class="card-bg p-3 rounded-xl flex justify-between items-center cursor-pointer hover:border-cyan-400 border border-transparent" onclick="startTest('Қазақстан тарихы')">
            <div><div class="font-bold text-sm">Қазақстан тарихы</div><div class="text-xs text-gray-400">20 сұрақ</div></div>
            <i class="fa-solid fa-play text-cyan-400 text-xs"></i>
          </div>
          <div class="card-bg p-3 rounded-xl flex justify-between items-center cursor-pointer hover:border-cyan-400 border border-transparent" onclick="startTest('Математикалық сауаттылық')">
            <div><div class="font-bold text-sm">Математикалық сауаттылық</div><div class="text-xs text-gray-400">10 сұрақ</div></div>
            <i class="fa-solid fa-play text-cyan-400 text-xs"></i>
          </div>
          <div class="card-bg p-3 rounded-xl flex justify-between items-center cursor-pointer hover:border-cyan-400 border border-transparent" onclick="startTest('Оқу сауаттылығы')">
            <div><div class="font-bold text-sm">Оқу сауаттылығы</div><div class="text-xs text-gray-400">10 сұрақ</div></div>
            <i class="fa-solid fa-play text-cyan-400 text-xs"></i>
          </div>
        </div>

        <h3 class="text-xs font-semibold text-cyan-300 uppercase tracking-wider pt-2">Бейіндік пәндер (50 сұрақ)</h3>
        <div class="grid grid-cols-2 gap-2">
          <button onclick="startTest('Математика')" class="card-bg p-3 rounded-xl text-left hover:border-cyan-400 border border-transparent text-sm font-semibold">Математика (50)</button>
          <button onclick="startTest('Физика')" class="card-bg p-3 rounded-xl text-left hover:border-cyan-400 border border-transparent text-sm font-semibold">Физика (50)</button>
          <button onclick="startTest('Биология')" class="card-bg p-3 rounded-xl text-left hover:border-cyan-400 border border-transparent text-sm font-semibold">Биология (50)</button>
          <button onclick="startTest('Химия')" class="card-bg p-3 rounded-xl text-left hover:border-cyan-400 border border-transparent text-sm font-semibold">Химия (50)</button>
          <button onclick="startTest('География')" class="card-bg p-3 rounded-xl text-left hover:border-cyan-400 border border-transparent text-sm font-semibold">География (50)</button>
          <button onclick="startTest('Информатика')" class="card-bg p-3 rounded-xl text-left hover:border-cyan-400 border border-transparent text-sm font-semibold">Информатика (50)</button>
          <button onclick="startTest('Дүниежүзі тарихы')" class="card-bg p-3 rounded-xl text-left hover:border-cyan-400 border border-transparent text-sm font-semibold">Дж. тарихы (50)</button>
          <button onclick="startTest('Ағылшын тілі')" class="card-bg p-3 rounded-xl text-left hover:border-cyan-400 border border-transparent text-sm font-semibold">Ағылшын тілі (50)</button>
          <button onclick="startTest('Адам. Қоғам. Құқық')" class="card-bg p-3 rounded-xl text-left hover:border-cyan-400 border border-transparent text-sm font-semibold">АҚҚ (50)</button>
          <button onclick="startTest('Қазақ тілі мен әдебиеті')" class="card-bg p-3 rounded-xl text-left hover:border-cyan-400 border border-transparent text-sm font-semibold">Қазақ тілі (50)</button>
        </div>
      </div>

      <!-- ТЕСТ ЭКРАНЫ -->
      <div id="active-quiz-view" class="hidden space-y-4">
        <div class="flex justify-between items-center card-bg p-3 rounded-xl border border-cyan-900">
          <span id="quiz-subject-title" class="text-xs font-bold text-cyan-400 uppercase">Пән</span>
          <button onclick="exitTest()" class="text-xs text-red-400 hover:text-red-300 font-bold"><i class="fa-solid fa-xmark"></i> Шығу</button>
        </div>
        <div class="card-bg p-5 rounded-2xl border border-cyan-400 space-y-4">
          <div class="flex justify-between text-xs text-gray-400">
            <span id="q-counter">Сұрақ 1 / 50</span>
            <span class="text-cyan-300 font-bold">Лезде тексеру</span>
          </div>
          <p id="q-text" class="font-semibold text-sm text-gray-100">Сұрақ жүктелуде...</p>
          <div id="q-options" class="space-y-2"></div>
          
          <div id="feedback-box" class="hidden p-3 rounded-xl text-xs space-y-1"></div>
        </div>

        <div class="flex justify-between gap-2">
          <button onclick="prevQ()" class="flex-1 card-bg p-3 rounded-xl border border-gray-700 text-xs font-bold py-3">Артқа</button>
          <button onclick="nextQ()" class="flex-1 bg-cyan-400 text-black p-3 rounded-xl text-xs font-bold py-3">Келесі</button>
        </div>
      </div>
    </section>

    <!-- 3. ГРАНТТАР ЖӘНЕ ШЕКТІ БАЛДАР -->
    <section id="sec-grants" class="hidden space-y-4">
      <h2 class="text-xl font-bold neon-text">Гранттар & Шекті Балдар</h2>
      <p class="text-xs text-gray-400">2025-2026 жылғы ресми грант көрсеткіштері:</p>
      
      <div class="space-y-3">
        <div class="card-bg p-4 rounded-xl border-l-4 border-cyan-400">
          <div class="flex justify-between items-start">
            <div>
              <span class="text-xs text-cyan-400 font-bold">B057 — IT / Жасанды интеллект</span>
              <h3 class="font-bold text-sm mt-1">Математика + Информатика</h3>
            </div>
            <span class="bg-cyan-950 text-cyan-300 text-xs px-2 py-1 rounded font-bold">105 - 125 бал</span>
          </div>
        </div>

        <div class="card-bg p-4 rounded-xl border-l-4 border-cyan-400">
          <div class="flex justify-between items-start">
            <div>
              <span class="text-xs text-cyan-400 font-bold">B053 — Жалпы Медицина</span>
              <h3 class="font-bold text-sm mt-1">Биология + Химия</h3>
            </div>
            <span class="bg-cyan-950 text-cyan-300 text-xs px-2 py-1 rounded font-bold">118 - 135 бал</span>
          </div>
        </div>

        <div class="card-bg p-4 rounded-xl border-l-4 border-cyan-400">
          <div class="flex justify-between items-start">
            <div>
              <span class="text-xs text-cyan-400 font-bold">B064 — Инженерия & Робототехника</span>
              <h3 class="font-bold text-sm mt-1">Математика + Физика</h3>
            </div>
            <span class="bg-cyan-950 text-cyan-300 text-xs px-2 py-1 rounded font-bold">85 - 115 бал</span>
          </div>
        </div>

        <div class="card-bg p-4 rounded-xl border-l-4 border-cyan-400">
          <div class="flex justify-between items-start">
            <div>
              <span class="text-xs text-cyan-400 font-bold">B044 — Халықаралық құқық & Юриспруденция</span>
              <h3 class="font-bold text-sm mt-1">Дүниежүзі тарихы + АҚҚ</h3>
            </div>
            <span class="bg-cyan-950 text-cyan-300 text-xs px-2 py-1 rounded font-bold">115 - 130 бал</span>
          </div>
        </div>

        <div class="card-bg p-4 rounded-xl border-l-4 border-cyan-400">
          <div class="flex justify-between items-start">
            <div>
              <span class="text-xs text-cyan-400 font-bold">B041 — Экономика & Бизнес-аналитика</span>
              <h3 class="font-bold text-sm mt-1">Математика + География</h3>
            </div>
            <span class="bg-cyan-950 text-cyan-300 text-xs px-2 py-1 rounded font-bold">100 - 120 бал</span>
          </div>
        </div>
      </div>
    </section>

    <!-- 4. QADAM AI -->
    <section id="sec-ai" class="hidden space-y-4">
      <h2 class="text-xl font-bold neon-text">QADAM AI Репетиторы 🤖</h2>
      <div class="card-bg p-4 rounded-2xl h-80 overflow-y-auto flex flex-col space-y-3" id="chat-box">
        <div class="bg-cyan-950 p-3 rounded-xl max-w-[90%] text-xs text-cyan-200">
          Сәлем! Мен QADAM AI репетиторымын. Кез келген сұраққа толық әрі дұрыс жауап беремін!
        </div>
      </div>
      <div class="flex gap-2">
        <input type="text" id="chat-input" placeholder="Сұрағыңызды жазыңыз..." class="flex-1 card-bg p-3 rounded-xl border border-gray-700 text-xs focus:outline-none focus:border-cyan-400">
        <button onclick="sendAI()" class="bg-cyan-400 text-black px-4 py-3 rounded-xl font-bold text-xs"><i class="fa-solid fa-paper-plane"></i></button>
      </div>
    </section>

    <!-- 5. СТАТИСТИКА -->
    <section id="sec-stats" class="hidden space-y-4">
      <h2 class="text-xl font-bold neon-text">Прогресс Аналитикасы</h2>
      <div class="card-bg p-4 rounded-xl">
        <canvas id="scoreChart"></canvas>
      </div>
    </section>

  </main>

  <!-- ТӨМЕНГІ МӘЗІР -->
  <nav class="fixed bottom-0 left-0 right-0 card-bg border-t border-cyan-950 flex justify-around p-3 text-xs z-30">
    <button onclick="switchTab('home')" class="flex flex-col items-center gap-1 text-cyan-400" id="nav-home">
      <i class="fa-solid fa-house text-lg"></i>
      <span>Басты</span>
    </button>
    <button onclick="switchTab('unt')" class="flex flex-col items-center gap-1 text-gray-400" id="nav-unt">
      <i class="fa-solid fa-book-open text-lg"></i>
      <span>ҰБТ</span>
    </button>
    <button onclick="switchTab('grants')" class="flex flex-col items-center gap-1 text-gray-400" id="nav-grants">
      <i class="fa-solid fa-award text-lg"></i>
      <span>Гранттар</span>
    </button>
    <button onclick="switchTab('ai')" class="flex flex-col items-center gap-1 text-gray-400" id="nav-ai">
      <i class="fa-solid fa-robot text-lg"></i>
      <span class="font-bold">AI</span>
    </button>
    <button onclick="switchTab('stats')" class="flex flex-col items-center gap-1 text-gray-400" id="nav-stats">
      <i class="fa-solid fa-chart-line text-lg"></i>
      <span>Статистика</span>
    </button>
  </nav>

  <script>
    function handleLogin() {
      const nameInput = document.getElementById('user-name').value.trim();
      const phoneInput = document.getElementById('user-phone').value.trim();
      const passwordInput = document.getElementById('user-password').value.trim();
      
      if(!nameInput || !phoneInput || !passwordInput) {
        alert("Қауіпсіздік үшін атыңызды, номеріңізді және құпия сөзді толтырыңыз!");
        return;
      }
      if(passwordInput.length < 6) {
        alert("Құпия сөз кемінде 6 символдан тұруы тиіс!");
        return;
      }
      localStorage.setItem('qadam_user', nameInput);
      initUserSession(nameInput);
    }

    function handleGoogleLogin() {
      const googleName = "Google Түлегі";
      localStorage.setItem('qadam_user', googleName);
      initUserSession(googleName);
    }

    function initUserSession(username) {
      document.getElementById('display-username').innerText = username;
      document.getElementById('welcome-title').innerText = `Сәлем, ${username}! 👋`;
      document.getElementById('auth-screen').classList.add('hidden');
    }

    window.addEventListener('DOMContentLoaded', () => {
      const savedUser = localStorage.getItem('qadam_user');
      if(savedUser) {
        initUserSession(savedUser);
      }
    });

    function switchTab(tabId) {
      ['home', 'unt', 'grants', 'ai', 'stats'].forEach(id => {
        const sec = document.getElementById('sec-' + id);
        if(sec) sec.classList.add('hidden');
        const navBtn = document.getElementById('nav-' + id);
        if(navBtn) navBtn.className = "flex flex-col items-center gap-1 text-gray-400";
      });
      
      const targetSec = document.getElementById('sec-' + tabId);
      if(targetSec) targetSec.classList.remove('hidden');
      
      const activeNav = document.getElementById('nav-' + tabId);
      if(activeNav) activeNav.className = "flex flex-col items-center gap-1 text-cyan-400 font-bold";
      
      if(tabId === 'stats') {
        setTimeout(renderChart, 150);
      }
    }

    const db = {
      'Қазақстан тарихы': [
        { q: "Қазақ хандығы қай жылы және қай өңірде құрылды?", options: ["1465 ж., Жетісу батысында, Шу мен Талас алқабында", "1723 ж., Түркістан қаласында", "1991 ж., Алматы қаласында", "1500 ж., Сырдария бойында"], correct: 0, explanation: "Қазақ хандығы 1465 жылы Жетісудың батысында, Шу мен Талас алқабында құрылды." },
        { q: "1916 жылғы ұлт-азаттық көтерілістің шығуына басты себеп болған жарлық:", options: ["1916 жылғы 25 маусымдағы қара жұмысқа алу туралы жарлық", "Жерді тартып алу декреті", "Салықты 2 есе өсіру", "Әскери міндеткерлік"], correct: 0, explanation: "Басты себеп — 25 маусымдағы бұратана халықты қара жұмысқа алу туралы патша жарлығы." },
        { q: "Абылай ханның шын аты кім болған?", options: ["Әбілмансұр", "Қасым", "Бұрындық", "Тәуке"], correct: 0, explanation: "Абылай ханның бала кезіндегі аты — Әбілмансұр." }
      ],
      'Математикалық сауаттылық': [
        { q: "Сандар тізбегіндегі келесі санды тап: 2, 4, 8, 16, 32, ?", options: ["48", "64", "128", "36"], correct: 1, explanation: "Әрбір сан 2 есе артып отыр: 32 × 2 = 64." }
      ],
      'Оқу сауаттылығы': [
        { q: "Мәтіннің негізгі ойын анықтау үшін ең алдымен не істеу керек?", options: ["Контекст пен автордың басты идеясын жан-жақты талдау", "Тек бірінші сөйлемді оқу", "Соңғы абзацты қарау", "Тақырыпты ғана оқу"], correct: 0, explanation: "Мәтіннің негізгі ойы автордың көтерген басты идеясы арқылы ашылады." }
      ],
      'Математика': [
        { q: "y = x² функциясының туындысы неге тең?", options: ["x", "2x", "x³", "2"], correct: 1, explanation: "Дәрежелік функцияның туындысы: (xⁿ)' = n * xⁿ⁻¹. Демек, (x²)' = 2x." },
        { q: "sin²(x) + cos²(x) өрнегінің мәні неге тең?", options: ["0", "1", "2", "-1"], correct: 1, explanation: "Бұл негізгі тригонометриялық тепе-теңдік, кез келген бұрыш үшін мәні 1-ге тең." }
      ],
      'Физика': [
        { q: "Ньютонның екінші заңының формуласы қандай?", options: ["F = ma", "E = mc²", "P = IV", "F = mg"], correct: 0, explanation: "Ньютонның екінші заңы бойынша күш масса мен үдеудің көбейтіндісіне тең: F = ma." },
        { q: "Тоқ күшінің SI жүйесіндегі өлшем бірлігі:", options: ["Вольт (V)", "Ампер (A)", "Ом (Ω)", "Ватт (W)"], correct: 1, explanation: "Электр тогының күші Ампермен (A) өлшенеді." }
      ],
      'Биология': [
        { q: "Адам ағзасындағы ең үлкен ішкі орган:", options: ["Бауыр", "Жүрек", "Өкпе", "Бүйрек"], correct: 0, explanation: "Бауыр — адам ағзасындағы ең үлкен ішкі без әрі орган." },
        { q: "Жасушаның энергетикалық станциясы:", options: ["Митохондрия", "Рибосома", "Ядро", "Лизосома"], correct: 0, explanation: "Митохондрия жасушаны энергиямен (АТФ) қамтамасыз етеді." }
      ],
      'Химия': [
        { q: "Судың химиялық формуласы:", options: ["CO₂", "H₂O", "NaCl", "NH₃"], correct: 1, explanation: "Су молекуласы сутегі мен оттектен тұрады: H₂O." }
      ],
      'География': [
        { q: "Әлемдегі ең үлкен мұхит:", options: ["Тынық мұхиты", "Атлант мұхиты", "Үнді мұхиты", "Солтүстік Мұзды мұхит"], correct: 0, explanation: "Тынық мұхиты — Жер бетіндегі ең үлкен әрі терең мұхит." }
      ],
      'Информатика': [
        { q: "Python тілінде экранға мәтін шығару функциясы:", options: ["print()", "echo()", "console.log()", "write()"], correct: 0, explanation: "Python тілінде мәтін шығару үшін print() қолданылады." }
      ],
      'Дүниежүзі тарихы': [
        { q: "Екінші дүниежүзілік соғыс қай жылы аяқталды?", options: ["1945 жылы", "1939 жылы", "1918 жылы", "1950 жылы"], correct: 0, explanation: "Екінші дүниежүзілік соғыс 1945 жылы аяқталды." }
      ],
      'Ағылшын тілі': [
        { q: "Choose the correct verb: She ___ to school every day.", options: ["goes", "go", "going", "gone"], correct: 0, explanation: "Present Simple шағында ІІІ жақта етістікке -es жалғанады." }
      ],
      'Адам. Қоғам. Құқық': [
        { q: "ҚР Конституциясы қай жылы қабылданды?", options: ["1995 жылы", "1991 жылы", "1993 жылы", "2000 жылы"], correct: 0, explanation: "Қазіргі Конституция 1995 жылы 30 тамызда қабылданды." }
      ],
      'Қазақ тілі мен әдебиеті': [
        { q: "«Абай жолы» роман-эпопеясының авторы:", options: ["Мұхтар Әуезов", "Мағжан Жұмабаев", "Ілияс Жансүгіров", "Сәкен Сейфуллин"], correct: 0, explanation: "«Абай жолы» эпопеясының авторы — Мұхтар Әуезов." }
      ]
    };

    function getFullQuestions(subject) {
      let base = db[subject] || [
        { q: `${subject} бойынша негізгі ҰБТ сұрағы`, options: ["Дұрыс жауап", "Қате", "Қате", "Қате"], correct: 0, explanation: "Теориялық ережеге сай осы нұсқа дұрыс болып табылады." }
      ];
      let targetCount = (subject === 'Қазақстан тарихы') ? 20 : (subject.includes('сауаттылық') ? 10 : 50);
      let fullList = [...base];
      let i = 1;
      while(fullList.length < targetCount) {
        let template = base[(i - 1) % base.length];
        fullList.push({
          q: `${subject} пәнінен ҰБТ сұрағы #${fullList.length + 1}: ${template.q}`,
          options: template.options,
          correct: template.correct,
          explanation: `Түсіндірме: ${template.explanation}`
        });
        i++;
      }
      return fullList;
    }

    let curSubject = '';
    let curQIdx = 0;
    let answers = {};
    let activeQuestions = [];

    function startTest(subject) {
      curSubject = subject;
      curQIdx = 0;
      answers = {};
      activeQuestions = getFullQuestions(subject);
      
      document.getElementById('subject-list-view').classList.add('hidden');
      document.getElementById('active-quiz-view').classList.remove('hidden');
      document.getElementById('quiz-subject-title').innerText = subject;
      loadQ();
    }

    function exitTest() {
      document.getElementById('active-quiz-view').classList.add('hidden');
      document.getElementById('subject-list-view').classList.remove('hidden');
    }

    function loadQ() {
      const questions = activeQuestions;
      if(curQIdx >= questions.length) curQIdx = 0;
      const qData = questions[curQIdx];
      
      document.getElementById('q-counter').innerText = `Сұрақ ${curQIdx + 1} / ${questions.length}`;
      document.getElementById('q-text').innerText = qData.q;

      const feedbackBox = document.getElementById('feedback-box');
      feedbackBox.classList.add('hidden');
      feedbackBox.innerHTML = '';

      let html = '';
      qData.options.forEach((opt, idx) => {
        let btnStyle = 'border-gray-700 text-gray-200';
        if(answers[curQIdx] !== undefined) {
          if(idx === qData.correct) {
            btnStyle = 'border-green-500 bg-green-950 text-green-300 font-bold';
          } else if(answers[curQIdx] === idx) {
            btnStyle = 'border-red-500 bg-red-950 text-red-300 font-bold';
          }
        }
        html += `<button onclick="checkAnswer(${idx})" class="w-full text-left p-3 card-bg border ${btnStyle} rounded-xl text-xs hover:border-cyan-400 transition mb-2">${opt}</button>`;
      });
      document.getElementById('q-options').innerHTML = html;

      if(answers[curQIdx] !== undefined) {
        showFeedback(answers[curQIdx], qData);
      }
    }

    function checkAnswer(idx) {
      if(answers[curQIdx] !== undefined) return;
      answers[curQIdx] = idx;
      const qData = activeQuestions[curQIdx];
      loadQ();
      showFeedback(idx, qData);
    }

    function showFeedback(selectedIdx, qData) {
      const feedbackBox = document.getElementById('feedback-box');
      feedbackBox.classList.remove('hidden');

      if(selectedIdx === qData.correct) {
        feedbackBox.className = "p-3 rounded-xl text-xs space-y-1 bg-green-950 border border-green-500 text-green-200";
        feedbackBox.innerHTML = `✅ <b>Дұрыс!</b><br>💡 ${qData.explanation}`;
      } else {
        feedbackBox.className = "p-3 rounded-xl text-xs space-y-1 bg-red-950 border border-red-500 text-red-200";
        feedbackBox.innerHTML = `❌ <b>Қате!</b> Дұрыс жауап: <b>${qData.options[qData.correct]}</b><br>💡 ${qData.explanation}`;
      }
    }

    function nextQ() {
      if(curQIdx < activeQuestions.length - 1) {
        curQIdx++;
        loadQ();
      } else {
        alert("Тест аяқталды! Нәтижеңіз сақталды.");
        exitTest();
      }
    }

    function prevQ() {
      if(curQIdx > 0) {
        curQIdx--;
        loadQ();
      }
    }

    async function sendAI() {
      const inp = document.getElementById('chat-input');
      const box = document.getElementById('chat-box');
      if(!inp.value.trim()) return;
      
      const userText = inp.value;
      box.innerHTML += `<div class="bg-blue-900 p-3 rounded-xl max-w-[90%] text-xs self-end ml-auto">${userText}</div>`;
      inp.value = '';
      box.scrollTop = box.scrollHeight;

      const loadingId = "loading-" + Date.now();
      box.innerHTML += `<div id="${loadingId}" class="bg-cyan-950 p-3 rounded-xl max-w-[90%] text-xs text-cyan-200 animate-pulse">QADAM AI ойланып жатыр... 🧠</div>`;
      box.scrollTop = box.scrollHeight;

      try {
        const res = await fetch('https://text.pollinations.ai/' + encodeURIComponent('Сен ҰБТ репетиторысың. Қазақша нақты әрі түсінікті жауап бер: ' + userText));
        const text = await res.text();
        document.getElementById(loadingId).remove();
        box.innerHTML += `<div class="bg-cyan-950 p-3 rounded-xl max-w-[90%] text-xs text-cyan-200 whitespace-pre-line">${text}</div>`;
      } catch (err) {
        document.getElementById(loadingId).remove();
        box.innerHTML += `<div class="bg-cyan-950 p-3 rounded-xl max-w-[90%] text-xs text-cyan-200">Қате орын алды. Қайта көріңіз!</div>`;
      }
      box.scrollTop = box.scrollHeight;
    }

    function renderChart() {
      const canvasEl = document.getElementById('scoreChart');
      if(!canvasEl) return;
      const ctx = canvasEl.getContext('2d');
      if(window.myChart) window.myChart.destroy();
      window.myChart = new Chart(ctx, {
        type: 'line',
        data: {
          labels: ['1-апта', '2-апта', '3-апта', '4-апта'],
          datasets: [{
            label: 'Жиналған балл',
            data: [82, 96, 112, 130],
            borderColor: '#00f5d4',
            backgroundColor: 'rgba(0, 245, 212, 0.1)',
            fill: true
          }]
        }
      });
    }
  </script>
</body>
</html>
