  <!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>WorshipSlide PMK NS - Persekutuan Mahasiswa Kristen Nafiri Sion</title>
    <!-- Tailwind CSS -->
    <script src="https://cdn.tailwindcss.com"></script>
    <!-- Google Fonts: Inter & Plus Jakarta Sans -->
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700;800&family=Plus+Jakarta+Sans:wght@600;700;800&display=swap" rel="stylesheet">
    <!-- Lucide Icons -->
    <script src="https://unpkg.com/lucide@latest"></script>
    
    <style>
        body {
            font-family: 'Inter', sans-serif;
            overflow: hidden;
            user-select: none;
        }

        .font-display {
            font-family: 'Plus Jakarta Sans', sans-serif;
        }

        /* Custom Scrollbar untuk Panel Operator */
        ::-webkit-scrollbar {
            width: 6px;
            height: 6px;
        }
        ::-webkit-scrollbar-track {
            background: rgba(15, 23, 42, 0.5);
        }
        ::-webkit-scrollbar-thumb {
            background: rgba(100, 116, 139, 0.4);
            border-radius: 9999px;
        }
        ::-webkit-scrollbar-thumb:hover {
            background: rgba(148, 163, 184, 0.7);
        }

        /* Tema Latar Belakang Stage */
        .bg-theme-royal {
            background: radial-gradient(circle at 22% 18%, #1e1b4b 0%, #0f172a 48%, #020617 100%);
        }
        .bg-theme-heavenly {
            background: radial-gradient(circle at 20% 20%, #111827 0%, #090d16 55%, #030712 100%);
        }
        .bg-theme-dawn {
            background: linear-gradient(135deg, #18181b 0%, #1e1b4b 50%, #09090b 100%);
        }
        .bg-theme-emerald {
            background: radial-gradient(circle at 80% 10%, #064e3b 0%, #090d16 60%, #020617 100%);
        }
        .bg-theme-minimal {
            background: #030303;
        }

        /* Animasi Partikel Cahaya Halus */
        @keyframes floatGlow {
            0%, 100% {
                transform: translateY(0px) scale(1);
                opacity: 0.35;
            }
            50% {
                transform: translateY(-25px) scale(1.1);
                opacity: 0.65;
            }
        }
        .animate-glow-slow {
            animation: floatGlow 8s ease-in-out infinite;
        }
        .animate-glow-delayed {
            animation: floatGlow 11s ease-in-out 3s infinite;
        }

        /* Bayangan Teks Kuat agar Mudah Dibaca Jemaat di Proyektor */
        .worship-text-shadow {
            text-shadow: 
                0 4px 12px rgba(0, 0, 0, 0.85),
                0 2px 4px rgba(0, 0, 0, 0.95),
                0 0 30px rgba(0, 0, 0, 0.5);
        }

        /* Transisi Halus Teks Slide */
        .slide-fade {
            transition: opacity 0.25s ease-in-out, transform 0.25s ease-out;
        }
    </style>
</head>
<body class="bg-[#06080f] text-slate-100 h-screen w-screen flex flex-col md:flex-row">

    <!-- =====================================================================
         1. PANEL KONTROL OPERATOR (SIDEBAR KIRI)
         ===================================================================== -->
    <aside id="operatorSidebar" class="w-full md:w-[380px] lg:w-[420px] h-[52vh] md:h-full bg-[#0b0e17] border-b md:border-b-0 md:border-r border-slate-800/90 flex flex-col z-20 shrink-0 shadow-2xl shadow-black/80">
        
        <!-- Header Aplikasi & Logo PMK Nafiri Sion -->
        <div class="px-4 py-3 bg-[#0f131f] border-b border-slate-800/90 flex items-center justify-between gap-2">
            <div class="flex items-center gap-3 min-w-0">
                <!-- Logo PMK NS (Emblem Perisai & Salib PMK Nafiri Sion + Klik untuk Ganti Logo) -->
                <div id="headerLogoWrapper" onclick="document.getElementById('logoFileInput').click()" title="Klik untuk mengganti/unggah file logo PMK NS" class="w-11 h-11 rounded-xl bg-white/95 border-2 border-amber-400 flex items-center justify-center shadow-lg shadow-amber-500/25 overflow-hidden cursor-pointer shrink-0 group relative transition-transform hover:scale-105">
                    <img id="customLogoImg" src="" alt="Logo PMK NS" class="hidden w-full h-full object-contain p-0.5">
                    <svg id="defaultLogoSvg" viewBox="0 0 100 100" class="w-10 h-10" fill="none" xmlns="http://www.w3.org/2000/svg">
                        <!-- Lingkaran Luar Emas & Putih -->
                        <circle cx="50" cy="50" r="46" fill="#FFFFFF" stroke="#D97706" stroke-width="4"/>
                        <circle cx="50" cy="50" r="35" fill="#EFF6FF" stroke="#1E3A8A" stroke-width="2"/>
                        <!-- Teks Melingkar Atas & Bawah -->
                        <path id="topArcHeader" d="M 14,50 A 36,36 0 1,1 86,50" fill="none"/>
                        <text font-size="6.8" font-weight="800" fill="#1E3A8A" letter-spacing="0.4">
                            <textPath href="#topArcHeader" startOffset="50%" text-anchor="middle">PMK NAFIRI SION</textPath>
                        </text>
                        <!-- Perisai Merah & Biru -->
                        <path d="M31 28 H69 V50 C69 65 50 76 50 76 C50 76 31 65 31 50 Z" fill="#1D4ED8" stroke="#F59E0B" stroke-width="2.5"/>
                        <!-- Salib Utama -->
                        <path d="M50 31 V68 M37 44 H63" stroke="#FACC15" stroke-width="5" stroke-linecap="round"/>
                        <!-- Nafiri Emas Menyilang -->
                        <path d="M35 60 L64 38 L67 43 L37 63 Z" fill="#FDE047"/>
                        <!-- Alkitab Terbuka di Bawah -->
                        <path d="M38 66 Q44 63 50 66 Q56 63 62 66 V72 Q56 69 50 72 Q44 69 38 72 Z" fill="#FFFFFF"/>
                    </svg>
                    <div class="absolute inset-0 bg-black/60 opacity-0 group-hover:opacity-100 transition-opacity flex items-center justify-center">
                        <i data-lucide="camera" class="w-4 h-4 text-amber-300"></i>
                    </div>
                </div>
                <div class="truncate">
                    <div class="flex items-center gap-1.5">
                        <h1 class="font-display font-extrabold text-sm tracking-wide text-white leading-tight truncate">WorshipSlide <span class="text-amber-400">PMK NS</span></h1>
                    </div>
                    <p class="text-[11px] text-slate-400 font-medium truncate">Persekutuan Mahasiswa Kristen Nafiri Sion</p>
                </div>
            </div>
            
            <!-- Status Live Indicator -->
            <div id="liveBadge" class="flex items-center gap-1.5 px-2.5 py-1 rounded-full bg-emerald-500/10 border border-emerald-500/30 text-emerald-400 text-[11px] font-semibold shrink-0">
                <span class="w-2 h-2 rounded-full bg-emerald-400 animate-pulse"></span>
                <span>TAYANG</span>
            </div>
        </div>

        <!-- Tombol Aksi Cepat Layar (Clear Text & Blackout) -->
        <div class="p-3 bg-[#090c14] border-b border-slate-800/80 grid grid-cols-2 gap-2">
            <button id="btnClearText" onclick="toggleClearText()" class="flex items-center justify-center gap-2 py-2.5 px-3 rounded-xl font-semibold text-xs transition-all border border-slate-700/80 bg-slate-900/90 hover:bg-slate-800 text-slate-200 active:scale-[0.98]">
                <i data-lucide="eye-off" class="w-4 h-4 text-amber-400"></i>
                <span>Clear Text (Latar)</span>
            </button>
            <button id="btnBlackout" onclick="toggleBlackout()" class="flex items-center justify-center gap-2 py-2.5 px-3 rounded-xl font-semibold text-xs transition-all border border-slate-700/80 bg-slate-900/90 hover:bg-slate-800 text-slate-200 active:scale-[0.98]">
                <i data-lucide="monitor-off" class="w-4 h-4 text-rose-400"></i>
                <span>Blackout (Hitam)</span>
            </button>
        </div>

        <!-- Navigasi Tab Sidebar: Daftar Lagu vs Pengaturan Visual -->
        <div class="px-3 pt-2 bg-[#0b0e17] border-b border-slate-800/80 flex gap-1">
            <button id="tabSongs" onclick="switchSidebarTab('songs')" class="flex-1 py-2 text-xs font-semibold rounded-t-lg border-b-2 border-amber-400 text-amber-300 bg-slate-900/80 transition-colors flex items-center justify-center gap-1.5">
                <i data-lucide="music" class="w-3.5 h-3.5 text-amber-400"></i>
                Daftar Lagu & Bait
            </button>
            <button id="tabVisual" onclick="switchSidebarTab('visual')" class="flex-1 py-2 text-xs font-semibold rounded-t-lg border-b-2 border-transparent text-slate-400 hover:text-slate-200 transition-colors flex items-center justify-center gap-1.5">
                <i data-lucide="palette" class="w-3.5 h-3.5"></i>
                Latar & Teks
            </button>
        </div>

        <!-- KONTEN TAB 1: DAFTAR LAGU & BAIT -->
        <div id="panelSongs" class="flex-1 flex flex-col overflow-hidden">
            <!-- Pencarian & Tombol Tambah Lagu -->
            <div class="p-3 border-b border-slate-800/80 flex gap-2 bg-[#0d111c]">
                <div class="relative flex-1">
                    <i data-lucide="search" class="w-3.5 h-3.5 text-slate-400 absolute left-3 top-1/2 -translate-y-1/2"></i>
                    <input type="text" id="searchSongInput" oninput="renderSongList()" placeholder="Cari judul lagu..." class="w-full bg-[#070910] border border-slate-800 rounded-xl pl-8 pr-3 py-1.5 text-xs text-slate-100 placeholder-slate-500 focus:outline-none focus:border-amber-400">
                </div>
                <button onclick="openSongModal('add')" class="px-3 py-1.5 rounded-xl bg-amber-500 hover:bg-amber-400 text-slate-950 font-bold text-xs flex items-center gap-1 transition-all shrink-0 shadow-md shadow-amber-500/20" title="Tambah Lagu Baru">
                    <i data-lucide="plus" class="w-4 h-4 stroke-[2.5]"></i>
                    <span>Baru</span>
                </button>
            </div>

            <!-- Daftar Lagu (Scrollable bagian atas) -->
            <div class="h-36 md:h-44 overflow-y-auto p-2 border-b border-slate-800/80 bg-[#080a12] space-y-1" id="songListContainer">
                <!-- Diisi melalui JavaScript -->
            </div>

            <!-- Header Daftar Bait Lagu Terpilih -->
            <div class="px-3 py-2 bg-[#0f131f] border-b border-slate-800/80 flex items-center justify-between">
                <div class="truncate pr-2">
                    <span class="text-[10px] uppercase tracking-wider text-slate-400 font-bold block">Lagu Aktif:</span>
                    <h2 id="activeSongTitle" class="text-xs font-bold text-amber-400 truncate">-</h2>
                </div>
                <div class="flex items-center gap-1 shrink-0">
                    <button onclick="openSongModal('edit')" class="p-1.5 rounded-lg bg-slate-900 hover:bg-slate-800 text-slate-300 border border-slate-700/80 transition-colors" title="Edit Lirik Lagu Ini">
                        <i data-lucide="edit-3" class="w-3.5 h-3.5"></i>
                    </button>
                    <button onclick="deleteCurrentSong()" class="p-1.5 rounded-lg bg-slate-900 hover:bg-rose-950/80 text-slate-400 hover:text-rose-400 border border-slate-700/80 transition-colors" title="Hapus Lagu">
                        <i data-lucide="trash-2" class="w-3.5 h-3.5"></i>
                    </button>
                </div>
            </div>

            <!-- Daftar Bait / Slide yang Bisa Langsung Diklik -->
            <div id="slidesGridContainer" class="flex-1 overflow-y-auto p-3 space-y-2 bg-[#0b0e17]">
                <!-- Diisi melalui JavaScript -->
            </div>
        </div>

        <!-- KONTEN TAB 2: KUSTOMISASI VISUAL LATAR & TEKS -->
        <div id="panelVisual" class="hidden flex-1 overflow-y-auto p-4 space-y-5 bg-[#0b0e17]">
            
            <!-- Pilihan Tema Latar Belakang -->
            <div>
                <label class="block text-xs font-bold uppercase tracking-wider text-slate-400 mb-2.5">Tema Latar Belakang Gelap</label>
                <div class="grid grid-cols-2 gap-2.5">
                    <button onclick="setTheme('heavenly')" id="themeBtn-heavenly" class="theme-option p-2.5 rounded-xl border-2 border-amber-400 bg-slate-900 text-left transition-all">
                        <div class="w-full h-10 rounded-lg bg-theme-heavenly mb-2 border border-white/10"></div>
                        <p class="text-xs font-bold text-white">Obsidian Gelap</p>
                        <p class="text-[10px] text-slate-400">Gelap elegan & teduh</p>
                    </button>

                    <button onclick="setTheme('royal')" id="themeBtn-royal" class="theme-option p-2.5 rounded-xl border-2 border-slate-800 bg-slate-900/50 hover:border-slate-700 text-left transition-all">
                        <div class="w-full h-10 rounded-lg bg-theme-royal mb-2 border border-white/10"></div>
                        <p class="text-xs font-bold text-white">Midnight Navy</p>
                        <p class="text-[10px] text-slate-400">Biru malam pekat</p>
                    </button>

                    <button onclick="setTheme('dawn')" id="themeBtn-dawn" class="theme-option p-2.5 rounded-xl border-2 border-slate-800 bg-slate-900/50 hover:border-slate-700 text-left transition-all">
                        <div class="w-full h-10 rounded-lg bg-theme-dawn mb-2 border border-white/10"></div>
                        <p class="text-xs font-bold text-white">Charcoal Indigo</p>
                        <p class="text-[10px] text-slate-400">Abu-abu gelap & violet</p>
                    </button>

                    <button onclick="setTheme('minimal')" id="themeBtn-minimal" class="theme-option p-2.5 rounded-xl border-2 border-slate-800 bg-slate-900/50 hover:border-slate-700 text-left transition-all">
                        <div class="w-full h-10 rounded-lg bg-theme-minimal mb-2 border border-white/10"></div>
                        <p class="text-xs font-bold text-white">Hitam Pekat</p>
                        <p class="text-[10px] text-slate-400">Kontras tinggi & fokus teks</p>
                    </button>
                </div>
            </div>

            <!-- Toggle Partikel Cahaya Halus -->
            <div class="p-3 rounded-xl bg-slate-800/60 border border-slate-700/80 flex items-center justify-between">
                <div>
                    <p class="text-xs font-bold text-white">Animasi Partikel Cahaya</p>
                    <p class="text-[11px] text-slate-400">Efek pendaran lembut di latar belakang</p>
                </div>
                <button id="toggleParticlesBtn" onclick="toggleParticles()" class="w-11 h-6 rounded-full bg-amber-500 p-0.5 transition-colors relative">
                    <span id="toggleParticlesDot" class="block w-5 h-5 rounded-full bg-white shadow transform translate-x-5 transition-transform"></span>
                </button>
            </div>

            <!-- Pengaturan Logo Organisasi (Header & Layar Proyeksi) -->
            <div class="p-3 rounded-xl bg-slate-800/60 border border-slate-700/80 space-y-2.5">
                <div class="flex items-center justify-between">
                    <div>
                        <p class="text-xs font-bold text-white">Logo PMK NS / Gereja</p>
                        <p class="text-[11px] text-slate-400">Tampilkan logo di pojok layar proyeksi</p>
                    </div>
                    <button id="toggleStageLogoBtn" onclick="toggleStageLogo()" class="w-11 h-6 rounded-full bg-amber-500 p-0.5 transition-colors relative">
                        <span id="toggleStageLogoDot" class="block w-5 h-5 rounded-full bg-white shadow transform translate-x-5 transition-transform"></span>
                    </button>
                </div>
                <div class="flex items-center gap-2 pt-1">
                    <label class="flex-1 py-2 px-3 rounded-lg bg-slate-900 hover:bg-slate-800 border border-slate-700 text-xs font-semibold text-amber-400 cursor-pointer flex items-center justify-center gap-1.5 transition-colors">
                        <i data-lucide="image-plus" class="w-3.5 h-3.5"></i>
                        <span>Unggah File Logo</span>
                        <input type="file" id="logoFileInput" accept="image/*" onchange="handleLogoUpload(event)" class="hidden">
                    </label>
                    <button onclick="resetCustomLogo()" class="py-2 px-3 rounded-lg bg-slate-900 hover:bg-slate-800 border border-slate-700 text-xs font-semibold text-slate-400 hover:text-white transition-colors" title="Gunakan Logo Bawaan">
                        Reset
                    </button>
                </div>
            </div>

            <!-- Panduan Pintasan Keyboard -->
            <div class="p-3 rounded-xl bg-slate-950/70 border border-slate-800 space-y-1.5">
                <p class="text-[11px] font-bold text-slate-300 flex items-center gap-1.5">
                    <i data-lucide="keyboard" class="w-3.5 h-3.5 text-amber-400"></i> Pintasan Keyboard Cepat
                </p>
                <div class="grid grid-cols-2 gap-y-1 text-[11px] text-slate-400 pt-1">
                    <span><kbd class="px-1.5 py-0.5 bg-slate-800 rounded text-slate-200">→</kbd> / <kbd class="px-1.5 py-0.5 bg-slate-800 rounded text-slate-200">Spasi</kbd></span>
                    <span>Slide Berikutnya</span>
                    <span><kbd class="px-1.5 py-0.5 bg-slate-800 rounded text-slate-200">←</kbd></span>
                    <span>Slide Sebelumnya</span>
                    <span><kbd class="px-1.5 py-0.5 bg-slate-800 rounded text-slate-200">C</kbd></span>
                    <span>Clear Text (Latar)</span>
                    <span><kbd class="px-1.5 py-0.5 bg-slate-800 rounded text-slate-200">B</kbd></span>
                    <span>Blackout Layar</span>
                    <span><kbd class="px-1.5 py-0.5 bg-slate-800 rounded text-slate-200">F</kbd></span>
                    <span>Mode Layar Penuh</span>
                </div>
            </div>
        </div>
    </aside>

    <!-- =====================================================================
         2. LAYAR PREVIEW / STAGE VIEW UTAMA (PROYEKSI JEMAAT)
         ===================================================================== -->
    <main id="stageWrapper" class="flex-1 h-[48vh] md:h-full relative flex flex-col bg-[#06080f] overflow-hidden">
        
        <!-- Toolbar Atas Stage (Sembunyi saat Fullscreen) -->
        <header id="stageTopBar" class="px-4 py-2.5 bg-[#0b0e17] border-b border-slate-800/90 flex items-center justify-between z-20">
            <div class="flex items-center gap-3">
                <span class="text-xs font-semibold text-slate-400 hidden sm:inline">Layar Proyeksi Utama</span>
                <span id="slideCounterBadge" class="px-2.5 py-0.5 rounded-full bg-slate-900 border border-slate-700 text-xs font-bold text-amber-400">
                    Slide 1 / 6
                </span>
            </div>

            <div class="flex items-center gap-2">
                <button onclick="enterFullscreenMode()" class="px-3.5 py-1.5 rounded-xl bg-amber-500 hover:bg-amber-400 text-slate-950 font-bold text-xs flex items-center gap-1.5 shadow-lg shadow-amber-500/20 transition-all active:scale-95">
                    <i data-lucide="maximize-2" class="w-3.5 h-3.5 stroke-[2.5]"></i>
                    <span>Fullscreen Mode (Proyektor)</span>
                </button>
            </div>
        </header>

        <!-- Kanvas Layar Proyeksi (Stage Area) -->
        <div id="projectionStage" class="flex-1 relative bg-theme-heavenly flex items-center justify-center p-6 sm:p-12 md:p-16 overflow-hidden transition-colors duration-700">
            
            <!-- Watermark Logo PMK NS di Pojok Kiri Atas Layar Proyeksi -->
            <div id="stageLogoBadge" class="absolute top-5 left-6 z-20 flex items-center gap-3 opacity-95 pointer-events-none transition-opacity duration-300">
                <div class="w-12 h-12 sm:w-14 sm:h-14 rounded-2xl bg-white/95 backdrop-blur-md border-2 border-amber-400 p-1 flex items-center justify-center shadow-xl shadow-black/50 overflow-hidden">
                    <img id="stageCustomLogoImg" src="" alt="Logo PMK NS" class="hidden w-full h-full object-contain">
                    <svg id="stageDefaultLogoSvg" viewBox="0 0 100 100" class="w-10 h-10 sm:w-12 sm:h-12" fill="none" xmlns="http://www.w3.org/2000/svg">
                        <circle cx="50" cy="50" r="46" fill="#FFFFFF" stroke="#D97706" stroke-width="4"/>
                        <circle cx="50" cy="50" r="35" fill="#EFF6FF" stroke="#1E3A8A" stroke-width="2"/>
                        <path id="topArcStage" d="M 14,50 A 36,36 0 1,1 86,50" fill="none"/>
                        <text font-size="6.8" font-weight="800" fill="#1E3A8A" letter-spacing="0.4">
                            <textPath href="#topArcStage" startOffset="50%" text-anchor="middle">PMK NAFIRI SION</textPath>
                        </text>
                        <path d="M31 28 H69 V50 C69 65 50 76 50 76 C50 76 31 65 31 50 Z" fill="#1D4ED8" stroke="#F59E0B" stroke-width="2.5"/>
                        <path d="M50 31 V68 M37 44 H63" stroke="#FACC15" stroke-width="5" stroke-linecap="round"/>
                        <path d="M35 60 L64 38 L67 43 L37 63 Z" fill="#FDE047"/>
                        <path d="M38 66 Q44 63 50 66 Q56 63 62 66 V72 Q56 69 50 72 Q44 69 38 72 Z" fill="#FFFFFF"/>
                    </svg>
                </div>
                <div class="text-left drop-shadow-md">
                    <p class="font-display font-extrabold text-xs sm:text-sm tracking-wider text-white uppercase">PMK Nafiri Sion</p>
                    <p class="text-[10px] sm:text-xs text-amber-300 font-semibold">Ibadah Persekutuan</p>
                </div>
            </div>

            <!-- Lapisan Animasi Partikel Cahaya Halus -->
            <div id="particlesLayer" class="absolute inset-0 pointer-events-none overflow-hidden">
                <div class="absolute top-1/4 left-1/4 w-72 h-72 md:w-96 md:h-96 bg-slate-700/15 rounded-full blur-3xl animate-glow-slow"></div>
                <div class="absolute bottom-1/4 right-1/4 w-80 h-80 md:w-[28rem] md:h-[28rem] bg-indigo-950/25 rounded-full blur-3xl animate-glow-delayed"></div>
                <canvas id="particleCanvas" class="w-full h-full opacity-55"></canvas>
            </div>

            <!-- Kontainer Teks Lirik Jemaat -->
            <div id="lyricDisplayContainer" class="relative z-10 w-full max-w-5xl text-center slide-fade">
                <p id="lyricTextDisplay" class="font-display font-extrabold text-white tracking-tight leading-snug sm:leading-snug md:leading-snug worship-text-shadow text-2xl sm:text-4xl md:text-5xl lg:text-6xl whitespace-pre-line">
                    Memuat lirik...
                </p>
            </div>

            <!-- Watermark Judul Lagu & Info Bait Halus di Pojok Bawah Stage -->
            <div id="stageFooterInfo" class="absolute bottom-4 left-6 right-6 flex items-center justify-between text-slate-400/60 text-xs font-medium pointer-events-none z-10">
                <div class="flex items-center gap-2">
                    <span class="w-2 h-2 rounded-full bg-amber-400/70"></span>
                    <span id="stageSongWatermark">Mujizat Itu Nyata</span>
                </div>
                <span class="hidden sm:inline text-slate-400/50 tracking-wider uppercase text-[10px] font-semibold">PMK Nafiri Sion</span>
                <span id="stageSectionWatermark">Bait 1</span>
            </div>

            <!-- Lapisan Blackout (Layar Hitam Pekat) -->
            <div id="blackoutOverlay" class="absolute inset-0 bg-black z-30 opacity-0 pointer-events-none transition-opacity duration-300 flex items-center justify-center">
                <span id="blackoutHint" class="text-slate-700 text-xs font-semibold tracking-widest uppercase">Layar Blackout Aktif</span>
            </div>

            <!-- Tombol Keluar & Petunjuk ESC saat Mode Fullscreen -->
            <div id="fullscreenControls" class="hidden fixed top-4 right-4 z-50 flex items-center gap-2 opacity-20 hover:opacity-100 transition-opacity duration-300">
                <span class="px-3 py-1.5 rounded-full bg-black/70 backdrop-blur-md text-white/80 text-xs border border-white/15">
                    Tekan <b>ESC</b> untuk keluar
                </span>
                <button onclick="exitFullscreenMode()" class="px-3.5 py-1.5 rounded-full bg-rose-600 hover:bg-rose-500 text-white font-bold text-xs flex items-center gap-1.5 shadow-lg">
                    <i data-lucide="minimize-2" class="w-3.5 h-3.5"></i>
                    <span>Keluar Layar Penuh</span>
                </button>
            </div>
        </div>

        <!-- Toolbar Navigasi Bawah Stage (Previous / Next Slide) -->
        <footer id="stageBottomBar" class="px-4 py-2.5 bg-[#0b0e17] border-t border-slate-800/90 flex items-center justify-between z-20">
            <button onclick="prevSlide()" id="btnPrevSlide" class="px-4 py-2 rounded-xl bg-slate-900 hover:bg-slate-800 disabled:opacity-40 disabled:pointer-events-none text-slate-200 font-semibold text-xs flex items-center gap-2 border border-slate-700/80 transition-all active:scale-95">
                <i data-lucide="chevron-left" class="w-4 h-4"></i>
                <span>Slide Sebelumnya</span>
            </button>

            <div class="hidden sm:flex items-center gap-1.5" id="slideDotsContainer">
                <!-- Indikator titik slide -->
            </div>

            <button onclick="nextSlide()" id="btnNextSlide" class="px-4 py-2 rounded-xl bg-slate-900 hover:bg-slate-800 disabled:opacity-40 disabled:pointer-events-none text-slate-200 font-semibold text-xs flex items-center gap-2 border border-slate-700/80 transition-all active:scale-95">
                <span>Slide Berikutnya</span>
                <i data-lucide="chevron-right" class="w-4 h-4"></i>
            </button>
        </footer>
    </main>

    <!-- =====================================================================
         3. MODAL TAMBAH / EDIT LAGU BARU
         ===================================================================== -->
    <div id="songModal" class="hidden fixed inset-0 z-50 bg-black/80 backdrop-blur-sm flex items-center justify-center p-4">
        <div class="bg-slate-900 border border-slate-700 rounded-2xl w-full max-w-lg shadow-2xl overflow-hidden flex flex-col max-h-[90vh]">
            <div class="px-5 py-4 bg-slate-950 border-b border-slate-800 flex items-center justify-between">
                <h3 id="modalTitle" class="font-display font-bold text-base text-white flex items-center gap-2">
                    <i data-lucide="music-2" class="w-4 h-4 text-amber-400"></i>
                    <span>Tambah Lagu Rohani Baru</span>
                </h3>
                <button onclick="closeSongModal()" class="text-slate-400 hover:text-white p-1 rounded-lg">
                    <i data-lucide="x" class="w-5 h-5"></i>
                </button>
            </div>

            <div class="p-5 space-y-4 overflow-y-auto">
                <div>
                    <label class="block text-xs font-bold text-slate-300 mb-1.5">Judul Lagu</label>
                    <input type="text" id="modalSongTitle" placeholder="Contoh: Mujizat Itu Nyata" class="w-full bg-slate-950 border border-slate-700 rounded-xl px-3.5 py-2.5 text-sm text-white placeholder-slate-500 focus:outline-none focus:border-amber-500">
                </div>

                <div>
                    <div class="flex items-center justify-between mb-1.5">
                        <label class="block text-xs font-bold text-slate-300">Lirik Lagu (Per Bait / Slide)</label>
                        <span class="text-[11px] text-amber-400 font-medium">Pisahkan tiap slide dengan 1 baris kosong</span>
                    </div>
                    <textarea id="modalSongLyrics" rows="10" placeholder="Tak terbatas kuasaMu Tuhan&#10;Semua dapat Kau lakukan&#10;Apa yang kelihatan mustahil bagiku&#10;Itu sangat mungkin bagiMu&#10;&#10;Di saat ku tak berdaya&#10;KuasaMu yang sempurna&#10;Ketika ku percaya&#10;Mujizat itu nyata" class="w-full bg-slate-950 border border-slate-700 rounded-xl p-3.5 text-sm text-white placeholder-slate-600 focus:outline-none focus:border-amber-500 leading-relaxed"></textarea>
                </div>

                <!-- Kotak Pesan Validasi (Pengganti alert) -->
                <div id="modalErrorBox" class="hidden p-3 rounded-xl bg-rose-500/10 border border-rose-500/30 text-rose-400 text-xs font-medium">
                    Judul lagu dan lirik tidak boleh kosong!
                </div>
            </div>

            <div class="px-5 py-3.5 bg-slate-950 border-t border-slate-800 flex justify-end gap-2.5">
                <button onclick="closeSongModal()" class="px-4 py-2 rounded-xl bg-slate-800 hover:bg-slate-700 text-slate-300 font-semibold text-xs transition-colors">
                    Batal
                </button>
                <button onclick="saveSongFromModal()" class="px-5 py-2 rounded-xl bg-amber-500 hover:bg-amber-400 text-slate-950 font-bold text-xs shadow-lg shadow-amber-500/20 transition-colors">
                    Simpan Lagu
                </button>
            </div>
        </div>
    </div>

    <!-- =====================================================================
         4. NOTIFIKASI TOAST HALUS (PENGGANTI ALERT)
         ===================================================================== -->
    <div id="toastNotification" class="fixed bottom-16 right-4 z-50 bg-slate-800 border border-slate-700 text-white px-4 py-2.5 rounded-xl shadow-2xl text-xs font-semibold flex items-center gap-2 opacity-0 pointer-events-none transition-all duration-300 transform translate-y-2">
        <i data-lucide="info" class="w-4 h-4 text-amber-400"></i>
        <span id="toastMessage">Pesan notifikasi</span>
    </div>

    <!-- =====================================================================
         5. LOGIKA JAVASCRIPT APLIKASI
         ===================================================================== -->
    <script>
        // --- DATA LAGU PRESET ROHANI POPULER INDONESIA ---
        const DEFAULT_SONGS = [
            {
                id: 'song-mujizat',
                title: 'Mujizat Itu Nyata',
                slides: [
                    "Tak terbatas kuasaMu Tuhan\nSemua dapat Kau lakukan\nApa yang kelihatan mustahil bagiku\nItu sangat mungkin bagiMu",
                    "Tak terbatas kuasaMu Tuhan\nSemua dapat Kau lakukan\nApa yang kelihatan mustahil bagiku\nItu sangat mungkin bagiMu",
                    "Di saat ku tak berdaya\nKuasaMu yang sempurna\nKetika ku percaya\nMujizat itu nyata",
                    "Bukan karna kekuatan\nNamun rohMu ya Tuhan\nKetika ku berdoa\nMujizat itu nyata",
                    "Di saat kutak berdaya\nKuasaMu yang sempurna\nKetika kupercaya\nMujizat itu nyata",
                    "Ketika kupercaya\nMujizat itu nyata\nKetika kuberdoa\nMujizat itu nyata"
                ]
            },
            {
                id: 'song-bahagia',
                title: 'Hari Ini Kurasa Bahagia',
                slides: [
                    "Hari ini kurasa bahagia\nBerkumpul bersama saudara seiman\nTuhan Yesus t'lah satukan kita\nTanpa memandang di antara kita",
                    "Bergandengan tangan dalam kasih\nDalam satu hati\nBerjalan dalam terang kasih Tuhan",
                    "Kau saudaraku, kau sahabatku\nTiada yang dapat memisahkan kita\nKau saudaraku, kau sahabatku\nTiada yang dapat memisahkan kita"
                ]
            },
            {
                id: 'song-sobatku',
                title: 'Ada Satu Sobatku Yang Setia',
                slides: [
                    "Ada satu sobatku yang setia\nTak pernah Dia tinggalkan diriku\nDi waktu aku susah, waktu ku sendirian\nDia selalu menemani diriku",
                    "Reff:\nNama-Nya Yesus, nama-Nya Yesus\nNama Yesus yang menghibur hatiku\nNama-Nya Yesus, nama-Nya Yesus\nNama Yesus yang menghibur hatiku"
                ]
            },
            {
                id: 'song-janjimu',
                title: 'Janji-Mu Seperti Fajar',
                slides: [
                    "Ketika kuhadapi kehidupan ini\nJalan mana yang harus kupilih\nKu tahu ku tak mampu, ku tahu ku tak sanggup\nHanya Kau, Tuhan, tempat jawabanku",
                    "Aku pun tahu ku tak pernah sendiri\nSebab Engkau Allah yang menggendongku\nTangan-Mu membelaiku, cinta-Mu memuaskanku\nKau mengangkatku ke tempat yang tinggi",
                    "Reff:\nJanji-Mu seperti fajar pagi hari\nDan tiada pernah terlambat bersinar\nCinta-Mu seperti sungai yang mengalir\nDan ku tahu betapa dalam kasih-Mu"
                ]
            },
            {
                id: 'song-sgala-puji',
                title: "S'gala Puji Syukur",
                slides: [
                    "S'gala puji syukur\nHanya bagi-Mu Tuhan\nSebab Kau yang layak dipuja",
                    "Kami mau bersorak\nTinggikan nama-Mu\nHaleluya\nSoraklah Haleluya\nSoraklah Haleluya\nHaleluya"
                ]
            },
            {
                id: 'song-doa-yabes',
                title: 'Doa Yabes (Kiranya Engkau Memberkati Aku)',
                slides: [
                    "Kiranya Engkau memberkati aku\nBerlimpah-limpah\nDan memperluas daerahku",
                    "Dan kiranya tangan-Mu menyertai aku\nDan melindungi aku dari pada malapetaka\nSehingga kesakitan tidak menimpa aku",
                    "Kupercaya Kau bekerja"
                ]
            },
            {
                id: 'song-1',
                title: 'Bapa Engkau Sungguh Baik',
                slides: [
                    "Bapa Engkau sungguh baik\nKasihMu melimpah di hidupku\nBapa ku berterima kasih\nBerkatMu hari ini\nYang Kau sediakan bagiku",
                    "Ku naikkan syukurku\nBuat hari yang Kau b'ri\nTak habis-habisnya\nKasih dan rahmatMu",
                    "S'lalu baru dan tak pernah\nTerlambat pertolonganMu\nBesar setiaMu\nDi s'panjang hidupku"
                ]
            },
            {
                id: 'song-2',
                title: "S'bab Kau Besar",
                slides: [
                    "Ku b'ri kemuliaan dan hormat\nKu angkat suara pujian\nKu agungkan namaMu",
                    "S'bab Kau besar\nPerbuatanMu ajaib\nTiada seperti Engkau\nTiada seperti Engkau",
                    "S'bab Kau besar\nPerbuatanMu ajaib\nTiada seperti Engkau\nTiada seperti Engkau"
                ]
            },
            {
                id: 'song-3',
                title: 'Kasih SetiaMu Yang Kurasakan',
                slides: [
                    "Kasih setiaMu yang kurasakan\nLebih tinggi dari langit biru\nKebaikanMu yang t'lah Kau nyatakan\nLebih dalam dari lautan",
                    "BerkatMu yang telah kuterima\nSempat membuatku terpesona\nApa yang tak pernah kupikirkan\nItu yang Kau sediakan bagiku",
                    "Siapakah aku ini Tuhan\nJadi biji mataMu\nDengan apakah kubalas Tuhan\nS'lain puji dan sembah Kau"
                ]
            },
            {
                id: 'song-4',
                title: 'Ku Kagum Hormat Akan Engkau',
                slides: [
                    "Kau sungguh indah tiada taranya\nSungguh menakjubkan\nSungguh ajaib 'tuk dimengerti\nLebih dari s'mua yang ada",
                    "HikmatMu tiada terselami\nKasihMu dalam tak terduga\nKau sungguh indah tiada taranya\nMulia dan berkuasa",
                    "Ku kagum hormat akan Engkau\nKu kagum hormat akan Engkau\nKau Allah yang layak dipuji\nKu kagum akan Engkau"
                ]
            }
        ];

        // --- STATE APLIKASI ---
        let songs = [];
        let activeSongId = 'song-mujizat';
        let activeSlideIndex = 0;
        let isClearText = false;
        let isBlackout = false;
        let isFullscreen = false;
        let modalMode = 'add'; // 'add' atau 'edit'
        let visualSettings = {
            theme: 'heavenly',
            particles: true,
            showStageLogo: true,
            fontSize: 'medium',
            textAlign: 'center'
        };

        // --- PENYIMPANAN & PEMUATAN LAGU ---
        function loadSongsFromStorage() {
            try {
                const saved = localStorage.getItem('worshipSlide_songs_v3');
                if (saved) {
                    const parsed = JSON.parse(saved);
                    if (Array.isArray(parsed) && parsed.length > 0) {
                        songs = parsed;
                        return;
                    }
                }
            } catch (e) {
                console.warn('Gagal memuat dari localStorage:', e);
            }
            songs = JSON.parse(JSON.stringify(DEFAULT_SONGS));
        }

        function saveSongsToStorage() {
            try {
                localStorage.setItem('worshipSlide_songs_v3', JSON.stringify(songs));
            } catch (e) {
                console.warn('Gagal menyimpan ke localStorage:', e);
            }
        }

        // --- NAVIGASI TAB SIDEBAR ---
        function switchSidebarTab(tab) {
            const tabSongs = document.getElementById('tabSongs');
            const tabVisual = document.getElementById('tabVisual');
            const panelSongs = document.getElementById('panelSongs');
            const panelVisual = document.getElementById('panelVisual');

            if (tab === 'songs') {
                tabSongs.className = 'flex-1 py-2 text-xs font-semibold rounded-t-lg border-b-2 border-amber-400 text-amber-300 bg-slate-900/80 transition-colors flex items-center justify-center gap-1.5';
                tabVisual.className = 'flex-1 py-2 text-xs font-semibold rounded-t-lg border-b-2 border-transparent text-slate-400 hover:text-slate-200 transition-colors flex items-center justify-center gap-1.5';
                panelSongs.classList.remove('hidden');
                panelVisual.classList.add('hidden');
            } else {
                tabVisual.className = 'flex-1 py-2 text-xs font-semibold rounded-t-lg border-b-2 border-amber-400 text-amber-300 bg-slate-900/80 transition-colors flex items-center justify-center gap-1.5';
                tabSongs.className = 'flex-1 py-2 text-xs font-semibold rounded-t-lg border-b-2 border-transparent text-slate-400 hover:text-slate-200 transition-colors flex items-center justify-center gap-1.5';
                panelVisual.classList.remove('hidden');
                panelSongs.classList.add('hidden');
            }
        }

        // --- RENDER DAFTAR LAGU & SLIDE ---
        function renderSongList() {
            const container = document.getElementById('songListContainer');
            const query = (document.getElementById('searchSongInput')?.value || '').toLowerCase().trim();
            const filtered = songs.filter(s => s.title.toLowerCase().includes(query));

            if (filtered.length === 0) {
                container.innerHTML = `<div class="text-center py-6 text-xs text-slate-500">Lagu tidak ditemukan</div>`;
                return;
            }

            container.innerHTML = filtered.map(song => {
                const isActive = song.id === activeSongId;
                return `
                    <button onclick="selectSong('${song.id}', 0)" class="w-full text-left px-3 py-2 rounded-xl text-xs transition-all flex items-center justify-between gap-2 ${
                        isActive
                            ? 'bg-amber-500/15 border border-amber-400/50 text-amber-300 font-bold shadow-sm'
                            : 'bg-slate-900/50 hover:bg-slate-800/70 border border-transparent text-slate-200 font-medium'
                    }">
                        <span class="truncate">${escapeHtml(song.title)}</span>
                        <span class="px-2 py-0.5 rounded-md text-[10px] shrink-0 ${
                            isActive ? 'bg-amber-400/20 text-amber-300' : 'bg-slate-800 text-slate-400'
                        }">${song.slides.length} slide</span>
                    </button>
                `;
            }).join('');
        }

        function selectSong(songId, slideIdx = 0) {
            const song = songs.find(s => s.id === songId) || songs[0];
            if (!song) return;

            activeSongId = song.id;
            activeSlideIndex = Math.max(0, Math.min(slideIdx, song.slides.length - 1));

            document.getElementById('activeSongTitle').textContent = song.title;
            renderSongList();
            renderSlidesGrid(song);
            updateStageProjection();
        }

        function renderSlidesGrid(song) {
            const container = document.getElementById('slidesGridContainer');
            container.innerHTML = song.slides.map((lyric, idx) => {
                const isCurrent = idx === activeSlideIndex;
                const isReff = lyric.trim().toLowerCase().startsWith('reff');
                const badgeLabel = isReff ? `REFF (SLIDE ${idx + 1})` : `BAIT ${idx + 1}`;

                return `
                    <div onclick="goToSlide(${idx})" class="p-3 rounded-xl border transition-all cursor-pointer ${
                        isCurrent
                            ? 'bg-amber-500/15 border-amber-400 shadow-md shadow-amber-500/10'
                            : 'bg-[#080a12] hover:bg-slate-900/80 border-slate-800/90'
                    }">
                        <div class="flex items-center justify-between mb-1.5">
                            <span class="px-2 py-0.5 rounded text-[10px] font-bold tracking-wider uppercase ${
                                isCurrent ? 'bg-amber-400 text-slate-950' : 'bg-slate-800 text-slate-300'
                            }">${badgeLabel}</span>
                            ${isCurrent ? '<span class="text-[11px] font-bold text-amber-400 flex items-center gap-1"><span class="w-1.5 h-1.5 rounded-full bg-amber-400"></span> Aktif</span>' : ''}
                        </div>
                        <p class="text-xs leading-relaxed whitespace-pre-line ${isCurrent ? 'text-white font-semibold' : 'text-slate-300'}">${escapeHtml(lyric)}</p>
                    </div>
                `;
            }).join('');
        }

        function goToSlide(index) {
            const song = songs.find(s => s.id === activeSongId);
            if (!song) return;
            activeSlideIndex = Math.max(0, Math.min(index, song.slides.length - 1));
            renderSlidesGrid(song);
            updateStageProjection();
        }

        function nextSlide() {
            const song = songs.find(s => s.id === activeSongId);
            if (!song) return;
            if (activeSlideIndex < song.slides.length - 1) {
                goToSlide(activeSlideIndex + 1);
            }
        }

        function prevSlide() {
            if (activeSlideIndex > 0) {
                goToSlide(activeSlideIndex - 1);
            }
        }

        function updateStageProjection() {
            const song = songs.find(s => s.id === activeSongId);
            if (!song) return;

            const total = song.slides.length;
            const currentText = song.slides[activeSlideIndex] || '';
            const lyricEl = document.getElementById('lyricTextDisplay');
            const containerEl = document.getElementById('lyricDisplayContainer');

            containerEl.style.opacity = '0';
            containerEl.style.transform = 'translateY(6px)';

            setTimeout(() => {
                lyricEl.textContent = currentText;
                if (!isClearText) {
                    containerEl.style.opacity = '1';
                    containerEl.style.transform = 'translateY(0)';
                }
            }, 100);

            document.getElementById('slideCounterBadge').textContent = `Slide ${activeSlideIndex + 1} / ${total}`;
            document.getElementById('stageSongWatermark').textContent = song.title;
            document.getElementById('stageSectionWatermark').textContent = `Bait ${activeSlideIndex + 1} dari ${total}`;

            document.getElementById('btnPrevSlide').disabled = activeSlideIndex === 0;
            document.getElementById('btnNextSlide').disabled = activeSlideIndex >= total - 1;

            // Update indikator titik di toolbar bawah
            const dotsContainer = document.getElementById('slideDotsContainer');
            dotsContainer.innerHTML = song.slides.map((_, i) => `
                <button onclick="goToSlide(${i})" class="h-2 rounded-full transition-all ${
                    i === activeSlideIndex ? 'w-6 bg-amber-400' : 'w-2 bg-slate-700 hover:bg-slate-500'
                }" title="Slide ${i + 1}"></button>
            `).join('');
        }

        // --- KONTROL CLEAR TEXT, BLACKOUT & FULLSCREEN ---
        function toggleClearText() {
            isClearText = !isClearText;
            const container = document.getElementById('lyricDisplayContainer');
            const btn = document.getElementById('btnClearText');

            if (isClearText) {
                container.style.opacity = '0';
                btn.classList.add('border-amber-400', 'bg-amber-500/20', 'text-amber-300');
                showToast('Teks disembunyikan (Hanya Latar)');
            } else {
                container.style.opacity = '1';
                btn.classList.remove('border-amber-400', 'bg-amber-500/20', 'text-amber-300');
                showToast('Teks lirik ditampilkan kembali');
            }
            updateLiveStatusBadge();
        }

        function toggleBlackout() {
            isBlackout = !isBlackout;
            const overlay = document.getElementById('blackoutOverlay');
            const btn = document.getElementById('btnBlackout');

            if (isBlackout) {
                overlay.classList.remove('opacity-0', 'pointer-events-none');
                overlay.classList.add('opacity-100');
                btn.classList.add('border-rose-500', 'bg-rose-500/20', 'text-rose-300');
                showToast('Layar Blackout Aktif');
            } else {
                overlay.classList.add('opacity-0', 'pointer-events-none');
                overlay.classList.remove('opacity-100');
                btn.classList.remove('border-rose-500', 'bg-rose-500/20', 'text-rose-300');
                showToast('Layar Proyeksi Aktif');
            }
            updateLiveStatusBadge();
        }

        function updateLiveStatusBadge() {
            const badge = document.getElementById('liveBadge');
            if (isBlackout) {
                badge.className = 'flex items-center gap-1.5 px-2.5 py-1 rounded-full bg-rose-500/15 border border-rose-500/40 text-rose-400 text-[11px] font-semibold shrink-0';
                badge.innerHTML = `<span class="w-2 h-2 rounded-full bg-rose-400"></span><span>BLACKOUT</span>`;
            } else if (isClearText) {
                badge.className = 'flex items-center gap-1.5 px-2.5 py-1 rounded-full bg-amber-500/15 border border-amber-500/40 text-amber-400 text-[11px] font-semibold shrink-0';
                badge.innerHTML = `<span class="w-2 h-2 rounded-full bg-amber-400"></span><span>CLEAR</span>`;
            } else {
                badge.className = 'flex items-center gap-1.5 px-2.5 py-1 rounded-full bg-emerald-500/10 border border-emerald-500/30 text-emerald-400 text-[11px] font-semibold shrink-0';
                badge.innerHTML = `<span class="w-2 h-2 rounded-full bg-emerald-400 animate-pulse"></span><span>TAYANG</span>`;
            }
        }

        function enterFullscreenMode() {
            isFullscreen = true;
            document.getElementById('operatorSidebar').classList.add('hidden');
            document.getElementById('stageTopBar').classList.add('hidden');
            document.getElementById('stageBottomBar').classList.add('hidden');
            document.getElementById('fullscreenControls').classList.remove('hidden');
            document.getElementById('stageWrapper').classList.remove('h-[48vh]');
            document.getElementById('stageWrapper').classList.add('h-screen', 'w-screen');

            if (document.documentElement.requestFullscreen) {
                document.documentElement.requestFullscreen().catch(() => {});
            }
            setTimeout(resizeCanvas, 100);
        }

        function exitFullscreenMode() {
            isFullscreen = false;
            document.getElementById('operatorSidebar').classList.remove('hidden');
            document.getElementById('stageTopBar').classList.remove('hidden');
            document.getElementById('stageBottomBar').classList.remove('hidden');
            document.getElementById('fullscreenControls').classList.add('hidden');
            document.getElementById('stageWrapper').classList.add('h-[48vh]');
            document.getElementById('stageWrapper').classList.remove('h-screen', 'w-screen');

            if (document.fullscreenElement && document.exitFullscreen) {
                document.exitFullscreen().catch(() => {});
            }
            setTimeout(resizeCanvas, 100);
        }

        document.addEventListener('fullscreenchange', () => {
            if (!document.fullscreenElement && isFullscreen) {
                exitFullscreenMode();
            }
        });

        // --- TEMA LATAR & PARTIKEL ---
        function setTheme(themeName) {
            visualSettings.theme = themeName;
            const stage = document.getElementById('projectionStage');
            stage.classList.remove('bg-theme-royal', 'bg-theme-heavenly', 'bg-theme-dawn', 'bg-theme-emerald', 'bg-theme-minimal');
            stage.classList.add(`bg-theme-${themeName}`);

            document.querySelectorAll('.theme-option').forEach(btn => {
                btn.classList.remove('border-amber-400', 'bg-slate-900');
                btn.classList.add('border-slate-800', 'bg-slate-900/50');
            });
            const activeBtn = document.getElementById(`themeBtn-${themeName}`);
            if (activeBtn) {
                activeBtn.classList.remove('border-slate-800', 'bg-slate-900/50');
                activeBtn.classList.add('border-amber-400', 'bg-slate-900');
            }
        }

        function toggleParticles() {
            visualSettings.particles = !visualSettings.particles;
            const layer = document.getElementById('particlesLayer');
            const btn = document.getElementById('toggleParticlesBtn');
            const dot = document.getElementById('toggleParticlesDot');

            if (visualSettings.particles) {
                layer.classList.remove('hidden');
                btn.classList.remove('bg-slate-700');
                btn.classList.add('bg-amber-500');
                dot.classList.add('translate-x-5');
            } else {
                layer.classList.add('hidden');
                btn.classList.add('bg-slate-700');
                btn.classList.remove('bg-amber-500');
                dot.classList.remove('translate-x-5');
            }
        }

        // --- KELOLA LOGO PMK NS (DEFAULT SVG & UNGGAH FILE KUSTOM) ---
        function applyLogoSource(imgSrc) {
            const headerImg = document.getElementById('customLogoImg');
            const headerSvg = document.getElementById('defaultLogoSvg');
            const stageImg = document.getElementById('stageCustomLogoImg');
            const stageSvg = document.getElementById('stageDefaultLogoSvg');

            if (imgSrc) {
                headerImg.src = imgSrc;
                stageImg.src = imgSrc;
                headerImg.classList.remove('hidden');
                stageImg.classList.remove('hidden');
                headerSvg.classList.add('hidden');
                stageSvg.classList.add('hidden');
            } else {
                headerImg.classList.add('hidden');
                stageImg.classList.add('hidden');
                headerSvg.classList.remove('hidden');
                stageSvg.classList.remove('hidden');
            }
        }

        function handleLogoUpload(event) {
            const file = event.target.files && event.target.files[0];
            if (!file) return;

            const reader = new FileReader();
            reader.onload = function(e) {
                const result = e.target.result;
                applyLogoSource(result);
                try {
                    localStorage.setItem('worshipSlide_customLogo', result);
                } catch (err) {
                    console.warn('Ukuran logo terlalu besar untuk penyimpanan lokal:', err);
                }
                showToast('Logo PMK NS berhasil dipasang');
            };
            reader.readAsDataURL(file);
        }

        function resetCustomLogo() {
            applyLogoSource(null);
            localStorage.removeItem('worshipSlide_customLogo');
            const input = document.getElementById('logoFileInput');
            if (input) input.value = '';
            showToast('Logo dikembalikan ke emblem bawaan');
        }

        function toggleStageLogo() {
            visualSettings.showStageLogo = !visualSettings.showStageLogo;
            const badge = document.getElementById('stageLogoBadge');
            const btn = document.getElementById('toggleStageLogoBtn');
            const dot = document.getElementById('toggleStageLogoDot');

            if (visualSettings.showStageLogo) {
                badge.classList.remove('hidden');
                btn.classList.remove('bg-slate-700');
                btn.classList.add('bg-amber-500');
                dot.classList.add('translate-x-5');
            } else {
                badge.classList.add('hidden');
                btn.classList.add('bg-slate-700');
                btn.classList.remove('bg-amber-500');
                dot.classList.remove('translate-x-5');
            }
        }

        function setFontSize(size) {
            visualSettings.fontSize = size;
            const lyricEl = document.getElementById('lyricTextDisplay');
            const label = document.getElementById('fontSizeLabel');

            lyricEl.classList.remove(
                'text-xl', 'sm:text-3xl', 'md:text-4xl', 'lg:text-5xl',
                'text-2xl', 'sm:text-4xl', 'md:text-5xl', 'lg:text-6xl',
                'text-3xl', 'sm:text-5xl', 'md:text-6xl', 'lg:text-7xl',
                'text-4xl', 'sm:text-6xl', 'md:text-7xl', 'lg:text-8xl'
            );

            const sizeMap = {
                small: { classes: ['text-xl', 'sm:text-3xl', 'md:text-4xl', 'lg:text-5xl'], text: 'Kecil' },
                medium: { classes: ['text-2xl', 'sm:text-4xl', 'md:text-5xl', 'lg:text-6xl'], text: 'Sedang (Standar)' },
                large: { classes: ['text-3xl', 'sm:text-5xl', 'md:text-6xl', 'lg:text-7xl'], text: 'Besar' },
                xlarge: { classes: ['text-4xl', 'sm:text-6xl', 'md:text-7xl', 'lg:text-8xl'], text: 'Ekstra Besar' }
            };

            lyricEl.classList.add(...sizeMap[size].classes);
            label.textContent = sizeMap[size].text;

            // Update tombol ukuran aktif
            document.querySelectorAll('.size-btn').forEach(b => {
                b.className = 'size-btn py-1.5 rounded-lg text-xs font-semibold bg-slate-900 border border-slate-700 text-slate-300 hover:bg-slate-800';
            });
            document.getElementById(`sizeBtn-${size}`).className = 'size-btn py-1.5 rounded-lg text-xs font-semibold bg-amber-500 text-slate-950 border border-amber-500';
        }

        function setTextAlign(align) {
            visualSettings.textAlign = align;
            const container = document.getElementById('lyricDisplayContainer');
            const btnCenter = document.getElementById('alignBtn-center');
            const btnLeft = document.getElementById('alignBtn-left');

            if (align === 'center') {
                container.classList.remove('text-left');
                container.classList.add('text-center');
                btnCenter.className = 'py-2 rounded-lg text-xs font-semibold bg-amber-500 text-slate-950 flex items-center justify-center gap-2';
                btnLeft.className = 'py-2 rounded-lg text-xs font-semibold bg-slate-900 text-slate-300 border border-slate-700 flex items-center justify-center gap-2';
            } else {
                container.classList.remove('text-center');
                container.classList.add('text-left');
                btnLeft.className = 'py-2 rounded-lg text-xs font-semibold bg-amber-500 text-slate-950 flex items-center justify-center gap-2';
                btnCenter.className = 'py-2 rounded-lg text-xs font-semibold bg-slate-900 text-slate-300 border border-slate-700 flex items-center justify-center gap-2';
            }
        }

        // --- MODAL TAMBAH / EDIT LAGU ---
        function openSongModal(mode) {
            modalMode = mode;
            const modal = document.getElementById('songModal');
            const titleEl = document.getElementById('modalTitle');
            const inputTitle = document.getElementById('modalSongTitle');
            const inputLyrics = document.getElementById('modalSongLyrics');
            document.getElementById('modalErrorBox').classList.add('hidden');

            if (mode === 'edit') {
                const currentSong = songs.find(s => s.id === activeSongId);
                if (!currentSong) return;
                titleEl.innerHTML = `<i data-lucide="edit-3" class="w-4 h-4 text-amber-400"></i><span>Edit Lagu: ${escapeHtml(currentSong.title)}</span>`;
                inputTitle.value = currentSong.title;
                inputLyrics.value = currentSong.slides.join('\n\n');
            } else {
                titleEl.innerHTML = `<i data-lucide="plus-circle" class="w-4 h-4 text-amber-400"></i><span>Tambah Lagu Rohani Baru</span>`;
                inputTitle.value = '';
                inputLyrics.value = '';
            }

            modal.classList.remove('hidden');
            lucide.createIcons();
            inputTitle.focus();
        }

        function closeSongModal() {
            document.getElementById('songModal').classList.add('hidden');
        }

        function saveSongFromModal() {
            const title = document.getElementById('modalSongTitle').value.trim();
            const rawLyrics = document.getElementById('modalSongLyrics').value.trim();
            const errorBox = document.getElementById('modalErrorBox');

            if (!title || !rawLyrics) {
                errorBox.classList.remove('hidden');
                return;
            }

            // Pisahkan lirik berdasarkan baris kosong (1 atau lebih baris kosong)
            const slidesArray = rawLyrics
                .split(/\n\s*\n/)
                .map(block => block.trim())
                .filter(block => block.length > 0);

            if (slidesArray.length === 0) {
                errorBox.classList.remove('hidden');
                return;
            }

            if (modalMode === 'edit') {
                const songIndex = songs.findIndex(s => s.id === activeSongId);
                if (songIndex !== -1) {
                    songs[songIndex].title = title;
                    songs[songIndex].slides = slidesArray;
                    saveSongsToStorage();
                    selectSong(activeSongId, 0);
                    showToast(`Lagu "${title}" berhasil diperbarui`);
                }
            } else {
                const newSong = {
                    id: 'song-' + Date.now(),
                    title: title,
                    slides: slidesArray
                };
                songs.unshift(newSong);
                saveSongsToStorage();
                selectSong(newSong.id, 0);
                showToast(`Lagu "${title}" ditambahkan ke daftar`);
            }

            closeSongModal();
        }

        function deleteCurrentSong() {
            if (songs.length <= 1) {
                showToast('Minimal harus tersisa 1 lagu dalam daftar');
                return;
            }
            const song = songs.find(s => s.id === activeSongId);
            if (!song) return;

            songs = songs.filter(s => s.id !== activeSongId);
            saveSongsToStorage();
            selectSong(songs[0].id, 0);
            showToast(`Lagu "${song.title}" dihapus`);
        }

        // --- KONTROL PINTASAN KEYBOARD (PANAH, SPASI, ESC, DLL) ---
        document.addEventListener('keydown', (e) => {
            // Abaikan pintasan jika sedang mengetik di input atau textarea
            const tag = e.target.tagName.toLowerCase();
            if (tag === 'input' || tag === 'textarea') return;

            if (e.key === 'ArrowRight' || e.key === ' ') {
                e.preventDefault();
                nextSlide();
            } else if (e.key === 'ArrowLeft') {
                e.preventDefault();
                prevSlide();
            } else if (e.key === 'Escape' && isFullscreen) {
                exitFullscreenMode();
            } else if (e.key.toLowerCase() === 'c') {
                toggleClearText();
            } else if (e.key.toLowerCase() === 'b') {
                toggleBlackout();
            } else if (e.key.toLowerCase() === 'f') {
                if (isFullscreen) exitFullscreenMode();
                else enterFullscreenMode();
            }
        });

        // --- ANIMASI PARTIKEL CAHAYA HALUS DI KANVAS STAGE ---
        let canvas, ctx, particles = [];

        function initParticleCanvas() {
            canvas = document.getElementById('particleCanvas');
            if (!canvas) return;
            ctx = canvas.getContext('2d');
            resizeCanvas();

            // Buat partikel debu cahaya lembut
            particles = [];
            for (let i = 0; i < 38; i++) {
                particles.push({
                    x: Math.random() * canvas.width,
                    y: Math.random() * canvas.height,
                    radius: Math.random() * 2.5 + 0.8,
                    speedX: (Math.random() - 0.5) * 0.35,
                    speedY: -Math.random() * 0.45 - 0.1,
                    alpha: Math.random() * 0.5 + 0.2
                });
            }
            animateParticles();
        }

        function resizeCanvas() {
            if (!canvas) return;
            const parent = canvas.parentElement;
            canvas.width = parent.clientWidth;
            canvas.height = parent.clientHeight;
        }

        window.addEventListener('resize', resizeCanvas);

        function animateParticles() {
            if (!ctx || !canvas) return;
            ctx.clearRect(0, 0, canvas.width, canvas.height);

            if (visualSettings.particles) {
                particles.forEach(p => {
                    p.x += p.speedX;
                    p.y += p.speedY;

                    if (p.y < -10) {
                        p.y = canvas.height + 10;
                        p.x = Math.random() * canvas.width;
                    }
                    if (p.x < -10) p.x = canvas.width + 10;
                    if (p.x > canvas.width + 10) p.x = -10;

                    ctx.beginPath();
                    ctx.arc(p.x, p.y, p.radius, 0, Math.PI * 2);
                    ctx.fillStyle = `rgba(255, 250, 230, ${p.alpha})`;
                    ctx.fill();
                });
            }
            requestAnimationFrame(animateParticles);
        }

        // --- HELPER: TOAST NOTIFICATION & ESCAPE HTML ---
        let toastTimeout;
        function showToast(msg) {
            const toast = document.getElementById('toastNotification');
            document.getElementById('toastMessage').textContent = msg;
            toast.classList.remove('opacity-0', 'translate-y-2');
            toast.classList.add('opacity-100', 'translate-y-0');

            clearTimeout(toastTimeout);
            toastTimeout = setTimeout(() => {
                toast.classList.add('opacity-0', 'translate-y-2');
                toast.classList.remove('opacity-100', 'translate-y-0');
            }, 2600);
        }

        function escapeHtml(text) {
            const div = document.createElement('div');
            div.textContent = text;
            return div.innerHTML;
        }

        // Inisialisasi aplikasi saat halaman dimuat
        window.addEventListener('DOMContentLoaded', () => {
            loadSongsFromStorage();
            const savedLogo = localStorage.getItem('worshipSlide_customLogo');
            if (savedLogo) {
                applyLogoSource(savedLogo);
            }
            selectSong(activeSongId, 0);
            initParticleCanvas();
            if (window.lucide) {
                lucide.createIcons();
            }
        });
    </script>
</body>
</html>
