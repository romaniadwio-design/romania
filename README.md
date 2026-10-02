 <!DOCTYPE html>
<html lang="id" class="h-full">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Kuis Matematika Seru - Pengurangan SD Kelas 2</title>
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
                            card: '#FFFFFF',
                            primary: '#0284C7',
                            accent: '#F59E0B',
                            correct: '#10B981',
                            wrong: '#EF4444',
                            purple: '#8B5CF6'
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
            background-image: radial-gradient(#BAE6FD 1.5px, transparent 1.5px);
            background-size: 24px 24px;
        }
        .glass-box {
            background: rgba(255, 255, 255, 0.95);
            backdrop-filter: blur(8px);
        }
        .btn-bounce:active {
            transform: scale(0.95);
        }
    </style>
</head>
<body class="font-sans text-slate-800 min-h-full flex flex-col justify-between antialiased">

    <!-- HEADER -->
    <header class="bg-sky-500 text-white shadow-md border-b-4 border-sky-600">
        <div class="max-w-3xl mx-auto px-4 py-3 flex items-center justify-between">
            <div class="flex items-center space-x-3 cursor-pointer" onclick="showScreen('loginScreen')">
                <div class="w-10 h-10 rounded-2xl bg-amber-400 text-sky-900 flex items-center justify-center font-bold text-xl shadow">
                    <i class="fa-solid fa-calculator"></i>
                </div>
                <div>
                    <h1 class="font-fredoka font-bold text-lg md:text-xl leading-tight tracking-wide">MATEMATIKA SERU</h1>
                    <p class="text-[10px] md:text-xs text-sky-100 font-semibold">Pengurangan • SD Kelas 2</p>
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

        <!-- 1. HALAMAN DAFTAR NAMA SISWA -->
        <section id="loginScreen" class="w-full glass-box rounded-3xl p-6 md:p-8 shadow-xl border-4 border-sky-300 text-center">
            <div class="w-20 h-20 mx-auto mb-4 rounded-full bg-amber-100 border-4 border-amber-400 flex items-center justify-center text-4xl text-amber-500 shadow-inner">
                <i class="fa-solid fa-face-smile"></i>
            </div>

            <h2 class="font-fredoka text-3xl font-bold text-sky-900 mb-2">Yuk, Belajar Pengurangan!</h2>
            <p class="text-slate-600 text-sm md:text-base max-w-sm mx-auto mb-6">
                Kuis matematika ceria dengan suara & waktu! Tulis namamu di bawah ini ya!
            </p>

            <form onsubmit="handleStartQuiz(event)" class="max-w-sm mx-auto space-y-4">
                <div>
                    <label class="block text-left font-fredoka text-sky-800 text-sm font-semibold mb-1">Nama Siswa / Panggilan:</label>
                    <input type="text" id="studentNameInput" required placeholder="Ketik namamu di sini..." class="w-full px-4 py-3 rounded-2xl border-2 border-sky-300 focus:border-sky-500 focus:ring-2 focus:ring-sky-200 outline-none font-bold text-slate-700 text-center text-lg shadow-sm">
                </div>

                <button type="submit" class="btn-bounce w-full bg-amber-400 hover:bg-amber-500 text-amber-950 font-fredoka font-bold text-lg py-3.5 px-6 rounded-2xl shadow-lg border-b-4 border-amber-600 transition flex items-center justify-center space-x-2">
                    <span>Mulai Main Kuis</span>
                    <i class="fa-solid fa-circle-play"></i>
                </button>
            </form>
        </section>

        <!-- 2. HALAMAN KUIS / SOAL -->
        <section id="quizScreen" class="hidden w-full glass-box rounded-3xl p-5 md:p-8 shadow-xl border-4 border-sky-300">
            <!-- STATUS BAR & TIMER -->
            <div class="flex items-center justify-between mb-4 bg-sky-50 p-3 rounded-2xl border border-sky-200">
                <div class="flex items-center space-x-2">
                    <span class="bg-sky-500 text-white font-fredoka text-xs px-3 py-1 rounded-full">Soal</span>
                    <span id="questionProgress" class="font-fredoka font-bold text-sky-900 text-base">1 / 10</span>
                </div>

                <!-- INDIKATOR WAKTU (1 MENIT PER SOAL) -->
                <div class="flex items-center space-x-2 bg-amber-100 text-amber-900 px-3 py-1 rounded-xl border border-amber-300 font-bold text-sm">
                    <i class="fa-solid fa-clock text-amber-600 animate-pulse"></i>
                    <span id="timerText">60 Detik</span>
                </div>

                <div class="flex items-center space-x-1" id="heartsContainer">
                    <i class="fa-solid fa-heart text-rose-500 text-lg"></i>
                    <i class="fa-solid fa-heart text-rose-500 text-lg"></i>
                    <i class="fa-solid fa-heart text-rose-500 text-lg"></i>
                </div>
            </div>

            <!-- VISUAL PROGRESS BAR TIMER -->
            <div class="w-full bg-slate-200 h-2.5 rounded-full overflow-hidden mb-5">
                <div id="timerBar" class="bg-amber-400 h-full w-full transition-all duration-1000 ease-linear"></div>
            </div>

            <!-- KARTU SOAL PENGURANGAN -->
            <div class="text-center mb-6">
                <div class="flex items-center justify-center gap-2 mb-2">
                    <p class="text-xs md:text-sm font-semibold text-slate-500 uppercase tracking-wider">Berapa Hasil Pengurangan Ini?</p>
                    
                    <!-- TOMBOL SUARA PEMBACA SOAL -->
                    <button onclick="speakQuestion()" class="bg-sky-500 hover:bg-sky-600 text-white w-8 h-8 rounded-full flex items-center justify-center shadow transition btn-bounce" title="Dengarkan Soal">
                        <i class="fa-solid fa-volume-high text-xs"></i>
                    </button>
                </div>

                <div class="bg-gradient-to-r from-sky-400 to-indigo-500 text-white rounded-3xl p-6 shadow-md border-4 border-white mb-4 relative">
                    <h3 id="mathQuestionText" class="font-fredoka text-5xl md:text-6xl font-bold tracking-wide">
                        15 - 7 = ?
                    </h3>
                </div>

                <!-- TOMBOL BANTUAN HITUNG BENDA -->
                <button onclick="toggleVisualHelp()" class="text-xs font-bold text-sky-700 bg-sky-100 hover:bg-sky-200 px-3 py-1.5 rounded-xl border border-sky-300 transition inline-flex items-center gap-1.5">
                    <i class="fa-solid fa-apple-whole text-rose-500"></i>
                    <span id="helpBtnText">Tampilkan Bantuan Gambar Apel</span>
                </button>

                <!-- AREA GAMBAR BANTUAN -->
                <div id="visualHelpBox" class="hidden mt-4 bg-amber-50 p-4 rounded-2xl border-2 border-dashed border-amber-300">
                    <p class="text-xs font-bold text-amber-800 mb-2">Bantuan Visual (Apel awal vs yang dicoret):</p>
                    <div id="applesContainer" class="flex flex-wrap justify-center gap-2 text-2xl"></div>
                </div>
            </div>

            <!-- PILIHAN JAWABAN -->
            <div id="optionsContainer" class="grid grid-cols-2 gap-3.5 max-w-md mx-auto"></div>
        </section>

        <!-- 3. HALAMAN HASIL / SKOR -->
        <section id="resultScreen" class="hidden w-full glass-box rounded-3xl p-6 md:p-8 shadow-xl border-4 border-sky-300 text-center">
            <div class="w-24 h-24 mx-auto mb-4 rounded-full bg-amber-100 border-4 border-amber-400 flex items-center justify-center text-5xl text-amber-500 shadow-md">
                <i class="fa-solid fa-trophy"></i>
            </div>

            <h2 class="font-fredoka text-3xl font-bold text-sky-900 mb-1">Hore! Kuis Selesai!</h2>
            <p id="resultMessage" class="text-slate-600 text-sm font-medium mb-6">Hebat sekali, kamu sudah menyelesaikan kuis pengurangan!</p>

            <div class="bg-sky-50 rounded-2xl p-4 max-w-xs mx-auto mb-6 border-2 border-sky-200 grid grid-cols-2 gap-3">
                <div>
                    <span class="block text-xs font-bold text-sky-600 uppercase">Jawaban Benar</span>
                    <span id="finalScoreText" class="font-fredoka text-3xl font-bold text-sky-900">0 / 10</span>
                </div>
                <div>
                    <span class="block text-xs font-bold text-sky-600 uppercase">Bintang Didapat</span>
                    <span id="finalStarsText" class="font-fredoka text-3xl font-bold text-amber-500">0 ★</span>
                </div>
            </div>

            <div class="flex flex-col sm:flex-row items-center justify-center gap-3 max-w-xs mx-auto">
                <button onclick="startQuiz()" class="btn-bounce w-full bg-amber-400 hover:bg-amber-500 text-amber-950 font-fredoka font-bold py-3 px-6 rounded-2xl shadow-md border-b-4 border-amber-600 transition flex items-center justify-center gap-2">
                    <i class="fa-solid fa-rotate-right"></i>
                    <span>Main Lagi</span>
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
        const QUESTION_BANK = [
            { num1: 8, num2: 3, answer: 5, options: [4, 5, 6, 3] },
            { num1: 10, num2: 4, answer: 6, options: [5, 6, 7, 4] },
            { num1: 12, num2: 5, answer: 7, options: [6, 7, 8, 9] },
            { num1: 15, num2: 7, answer: 8, options: [7, 8, 9, 6] },
            { num1: 14, num2: 6, answer: 8, options: [8, 7, 9, 10] },
            { num1: 11, num2: 4, answer: 7, options: [6, 7, 8, 5] },
            { num1: 16, num2: 8, answer: 8, options: [8, 9, 7, 6] },
            { num1: 13, num2: 5, answer: 8, options: [7, 8, 9, 10] },
            { num1: 18, num2: 9, answer: 9, options: [8, 9, 10, 7] },
            { num1: 20, num2: 8, answer: 12, options: [11, 12, 13, 10] },
            { num1: 17, num2: 9, answer: 8, options: [7, 8, 9, 10] },
            { num1: 19, num2: 7, answer: 12, options: [11, 12, 13, 14] }
        ];

        let activeQuizQuestions = [];
        let currentQuestionIndex = 0;
        let score = 0;
        let stars = 0;
        let lives = 3;
        let isProcessing = false;
        let studentName = '';

        // HITUNG MUNDUR WAKTU (1 MENIT = 60 DETIK)
        const QUESTION_TIME = 60; 
        let timeLeft = QUESTION_TIME;
        let timerInterval = null;

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
            activeQuizQuestions = [...QUESTION_BANK].sort(() => Math.random() - 0.5).slice(0, 10);
            currentQuestionIndex = 0;
            score = 0;
            stars = 0;
            lives = 3;
            isProcessing = false;

            document.getElementById('globalStars').innerText = stars;
            document.getElementById('visualHelpBox').classList.add('hidden');
            document.getElementById('helpBtnText').innerText = 'Tampilkan Bantuan Gambar Apel';

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

        function renderQuestion() {
            isProcessing = false;
            clearInterval(timerInterval);
            document.getElementById('visualHelpBox').classList.add('hidden');
            document.getElementById('helpBtnText').innerText = 'Tampilkan Bantuan Gambar Apel';

            if (currentQuestionIndex >= activeQuizQuestions.length || lives <= 0) {
                endQuiz();
                return;
            }

            renderHearts();

            const q = activeQuizQuestions[currentQuestionIndex];
            document.getElementById('questionProgress').innerText = `${currentQuestionIndex + 1} / ${activeQuizQuestions.length}`;
            document.getElementById('mathQuestionText').innerText = `${q.num1} - ${q.num2} = ?`;

            // Acak pilihan jawaban
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

            // Putar Pembacaan Soal secara Otomatis
            speakQuestion();

            // Jalankan Timer 60 Detik
            startTimer(q.answer);
        }

        // FUNSI PEMBACA SUARA (TEXT-TO-SPEECH)
        function speakQuestion() {
            if ('speechSynthesis' in window) {
                window.speechSynthesis.cancel(); // Hentikan suara sebelumnya jika ada
                const q = activeQuizQuestions[currentQuestionIndex];
                const textToSpeak = `Berapa hasil dari ${q.num1} dikurang ${q.num2}?`;

                const utterance = new SpeechSynthesisUtterance(textToSpeak);
                utterance.lang = 'id-ID'; // Menggunakan Bahasa Indonesia
                utterance.rate = 0.85; // Kecepatan agak lambat agar ramah anak

                window.speechSynthesis.speak(utterance);
            }
        }

        // FUNGSI TIMER (1 MENIT PER SOAL)
        function startTimer(correctOpt) {
            timeLeft = QUESTION_TIME;
            updateTimerDisplay();

            timerInterval = setInterval(() => {
                timeLeft--;
                updateTimerDisplay();

                if (timeLeft <= 0) {
                    clearInterval(timerInterval);
                    handleTimeOut(correctOpt);
                }
            }, 1000);
        }

        function updateTimerDisplay() {
            document.getElementById('timerText').innerText = `${timeLeft} Detik`;
            const percentage = (timeLeft / QUESTION_TIME) * 100;
            const timerBar = document.getElementById('timerBar');
            timerBar.style.width = `${percentage}%`;

            if (timeLeft <= 10) {
                timerBar.className = 'bg-rose-500 h-full w-full transition-all duration-1000 ease-linear';
            } else {
                timerBar.className = 'bg-amber-400 h-full w-full transition-all duration-1000 ease-linear';
            }
        }

        function handleTimeOut(correctOpt) {
            if (isProcessing) return;
            isProcessing = true;

            const allBtns = document.querySelectorAll('.option-btn');
            allBtns.forEach(b => {
                b.disabled = true;
                if (parseInt(b.innerText) === correctOpt) {
                    b.className = 'option-btn w-full bg-emerald-500 text-white font-fredoka font-bold text-2xl py-3.5 px-4 rounded-2xl shadow-lg border-b-4 border-emerald-700';
                }
            });

            lives--;
            renderHearts();

            // Ucapkan waktu habis
            if ('speechSynthesis' in window) {
                const timeoutUtterance = new SpeechSynthesisUtterance('Waktu habis!');
                timeoutUtterance.lang = 'id-ID';
                window.speechSynthesis.speak(timeoutUtterance);
            }

            setTimeout(() => {
                if (lives <= 0) {
                    endQuiz();
                } else {
                    currentQuestionIndex++;
                    renderQuestion();
                }
            }, 1500);
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
            clearInterval(timerInterval); // Hentikan hitung mundur jika sudah dijawab

            const allBtns = document.querySelectorAll('.option-btn');
            allBtns.forEach(b => b.disabled = true);

            if (selectedOpt === correctOpt) {
                btn.className = 'option-btn w-full bg-emerald-500 text-white font-fredoka font-bold text-2xl py-3.5 px-4 rounded-2xl shadow-lg border-b-4 border-emerald-700 animate-bounce';
                score++;
                stars += 10;
                document.getElementById('globalStars').innerText = stars;

                setTimeout(() => {
                    currentQuestionIndex++;
                    renderQuestion();
                }, 1000);
            } else {
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
                }, 1400);
            }
        }

        function endQuiz() {
            clearInterval(timerInterval);
            if ('speechSynthesis' in window) {
                window.speechSynthesis.cancel();
            }
            showScreen('resultScreen');

            document.getElementById('finalScoreText').innerText = `${score} / ${activeQuizQuestions.length}`;
            document.getElementById('finalStarsText').innerText = `${stars} ★`;

            const msg = document.getElementById('resultMessage');
            if (score >= 8) {
                msg.innerText = `Luar Biasa, ${studentName}! Kamu sangat pintar pengurangan! 🌟`;
            } else if (score >= 5) {
                msg.innerText = `Bagus Sekali, ${studentName}! Terus berlatih ya agar makin jago! 👍`;
            } else {
                msg.innerText = `Tetap Semangat, ${studentName}! Coba lagi yuk pasti bisa! 💪`;
            }
        }
    </script>
</body>
</html>
