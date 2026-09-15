<!DOCTYPE html>
<html lang="ru" class="h-full bg-black text-white antialiased">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
    <title></title>
    <script src="https://cdn.tailwindcss.com"></script>
    <style>
        .liquid-glass {
            background: rgba(255, 255, 255, 0.03);
            backdrop-filter: blur(25px) saturate(190%);
            -webkit-backdrop-filter: blur(25px) saturate(190%);
            border: 1px solid rgba(255, 255, 255, 0.08);
            box-shadow: 0 20px 50px rgba(0, 0, 0, 0.5), inset 0 1px 0 rgba(255, 255, 255, 0.1);
        }
        .liquid-glass-active {
            background: rgba(255, 255, 255, 0.07);
            border: 1px solid rgba(255, 255, 255, 0.18);
            box-shadow: 0 0 30px rgba(168, 85, 247, 0.25), inset 0 1px 0 rgba(255, 255, 255, 0.2);
        }
        .liquid-blob {
            background: linear-gradient(135deg, rgba(99, 102, 241, 0.8), rgba(168, 85, 247, 0.8), rgba(236, 72, 153, 0.8));
            filter: blur(30px);
            border-radius: 40% 60% 70% 30% / 40% 50% 60% 50%;
            animation: morph 8s ease-in-out infinite, rotate 25s linear infinite;
        }
        .liquid-blob.speaking {
            filter: blur(20px) drop-shadow(0 0 40px rgba(168, 85, 247, 0.8));
            animation: morph 2s ease-in-out infinite, rotate 10s linear infinite;
        }
        @keyframes morph {
            0%, 100% { border-radius: 40% 60% 70% 30% / 40% 50% 60% 50%; }
            34% { border-radius: 70% 30% 50% 50% / 30% 30% 70% 70%; }
            67% { border-radius: 100% 60% 60% 100% / 100% 100% 60% 60%; }
        }
        @keyframes rotate { 100% { transform: rotate(360deg); } }
        .hide-scrollbar::-webkit-scrollbar { display: none; }
        .hide-scrollbar { -ms-overflow-style: none; scrollbar-width: none; }
    </style>
</head>
<body class="h-full flex flex-col justify-between p-4 md:p-8 select-none overflow-hidden bg-black">

    <div class="fixed top-1/4 left-1/2 -translate-x-1/2 -translate-y-1/2 w-96 h-96 liquid-blob opacity-30 pointer-events-none"></div>

    <!-- ЭКРАН 1: Настройка -->
    <div id="screenSetup" class="relative z-10 max-w-lg w-full mx-auto my-auto space-y-6">
        <div class="liquid-glass rounded-3xl p-6 md:p-8 space-y-6">
            <div class="space-y-2">
                <label class="text-xs uppercase tracking-widest text-zinc-400 font-semibold">Ситуация</label>
                <select id="scenarioSelect" onchange="loadScenarioData()" class="w-full bg-zinc-900/80 text-white text-sm rounded-2xl p-4 border border-zinc-800 focus:outline-none focus:border-zinc-500 transition">
                    <option value="1">1. Договор родных дороже?</option>
                    <option value="2">2. Подарок от троих</option>
                    <option value="3">3. Отпустите меня</option>
                    <option value="4">4. Компьютерные войны</option>
                    <option value="5">5. Удачное собеседование</option>
                </select>
            </div>

            <div class="space-y-2">
                <label class="text-xs uppercase tracking-widest text-zinc-400 font-semibold">Стартовая роль (Первые 4 мин)</label>
                <div class="grid grid-cols-2 gap-3" id="roleContainer"></div>
            </div>

            <button onclick="startSession()" class="w-full liquid-glass-active hover:bg-white/10 text-white font-medium py-4 rounded-2xl transition duration-300 flex items-center justify-center gap-2">
                <svg class="w-5 h-5 fill-current" viewBox="0 0 24 24"><path d="M8 5v14l11-7z"/></svg>
                <span>Начать поединок</span>
            </button>
        </div>
    </div>

    <!-- ЭКРАН 2: Поединок -->
    <div id="screenFight" class="hidden relative z-10 flex-1 flex flex-col justify-between max-w-md w-full mx-auto py-4">
        <div class="liquid-glass rounded-2xl p-4 flex items-center justify-between">
            <div class="flex items-center gap-3">
                <div class="w-2.5 h-2.5 rounded-full bg-emerald-400 animate-pulse"></div>
                <span id="roundIndicator" class="text-xs font-semibold tracking-wider text-zinc-300 uppercase">Раунд 1 / 2</span>
            </div>
            <div id="timerDisplay" class="font-mono text-xl font-bold tracking-tight text-white">08:00</div>
        </div>

        <div class="liquid-glass rounded-2xl p-4 my-4 space-y-2 max-h-36 overflow-y-auto hide-scrollbar">
            <div id="activeRoleTitle" class="text-xs font-bold uppercase tracking-wider text-purple-400">---</div>
            <div id="activeRoleGoal" class="text-xs text-zinc-300 leading-relaxed">Нажмите микрофон и начинайте переговоры.</div>
        </div>

        <div class="relative my-auto flex items-center justify-center py-12">
            <div id="aiVisualizer" class="w-44 h-44 md:w-56 md:h-56 liquid-blob transition-all duration-500"></div>
        </div>

        <div class="space-y-3">
            <button id="micBtn" onclick="handleMicClick()" class="w-full liquid-glass hover:bg-white/10 text-white font-medium py-5 rounded-3xl transition duration-300 flex items-center justify-center gap-3">
                <svg id="micIcon" class="w-6 h-6 stroke-current fill-none stroke-2" viewBox="0 0 24 24"><path d="M12 2a3 3 0 0 0-3 3v7a3 3 0 0 0 6 0V5a3 3 0 0 0-3-3z"/><path d="M19 10v2a7 7 0 0 1-14 0v-2"/><line x1="12" y1="19" x2="12" y2="22"/></svg>
                <span id="micStatusText" class="text-sm">Нажмите, чтобы говорить</span>
            </button>
        </div>
    </div>

    <!-- ЭКРАН 3: Разбор -->
    <div id="screenDebrief" class="hidden relative z-10 max-w-lg w-full mx-auto my-auto">
        <div class="liquid-glass rounded-3xl p-6 md:p-8 space-y-6">
            <div class="flex items-center gap-3 border-b border-zinc-800 pb-4">
                <svg class="w-6 h-6 stroke-purple-400 fill-none stroke-2" viewBox="0 0 24 24"><path d="M14 2H6a2 2 0 0 0-2 2v16a2 2 0 0 0 2 2h12a2 2 0 0 0 2-2V8z"/><polyline points="14 2 14 8 20 8"/></svg>
                <span class="font-semibold text-sm tracking-wide">Разбор Судьи</span>
            </div>

            <div id="debriefContent" class="text-xs md:text-sm text-zinc-300 leading-relaxed space-y-4 max-h-80 overflow-y-auto hide-scrollbar">
                Анализируем поединок...
            </div>

            <button onclick="location.reload()" class="w-full liquid-glass-active hover:bg-white/10 text-white font-medium py-4 rounded-2xl transition duration-300 flex items-center justify-center gap-2">
                <svg class="w-5 h-5 stroke-current fill-none stroke-2" viewBox="0 0 24 24"><polyline points="1 4 1 10 7 10"/><path d="M3.51 15a9 9 0 1 0 2.13-9.36L1 10"/></svg>
                <span>Пройти снова</span>
            </button>
        </div>
    </div>

    <script>
        const rolesMap = {
            "1": ["Аркадий", "Алексей"],
            "2": ["Александр", "Сергей"],
            "3": ["Анна", "Родители"],
            "4": ["Мама", "Папа"],
            "5": ["Молодой специалист", "Приятель"]
        };

        let selectedScenario = "1";
        let selectedRole = "";
        let currentRound = 1;
        let timeLeft = 480;
        let timerInterval = null;
        let recognition = null;
        let isSpeaking = false;
        let transcriptHistory = [];

        function loadScenarioData() {
            selectedScenario = document.getElementById('scenarioSelect').value;
            const container = document.getElementById('roleContainer');
            container.innerHTML = '';
            
            rolesMap[selectedScenario].forEach((role, idx) => {
                const btn = document.createElement('button');
                btn.className = `p-4 rounded-2xl text-xs font-medium text-left border transition ${idx === 0 ? 'liquid-glass-active border-purple-500/50' : 'liquid-glass border-transparent'}`;
                btn.innerText = role;
                btn.onclick = () => {
                    Array.from(container.children).forEach(c => c.className = 'p-4 rounded-2xl text-xs font-medium text-left border liquid-glass border-transparent');
                    btn.className = 'p-4 rounded-2xl text-xs font-medium text-left border liquid-glass-active border-purple-500/50';
                    selectedRole = role;
                };
                container.appendChild(btn);
            });
            selectedRole = rolesMap[selectedScenario][0];
        }

        function startSession() {
            document.getElementById('screenSetup').classList.add('hidden');
            document.getElementById('screenFight').classList.remove('hidden');
            
            updateFightUI();
            
            timerInterval = setInterval(() => {
                timeLeft--;
                let m = Math.floor(timeLeft / 60);
                let s = timeLeft % 60;
                document.getElementById('timerDisplay').innerText = `${m.toString().padStart(2, '0')}:${s.toString().padStart(2, '0')}`;

                if (timeLeft === 240) {
                    currentRound = 2;
                    if ("vibrate" in navigator) navigator.vibrate([200, 100, 200]);
                    const roles = rolesMap[selectedScenario];
                    selectedRole = roles.find(r => r !== selectedRole);
                    updateFightUI();
                }

                if (timeLeft <= 0) {
                    clearInterval(timerInterval);
                    finishSession();
                }
            }, 1000);

            initSpeech();
        }

        function updateFightUI() {
            document.getElementById('roundIndicator').innerText = `Раунд ${currentRound} / 2`;
            document.getElementById('activeRoleTitle').innerText = `Ваша роль: ${selectedRole}`;
        }

        function initSpeech() {
            const Speech = window.SpeechRecognition || window.webkitSpeechRecognition;
            if (Speech) {
                recognition = new Speech();
                recognition.lang = 'ru-RU';
                recognition.onstart = () => {
                    isSpeaking = true;
                    document.getElementById('micStatusText').innerText = "Слушаю...";
                    document.getElementById('aiVisualizer').classList.add('speaking');
                };
                recognition.onresult = (e) => {
                    const text = e.results[0][0].transcript;
                    transcriptHistory.push(`[Подруга (${selectedRole})]: ${text}`);
                    sendToBackend(text);
                };
                recognition.onend = () => {
                    isSpeaking = false;
                    document.getElementById('micStatusText').innerText = "Нажмите, чтобы говорить";
                    document.getElementById('aiVisualizer').classList.remove('speaking');
                };
            }
        }

        function handleMicClick() {
            if (recognition) {
                if (isSpeaking) recognition.stop();
                else recognition.start();
            }
        }

        async function sendToBackend(text) {
            document.getElementById('micStatusText').innerText = "ИИ думает...";
            try {
                const res = await fetch('/api/chat', {
                    method: 'POST',
                    headers: { 'Content-Type': 'application/json' },
                    body: JSON.stringify({
                        scenarioId: selectedScenario,
                        userRole: selectedRole,
                        text: text
                    })
                });
                const data = await res.json();
                transcriptHistory.push(`[ИИ]: ${data.reply}`);
                speak(data.reply);
            } catch (err) {
                document.getElementById('micStatusText').innerText = "Ошибка сети";
            }
        }

        function speak(text) {
            const utter = new SpeechSynthesisUtterance(text);
            utter.lang = 'ru-RU';
            utter.onstart = () => document.getElementById('aiVisualizer').classList.add('speaking');
            utter.onend = () => document.getElementById('aiVisualizer').classList.remove('speaking');
            window.speechSynthesis.speak(utter);
        }

        async function finishSession() {
            document.getElementById('screenFight').classList.add('hidden');
            document.getElementById('screenDebrief').classList.remove('hidden');

            const res = await fetch('/api/debrief', {
                method: 'POST',
                headers: { 'Content-Type': 'application/json' },
                body: JSON.stringify({ history: transcriptHistory })
            });
            const data = await res.json();
            document.getElementById('debriefContent').innerText = data.analysis;
        }

        loadScenarioData();
    </script>
</body>
</html>
