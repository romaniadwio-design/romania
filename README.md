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
        body {
            background-color: #E0F2FE;
            background-image: radial-gradient(#BAE6FD 2px, transparent 2px);
            background-size: 24px 24px;
        }
        .glass-box {
            background: rgba(255, 255, 255, 0.96);
            backdrop-filter: blur(10px);
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

    <!-- HEADER -->
    <header class="bg-sky-500 text-white shadow-lg border-b-4 border-sky-600">
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
                <div id="playerBadge" class="hidden bg-sky-700/60 px-3 py-1 rounded-full text-xs font-bold text-sky-100 border border-sky-400">
                    <i class="fa-solid fa-user-ninja mr-1"></i> <span id="playerNameDisplay">Siswa</span>
                </div>
                <div class="bg-amber-400 text-amber-950 px-3 py-1 rounded-full flex items-center space-x-1.5 font-fredoka font-bold text-sm shadow">
                    <i class="fa-solid fa-star text-amber-600"></i>
                    <span id="globalStars">0</span>
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
                Ada 5 soal tantangan. Waktumu <b>1 menit per soal</b>! Jangan lupa aktifkan suaramu ya 🔊
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
                <div class="flex items-center space-x-2 bg-white px-3 py-1 rounded-xl border border-sky-200 shadow-sm">
                    <i class="fa-solid fa-stopwatch text-amber-500 text-lg" id="timerIcon"></i>
                    <span id="timerText" class="font-fredoka font-bold text-sky-900 text-lg w-10 text-center">01:00</span>
                </div>

                <div class="flex items-center space-x-1" id="heartsContainer">
                    <i class="fa-solid fa-heart text-rose-500 text-lg"></i>
                    <i class="fa-solid fa-heart text-rose-500 text-lg"></i>
                    <i class="fa-solid fa-heart text-rose-500 text-lg"></i>
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
                    <span class="block text-xs font-bold text-sky-600 uppercase">Benar</span>
                    <span id="finalScoreText" class="font-fredoka text-3xl font-bold text-sky-900">0 / 5</span>
                </div>
                <div>
                    <span class="block text-xs font-bold text-sky-600 uppercase">Total Bintang</span>
                    <span id="finalStarsText" class="font-fredoka text-3xl font-bold text-amber-500">0 ★</span>
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
    <footer class="bg-sky-600 text-sky-100 text-xs text-center py-3 font-medium border-t border-sky-400">
        <p>&copy; 2026 Kuis Matematika SD Kelas 2 — Belajar Pengurangan Ceria</p>
    </footer>

    <!-- LOGIKA JAVASCRIPT -->
    <script>
        // SOAL KHUSUS PENGURANGAN SESUAI PERMINTAAN
        const QUIZ_QUESTIONS = [
            { num1: 12, num2: 5, answer: 7, options: [6, 7, 8, 5] },
            { num1: 15, num2: 3, answer: 12, options: [11, 12, 13, 10] },
            { num1: 23, num2: 12, answer: 11, options: [10, 11, 12, 13] },
            { num1: 32, num2: 15, answer: 17, options: [16, 17, 18, 15] },
            { num1: 43, num2: 27, answer: 16, options: [15, 16, 17, 18] }
        ];

        let currentQuestionIndex = 0;
        let score = 0;
        let stars = 0;
        let lives = 3;
        let isProcessing = false;
        let studentName = '';
        
        // Timer Variables
        let timeLeft = 60; // 1 Menit
        let timerInterval = null;

        // WEB AUDIO SYNTHESIZER (Tanpa File Eksternal)
        const audioCtx = new (window.AudioContext || window.webkitAudioContext)();

        function playSound(type) {
            if (audioCtx.state === 'suspended') {
                audioCtx.resume();
            }
            
            const osc = audioCtx.createOscillator();
            const gain = audioCtx.createGain();
            osc.connect(gain);
            gain.connect(audioCtx.destination);

            const now = audioCtx.currentTime;

            if (type === 'correct') {
                // Suara Ting-Ting Ceria (Arpeggio Major)
                osc.type = 'sine';
                osc.frequency.setValueAtTime(523.25, now); // C5
                osc.frequency.setValueAtTime(659.25, now + 0.1); // E5
                osc.frequency.setValueAtTime(783.99, now + 0.2); // G5
                osc.frequency.setValueAtTime(1046.50, now + 0.3); // C6

                gain.gain.setValueAtTime(0.3, now);
                gain.gain.exponentialRampToValueAtTime(0.01, now + 0.6);

                osc.start(now);
                osc.stop(now + 0.6);
            } else if (type === 'wrong') {
                // Suara Tet-Tet Salah (Low Sawtooth)
                osc.type = 'sawtooth';
                osc.frequency.setValueAtTime(180, now);
                osc.frequency.setValueAtTime(130, now + 0.15);

                gain.gain.setValueAtTime(0.3, now);
                gain.gain.exponentialRampToValueAtTime(0.01, now + 0.4);

                osc.start(now);
                osc.stop(now + 0.4);
            } else if (type === 'timeout') {
                // Suara Waktu Habis
                osc.type = 'triangle';
                osc.frequency.setValueAtTime(300, now);
                osc.frequency.setValueAtTime(150, now + 0.2);

                gain.gain.setValueAtTime(0.3, now);
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
            score = 0;
            stars = 0;
            lives = 3;
            isProcessing = false;

            document.getElementById('globalStars').innerText = stars;
            showScreen('quizScreen');
            renderQuestion();
        }

        function renderHearts() {
            const container = document.getElementById('heartsContainer');
            container.innerHTML = '';
            for (let i = 0; i < 3; i++) {
                const heart = document.createElement('i');
                heart.className = i < lives 
                    ? 'fa-solid fa-heart text-rose-500 text-lg' 
                    : 'fa-regular fa-heart text-slate-300 text-lg';
                container.appendChild(heart);
            }
        }

        function startTimer() {
            clearInterval(timerInterval);
            timeLeft = 60; // Reset ke 1 Menit (60 Detik)
            
            const timerText = document.getElementById('timerText');
            const timerBar = document.getElementById('timerBar');
            const timerIcon = document.getElementById('timerIcon');

            timerText.classList.remove('timer-warning');
            timerIcon.classList.remove('timer-warning');

            const updateDisplay = () => {
                const mins = Math.floor(timeLeft / 60);
                const secs = timeLeft % 60;
                timerText.innerText = `${mins.toString().padStart(2, '0')}:${secs.toString().padStart(2, '0')}`;
                
                // Progress bar animasi
                const percentage = (timeLeft / 60) * 100;
                timerBar.style.width = `${percentage}%`;

                if (timeLeft <= 10) {
                    timerText.classList.add('timer-warning');
                    timerIcon.classList.add('timer-warning');
                    timerBar.className = 'bg-rose-500 h-full transition-all duration-1000 linear';
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

            lives--;
            renderHearts();

            setTimeout(() => {
                if (lives <= 0 || currentQuestionIndex + 1 >= QUIZ_QUESTIONS.length) {
                    endQuiz();
                } else {
                    currentQuestionIndex++;
                    renderQuestion();
                }
            }, 1500);
        }

        function renderQuestion() {
            isProcessing = false;
            document.getElementById('visualHelpBox').classList.add('hidden');
            document.getElementById('helpBtnText').innerText = 'Tampilkan Bantuan Gambar Apel';

            if (currentQuestionIndex >= QUIZ_QUESTIONS.length || lives <= 0) {
                endQuiz();
                return;
            }

            renderHearts();
            startTimer();

            const q = QUIZ_QUESTIONS[currentQuestionIndex];
            document.getElementById('questionProgress').innerText = `${currentQuestionIndex + 1} / ${QUIZ_QUESTIONS.length}`;
            document.getElementById('mathQuestionText').innerText = `${q.num1} - ${q.num2} = ?`;

            // Acak urutan pilihan jawaban
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
                btn.className = 'option-btn w-full bg-emerald-500 text-white font-fredoka font-bold text-2xl py-3.5 px-4 rounded-2xl shadow-lg border-b-4 border-emerald-700 animate-bounce';
                score++;
                stars += 20;
                document.getElementById('globalStars').innerText = stars;

                setTimeout(() => {
                    currentQuestionIndex++;
                    renderQuestion();
                }, 1200);
            } else {
                playSound('wrong');
                btn.className = 'option-btn w-full bg-rose-500 text-white font-fredoka font-bold text-2xl py-3.5 px-4 rounded-2xl shadow-lg border-b-4 border-rose-700';
                
                allBtns.forEach(b => {
                    if (parseInt(b.innerText) === correctOpt) {
                        b.className = 'option-btn w-full bg-emerald-500 text-white font-fredoka font-bold text-2xl py-3.5 px-4 rounded-2xl shadow-lg border-b-4 border-emerald-700';
                    }
                });

                lives--;
                renderHearts();

                setTimeout(() => {
                    if (lives <= 0) {
                        endQuiz();
                    } else {
                        currentQuestionIndex++;
                        renderQuestion();
                    }
                }, 1500);
            }
        }

        function endQuiz() {
            clearInterval(timerInterval);
            showScreen('resultScreen');

            document.getElementById('finalScoreText').innerText = `${score} / ${QUIZ_QUESTIONS.length}`;
            document.getElementById('finalStarsText').innerText = `${stars} ★`;

            const msg = document.getElementById('resultMessage');
            if (score === 5) {
                msg.innerText = `Sempurna, ${studentName}! Kamu menjawab semua soal dengan benar! 🎉🌟`;
            } else if (score >= 3) {
                msg.innerText = `Hebat Sekali, ${studentName}! Nilaimu sangat bagus! 👍`;
            } else {
                msg.innerText = `Tetap Semangat, ${studentName}! Belajar lagi pasti bisa mendapat skor sempurna! 💪`;
            }
        }
    </script>
</body>
</html>
