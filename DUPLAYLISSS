<!doctype html>
<html lang="id" class="h-full">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>LISSS - Literasi Sehari Satu Soal</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <style>
        body { box-sizing: border-box; }
        * { font-family: 'Inter', -apple-system, sans-serif; }
        .hidden { display: none !important; }
        
        /* Loading Overlay */
        #loadingOverlay {
            position: fixed; top: 0; left: 0; width: 100%; height: 100%;
            background: rgba(0,0,0,0.7); z-index: 2000;
            display: flex; justify-content: center; align-items: center;
            backdrop-filter: blur(5px);
        }
        .spinner {
            width: 50px; height: 50px; border: 5px solid rgba(255,255,255,0.3);
            border-top: 5px solid #a855f7; border-radius: 50%;
            animation: spin 1s linear infinite;
        }
        @keyframes spin { 0% { transform: rotate(0deg); } 100% { transform: rotate(360deg); } }

        .toast {
            position: fixed; top: 20px; right: 20px;
            padding: 16px 24px; border-radius: 12px; color: white; font-weight: 600;
            z-index: 1000; animation: slideIn 0.3s ease;
            box-shadow: 0 10px 15px -3px rgba(0, 0, 0, 0.1);
        }
        .toast-success { background: #10b981; }
        .toast-error { background: #ef4444; }
        .toast-warning { background: #f59e0b; }
        
        @keyframes slideIn { from { transform: translateX(400px); opacity: 0; } to { transform: translateX(0); opacity: 1; } }
        
        .glass {
            background: rgba(255, 255, 255, 0.08);
            backdrop-filter: blur(12px);
            border: 1px solid rgba(255, 255, 255, 0.1);
        }
        
        .pulse { animation: pulse 2s infinite; }
        @keyframes pulse { 0%, 100% { opacity: 1; } 50% { opacity: 0.7; } }
        
        .card-3d { transform-style: preserve-3d; transition: transform 0.4s ease; }
        .card-3d:hover { transform: translateY(-5px) rotateX(2deg); }
        
        .hover-lift { transition: all 0.3s ease; }
        .hover-lift:hover { transform: translateY(-8px) scale(1.05); box-shadow: 0 20px 40px rgba(0,0,0,0.3); }
        
        .floating { animation: floating 3s ease-in-out infinite; }
        @keyframes floating { 0%, 100% { transform: translateY(0px); } 50% { transform: translateY(-10px); } }
        
        .confetti {
            position: fixed; width: 10px; height: 10px; pointer-events: none;
            animation: confetti-fall linear forwards; z-index: 9999;
        }
        @keyframes confetti-fall {
            to { transform: translateY(100vh) rotate(720deg); opacity: 0; }
        }
        
        .sparkle {
            position: fixed; font-size: 24px; pointer-events: none;
            animation: sparkle-float 1.5s ease-out forwards; z-index: 9999;
        }
        @keyframes sparkle-float {
            0% { transform: translateY(0) scale(0); opacity: 1; }
            50% { transform: translateY(-50px) scale(1.2); opacity: 1; }
            100% { transform: translateY(-100px) scale(0); opacity: 0; }
        }
        
        .btn-3d {
            box-shadow: 0 4px 15px rgba(0,0,0,0.3); transition: all 0.3s ease;
        }
        .btn-3d:hover { transform: translateY(-2px); box-shadow: 0 8px 25px rgba(0,0,0,0.4); }
        .btn-3d:active { transform: translateY(0); box-shadow: 0 2px 10px rgba(0,0,0,0.3); }
    </style>
</head>
<body class="h-full bg-gradient-to-br from-slate-900 via-purple-900 to-slate-900">
    <!-- Loading Screen -->
    <div id="loadingOverlay" class="hidden">
        <div class="text-center">
            <div class="spinner mx-auto mb-4"></div>
            <p class="text-white font-semibold">Memuat Data...</p>
        </div>
    </div>

    <div id="app" class="w-full h-full overflow-auto p-4 sm:p-8">
        <div class="max-w-4xl mx-auto">
            
            <!-- MENU UTAMA -->
            <div id="menuUtama">
                <div class="text-center mb-12">
                    <div class="text-6xl mb-4">📚</div>
                    <h1 class="text-5xl font-bold text-white mb-2">LISSS</h1>
                    <p class="text-xl text-purple-200">Literasi Sehari Satu Soal</p>
                    <p class="text-purple-300 mt-1">SMAN 2 Playen</p>
                </div>
                
                <div class="flex flex-col sm:flex-row gap-4 max-w-xl mx-auto mb-12">
                    <button onclick="showLogin('guru')" class="flex-1 glass hover:bg-white/10 text-white font-bold py-6 px-8 rounded-2xl transition-all flex items-center justify-center gap-3 btn-3d card-3d">
                        <span class="text-3xl">👨‍🏫</span> <span class="text-xl">GURU</span>
                    </button>
                    <button onclick="showLogin('siswa')" class="flex-1 glass hover:bg-white/10 text-white font-bold py-6 px-8 rounded-2xl transition-all flex items-center justify-center gap-3 btn-3d card-3d">
                        <span class="text-3xl">🎓</span> <span class="text-xl">SISWA</span>
                    </button>
                </div>

                <!-- Info Program -->
                <div class="glass rounded-2xl p-8 mb-8 card-3d">
                    <h2 class="text-3xl font-bold text-white mb-4 text-center bg-gradient-to-r from-purple-400 to-pink-400 bg-clip-text text-transparent">Program LISSS</h2>
                    <div class="w-24 h-1 bg-gradient-to-r from-purple-500 to-pink-500 mx-auto rounded-full mb-6"></div>
                    <p class="text-purple-100 mb-4 text-lg leading-relaxed"><span class="font-bold text-yellow-300">LISSS (Literasi Sehari Satu Soal)</span> adalah program literasi yang dirancang khusus untuk meningkatkan kemampuan literasi siswa <span class="font-semibold text-cyan-300">SMAN 2 Playen</span>.</p>
                    <p class="text-purple-100 mb-6 leading-relaxed">Website ini bertujuan melatih siswa agar lebih terbiasa mengerjakan soal berbasis literasi yang akan meningkatkan hasil mereka, terutama pada <span class="font-bold text-green-300">Tes Kemampuan Akademik (TKA)</span>.</p>
                    <div class="grid grid-cols-1 sm:grid-cols-3 gap-4 mb-6">
                        <div class="glass rounded-xl p-5 text-center border border-purple-400/30 hover:border-purple-400/60 transition-all hover:scale-105 hover-lift">
                            <div class="text-4xl mb-2 floating">📖</div>
                            <p class="text-white font-bold mb-1">Soal Harian</p>
                            <p class="text-purple-200 text-xs">Satu soal setiap hari untuk konsistensi belajar</p>
                        </div>
                        <div class="glass rounded-xl p-5 text-center border border-orange-400/30 hover:border-orange-400/60 transition-all hover:scale-105 hover-lift">
                            <div class="text-4xl mb-2 floating" style="animation-delay: 0.2s">🔥</div>
                            <p class="text-white font-bold mb-1">Sistem Streak</p>
                            <p class="text-purple-200 text-xs">Bonus poin untuk belajar rutin setiap hari</p>
                        </div>
                        <div class="glass rounded-xl p-5 text-center border border-blue-400/30 hover:border-blue-400/60 transition-all hover:scale-105 hover-lift">
                            <div class="text-4xl mb-2 floating" style="animation-delay: 0.4s">🏆</div>
                            <p class="text-white font-bold mb-1">Peringkat</p>
                            <p class="text-purple-200 text-xs">Kompetisi sehat antar siswa setiap bulan</p>
                        </div>
                    </div>
                    <div class="glass rounded-xl p-4 border border-yellow-400/30">
                        <p class="text-center text-sm italic text-yellow-200">💡 "Membaca adalah jendela dunia, dan literasi adalah kunci kesuksesan akademik"</p>
                    </div>
                </div>

                <!-- Papan Info -->
                <div id="papanInfo" class="hidden glass rounded-2xl p-6">
                    <h3 class="text-xl font-bold text-white mb-4">📢 Informasi</h3>
                    <div id="isiInfo" class="text-purple-100"></div>
                </div>
            </div>

            <!-- LOGIN GURU -->
            <div id="loginGuru" class="hidden max-w-md mx-auto">
                <div class="glass rounded-2xl p-8">
                    <div class="text-center mb-6">
                        <div class="text-5xl mb-3">👨‍🏫</div>
                        <h2 class="text-2xl font-bold text-white">Login Guru</h2>
                    </div>
                    <input type="password" id="passGuru" placeholder="Password" class="w-full px-4 py-3 rounded-xl glass text-white mb-4 focus:outline-none focus:ring-2 focus:ring-purple-500">
                    <div class="flex gap-3">
                        <button onclick="backToMenu()" class="flex-1 bg-gray-600 hover:bg-gray-700 text-white font-bold py-3 rounded-xl">Kembali</button>
                        <button onclick="loginGuru()" class="flex-1 bg-purple-600 hover:bg-purple-700 text-white font-bold py-3 rounded-xl">Masuk</button>
                    </div>
                </div>
            </div>

            <!-- LOGIN SISWA -->
            <div id="loginSiswa" class="hidden max-w-md mx-auto">
                <div class="glass rounded-2xl p-8">
                    <div class="text-center mb-6">
                        <div class="text-5xl mb-3">🎓</div>
                        <h2 class="text-2xl font-bold text-white">Login Siswa</h2>
                    </div>
                    <input type="text" id="namaSiswa" placeholder="Nama Lengkap" class="w-full px-4 py-3 rounded-xl glass text-white mb-4 focus:outline-none focus:ring-2 focus:ring-blue-500">
                    <div class="flex gap-3">
                        <button onclick="backToMenu()" class="flex-1 bg-gray-600 hover:bg-gray-700 text-white font-bold py-3 rounded-xl">Kembali</button>
                        <button onclick="loginSiswa()" class="flex-1 bg-blue-600 hover:bg-blue-700 text-white font-bold py-3 rounded-xl">Masuk</button>
                    </div>
                </div>
            </div>

            <!-- DASHBOARD GURU -->
            <div id="dashboardGuru" class="hidden">
                <div class="flex justify-between items-center mb-6">
                    <h2 class="text-2xl font-bold text-white">Dashboard Guru</h2>
                    <button onclick="logoutGuru()" class="bg-red-600 hover:bg-red-700 text-white px-4 py-2 rounded-xl">Keluar</button>
                </div>
                <!-- Tab -->
                <div class="flex gap-2 mb-6">
                    <button id="tabSoal" onclick="switchTab('soal')" class="px-6 py-3 rounded-xl bg-purple-600 text-white font-semibold">Soal</button>
                    <button id="tabInfo" onclick="switchTab('info')" class="px-6 py-3 rounded-xl glass text-purple-200 font-semibold">Info</button>
                    <button id="tabRiwayat" onclick="switchTab('riwayat')" class="px-6 py-3 rounded-xl glass text-purple-200 font-semibold">Riwayat</button>
                </div>

                <!-- Content Soal -->
                <div id="contentSoal">
                    <div class="glass rounded-2xl p-6 mb-6 card-3d">
                        <h3 class="text-xl font-bold text-white mb-4">✏️ Buat Soal</h3>
                        <div class="space-y-4">
                            <input type="date" id="tanggal" class="w-full px-4 py-3 rounded-xl glass text-white">
                            <!-- Upload Gambar Soal -->
                            <div>
                                <label class="text-purple-200 text-sm mb-1 block">🖼️ URL Gambar Soal (Opsional)</label>
                                <input type="text" id="gambarURL" placeholder="Paste URL gambar (Disarankan pakai Google Photos/Imgur)" class="w-full px-4 py-3 rounded-xl glass text-white">
                            </div>
                            <textarea id="soal" rows="3" placeholder="Pertanyaan" class="w-full px-4 py-3 rounded-xl glass text-white resize-none"></textarea>
                            <input id="opsiA" placeholder="Opsi A" class="w-full px-4 py-3 rounded-xl glass text-white">
                            <input id="opsiB" placeholder="Opsi B" class="w-full px-4 py-3 rounded-xl glass text-white">
                            <input id="opsiC" placeholder="Opsi C" class="w-full px-4 py-3 rounded-xl glass text-white">
                            <input id="opsiD" placeholder="Opsi D" class="w-full px-4 py-3 rounded-xl glass text-white">
                            <input id="opsiE" placeholder="Opsi E" class="w-full px-4 py-3 rounded-xl glass text-white">
                            <input id="kunci" placeholder="Kunci (A-E)" maxlength="1" class="w-full px-4 py-3 rounded-xl glass text-white">
                            <textarea id="pembahasan" rows="2" placeholder="Pembahasan" class="w-full px-4 py-3 rounded-xl glass text-white resize-none"></textarea>
                            <div class="flex gap-3">
                                <button onclick="simpanSoal()" class="flex-1 bg-green-600 hover:bg-green-700 text-white font-bold py-3 rounded-xl btn-3d">✅ Simpan & Publikasi</button>
                            </div>
                        </div>
                    </div>
                </div>

                <!-- Content Info -->
                <div id="contentInfo" class="hidden">
                    <div class="glass rounded-2xl p-6">
                        <h3 class="text-xl font-bold text-white mb-4">📢 Kelola Informasi</h3>
                        <input id="judulInfo" placeholder="Judul" class="w-full px-4 py-3 rounded-xl glass text-white mb-4">
                        <textarea id="isiInfoInput" rows="5" placeholder="Isi informasi" class="w-full px-4 py-3 rounded-xl glass text-white resize-none mb-4"></textarea>
                        <div class="flex gap-3">
                            <button onclick="simpanInfo()" class="flex-1 bg-blue-600 hover:bg-blue-700 text-white font-bold py-3 rounded-xl">Simpan</button>
                            <button onclick="hapusInfo()" class="bg-red-600 hover:bg-red-700 text-white font-bold py-3 px-6 rounded-xl">Hapus</button>
                        </div>
                    </div>
                </div>

                <!-- Content Riwayat -->
                <div id="contentRiwayat" class="hidden">
                    <div class="glass rounded-2xl p-6 mb-6 card-3d">
                        <h3 class="text-xl font-bold text-white mb-4">🏆 Top 10 Peringkat</h3>
                        <div id="peringkat" class="space-y-2"></div>
                    </div>
                    <div class="glass rounded-2xl p-6 card-3d">
                        <div class="flex justify-between items-center mb-4">
                            <h3 class="text-xl font-bold text-white">📊 Riwayat Pengerjaan</h3>
                            <a href="https://docs.google.com/spreadsheets/d/194pXd1xeEYu8RoWglDnvEMgQRSusLyJlX5VldbZprj0/edit?usp=drivesdk" target="_blank" class="bg-blue-600 hover:bg-blue-700 text-white px-4 py-2 rounded-xl text-sm font-semibold btn-3d flex items-center gap-2">
                                <span>📥</span> Buka Spreadsheet
                            </a>
                        </div>
                        <div class="overflow-x-auto">
                            <table class="w-full text-sm">
                                <thead class="text-purple-200 border-b border-white/20">
                                    <tr>
                                        <th class="py-2 text-left">Nama</th>
                                        <th class="py-2 text-left">Tanggal</th>
                                        <th class="py-2 text-center">Jawaban</th>
                                        <th class="py-2 text-center">Nilai</th>
                                        <th class="py-2 text-center">Poin</th>
                                    </tr>
                                </thead>
                                <tbody id="riwayat" class="text-white"></tbody>
                            </table>
                        </div>
                        <button onclick="loadRiwayatGuru()" class="mt-4 w-full bg-gray-600 hover:bg-gray-700 text-white py-2 rounded-xl">🔄 Refresh Data</button>
                    </div>
                </div>
            </div>

            <!-- HALAMAN SISWA -->
            <div id="halamanSiswa" class="hidden max-w-2xl mx-auto">
                <button onclick="backToMenu()" class="mb-4 glass text-white px-4 py-2 rounded-xl">← Kembali</button>
                
                <!-- Menu Siswa -->
                <div id="menuSiswa" class="glass rounded-2xl p-8">
                    <div class="text-center mb-6">
                        <div class="text-5xl mb-3">👨‍🎓</div>
                        <h2 id="namaSiswaDisplay" class="text-2xl font-bold text-white mb-4"></h2>
                    </div>
                    <div class="flex flex-col gap-3">
                        <button onclick="lihatDashboard()" class="w-full bg-purple-600 hover:bg-purple-700 text-white font-bold py-4 rounded-xl">📊 Dashboard</button>
                        <button onclick="mulaiKuis()" class="w-full bg-blue-600 hover:bg-blue-700 text-white font-bold py-4 rounded-xl">🎯 Kuis Hari Ini</button>
                    </div>
                </div>

                <!-- Dashboard Siswa -->
                <div id="dashboardSiswa" class="hidden glass rounded-2xl p-8">
                    <button onclick="backToMenuSiswa()" class="mb-4 text-purple-300 hover:text-white">← Kembali</button>
                    <h3 class="text-2xl font-bold text-white mb-6 text-center">Dashboard</h3>
                    <div class="grid grid-cols-3 gap-3 mb-6">
                        <div class="glass rounded-xl p-4 text-center">
                            <p id="dashPoin" class="text-2xl font-bold text-yellow-400">0</p>
                            <p class="text-purple-200 text-xs">Poin</p>
                        </div>
                        <div class="glass rounded-xl p-4 text-center">
                            <p id="dashStreak" class="text-2xl font-bold text-orange-400">0🔥</p>
                            <p class="text-purple-200 text-xs">Streak</p>
                        </div>
                        <div class="glass rounded-xl p-4 text-center">
                            <p id="dashRank" class="text-2xl font-bold text-blue-400">-</p>
                            <p class="text-purple-200 text-xs">Rank</p>
                        </div>
                    </div>
                    <div class="glass rounded-xl p-5 mb-6">
                        <h4 class="text-white font-bold mb-3">📈 Riwayat Terakhir</h4>
                        <div id="riwayatSiswa" class="space-y-2 max-h-64 overflow-y-auto"></div>
                    </div>
                    <div class="glass rounded-xl p-5">
                        <h4 class="text-white font-bold mb-3">🏆 Top 5</h4>
                        <div id="top5" class="space-y-2"></div>
                    </div>
                </div>

                <!-- Kuis Area -->
                <div id="kuisArea" class="hidden glass rounded-2xl p-8">
                    <div class="text-center mb-6">
                        <div class="inline-block px-6 py-3 rounded-full bg-red-500/20 border border-red-400">
                            <span id="timer" class="text-2xl font-bold text-red-300">03:00</span>
                        </div>
                    </div>
                    <div id="soalImageContainer" class="mb-4 hidden text-center"></div>
                    <p id="soalText" class="text-white text-lg mb-6"></p>
                    <div id="opsiContainer" class="space-y-3 mb-6"></div>
                    <button onclick="kirimJawaban()" class="w-full bg-green-600 hover:bg-green-700 text-white font-bold py-4 rounded-xl">Kirim Jawaban</button>
                </div>

                <!-- Hasil -->
                <div id="hasilArea" class="hidden glass rounded-2xl p-8 text-center">
                    <div class="text-6xl mb-4">🎉</div>
                    <h3 class="text-2xl font-bold text-white mb-4">Hasil Kuis</h3>
                    <div id="hasilContent"></div>
                    <button onclick="backToMenu()" class="mt-6 w-full bg-purple-600 hover:bg-purple-700 text-white font-bold py-3 rounded-xl">Kembali</button>
                </div>
            </div>
        </div>
    </div>

    <script>
        // ==========================================
        // KONFIGURASI PENTING
        // ==========================================
        // GANTI URL DI BAWAH INI DENGAN URL DEPLOYMENT GOOGLE APPS SCRIPT ANDA
        const APPS_SCRIPT_URL = '[URL_APPS_SCRIPT_ANDA_DISINI](https://script.google.com/macros/s/AKfycbzkfmzuGaGasA9oDqTSYmi5zrQFZt0m1dpvStxXLU6tU1VnXCh4Y4kvuNhmnIEQezGojA/exec)'; 

        // ==========================================
        // STATE & UTILITIES
        // ==========================================
        let currentUser = '';
        let currentRole = '';
        let soalAktif = null;
        let jawabanPilihan = '';
        let waktu = 180;
        let timer = null;
        let pollingInterval = null;

        function showLoading(show) {
            const el = document.getElementById('loadingOverlay');
            if(show) el.classList.remove('hidden');
            else el.classList.add('hidden');
        }

        function showToast(msg, type = 'success') {
            const toast = document.createElement('div');
            toast.className = `toast toast-${type}`;
            toast.textContent = msg;
            document.body.appendChild(toast);
            setTimeout(() => toast.remove(), 3000);
        }

        function formatTanggal(tgl) {
            const d = new Date(tgl);
            return d.toLocaleDateString('id-ID', { day: 'numeric', month: 'long', year: 'numeric' });
        }

        function hide(...ids) { ids.forEach(id => document.getElementById(id).classList.add('hidden')); }
        function show(...ids) { ids.forEach(id => document.getElementById(id).classList.remove('hidden')); }

        // Helper untuk fetch ke Google Apps Script
        async function fetchData(action, params = {}, method = 'GET') {
            showLoading(true);
            try {
                let url = `${APPS_SCRIPT_URL}?action=${action}`;
                if (method === 'GET') {
                    Object.keys(params).forEach(key => url += `&${key}=${encodeURIComponent(params[key])}`);
                }

                const options = {
                    method: method,
                    redirect: 'follow' // Penting untuk Google Apps Script
                };

                if (method === 'POST') {
                    // Menggunakan mode no-cors tidak memungkinkan membaca response JSON
                    // Kita gunakan POST standar dan harap server mengizinkan CORS (Apps Script "Anyone" access)
                    options.body = JSON.stringify(params);
                    // Note: Apps Script doPost kadang butuh header khusus jika kita ingin baca response JSON
                    // Namun untuk kasus simple 'Anyone', fetch biasanya bekerja.
                }

                const response = await fetch(url, options);
                const result = await response.json();
                showLoading(false);
                return result;
            } catch (error) {
                showLoading(false);
                console.error(error);
                showToast('Gagal terhubung ke server. Cek koneksi internet.', 'error');
                return { status: 'error' };
            }
        }

        // Animasi
        function createConfetti() {
            const colors = ['#fbbf24', '#f59e0b', '#3b82f6', '#8b5cf6', '#ec4899', '#10b981'];
            for (let i = 0; i < 50; i++) {
                setTimeout(() => {
                    const confetti = document.createElement('div');
                    confetti.className = 'confetti';
                    confetti.style.left = Math.random() * 100 + '%';
                    confetti.style.backgroundColor = colors[Math.floor(Math.random() * colors.length)];
                    confetti.style.animationDuration = (Math.random() * 2 + 2) + 's';
                    document.body.appendChild(confetti);
                    setTimeout(() => confetti.remove(), 4000);
                }, i * 30);
            }
        }

        // ==========================================
        // NAVIGATION
        // ==========================================
        function showLogin(role) {
            hide('menuUtama');
            show(role === 'guru' ? 'loginGuru' : 'loginSiswa');
        }

        function backToMenu() {
            hide('loginGuru', 'loginSiswa', 'dashboardGuru', 'halamanSiswa');
            show('menuUtama');
            if (timer) clearInterval(timer);
            if (pollingInterval) clearInterval(pollingInterval);
            loadInfo();
        }

        function backToMenuSiswa() {
            hide('dashboardSiswa', 'kuisArea', 'hasilArea');
            show('menuSiswa');
            if (timer) clearInterval(timer);
        }

        // ==========================================
        // AUTHENTICATION
        // ==========================================
        function loginGuru() {
            const pass = document.getElementById('passGuru').value;
            if (pass === 'nilaiistimewa') {
                hide('loginGuru');
                show('dashboardGuru');
                currentRole = 'guru';
                switchTab('soal');
                showToast('Selamat datang, Guru!');
            } else {
                showToast('Password salah!', 'error');
            }
        }

        function loginSiswa() {
            const nama = document.getElementById('namaSiswa').value.trim();
            if (!nama) {
                showToast('Masukkan nama!', 'warning');
                return;
            }
            currentUser = nama;
            currentRole = 'siswa';
            hide('loginSiswa');
            show('halamanSiswa', 'menuSiswa');
            document.getElementById('namaSiswaDisplay').textContent = nama;
            showToast(`Halo, ${nama}!`);
        }

        function logoutGuru() {
            hide('dashboardGuru');
            show('menuUtama');
            document.getElementById('passGuru').value = '';
        }

        // ==========================================
        // GURU FUNCTIONS
        // ==========================================
        function switchTab(tab) {
            document.querySelectorAll('[id^="tab"]').forEach(el => {
                if (el.id.startsWith('tab') && ['Soal','Info','Riwayat'].some(t => el.id.includes(t))) {
                    el.className = 'px-6 py-3 rounded-xl glass text-purple-200 font-semibold';
                }
            });
            
            // Highlight active tab
            const activeTab = document.getElementById('tab' + tab.charAt(0).toUpperCase() + tab.slice(1));
            if(activeTab) activeTab.className = 'px-6 py-3 rounded-xl bg-purple-600 text-white font-semibold';

            hide('contentSoal', 'contentInfo', 'contentRiwayat');
            show('content' + tab.charAt(0).toUpperCase() + tab.slice(1));
            
            if (tab === 'info') loadInfoForm();
            if (tab === 'riwayat') loadRiwayatGuru();
        }

        async function simpanSoal() {
            const tanggal = document.getElementById('tanggal').value;
            const soalText = document.getElementById('soal').value;
            const A = document.getElementById('opsiA').value;
            const B = document.getElementById('opsiB').value;
            const kunci = document.getElementById('kunci').value.toUpperCase();

            if (!tanggal || !soalText || !A || !B || !kunci) {
                showToast('Lengkapi minimal tanggal, soal, opsi A-B, dan kunci!', 'warning');
                return;
            }

            if (!['A','B','C','D','E'].includes(kunci)) {
                showToast('Kunci harus A-E!', 'warning');
                return;
            }

            const payload = {
                tanggal: tanggal,
                soal: soalText,
                gambar: document.getElementById('gambarURL').value,
                opsi: {
                    A: A, B: B, 
                    C: document.getElementById('opsiC').value,
                    D: document.getElementById('opsiD').value,
                    E: document.getElementById('opsiE').value
                },
                kunci: kunci,
                pembahasan: document.getElementById('pembahasan').value
            };

            // Menggunakan fetch POST
            showLoading(true);
            try {
                const response = await fetch(`${APPS_SCRIPT_URL}?action=saveSoal`, {
                    method: 'POST',
                    body: JSON.stringify(payload)
                });
                const result = await response.json();
                showLoading(false);
                
                if (result.status === 'success') {
                    showToast('Soal berhasil dipublikasikan! 🎉');
                } else {
                    showToast('Gagal menyimpan soal', 'error');
                }
            } catch (e) {
                showLoading(false);
                showToast('Terjadi kesalahan jaringan', 'error');
            }
        }

        async function simpanInfo() {
            const judul = document.getElementById('judulInfo').value.trim();
            const isi = document.getElementById('isiInfoInput').value.trim();
            if (!judul || !isi) return showToast('Lengkapi judul dan isi!', 'warning');

            const res = await fetchData('saveInfo', { judul, isi }, 'POST');
            if (res.status === 'success') {
                showToast('Informasi disimpan!');
                loadInfo();
            }
        }

        async function hapusInfo() {
            document.getElementById('judulInfo').value = '';
            document.getElementById('isiInfoInput').value = '';
            const res = await fetchData('saveInfo', { judul: '', isi: '' }, 'POST');
            if (res.status === 'success') {
                showToast('Informasi dihapus!');
                loadInfo();
            }
        }

        async function loadInfoForm() {
            const res = await fetchData('getInfo');
            if (res.status === 'success') {
                document.getElementById('judulInfo').value = res.judul;
                document.getElementById('isiInfoInput').value = res.isi;
            }
        }

        async function loadRiwayatGuru() {
            // Load Leaderboard
            const resRank = await fetchData('getLeaderboard');
            const peringkatDiv = document.getElementById('peringkat');
            
            if (resRank.status === 'success' && resRank.data.length > 0) {
                peringkatDiv.innerHTML = resRank.data.slice(0, 10).map((s, i) => {
                    const medal = ['🥇','🥈','🥉'][i] || `#${i+1}`;
                    return `
                        <div class="glass rounded-xl p-3 flex items-center gap-3 hover-lift">
                            <span class="text-2xl w-10 text-center">${medal}</span>
                            <div class="flex-1">
                                <p class="text-white font-bold">${s.nama}</p>
                                <p class="text-purple-300 text-xs">Streak: ${s.streak}🔥</p>
                            </div>
                            <p class="text-yellow-400 font-bold text-xl">${s.poin}</p>
                        </div>
                    `;
                }).join('');
            } else {
                peringkatDiv.innerHTML = '<p class="text-center text-purple-200 py-4">Belum ada data</p>';
            }

            // Load History Table
            const resHist = await fetchData('getHistory');
            const tbody = document.getElementById('riwayat');
            if (resHist.status === 'success' && resHist.data.length > 0) {
                tbody.innerHTML = resHist.data.map(r => `
                    <tr class="border-b border-white/10 hover:bg-white/5">
                        <td class="py-2">${r.nama}</td>
                        <td class="py-2 text-xs">${formatTanggal(r.tanggal)}</td>
                        <td class="py-2 text-center">${r.jawaban}</td>
                        <td class="py-2 text-center ${r.nilai === 100 ? 'text-green-400' : 'text-red-400'} font-bold">${r.nilai}</td>
                        <td class="py-2 text-center text-yellow-400 font-bold">${r.poin}</td>
                    </tr>
                `).join('');
            } else {
                tbody.innerHTML = '<tr><td colspan="5" class="text-center py-4 text-purple-200">Belum ada data</td></tr>';
            }
        }

        // ==========================================
        // SISWA FUNCTIONS
        // ==========================================
        async function lihatDashboard() {
            hide('menuSiswa');
            show('dashboardSiswa');
            
            const res = await fetchData('getLeaderboard');
            if (res.status === 'success') {
                const list = res.data;
                // Cari profil siswa sendiri
                const myData = list.find(s => s.nama === currentUser) || { poin: 0, streak: 0 };
                
                document.getElementById('dashPoin').textContent = myData.poin;
                document.getElementById('dashStreak').textContent = myData.streak + '🔥';
                
                const rank = list.findIndex(s => s.nama === currentUser) + 1;
                document.getElementById('dashRank').textContent = rank > 0 ? `#${rank}` : '-';

                // Top 5
                const top5Div = document.getElementById('top5');
                top5Div.innerHTML = list.slice(0, 5).map((s, i) => {
                    const medal = ['🥇','🥈','🥉'][i] || `#${i+1}`;
                    const isSelf = s.nama === currentUser;
                    return `
                        <div class="flex items-center gap-3 p-2 rounded-xl ${isSelf ? 'bg-blue-500/20' : 'bg-white/5'}">
                            <span class="text-xl w-8">${medal}</span>
                            <p class="flex-1 text-white text-sm ${isSelf ? 'font-bold' : ''}">${s.nama}</p>
                            <p class="text-yellow-400 font-bold">${s.poin}</p>
                        </div>
                    `;
                }).join('');
            }

            // History Siswa
            const resHist = await fetchData('getHistory');
            if (resHist.status === 'success') {
                const myHistory = resHist.data.filter(r => r.nama === currentUser);
                const riwayatDiv = document.getElementById('riwayatSiswa');
                if (myHistory.length === 0) {
                    riwayatDiv.innerHTML = '<p class="text-purple-200 text-center py-4 text-sm">Belum ada riwayat</p>';
                } else {
                    riwayatDiv.innerHTML = myHistory.slice(0, 10).map(r => `
                        <div class="flex justify-between items-center border-b border-white/10 pb-2">
                            <div>
                                <p class="text-white text-sm">${formatTanggal(r.tanggal)}</p>
                                <p class="text-purple-300 text-xs">Jawaban: ${r.jawaban}</p>
                            </div>
                            <div class="text-right">
                                <p class="${r.nilai === 100 ? 'text-green-400' : 'text-red-400'} font-bold">${r.nilai}</p>
                                <p class="text-yellow-400 text-xs">+${r.poin}</p>
                            </div>
                        </div>
                    `).join('');
                }
            }
        }

        async function mulaiKuis() {
            const today = new Date().toISOString().slice(0, 10);
            const res = await fetchData('getSoal', { date: today });

            if (res.status === 'not_found') {
                showToast('Belum ada soal hari ini!', 'error');
                return;
            }
            if (res.status === 'error') return;

            const soal = res.data;

            // Cek riwayat lokal mencegah spam (tapi tetap di cek server nanti)
            // Kita izinkan mencoba, nanti server yang menentukan overwrite atau tidak (logic di sini sederhana)
            
            hide('menuSiswa');
            show('kuisArea');
            
            soalAktif = soal;
            jawabanPilihan = '';
            
            // Gambar
            const imgContainer = document.getElementById('soalImageContainer');
            if (soal.gambar) {
                imgContainer.innerHTML = `<img src="${soal.gambar}" class="max-w-full max-h-64 rounded-xl mx-auto shadow-lg" alt="Soal" onerror="this.parentElement.style.display='none'">`;
                imgContainer.classList.remove('hidden');
            } else {
                imgContainer.classList.add('hidden');
            }
            
            document.getElementById('soalText').textContent = soal.soal;
            
            const opsiDiv = document.getElementById('opsiContainer');
            opsiDiv.innerHTML = ['A','B','C','D','E'].filter(k => soal.opsi[k]).map(k => `
                <button onclick="pilihOpsi('${k}', this)" class="w-full text-left px-4 py-3 rounded-xl glass text-white hover:bg-white/20 transition-all border-2 border-transparent hover-lift">
                    <span class="font-bold text-blue-300">${k}.</span> ${soal.opsi[k]}
                </button>
            `).join('');

            waktu = 180;
            updateTimer();
            if (timer) clearInterval(timer);
            timer = setInterval(() => {
                waktu--;
                updateTimer();
                if (waktu <= 0) {
                    clearInterval(timer);
                    kirimJawaban(true);
                }
            }, 1000);
        }

        function pilihOpsi(key, btn) {
            document.querySelectorAll('#opsiContainer button').forEach(b => {
                b.classList.remove('border-blue-500', 'bg-blue-500/20');
            });
            btn.classList.add('border-blue-500', 'bg-blue-500/20');
            jawabanPilihan = key;
        }

        function updateTimer() {
            const m = Math.floor(waktu / 60);
            const s = waktu % 60;
            document.getElementById('timer').textContent = `${String(m).padStart(2,'0')}:${String(s).padStart(2,'0')}`;
        }

        async function kirimJawaban(timeout = false) {
            if (!jawabanPilihan && !timeout) {
                showToast('Pilih jawaban dulu!', 'warning');
                return;
            }

            if (timer) clearInterval(timer);

            const benar = jawabanPilihan === soalAktif.kunci;
            const nilai = benar ? 100 : 0;
            
            // Hitung Poin & Streak (Client-side logic for instant feedback)
            // Idealnya dihitung server, tapi untuk speed UX kita hitung di sini dulu
            let poin = benar ? 100 : 25;
            let streak = 1; // Default
            
            // Fetch current profile untuk hitung streak yang akurat
            const resProf = await fetchData('getLeaderboard');
            let currentStreak = 0;
            let lastDate = null;

            if (resProf.status === 'success') {
                const me = resProf.data.find(s => s.nama === currentUser);
                if (me) {
                    currentStreak = me.streak;
                    lastDate = me.lastDate; // Perlu disimpan di sheet Siswa kolom D
                }
            }

            const today = new Date().toISOString().slice(0, 10);
            const yesterday = new Date();
            yesterday.setDate(yesterday.getDate() - 1);
            const yesterdayStr = yesterday.toISOString().slice(0, 10);

            if (lastDate === yesterdayStr) {
                streak = currentStreak + 1;
            } else if (lastDate !== today) {
                streak = 1;
            } else {
                streak = currentStreak; // Sudah mengerjakan hari ini?
            }

            // Bonus Streak
            if (streak >= 7) poin += 50;
            else if (streak >= 3) poin += 20;

            // Kirim ke Server
            const payload = {
                nama: currentUser,
                tanggal: today,
                jawaban: jawabanPilihan || '-',
                nilai: nilai,
                poin: poin,
                streak: streak
            };

            showLoading(true);
            try {
                const response = await fetch(`${APPS_SCRIPT_URL}?action=submitJawaban`, {
                    method: 'POST',
                    body: JSON.stringify(payload)
                });
                const result = await response.json();
                showLoading(false);

                if (benar) {
                    createConfetti();
                }

                hide('kuisArea');
                show('hasilArea');

                const hasil = document.getElementById('hasilContent');
                hasil.innerHTML = `
                    <div class="glass rounded-xl p-6 mb-4 card-3d">
                        <p class="text-6xl mb-3 floating">${benar ? '✅' : '❌'}</p>
                        <p class="text-3xl font-bold ${benar ? 'text-green-400' : 'text-red-400'} mb-2">${benar ? 'BENAR!' : 'SALAH'}</p>
                        <p class="text-white mb-4">Jawaban kamu: <span class="font-bold">${jawabanPilihan || '-'}</span><br>Jawaban benar: <span class="font-bold text-green-400">${soalAktif.kunci}</span></p>
                        <div class="bg-white/10 rounded-lg p-4 mb-4">
                            <p class="text-purple-200 text-sm font-semibold mb-2">💡 Pembahasan:</p>
                            <p class="text-white text-sm">${soalAktif.pembahasan || 'Tidak ada pembahasan'}</p>
                        </div>
                    </div>
                    <div class="grid grid-cols-2 gap-3">
                        <div class="glass rounded-xl p-4 text-center hover-lift">
                            <p class="text-yellow-400 text-2xl font-bold">${poin}</p>
                            <p class="text-purple-200 text-xs">Poin Didapat</p>
                        </div>
                        <div class="glass rounded-xl p-4 text-center hover-lift">
                            <p class="text-orange-400 text-2xl font-bold">${streak}🔥</p>
                            <p class="text-purple-200 text-xs">Streak</p>
                        </div>
                    </div>
                `;
            } catch (e) {
                showLoading(false);
                showToast('Gagal mengirim jawaban', 'error');
            }
        }

        // ==========================================
        // GENERAL INIT
        // ==========================================
        async function loadInfo() {
            const res = await fetchData('getInfo');
            const container = document.getElementById('papanInfo');
            const isi = document.getElementById('isiInfo');
            
            if (res.status === 'success') {
                isi.innerHTML = `<h4 class="font-bold text-white mb-2">${res.judul}</h4><p>${res.isi}</p>`;
                container.classList.remove('hidden');
            } else {
                container.classList.add('hidden');
            }
        }

        window.onload = () => {
            loadInfo();
            document.getElementById('tanggal').value = new Date().toISOString().slice(0, 10);
        };
    </script>
</body>
</html>
