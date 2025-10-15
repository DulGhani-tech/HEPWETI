
<html lang="id" class="scroll-smooth">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>HFC - Hepweti Futsal Competition 2025</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link href="https://fonts.googleapis.com/css2?family=Bebas+Neue&family=Montserrat:wght@300;400;500;600;700&display=swap" rel="stylesheet">
    <style>
        body {
            box-sizing: border-box;
        }
        
        .font-bebas { font-family: 'Bebas Neue', cursive; }
        .font-montserrat { font-family: 'Montserrat', sans-serif; }
        
        .bg-electric-blue { background-color: #0066ff; }
        .text-electric-blue { color: #0066ff; }
        .border-electric-blue { border-color: #0066ff; }
        
        .stadium-lights {
            background: radial-gradient(circle at 30% 20%, rgba(0, 102, 255, 0.3) 0%, transparent 50%),
                        radial-gradient(circle at 70% 20%, rgba(255, 255, 255, 0.2) 0%, transparent 50%),
                        radial-gradient(circle at 50% 80%, rgba(0, 102, 255, 0.2) 0%, transparent 50%);
        }
        
        .futsal-field {
            background: 
                radial-gradient(circle at 20% 30%, rgba(0, 102, 255, 0.4) 0%, transparent 40%),
                radial-gradient(circle at 80% 20%, rgba(255, 255, 255, 0.3) 0%, transparent 30%),
                radial-gradient(circle at 60% 70%, rgba(0, 102, 255, 0.3) 0%, transparent 35%),
                radial-gradient(circle at 30% 80%, rgba(255, 255, 255, 0.2) 0%, transparent 25%),
                linear-gradient(135deg, #0a0a0a 0%, #1a1a2e 25%, #16213e 50%, #0f3460 75%, #0066ff 100%);
            position: relative;
            overflow: hidden;
        }
        
        .futsal-field::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background-image: 
                radial-gradient(circle at 25% 25%, rgba(255,255,255,0.1) 2px, transparent 2px),
                radial-gradient(circle at 75% 75%, rgba(0,102,255,0.2) 1px, transparent 1px),
                linear-gradient(45deg, transparent 48%, rgba(255,255,255,0.05) 49%, rgba(255,255,255,0.05) 51%, transparent 52%),
                linear-gradient(-45deg, transparent 48%, rgba(0,102,255,0.1) 49%, rgba(0,102,255,0.1) 51%, transparent 52%);
            background-size: 80px 80px, 60px 60px, 100px 100px, 100px 100px;
            animation: backgroundMove 20s linear infinite;
        }
        
        .futsal-field::after {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: 
                radial-gradient(ellipse at top, rgba(0, 102, 255, 0.1) 0%, transparent 70%),
                radial-gradient(ellipse at bottom, rgba(0, 0, 0, 0.3) 0%, transparent 70%);
        }
        
        @keyframes backgroundMove {
            0% { transform: translate(0, 0) rotate(0deg); }
            25% { transform: translate(-10px, -10px) rotate(90deg); }
            50% { transform: translate(10px, -5px) rotate(180deg); }
            75% { transform: translate(-5px, 10px) rotate(270deg); }
            100% { transform: translate(0, 0) rotate(360deg); }
        }
        
        .ball-bounce {
            animation: bounce 2s infinite;
        }
        
        @keyframes bounce {
            0%, 20%, 50%, 80%, 100% { transform: translateY(0); }
            40% { transform: translateY(-20px); }
            60% { transform: translateY(-10px); }
        }
        
        .glow-effect {
            box-shadow: 0 0 20px rgba(0, 102, 255, 0.5);
        }
        
        .slide-in {
            animation: slideIn 0.8s ease-out;
        }
        
        @keyframes slideIn {
            from { opacity: 0; transform: translateY(30px); }
            to { opacity: 1; transform: translateY(0); }
        }
        
        .countdown-box {
            background: linear-gradient(135deg, #0066ff, #004db3);
            border-radius: 10px;
            padding: 1rem;
            text-align: center;
            color: white;
            min-width: 80px;
        }
        
        .nav-active {
            background-color: #0066ff;
            color: white;
        }
        
        .hidden-section {
            display: none;
        }
        
        .active-section {
            display: block;
        }
    </style>
</head>
<body class="font-montserrat bg-black text-white min-h-full">
    <!-- Navigation -->
    <nav class="fixed top-0 w-full bg-black/90 backdrop-blur-sm z-50 border-b border-electric-blue">
        <div class="container mx-auto px-4 py-3">
            <div class="flex items-center justify-between">
                <div class="flex items-center space-x-3">
                    <div class="w-10 h-10 bg-electric-blue rounded-full flex items-center justify-center">
                        <img src="logohfc.png">
                    </div>
                    <span class="font-bebas text-2xl text-electric-blue">HFC 2026</span>
                </div>
                
                <div class="hidden md:flex space-x-6">
                    <button onclick="showSection('home')" class="nav-btn nav-active px-4 py-2 rounded-lg transition-all duration-300 hover:bg-electric-blue">Beranda</button>
                    <button onclick="showSection('about')" class="nav-btn px-4 py-2 rounded-lg transition-all duration-300 hover:bg-electric-blue">Tentang</button>
                    <button onclick="showSection('schedule')" class="nav-btn px-4 py-2 rounded-lg transition-all duration-300 hover:bg-electric-blue">Jadwal</button>
                    <button onclick="showSection('registration')" class="nav-btn px-4 py-2 rounded-lg transition-all duration-300 hover:bg-electric-blue">Pendaftaran</button>
                    <button onclick="showSection('gallery')" class="nav-btn px-4 py-2 rounded-lg transition-all duration-300 hover:bg-electric-blue">Galeri</button>
                    <button onclick="showSection('contact')" class="nav-btn px-4 py-2 rounded-lg transition-all duration-300 hover:bg-electric-blue">Kontak</button>
                </div>
                
                <button id="mobile-menu-btn" class="md:hidden text-white">
                    <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                        <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h16M4 18h16"></path>
                    </svg>
                </button>
            </div>
            
            <!-- Mobile Menu -->
            <div id="mobile-menu" class="hidden md:hidden mt-4 space-y-2">
                <button onclick="showSection('home')" class="nav-btn-mobile block w-full text-left px-4 py-2 rounded-lg transition-all duration-300 hover:bg-electric-blue">Beranda</button>
                <button onclick="showSection('about')" class="nav-btn-mobile block w-full text-left px-4 py-2 rounded-lg transition-all duration-300 hover:bg-electric-blue">Tentang</button>
                <button onclick="showSection('schedule')" class="nav-btn-mobile block w-full text-left px-4 py-2 rounded-lg transition-all duration-300 hover:bg-electric-blue">Jadwal</button>
                <button onclick="showSection('registration')" class="nav-btn-mobile block w-full text-left px-4 py-2 rounded-lg transition-all duration-300 hover:bg-electric-blue">Pendaftaran</button>
                <button onclick="showSection('gallery')" class="nav-btn-mobile block w-full text-left px-4 py-2 rounded-lg transition-all duration-300 hover:bg-electric-blue">Galeri</button>
                <button onclick="showSection('contact')" class="nav-btn-mobile block w-full text-left px-4 py-2 rounded-lg transition-all duration-300 hover:bg-electric-blue">Kontak</button>
            </div>
        </div>
    </nav>

    <!-- Home Section -->
    <section id="home" class="active-section min-h-screen futsal-field stadium-lights relative overflow-hidden pt-20">
        <div class="absolute inset-0 bg-black/50"></div>
        <div class="relative z-10 container mx-auto px-4 py-20">
            <div class="text-center slide-in">
                <div class="mb-8">
                    <div class="inline-block ball-bounce text-6xl mb-4">⚽</div>
                </div>
                <h1 class="font-bebas text-6xl md:text-8xl text-white mb-4 glow-effect">
                    HFC 2026
                </h1>
                <h2 class="font-bebas text-3xl md:text-5xl text-electric-blue mb-6">
                    HEPWETI FUTSAL COMPETITION
                </h2>
                <p class="text-xl md:text-3xl text-white mb-8 max-w-4xl mx-auto font-bold">
                    ⚡ "BERSIAPLAH UNTUK PERTEMPURAN EPIK!" ⚡
                </p>
                <p class="text-lg md:text-xl text-yellow-300 mb-6 max-w-4xl mx-auto font-semibold">
                    🔥 ARENA TERBESAR • KOMPETISI TERGANAS • HADIAH TERBESAR 🔥
                </p>
                <p class="text-lg text-gray-300 mb-8 max-w-5xl mx-auto leading-relaxed">
                    Rasakan sensasi pertandingan futsal paling mendebarkan se-Kabupaten Ciamis! 32 tim terbaik akan bertarung habis-habisan untuk merebut gelar juara. Hanya yang terkuat yang akan bertahan hingga akhir!
                </p>
                <div class="bg-gradient-to-r from-red-600 to-orange-500 rounded-lg p-4 mb-8 max-w-3xl mx-auto border-2 border-yellow-400">
                    <p class="text-white font-bold text-lg">
                        🏆 TOTAL HADIAH: Rp 14.200.000 + TROFI + SERTIFIKAT 🏆
                    </p>
                </div>
                
                <!-- Countdown Timer -->
                <div class="mb-12">
                    <h3 class="text-2xl font-bold mb-6">Countdown Menuju Pembukaan</h3>
                    <div class="flex justify-center space-x-4" id="countdown">
                        <div class="countdown-box">
                            <div class="text-3xl font-bold" id="days">00</div>
                            <div class="text-sm">Hari</div>
                        </div>
                        <div class="countdown-box">
                            <div class="text-3xl font-bold" id="hours">00</div>
                            <div class="text-sm">Jam</div>
                        </div>
                        <div class="countdown-box">
                            <div class="text-3xl font-bold" id="minutes">00</div>
                            <div class="text-sm">Menit</div>
                        </div>
                        <div class="countdown-box">
                            <div class="text-3xl font-bold" id="seconds">00</div>
                            <div class="text-sm">Detik</div>
                        </div>
                    </div>
                </div>
                
                <div class="flex flex-col md:flex-row gap-6 justify-center">
                    <button onclick="showSection('registration')" class="bg-electric-blue hover:bg-blue-700 text-white font-bold py-4 px-8 rounded-lg text-xl transition-all duration-300 transform hover:scale-105 glow-effect">
                        🏆 Daftar Sekarang
                    </button>
                    <button onclick="showSection('schedule')" class="border-2 border-electric-blue text-electric-blue hover:bg-electric-blue hover:text-white font-bold py-4 px-8 rounded-lg text-xl transition-all duration-300 transform hover:scale-105">
                        📅 Lihat Jadwal Pertandingan
                    </button>
                </div>
            </div>
        </div>
    </section>

    <!-- About Section -->
    <section id="about" class="hidden-section min-h-screen bg-gradient-to-br from-gray-900 to-black py-20">
        <div class="container mx-auto px-4 pt-20">
            <div class="slide-in">
                <h2 class="font-bebas text-5xl md:text-6xl text-center text-electric-blue mb-12">
                    TENTANG HFC
                </h2>
                
                <div class="grid md:grid-cols-2 gap-12 items-center">
                    <div>
                        <div class="text-6xl mb-6 text-center">🏟️</div>
                        <p class="text-lg text-gray-300 mb-6 leading-relaxed">
                            Hepweti Futsal Competition (HFC) adalah ajang kompetisi futsal tahunan yang diadakan oleh SMK Hepweti Ciamis untuk mengembangkan bakat olahraga futsal pelajar tingkat SMP/MTS.
                        </p>
                        <p class="text-lg text-gray-300 mb-8 leading-relaxed">
                            Acara ini bertujuan untuk menjalin sportivitas, mempererat persaudaraan, dan menumbuhkan semangat kompetisi sehat di kalangan pelajar.
                        </p>
                    </div>
                    
                    <div class="bg-gray-800 rounded-lg p-8 border border-electric-blue">
                        <h3 class="font-bebas text-3xl text-electric-blue mb-6">DETAIL TURNAMEN</h3>
                        <div class="space-y-4">
                            <div class="flex items-center">
                                <span class="text-2xl mr-3">📅</span>
                                <div>
                                    <strong>Tahun:</strong> 2026
                                </div>
                            </div>
                            <div class="flex items-center">
                                <span class="text-2xl mr-3">🎯</span>
                                <div>
                                    <strong>Tema:</strong> "Spirit, Skill, and Solidarity"
                                </div>
                            </div>
                            <div class="flex items-center">
                                <span class="text-2xl mr-3">📍</span>
                                <div>
                                    <strong>Lokasi:</strong> Gelanggang Galuh Taruna (GGT) Ciamis
                                </div>
                            </div>
                            <div class="flex items-center">
                                <span class="text-2xl mr-3">⏰</span>
                                <div>
                                    <strong>Tanggal:</strong> 26 Januari – 1 Februari 2026
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Schedule Section -->
    <section id="schedule" class="hidden-section min-h-screen bg-gradient-to-br from-black to-gray-900 py-20">
        <div class="container mx-auto px-4 pt-20">
            <div class="slide-in">
                <h2 class="font-bebas text-5xl md:text-6xl text-center text-electric-blue mb-12">
                    JADWAL & FORMAT TURNAMEN
                </h2>
                
                <div class="grid md:grid-cols-2 gap-12">
                    <!-- Schedule -->
                    <div class="bg-gray-800 rounded-lg p-8 border border-electric-blue">
                        <h3 class="font-bebas text-3xl text-electric-blue mb-6 flex items-center">
                            📅 JADWAL PERTANDINGAN
                        </h3>
                        <div class="space-y-6">
                            <div class="bg-gray-700 rounded-lg p-4">
                                <h4 class="font-bold text-xl text-white mb-2">Babak Penyisihan</h4>
                                <p class="text-electric-blue font-semibold">26–29 Januari 2026</p>
                            </div>
                            <div class="bg-gray-700 rounded-lg p-4">
                                <h4 class="font-bold text-xl text-white mb-2">Semifinal</h4>
                                <p class="text-electric-blue font-semibold">30–31 Januari 2026</p>
                            </div>
                            <div class="bg-gradient-to-r from-electric-blue to-blue-700 rounded-lg p-4">
                                <h4 class="font-bold text-xl text-white mb-2">Final & Penutupan</h4>
                                <p class="text-white font-semibold">1 Februari 2026</p>
                            </div>
                        </div>
                    </div>
                    
                    <!-- Format -->
                    <div class="bg-gray-800 rounded-lg p-8 border border-electric-blue">
                        <h3 class="font-bebas text-3xl text-electric-blue mb-6 flex items-center">
                            ⚽ FORMAT PERTANDINGAN
                        </h3>
                        <div class="space-y-4">
                            <div class="flex items-center">
                                <span class="text-2xl mr-3">🏆</span>
                                <div>
                                    <strong>Sistem:</strong> Setengah Kompetisi
                                </div>
                            </div>
                            <div class="flex items-center">
                                <span class="text-2xl mr-3">⏱️</span>
                                <div>
                                    <strong>Durasi:</strong> 2 x 10 menit
                                </div>
                            </div>
                            <div class="flex items-center">
                                <span class="text-2xl mr-3">👥</span>
                                <div>
                                    <strong>Pemain:</strong> 5 inti + 3 cadangan
                                </div>
                            </div>
                            <div class="flex items-center">
                                <span class="text-2xl mr-3">📋</span>
                                <div>
                                    <strong>Peraturan:</strong> Standar FFI
                                </div>
                            </div>
                        </div>
                        
                        <div class="mt-8 text-center">
                            <div class="text-6xl mb-4">🥇</div>
                            <p class="text-lg text-gray-300">Siap bertanding dengan sportivitas tinggi!</p>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Registration Section -->
    <section id="registration" class="hidden-section min-h-screen bg-gradient-to-br from-gray-900 to-black py-20">
        <div class="container mx-auto px-4 pt-20">
            <div class="slide-in">
                <h2 class="font-bebas text-5xl md:text-6xl text-center text-electric-blue mb-12">
                    DAFTARKAN TIM FUTSALMU SEKARANG!
                </h2>
                
                <div class="grid md:grid-cols-3 gap-8 mb-12">
                    <!-- Biaya -->
                    <div class="bg-gradient-to-br from-electric-blue to-blue-700 rounded-lg p-8 text-center">
                        <div class="text-4xl mb-4">💰</div>
                        <h3 class="font-bebas text-2xl mb-4">BIAYA PENDAFTARAN</h3>
                        <div class="text-3xl font-bold">Rp300.000</div>
                        <div class="text-lg">/tim</div>
                    </div>
                    
                    <!-- Fasilitas -->
                    <div class="bg-gray-800 rounded-lg p-8 border border-electric-blue">
                        <div class="text-4xl mb-4 text-center">🎁</div>
                        <h3 class="font-bebas text-2xl text-electric-blue mb-4 text-center">FASILITAS</h3>
                        <ul class="space-y-2">
                            <li class="flex items-center">
                                <span class="text-green-400 mr-2">✓</span>
                                E-sertifikat peserta
                            </li>
                            <li class="flex items-center">
                                <span class="text-green-400 mr-2">✓</span>
                                Air mineral & konsumsi untuk bapak ibu guru SMP
                            </li>
                            <li class="flex items-center">
                                <span class="text-green-400 mr-2">✓</span>
                                Medali & trofi juara 1, 2, 3
                            </li>
                            <li class="flex items-center">
                                <span class="text-green-400 mr-2">✓</span>
                                Best Player Award
                            </li>
                        </ul>
                    </div>
                    
                    <!-- Syarat -->
                    <div class="bg-gray-800 rounded-lg p-8 border border-electric-blue">
                        <div class="text-4xl mb-4 text-center">📋</div>
                        <h3 class="font-bebas text-2xl text-electric-blue mb-4 text-center">SYARAT & KETENTUAN</h3>
                        <ul class="space-y-2">
                            <li class="flex items-start">
                                <span class="text-electric-blue mr-2">•</span>
                                Peserta pelajar aktif SMP/MTS
                            </li>
                            <li class="flex items-start">
                                <span class="text-electric-blue mr-2">•</span>
                                Maksimal 2 tim per sekolah
                            </li>
                            <li class="flex items-start">
                                <span class="text-electric-blue mr-2">•</span>
                                Bawa kartu pelajar saat registrasi
                            </li>
                        </ul>
                    </div>
                </div>
                
                <div class="text-center">
                    <h3 class="font-bebas text-3xl text-white mb-8">DAFTAR SEKARANG!</h3>
                    <div class="flex justify-center">
                        <button onclick="contactWhatsApp()" class="bg-green-500 hover:bg-green-600 text-white font-bold py-4 px-8 rounded-lg text-xl transition-all duration-300 transform hover:scale-105 flex items-center justify-center">
                            📱 WhatsApp Panitia
                        </button>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Gallery Section -->
    <section id="gallery" class="hidden-section min-h-screen bg-gradient-to-br from-black to-gray-900 py-20">
        <div class="container mx-auto px-4 pt-20">
            <div class="slide-in">
                <h2 class="font-bebas text-5xl md:text-6xl text-center text-electric-blue mb-12">
                    GALERI HFC
                </h2>
                
                <div class="grid md:grid-cols-2 lg:grid-cols-3 gap-6">
                    <!-- Gallery Items -->
                    <div class="bg-gray-800 rounded-lg overflow-hidden border border-electric-blue hover:border-white transition-all duration-300 transform hover:scale-105">
                        <div class="h-48 bg-gradient-to-br from-electric-blue to-blue-700 flex items-center justify-center">
                            <div class="text-center text-white">
                                <div class="text-4xl mb-2">⚽</div>
                                <p class="font-semibold">Aksi Pemain di Lapangan</p>
                            </div>
                        </div>
                        <div class="p-4">
                            <p class="text-gray-300">Momen seru pertandingan HFC 2024</p>
                        </div>
                    </div>
                    
                    <div class="bg-gray-800 rounded-lg overflow-hidden border border-electric-blue hover:border-white transition-all duration-300 transform hover:scale-105">
                        <div class="h-48 bg-gradient-to-br from-yellow-500 to-yellow-600 flex items-center justify-center">
                            <div class="text-center text-white">
                                <div class="text-4xl mb-2">🏆</div>
                                <p class="font-semibold">Penyerahan Trofi</p>
                            </div>
                        </div>
                        <div class="p-4">
                            <p class="text-gray-300">Momen kebanggaan para juara</p>
                        </div>
                    </div>
                    
                    <div class="bg-gray-800 rounded-lg overflow-hidden border border-electric-blue hover:border-white transition-all duration-300 transform hover:scale-105">
                        <div class="h-48 bg-gradient-to-br from-green-500 to-green-600 flex items-center justify-center">
                            <div class="text-center text-white">
                                <div class="text-4xl mb-2">👥</div>
                                <p class="font-semibold">Antusiasme Penonton</p>
                            </div>
                        </div>
                        <div class="p-4">
                            <p class="text-gray-300">Dukungan luar biasa dari supporter</p>
                        </div>
                    </div>
                    
                    <div class="bg-gray-800 rounded-lg overflow-hidden border border-electric-blue hover:border-white transition-all duration-300 transform hover:scale-105">
                        <div class="h-48 bg-gradient-to-br from-purple-500 to-purple-600 flex items-center justify-center">
                            <div class="text-center text-white">
                                <div class="text-4xl mb-2">🤝</div>
                                <p class="font-semibold">Kebersamaan Antar Tim</p>
                            </div>
                        </div>
                        <div class="p-4">
                            <p class="text-gray-300">Sportivitas dan persahabatan</p>
                        </div>
                    </div>
                    
                    <div class="bg-gray-800 rounded-lg overflow-hidden border border-electric-blue hover:border-white transition-all duration-300 transform hover:scale-105">
                        <div class="h-48 bg-gradient-to-br from-red-500 to-red-600 flex items-center justify-center">
                            <div class="text-center text-white">
                                <div class="text-4xl mb-2">📸</div>
                                <p class="font-semibold">Dokumentasi Acara</p>
                            </div>
                        </div>
                        <div class="p-4">
                            <p class="text-gray-300">Kenangan indah turnamen</p>
                        </div>
                    </div>
                    
                    <div class="bg-gray-800 rounded-lg overflow-hidden border border-electric-blue hover:border-white transition-all duration-300 transform hover:scale-105">
                        <div class="h-48 bg-gradient-to-br from-indigo-500 to-indigo-600 flex items-center justify-center">
                            <div class="text-center text-white">
                                <div class="text-4xl mb-2">🎉</div>
                                <p class="font-semibold">Penutupan Meriah</p>
                            </div>
                        </div>
                        <div class="p-4">
                            <p class="text-gray-300">Penutupan yang tak terlupakan</p>
                        </div>
                    </div>
                </div>
                
                <div class="text-center mt-12">
                    <p class="text-xl text-gray-300 mb-6">Ikuti media sosial kami untuk update terbaru!</p>
                    <button onclick="openInstagram()" class="bg-gradient-to-r from-pink-500 to-purple-600 hover:from-pink-600 hover:to-purple-700 text-white font-bold py-3 px-6 rounded-lg transition-all duration-300 transform hover:scale-105">
                        📱 @hepwetifutsalcompetition
                    </button>
                </div>
            </div>
        </div>
    </section>

    <!-- Contact Section -->
    <section id="contact" class="hidden-section min-h-screen bg-gradient-to-br from-gray-900 to-black py-20">
        <div class="container mx-auto px-4 pt-20">
            <div class="slide-in">
                <h2 class="font-bebas text-5xl md:text-6xl text-center text-electric-blue mb-12">
                    HUBUNGI KAMI
                </h2>
                
                <div class="grid md:grid-cols-2 gap-12">
                    <!-- Contact Info -->
                    <div class="bg-gray-800 rounded-lg p-8 border border-electric-blue">
                        <h3 class="font-bebas text-3xl text-electric-blue mb-6">KONTAK PANITIA</h3>
                        <div class="space-y-6">
                            <div class="flex items-center">
                                <div class="w-12 h-12 bg-electric-blue rounded-full flex items-center justify-center mr-4">
                                    <span class="text-white text-xl">👥</span>
                                </div>
                                <div>
                                    <p class="font-semibold">Panitia HFC SMK Hepweti Ciamis</p>
                                </div>
                            </div>
                            
                            <div class="flex items-center">
                                <div class="w-12 h-12 bg-green-500 rounded-full flex items-center justify-center mr-4">
                                    <span class="text-white text-xl">📱</span>
                                </div>
                                <div>
                                    <p class="font-semibold">WhatsApp</p>
                                    <p class="text-electric-blue">0812-2163-6632</p>
                                </div>
                            </div>
                            
                            <div class="flex items-center">
                                <div class="w-12 h-12 bg-gradient-to-r from-pink-500 to-purple-600 rounded-full flex items-center justify-center mr-4">
                                    <span class="text-white text-xl">📷</span>
                                </div>
                                <div>
                                    <p class="font-semibold">Instagram</p>
                                    <p class="text-electric-blue">@hepwetifutsalcompetition</p>
                                </div>
                            </div>
                            
                            <div class="flex items-center">
                                <div class="w-12 h-12 bg-red-500 rounded-full flex items-center justify-center mr-4">
                                    <span class="text-white text-xl">📧</span>
                                </div>
                                <div>
                                    <p class="font-semibold">Email</p>
                                    <p class="text-electric-blue">hepwetifutsalcup@gmail.com</p>
                                </div>
                            </div>
                        </div>
                        
                        <div class="mt-8 flex flex-col space-y-4">
                            <button onclick="contactWhatsApp()" class="bg-green-500 hover:bg-green-600 text-white font-bold py-3 px-6 rounded-lg transition-all duration-300 transform hover:scale-105">
                                💬 Chat WhatsApp
                            </button>
                            <button onclick="openInstagram()" class="bg-gradient-to-r from-pink-500 to-purple-600 hover:from-pink-600 hover:to-purple-700 text-white font-bold py-3 px-6 rounded-lg transition-all duration-300 transform hover:scale-105">
                                📱 Follow Instagram
                            </button>
                        </div>
                    </div>
                    
                    <!-- Sponsors -->
                    <div class="bg-gray-800 rounded-lg p-8 border border-electric-blue">
                        <h3 class="font-bebas text-3xl text-electric-blue mb-6">SPONSOR & PARTNER</h3>
                        <div class="grid grid-cols-2 gap-6">
                            <div class="bg-gray-700 rounded-lg p-6 text-center border border-gray-600 hover:border-electric-blue transition-all duration-300">
                                <div class="text-3xl mb-2">🏪</div>
                                <p class="font-semibold">Toko Olahraga</p>
                                <p class="text-sm text-gray-400">Sport Center</p>
                            </div>
                            
                            <div class="bg-gray-700 rounded-lg p-6 text-center border border-gray-600 hover:border-electric-blue transition-all duration-300">
                                <div class="text-3xl mb-2">🖨️</div>
                                <p class="font-semibold">Percetakan</p>
                                <p class="text-sm text-gray-400">Digital Print</p>
                            </div>
                            
                            <div class="bg-gray-700 rounded-lg p-6 text-center border border-gray-600 hover:border-electric-blue transition-all duration-300">
                                <div class="text-3xl mb-2">🍔</div>
                                <p class="font-semibold">Makanan</p>
                                <p class="text-sm text-gray-400">Warung Lokal</p>
                            </div>
                            
                            <div class="bg-gray-700 rounded-lg p-6 text-center border border-gray-600 hover:border-electric-blue transition-all duration-300">
                                <div class="text-3xl mb-2">🥤</div>
                                <p class="font-semibold">Minuman</p>
                                <p class="text-sm text-gray-400">Fresh Drink</p>
                            </div>
                        </div>
                        
                        <div class="mt-8 text-center">
                            <p class="text-gray-400 mb-4">Tertarik menjadi sponsor?</p>
                            <button onclick="contactWhatsApp()" class="bg-electric-blue hover:bg-blue-700 text-white font-bold py-2 px-6 rounded-lg transition-all duration-300">
                                Hubungi Kami
                            </button>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer class="bg-black border-t border-electric-blue py-8">
        <div class="container mx-auto px-4 text-center">
            <div class="flex items-center justify-center space-x-3 mb-4">
                <div class="w-8 h-8 bg-electric-blue rounded-full flex items-center justify-center">
                    <img src="logohfc.png">
                </div>
                <span class="font-bebas text-xl text-electric-blue">HFC 2026</span>
            </div>
            <p class="text-gray-400 mb-2">© 2026 Hepweti Futsal Competition. All rights reserved.</p>
            <p class="text-gray-500 text-sm">Diselenggarakan oleh SMK Hepweti Ciamis</p>
        </div>
    </footer>

    <script>
        // Navigation functionality
        function showSection(sectionId) {
            // Hide all sections
            const sections = document.querySelectorAll('section');
            sections.forEach(section => {
                section.classList.remove('active-section');
                section.classList.add('hidden-section');
            });
            
            // Show selected section
            const targetSection = document.getElementById(sectionId);
            targetSection.classList.remove('hidden-section');
            targetSection.classList.add('active-section');
            
            // Update navigation buttons
            const navButtons = document.querySelectorAll('.nav-btn');
            const mobileNavButtons = document.querySelectorAll('.nav-btn-mobile');
            
            navButtons.forEach(btn => btn.classList.remove('nav-active'));
            mobileNavButtons.forEach(btn => btn.classList.remove('nav-active'));
            
            // Add active class to current button
            event.target.classList.add('nav-active');
            
            // Close mobile menu
            document.getElementById('mobile-menu').classList.add('hidden');
            
            // Add slide-in animation
            targetSection.querySelector('.slide-in').style.animation = 'none';
            setTimeout(() => {
                targetSection.querySelector('.slide-in').style.animation = 'slideIn 0.8s ease-out';
            }, 10);
        }
        
        // Mobile menu toggle
        document.getElementById('mobile-menu-btn').addEventListener('click', function() {
            const mobileMenu = document.getElementById('mobile-menu');
            mobileMenu.classList.toggle('hidden');
        });
        
        // Countdown timer
        function updateCountdown() {
            const targetDate = new Date('January 26, 2026 00:00:00').getTime();
            const now = new Date().getTime();
            const difference = targetDate - now;
            
            if (difference > 0) {
                const days = Math.floor(difference / (1000 * 60 * 60 * 24));
                const hours = Math.floor((difference % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60));
                const minutes = Math.floor((difference % (1000 * 60 * 60)) / (1000 * 60));
                const seconds = Math.floor((difference % (1000 * 60)) / 1000);
                
                document.getElementById('days').textContent = days.toString().padStart(2, '0');
                document.getElementById('hours').textContent = hours.toString().padStart(2, '0');
                document.getElementById('minutes').textContent = minutes.toString().padStart(2, '0');
                document.getElementById('seconds').textContent = seconds.toString().padStart(2, '0');
            } else {
                document.getElementById('countdown').innerHTML = '<div class="text-2xl font-bold text-electric-blue">Turnamen Telah Dimulai!</div>';
            }
        }
        
        // Update countdown every second
        setInterval(updateCountdown, 1000);
        updateCountdown();
        
        // Contact functions
        function contactWhatsApp() {
            window.open('https://wa.me/6281221636632?text=Halo,%20saya%20ingin%20bertanya%20tentang%20HFC%202026', '_blank', 'noopener,noreferrer');
        }
        
        function openInstagram() {
            window.open('https://instagram.com/hepwetifutsalcompetition', '_blank', 'noopener,noreferrer');
        }
        
        function openRegistrationForm() {
            // In a real implementation, this would open a Google Form or registration page
            alert('Formulir pendaftaran akan segera dibuka! Silakan hubungi panitia melalui WhatsApp untuk informasi lebih lanjut.');
        }
        
        // Add smooth scrolling and animations on load
        document.addEventListener('DOMContentLoaded', function() {
            // Initial animation for home section
            const homeSection = document.getElementById('home');
            const slideInElement = homeSection.querySelector('.slide-in');
            slideInElement.style.animation = 'slideIn 0.8s ease-out';
        });
    </script>
<script>(function(){function c(){var b=a.contentDocument||a.contentWindow.document;if(b){var d=b.createElement('script');d.innerHTML="window.__CF$cv$params={r:'98cc288e5292fdc5',t:'MTc2MDE2MjY0OS4wMDAwMDA='};var a=document.createElement('script');a.nonce='';a.src='/cdn-cgi/challenge-platform/scripts/jsd/main.js';document.getElementsByTagName('head')[0].appendChild(a);";b.getElementsByTagName('head')[0].appendChild(d)}}if(document.body){var a=document.createElement('iframe');a.height=1;a.width=1;a.style.position='absolute';a.style.top=0;a.style.left=0;a.style.border='none';a.style.visibility='hidden';document.body.appendChild(a);if('loading'!==document.readyState)c();else if(window.addEventListener)document.addEventListener('DOMContentLoaded',c);else{var e=document.onreadystatechange||function(){};document.onreadystatechange=function(b){e(b);'loading'!==document.readyState&&(document.onreadystatechange=e,c())}}}})();</script></body>
</html>


<environment_details>
# VSCode Visible Files
HFC.html

# VSCode Open Tabs
websmkhepewticms.html
HFC.html
</environment_details>
