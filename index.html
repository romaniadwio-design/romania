 <!DOCTYPE html>
<html lang="id" class="h-full">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Kuis Pengurangan Seru SD Kelas 2</title>
    <!-- Tailwind CSS -->
    <script src="https://cdn.tailwindcss.com"></script>
    <!-- Google Fonts -->
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Fredoka:wght@400;600;700&family=Plus+Jakarta+Sans:wght@500;700;800&display=swap" rel="stylesheet">
    <!-- FontAwesome Icons -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <!-- Canvas Confetti Library untuk Kembang Api -->
    <script src="https://cdn.jsdelivr.net/npm/canvas-confetti@1.6.0/dist/confetti.browser.min.js"></script>

    <script>
        tailwind.config = {
            theme: {
                extend: {
                    colors: {
                        kid: {
                            bg: '#F0F9FF',
                            primary: '#0284C7',
                            accent: '#F59E0B',
                            correct: '#10B981',
                            wrong: '#EF4444'
                        }
                    },
                    fontFamily: {
                        fredoka: ['Fredoka', 'sans-serif'],
                        sans: ['Plus Jakarta Sans', 'sans-serif']
                    }
                }
            }
        }
    </script>

    <style>
        /* ANIMASI BACKGROUND BERGERAK MATEMATIKA */
        body {
            background-color: #0f172a;
            overflow-x: hidden;
            position: relative;
        }

        .animated-bg {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            z-index: 0;
            background: linear-gradient(135deg, #0ea5e9, #3b82f6, #6366f1);
            overflow: hidden;
        }

        .math-symbol {
            position: absolute;
            color: rgba(255, 255, 255, 0.18);
            font-family: 'Fredoka', sans-serif;
            font-weight: bold;
            user-select: none;
            animation: floatUp 12s infinite linear;
        }

        @keyframes floatUp {
            0% {
                transform: translateY(110vh) rotate(0deg) scale(0.8);
                opacity: 0;
            }
            10% {
                opacity: 0.8;
            }
            90% {
                opacity: 0.8;
            }
            100% {
                transform: translateY(-10vh) rotate(360deg) scale(1.2);
                opacity: 0;
            }
        }

        .glass-box {
            background: rgba(255, 255, 255, 0.95);
            backdrop-filter: blur(12px);
        }

        .btn-bounce:active {
            transform: scale(0.95);
        }

        @keyframes pulse-timer {
            0%, 100% { transform: scale(1); }
            50% { transform: scale(1.1); }
        }

        .timer-warning {
            animation: pulse-timer 0.6s infinite;
            color: #EF4444 !important;
        }
    </style>
</head>
<body class="font-sans text-slate-800 min-h-full flex flex-col justify-between antialiased">

    <!-- LATAR BELAKANG ANIMASI SIMBOL MATEMATIKA BERGERAK -->
    <div class="animated-bg" id="mathBg"></div>

    <!-- HEADER -->
    <header class="bg-sky-600/90 backdrop-blur-md text-white shadow-lg border-b-4 border-sky-700 relative z-10">
        <div class="max-w-3xl mx-auto px-4 py-3 flex items-center justify-between">
            <div class="flex items-center space-x-3 cursor-pointer" onclick="showScreen('loginScreen')">
                <div class="w-10 h-10 rounded-2xl bg-amber-400 text-sky-900 flex items-center justify-center font-bold text-xl shadow">
                    <i class="fa-solid fa-calculator"></i>
                </div>
                <div>
                    <h1 class="font-fredoka font-bold text-lg md:text-xl leading-tight tracking-wide">KUIS MATEMATIKA</h1>
                    <p class="text-[10px] md:text-xs text-sky-100 font-semibold">Pengurangan Kelas 2 SD</p>
                </div>
            </div>

            <div class="flex items-center space-x-3">
                <div id="playerBadge" class="hidden bg-sky-800/60 px-3 py-1 rounded-full text-xs font-bold text-sky-100 border border-sky-400">
                    <i class="fa-solid fa-user-ninja mr-1"></i> <span id="playerNameDisplay">Siswa</span>
                </div>
                <!-- SKOR DI HEADER -->
                <div class="bg-amber-400 text-amber-950 px-3 py-1 rounded-full flex items-center space-x-1.5 font-fredoka font-bold text-sm shadow">
                    <i class="fa-solid fa-trophy text-amber-700"></i>
                    <span>Skor: <span id="globalScore">0</span></span>
                </div>
            </div>
        </div>
    </header>

    <!-- MAIN CONTAINER -->
    <main class="max-w-2xl w-full mx-auto p-4 my-auto relative z-10 flex-grow flex items-center justify-center">

        <!-- 1. HALAMAN LOGIN/MULAI -->
        <section id="loginScreen" class="w-full glass-box rounded-3xl p-6 md:p-8 shadow-2xl border-4 border-sky-300 text-center">
            <div class="w-20 h-20 mx-auto mb-4 rounded-full bg-amber-100 border-4 border-amber-400 flex items-center justify-center text-4xl text-amber-500 shadow-inner">
                <i class="fa-solid fa-face-smile-wink"></i>
            </div>

            <h2 class="font-fredoka text-3xl font-bold text-sky-900 mb-2">Siap Belajar Pengurangan?</h2>
            <p class="text-slate-600 text-sm md:text-base max-w-sm mx-auto mb-6">
                Ada 5 soal tantangan. Waktumu <b>1 menit per soal</b>! Pastikan suaramu aktif ya 🔊
            </p>

            <form onsubmit="handleStartQuiz(event)" class="max-w-sm mx-auto space-y-4">
                <div>
                    <label class="block text-left font-fredoka text-sky-800 text-sm font-semibold mb-1">Tulis Namamu:</label>
                    <input type="text" id="studentNameInput" required placeholder="Contoh: Budi" class="w-full px-4 py-3 rounded-2xl border-2 border-sky-300 focus:border-sky-500 focus:ring-2 focus:ring-sky-200 outline-none font-bold text-slate-700 text-center text-lg shadow-sm">
                </div>

                <button type="submit" class="btn-bounce w-full bg-amber-400 hover:bg-amber-500 text-amber-950 font-fredoka font-bold text-xl py-3.5 px-6 rounded-2xl shadow-lg border-b-4 border-amber-600 transition flex items-center justify-center space-x-2">
                    <span>Mulai Kuis</span>
                    <i class="fa-solid fa-play"></i>
                </button>
            </form>
        </section>

        <!-- 2. HALAMAN KUIS / SOAL -->
        <section id="quizScreen" class="hidden w-full glass-box rounded-3xl p-5 md:p-8 shadow-2xl border-4 border-sky-300">
            <!-- STATUS BAR & TIMER -->
            <div class="flex items-center justify-between mb-4 bg-sky-50 p-3 rounded-2xl border border-sky-200">
                <div class="flex items-center space-x-2">
                    <span class="bg-sky-500 text-white font-fredoka text-xs px-3 py-1 rounded-full">Soal</span>
                    <span id="questionProgress" class="font-fredoka font-bold text-sky-900 text-base">1 / 5</span>
                </div>

                <!-- TIMER 1 MENIT -->
                <div class="flex items-center space-x-2 bg-white px-4 py-1.5 rounded-xl border border-sky-200 shadow-sm">
                    <i class="fa-solid fa-stopwatch text-amber-500 text-lg" id="timerIcon"></i>
                    <span id="timerText" class="font-fredoka font-bold text-sky-900 text-lg w-12 text-center">01:00</span>
                </div>
            </div>

            <!-- PROGRESS BAR WAKTU -->
            <div class="w-full bg-slate-200 h-2.5 rounded-full overflow-hidden mb-6">
                <div id="timerBar" class="bg-amber-400 h-full w-full transition-all duration-1000 linear"></div>
            </div>

            <!-- KARTU SOAL PENGURANGAN -->
            <div class="text-center mb-6">
                <p class="text-xs md:text-sm font-semibold text-slate-500 uppercase tracking-wider mb-2">Berapa Hasil Pengurangan Ini?</p>

                <div class="bg-gradient-to-r from-sky-400 to-indigo-500 text-white rounded-3xl p-6 shadow-lg border-4 border-white mb-4">
                    <h3 id="mathQuestionText" class="font-fredoka text-5xl md:text-6xl font-bold tracking-wide">
                        12 - 5 = ?
                    </h3>
                </div>

                <!-- BANTUAN VISUAL GAMBAR -->
                <button onclick="toggleVisualHelp()" class="text-xs font-bold text-sky-700 bg-sky-100 hover:bg-sky-200 px-3 py-1.5 rounded-xl border border-sky-300 transition inline-flex items-center gap-1.5">
                    <i class="fa-solid fa-apple-whole text-rose-500"></i>
                    <span id="helpBtnText">Tampilkan Bantuan Gambar Apel</span>
                </button>

                <div id="visualHelpBox" class="hidden mt-4 bg-amber-50 p-4 rounded-2xl border-2 border-dashed border-amber-300">
                    <p class="text-xs font-bold text-amber-800 mb-2">Hitung Apel (Apel pudar = yang dikurangi):</p>
                    <div id="applesContainer" class="flex flex-wrap justify-center gap-1.5 text-xl md:text-2xl max-h-40 overflow-y-auto"></div>
                </div>
            </div>

            <!-- PILIHAN JAWABAN -->
            <div id="optionsContainer" class="grid grid-cols-2 gap-3.5 max-w-md mx-auto"></div>
        </section>

        <!-- 3. HALAMAN HASIL / SKOR -->
        <section id="resultScreen" class="hidden w-full glass-box rounded-3xl p-6 md:p-8 shadow-2xl border-4 border-sky-300 text-center">
            <div class="w-24 h-24 mx-auto mb-4 rounded-full bg-amber-100 border-4 border-amber-400 flex items-center justify-center text-5xl text-amber-500 shadow-md">
                <i class="fa-solid fa-trophy"></i>
            </div>

            <h2 class="font-fredoka text-3xl font-bold text-sky-900 mb-1">Hore! Kuis Selesai!</h2>
            <p id="resultMessage" class="text-slate-600 text-sm font-medium mb-6">Hebat sekali, kamu berhasil menyelesaikan tantangan!</p>

            <div class="bg-sky-50 rounded-2xl p-4 max-w-xs mx-auto mb-6 border-2 border-sky-200 grid grid-cols-2 gap-3">
                <div>
                    <span class="block text-xs font-bold text-sky-600 uppercase">Jawaban Benar</span>
                    <span id="finalCorrectText" class="font-fredoka text-3xl font-bold text-sky-900">0 / 5</span>
                </div>
                <div>
                    <span class="block text-xs font-bold text-sky-600 uppercase">Total Skor</span>
                    <span id="finalScoreText" class="font-fredoka text-3xl font-bold text-amber-500">0</span>
                </div>
            </div>

            <div class="flex flex-col sm:flex-row items-center justify-center gap-3 max-w-xs mx-auto">
                <button onclick="startQuiz()" class="btn-bounce w-full bg-amber-400 hover:bg-amber-500 text-amber-950 font-fredoka font-bold py-3 px-6 rounded-2xl shadow-md border-b-4 border-amber-600 transition flex items-center justify-center gap-2">
                    <i class="fa-solid fa-rotate-right"></i>
                    <span>Coba Lagi</span>
                </button>
                <button onclick="showScreen('loginScreen')" class="btn-bounce w-full bg-slate-200 hover:bg-slate-300 text-slate-700 font-fredoka font-bold py-3 px-6 rounded-2xl shadow-md transition">
                    Ganti Nama
                </button>
            </div>
        </section>

    </main>

    <!-- FOOTER -->
    <footer class="bg-sky-900/80 backdrop-blur-md text-sky-200 text-xs text-center py-3 font-medium border-t border-sky-700 relative z-10">
        <p>&copy; 2026 Kuis Matematika SD Kelas 2 — Belajar Pengurangan Ceria</p>
    </footer>

    <!-- LOGIKA JAVASCRIPT -->
    <script>
        // GENERATE BACKGROUND MATEMATIKA BERGERAK
        function createMathBackground() {
            const bgContainer = document.getElementById('mathBg');
            const symbols = ['-', '+', '=', '1', '2', '3', '4', '5', '6', '7', '8', '9', '0', '✖', '➗'];
            const count = 30; // Jumlah elemen bergerak

            for (let i = 0; i < count; i++) {
                const span = document.createElement('span');
                span.className = 'math-symbol';
                span.innerText = symbols[Math.floor(Math.random() * symbols.length)];
                
                // Variasi posisi, ukuran, dan kecepatan animasi
                span.style.left = `${Math.random() * 100}%`;
                span.style.fontSize = `${Math.random() * 2.5 + 1.5}rem`;
                span.style.animationDuration = `${Math.random() * 8 + 8}s`;
                span.style.animationDelay = `${Math.random() * 5}s`;

                bgContainer.appendChild(span);
            }
        }
        createMathBackground();

        // EFEK KEMBANG API / KONFETI BANYAK
        function triggerFireworks() {
            // Tembakan dari kiri
            confetti({
                particleCount: 80,
                angle: 60,
                spread: 70,
                origin: { x: 0, y: 0.7 }
            });
            // Tembakan dari kanan
            confetti({
                particleCount: 80,
                angle: 120,
                spread: 70,
                origin: { x: 1, y: 0.7 }
            });
        }

        // SOAL KHUSUS PENGURANGAN
        const QUIZ_QUESTIONS = [
            { num1: 12, num2: 5, answer: 7, options: [6, 7, 8, 5] },
            { num1: 15, num2: 3, answer: 12, options: [11, 12, 13, 10] },
            { num1: 23, num2: 12, answer: 11, options: [10, 11, 12, 13] },
            { num1: 32, num2: 15, answer: 17, options: [16, 17, 18, 15] },
            { num1: 43, num2: 27, answer: 16, options: [15, 16, 17, 18] }
        ];

        let currentQuestionIndex = 0;
        let correctAnswers = 0;
        let totalScore = 0;
        let isProcessing = false;
        let studentName = '';
        
        // Timer Variables
        let timeLeft = 60; // 1 Menit
        let timerInterval = null;

        // WEB AUDIO SYNTHESIZER (AUDIO FULL VOLUME KENCANG)
        const audioCtx = new (window.AudioContext || window.webkitAudioContext)();

        function playSound(type) {
            if (audioCtx.state === 'suspended') {
                audioCtx.resume();
            }
            
            const osc = audioCtx.createOscillator();
            const gain = audioCtx.createGain();
            const compressor = audioCtx.createDynamicsCompressor();

            osc.connect(gain);
            gain.connect(compressor);
            compressor.connect(audioCtx.destination);

            const now = audioCtx.currentTime;

            if (type === 'correct') {
                osc.type = 'triangle';
                osc.frequency.setValueAtTime(523.25, now);
                osc.frequency.setValueAtTime(659.25, now + 0.08);
                osc.frequency.setValueAtTime(783.99, now + 0.16);
                osc.frequency.setValueAtTime(1046.50, now + 0.24);

                gain.gain.setValueAtTime(1.0, now);
                gain.gain.exponentialRampToValueAtTime(0.01, now + 0.6);

                osc.start(now);
                osc.stop(now + 0.6);
            } else if (type === 'wrong') {
                osc.type = 'sawtooth';
                osc.frequency.setValueAtTime(220, now);
                osc.frequency.setValueAtTime(140, now + 0.15);

                gain.gain.setValueAtTime(1.0, now);
                gain.gain.exponentialRampToValueAtTime(0.01, now + 0.45);

                osc.start(now);
                osc.stop(now + 0.45);
            } else if (type === 'warning') {
                osc.type = 'square';
                osc.frequency.setValueAtTime(950, now);

                gain.gain.setValueAtTime(0.8, now);
                gain.gain.exponentialRampToValueAtTime(0.01, now + 0.12);

                osc.start(now);
                osc.stop(now + 0.12);
            } else if (type === 'timeout') {
                osc.type = 'sawtooth';
                osc.frequency.setValueAtTime(350, now);
                osc.frequency.setValueAtTime(180, now + 0.2);

                gain.gain.setValueAtTime(1.0, now);
                gain.gain.exponentialRampToValueAtTime(0.01, now + 0.5);

                osc.start(now);
                osc.stop(now + 0.5);
            }
        }

        function showScreen(screenId) {
            ['loginScreen', 'quizScreen', 'resultScreen'].forEach(id => {
                document.getElementById(id).classList.add('hidden');
            });
            document.getElementById(screenId).classList.remove('hidden');
        }

        function handleStartQuiz(e) {
            e.preventDefault();
            const nameInput = document.getElementById('studentNameInput').value.trim();
            if (!nameInput) return;

            studentName = nameInput;
            document.getElementById('playerNameDisplay').innerText = studentName;
            document.getElementById('playerBadge').classList.remove('hidden');

            startQuiz();
        }

        function startQuiz() {
            currentQuestionIndex = 0;
            correctAnswers = 0;
            totalScore = 0;
            isProcessing = false;

            document.getElementById('globalScore').innerText = totalScore;
            showScreen('quizScreen');
            renderQuestion();
        }

        function startTimer() {
            clearInterval(timerInterval);
            timeLeft = 60;
            
            const timerText = document.getElementById('timerText');
            const timerBar = document.getElementById('timerBar');
            const timerIcon = document.getElementById('timerIcon');

            timerText.classList.remove('timer-warning');
            timerIcon.classList.remove('timer-warning');

            const updateDisplay = () => {
                const mins = Math.floor(timeLeft / 60);
                const secs = timeLeft % 60;
                timerText.innerText = `${mins.toString().padStart(2, '0')}:${secs.toString().padStart(2, '0')}`;
                
                const percentage = (timeLeft / 60) * 100;
                timerBar.style.width = `${percentage}%`;

                if (timeLeft <= 10 && timeLeft > 0) {
                    timerText.classList.add('timer-warning');
                    timerIcon.classList.add('timer-warning');
                    timerBar.className = 'bg-rose-500 h-full transition-all duration-1000 linear';
                    playSound('warning');
                } else {
                    timerBar.className = 'bg-amber-400 h-full transition-all duration-1000 linear';
                }
            };

            updateDisplay();

            timerInterval = setInterval(() => {
                timeLeft--;
                updateDisplay();

                if (timeLeft <= 0) {
                    clearInterval(timerInterval);
                    handleTimeout();
                }
            }, 1000);
        }

        function handleTimeout() {
            if (isProcessing) return;
            isProcessing = true;

            playSound('timeout');

            const allBtns = document.querySelectorAll('.option-btn');
            allBtns.forEach(b => b.disabled = true);

            const q = QUIZ_QUESTIONS[currentQuestionIndex];
            allBtns.forEach(b => {
                if (parseInt(b.innerText) === q.answer) {
                    b.className = 'option-btn w-full bg-emerald-500 text-white font-fredoka font-bold text-2xl py-3.5 px-4 rounded-2xl shadow-lg border-b-4 border-emerald-700';
                }
            });

            setTimeout(() => {
                currentQuestionIndex++;
                if (currentQuestionIndex >= QUIZ_QUESTIONS.length) {
                    endQuiz();
                } else {
                    renderQuestion();
                }
            }, 1500);
        }

        function renderQuestion() {
            isProcessing = false;
            document.getElementById('visualHelpBox').classList.add('hidden');
            document.getElementById('helpBtnText').innerText = 'Tampilkan Bantuan Gambar Apel';

            if (currentQuestionIndex >= QUIZ_QUESTIONS.length) {
                endQuiz();
                return;
            }

            startTimer();

            const q = QUIZ_QUESTIONS[currentQuestionIndex];
            document.getElementById('questionProgress').innerText = `${currentQuestionIndex + 1} / ${QUIZ_QUESTIONS.length}`;
            document.getElementById('mathQuestionText').innerText = `${q.num1} - ${q.num2} = ?`;

            let opts = [...q.options].sort(() => Math.random() - 0.5);
            const container = document.getElementById('optionsContainer');
            container.innerHTML = '';

            opts.forEach(opt => {
                const btn = document.createElement('button');
                btn.className = 'btn-bounce option-btn w-full bg-white hover:bg-sky-100 text-sky-900 font-fredoka font-bold text-2xl py-3.5 px-4 rounded-2xl shadow-md border-2 border-sky-200 hover:border-sky-400 transition text-center';
                btn.innerText = opt;
                btn.onclick = () => checkAnswer(opt, q.answer, btn);
                container.appendChild(btn);
            });

            generateAppleHelp(q.num1, q.num2);
        }

        function generateAppleHelp(total, taken) {
            const applesContainer = document.getElementById('applesContainer');
            applesContainer.innerHTML = '';

            for (let i = 0; i < total; i++) {
                const apple = document.createElement('span');
                if (i < total - taken) {
                    apple.innerHTML = '🍎';
                } else {
                    apple.innerHTML = '<span class="opacity-30 line-through grayscale">🍎</span>';
                }
                applesContainer.appendChild(apple);
            }
        }

        function toggleVisualHelp() {
            const helpBox = document.getElementById('visualHelpBox');
            const helpText = document.getElementById('helpBtnText');
            if (helpBox.classList.contains('hidden')) {
                helpBox.classList.remove('hidden');
                helpText.innerText = 'Sembunyikan Bantuan Gambar';
            } else {
                helpBox.classList.add('hidden');
                helpText.innerText = 'Tampilkan Bantuan Gambar Apel';
            }
        }

        function checkAnswer(selectedOpt, correctOpt, btn) {
            if (isProcessing) return;
            isProcessing = true;
            clearInterval(timerInterval);

            const allBtns = document.querySelectorAll('.option-btn');
            allBtns.forEach(b => b.disabled = true);

            if (selectedOpt === correctOpt) {
                playSound('correct');
                triggerFireworks(); // PANGGIL EFEK KEMBANG API

                btn.className = 'option-btn w-full bg-emerald-500 text-white font-fredoka font-bold text-2xl py-3.5 px-4 rounded-2xl shadow-lg border-b-4 border-emerald-700 animate-bounce';
                correctAnswers++;
                totalScore += 20;
                document.getElementById('globalScore').innerText = totalScore;

                setTimeout(() => {
                    currentQuestionIndex++;
                    renderQuestion();
                }, 1400);
            } else {
                playSound('wrong');
                btn.className = 'option-btn w-full bg-rose-500 text-white font-fredoka font-bold text-2xl py-3.5 px-4 rounded-2xl shadow-lg border-b-4 border-rose-700';
                
                allBtns.forEach(b => {
                    if (parseInt(b.innerText) === correctOpt) {
                        b.className = 'option-btn w-full bg-emerald-500 text-white font-fredoka font-bold text-2xl py-3.5 px-4 rounded-2xl shadow-lg border-b-4 border-emerald-700';
                    }
                });

                setTimeout(() => {
                    currentQuestionIndex++;
                    renderQuestion();
                }, 1500);
            }
        }

        function endQuiz() {
            clearInterval(timerInterval);
            showScreen('resultScreen');

            // Selebrasi Akhir Kuis
            if (totalScore >= 60) {
                triggerFireworks();
                setTimeout(triggerFireworks, 500);
            }

            document.getElementById('finalCorrectText').innerText = `${correctAnswers} / ${QUIZ_QUESTIONS.length}`;
            document.getElementById('finalScoreText').innerText = totalScore;

            const msg = document.getElementById('resultMessage');
            if (totalScore === 100) {
                msg.innerText = `Sempurna, ${studentName}! Kamu berhasil mendapat skor 100! 🎉🌟`;
            } else if (totalScore >= 60) {
                msg.innerText = `Hebat Sekali, ${studentName}! Nilaimu sangat bagus! 👍`;
            } else {
                msg.innerText = `Tetap Semangat, ${studentName}! Belajar lagi pasti bisa dapat nilai 100! 💪`;
            }
        }
    </script>
</body>
</html>
