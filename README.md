# FRAGX-github.io
<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>FRAGX - Torneos CS2 & Minecraft Gratis</title>
    <script src="https://cdn.jsdelivr.net/npm/@tailwindcss/browser@4"></script>
    <link href="https://fonts.googleapis.com/css2?family=Orbitron:wght@400;500;600;700;800;900&family=Rajdhani:wght@300;400;500;600;700&display=swap" rel="stylesheet">
    <style>
        * {
            font-family: 'Rajdhani', sans-serif;
        }
        h1, h2, h3, .logo, .nav-link, .stat-number {
            font-family: 'Orbitron', sans-serif;
        }
        
        :root {
            --neon-green: #39ff14;
            --neon-cyan: #00fff5;
            --neon-pink: #ff00ff;
            --neon-orange: #ff6a00;
            --neon-yellow: #ffd700;
            --cs-orange: #de9b35;
            --dark-bg: #0a0a0f;
            --darker-bg: #050508;
            --card-bg: #12121a;
        }

        body {
            background-color: var(--dark-bg);
            overflow-x: hidden;
        }

        /* Glitch Effect */
        .glitch {
            position: relative;
            animation: glitch 2s infinite;
        }
        .glitch::before,
        .glitch::after {
            content: attr(data-text);
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
        }
        .glitch::before {
            animation: glitch-1 0.5s infinite;
            color: var(--neon-cyan);
            z-index: -1;
        }
        .glitch::after {
            animation: glitch-2 0.5s infinite;
            color: var(--neon-orange);
            z-index: -2;
        }
        @keyframes glitch-1 {
            0%, 100% { clip-path: inset(20% 0 30% 0); transform: translate(-3px, 0); }
            50% { clip-path: inset(50% 0 20% 0); transform: translate(3px, 0); }
        }
        @keyframes glitch-2 {
            0%, 100% { clip-path: inset(60% 0 10% 0); transform: translate(3px, 0); }
            50% { clip-path: inset(10% 0 60% 0); transform: translate(-3px, 0); }
        }

        /* Neon Effects */
        .neon-text {
            text-shadow: 0 0 10px var(--neon-orange), 0 0 20px var(--neon-orange), 0 0 40px var(--neon-orange);
        }
        .neon-text-cyan {
            text-shadow: 0 0 10px var(--neon-cyan), 0 0 20px var(--neon-cyan), 0 0 40px var(--neon-cyan);
        }
        .neon-text-green {
            text-shadow: 0 0 10px var(--neon-green), 0 0 20px var(--neon-green), 0 0 40px var(--neon-green);
        }

        .neon-border {
            box-shadow: 0 0 5px var(--neon-orange), 0 0 10px var(--neon-orange), inset 0 0 5px rgba(222, 155, 53, 0.1);
            border: 1px solid var(--neon-orange);
        }

        /* Gamer Card */
        .gamer-card {
            background: linear-gradient(145deg, #12121a 0%, #1a1a2e 100%);
            border: 1px solid rgba(222, 155, 53, 0.2);
            transition: all 0.3s ease;
        }
        .gamer-card:hover {
            transform: translateY(-10px) scale(1.02);
            box-shadow: 0 0 30px rgba(222, 155, 53, 0.3), 0 20px 40px rgba(0, 0, 0, 0.5);
            border-color: var(--cs-orange);
        }

        /* CS2 Grid Background */
        .cyber-grid {
            background-image: 
                linear-gradient(rgba(222, 155, 53, 0.03) 1px, transparent 1px),
                linear-gradient(90deg, rgba(222, 155, 53, 0.03) 1px, transparent 1px);
            background-size: 50px 50px;
        }

        /* Particles */
        .particles {
            position: absolute;
            width: 100%;
            height: 100%;
            overflow: hidden;
        }
        .particle {
            position: absolute;
            width: 4px;
            height: 4px;
            background: var(--cs-orange);
            border-radius: 50%;
            animation: float-particle 15s infinite linear;
            box-shadow: 0 0 10px var(--cs-orange);
        }
        @keyframes float-particle {
            0% { transform: translateY(100vh) rotate(0deg); opacity: 0; }
            10% { opacity: 1; }
            90% { opacity: 1; }
            100% { transform: translateY(-100vh) rotate(720deg); opacity: 0; }
        }

        /* Pulse Animation */
        .pulse-glow {
            animation: pulse-glow 2s infinite;
        }
        @keyframes pulse-glow {
            0%, 100% { box-shadow: 0 0 5px var(--cs-orange), 0 0 10px var(--cs-orange); }
            50% { box-shadow: 0 0 20px var(--cs-orange), 0 0 40px var(--cs-orange), 0 0 60px var(--cs-orange); }
        }

        /* RGB Border */
        .rgb-border {
            position: relative;
            background: var(--card-bg);
        }
        .rgb-border::before {
            content: '';
            position: absolute;
            top: -2px;
            left: -2px;
            right: -2px;
            bottom: -2px;
            background: linear-gradient(45deg, var(--neon-orange), var(--neon-cyan), var(--neon-pink), var(--neon-green), var(--neon-orange));
            background-size: 400% 400%;
            animation: rgb-shift 3s ease infinite;
            z-index: -1;
            border-radius: inherit;
        }
        @keyframes rgb-shift {
            0%, 100% { background-position: 0% 50%; }
            50% { background-position: 100% 50%; }
        }

        /* Scrollbar */
        ::-webkit-scrollbar {
            width: 8px;
        }
        ::-webkit-scrollbar-track {
            background: var(--darker-bg);
        }
        ::-webkit-scrollbar-thumb {
            background: var(--cs-orange);
            border-radius: 4px;
        }

        /* Button Gamer */
        .btn-gamer {
            background: linear-gradient(135deg, transparent 0%, transparent 100%);
            border: 2px solid var(--cs-orange);
            color: var(--cs-orange);
            position: relative;
            overflow: hidden;
            transition: all 0.3s ease;
        }
        .btn-gamer::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, var(--cs-orange), transparent);
            transition: left 0.5s ease;
        }
        .btn-gamer:hover::before {
            left: 100%;
        }
        .btn-gamer:hover {
            background: var(--cs-orange);
            color: #000;
            box-shadow: 0 0 30px var(--cs-orange);
        }

        .btn-green {
            border-color: var(--neon-green);
            color: var(--neon-green);
        }
        .btn-green:hover {
            background: var(--neon-green);
            box-shadow: 0 0 30px var(--neon-green);
        }

        /* Rank Colors */
        .rank-silver { color: #b4b4b4; }
        .rank-gold { color: #ffd700; }
        .rank-master { color: #00d4ff; }
        .rank-global { color: #ff4444; }

        /* Modal */
        .modal-content {
            animation: modalIn 0.3s ease-out;
            background: linear-gradient(145deg, #12121a 0%, #1a1a2e 100%);
        }
        @keyframes modalIn {
            from { opacity: 0; transform: scale(0.9) translateY(-20px); }
            to { opacity: 1; transform: scale(1) translateY(0); }
        }

        /* Notification */
        .notification {
            animation: slideIn 0.5s ease-out;
        }
        @keyframes slideIn {
            from { transform: translateX(100%); opacity: 0; }
            to { transform: translateX(0); opacity: 1; }
        }

        .fade-in {
            animation: fadeIn 0.8s ease-out forwards;
        }
        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(30px); }
            to { opacity: 1; transform: translateY(0); }
        }

        /* Free Badge */
        .free-badge {
            background: linear-gradient(135deg, #39ff14, #00ff88);
            animation: free-pulse 1.5s ease infinite;
        }
        @keyframes free-pulse {
            0%, 100% { transform: scale(1); }
            50% { transform: scale(1.05); }
        }

        /* Team Card */
        .team-card {
            transition: all 0.3s ease;
        }
        .team-card:hover {
            transform: scale(1.05);
        }

        /* Live indicator */
        .live-dot {
            animation: live-blink 1s ease infinite;
        }
        @keyframes live-blink {
            0%, 100% { opacity: 1; }
            50% { opacity: 0.3; }
        }
    </style>
</head>
<body class="bg-[#0a0a0f] text-gray-100 cyber-grid">
    <!-- Particles -->
    <div class="particles fixed inset-0 pointer-events-none z-0" id="particles"></div>

    <!-- Notifications -->
    <div id="notifications" class="fixed top-20 right-4 z-50 space-y-2"></div>

    <!-- Modal -->
    <div id="modal" class="fixed inset-0 bg-black/80 z-50 hidden flex items-center justify-center p-4 backdrop-blur-sm">
        <div class="modal-content rounded-lg max-w-2xl w-full max-h-[90vh] overflow-y-auto neon-border">
            <div class="p-6">
                <div class="flex justify-between items-center mb-4">
                    <h3 id="modalTitle" class="text-2xl font-bold text-[#de9b35] neon-text"></h3>
                    <button onclick="closeModal()" class="text-gray-400 hover:text-[#de9b35] text-3xl transition">&times;</button>
                </div>
                <div id="modalContent"></div>
            </div>
        </div>
    </div>

    <!-- FRAGX Branding -->

    <!-- Navigation -->
    <nav id="navbar" class="fixed w-full z-40 transition-all duration-300 bg-transparent">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="flex justify-between items-center h-20">
                <div class="flex-shrink-0 cursor-pointer flex items-center gap-3" onclick="scrollToTop()">
                    <span class="text-3xl">🎯</span>
                    <span class="logo text-2xl font-bold text-[#de9b35] neon-text glitch" data-text="FRAGX">FRAGX</span>
                    <span class="free-badge px-2 py-1 rounded text-black text-xs font-bold">100% GRATIS</span>
                </div>
                <div class="hidden md:flex space-x-6 items-center">
                    <a href="#inicio" class="nav-link text-gray-300 hover:text-[#de9b35] transition uppercase text-sm tracking-widest">Inicio</a>
                    <a href="#torneos" class="nav-link text-gray-300 hover:text-[#de9b35] transition uppercase text-sm tracking-widest">Torneos</a>
                    <a href="#jugar" class="nav-link text-gray-300 hover:text-[#39ff14] transition uppercase text-sm tracking-widest">🎮 Jugar</a>
                    <a href="#equipos" class="nav-link text-gray-300 hover:text-[#de9b35] transition uppercase text-sm tracking-widest">Equipos</a>
                    <a href="#crear-equipo" class="nav-link text-gray-300 hover:text-[#de9b35] transition uppercase text-sm tracking-widest">Crear Equipo</a>
                    <a href="#minecraft" class="nav-link text-gray-300 hover:text-[#39ff14] transition uppercase text-sm tracking-widest">⛏️ Minecraft</a>
                    <button id="loginBtn" onclick="openLoginModal()" class="btn-gamer px-6 py-2 rounded font-bold uppercase text-sm">Iniciar Sesión</button>
                    <div id="userMenu" class="hidden"></div>
                </div>
                <div class="md:hidden">
                    <button id="menuBtn" class="text-[#de9b35] text-3xl">☰</button>
                </div>
            </div>
        </div>
        <!-- Mobile Menu -->
        <div id="mobileMenu" class="hidden md:hidden bg-[#0a0a0f]/95 border-t border-[#de9b35]/30 px-4 py-4">
            <a href="#inicio" class="block py-3 text-gray-300 hover:text-[#de9b35] uppercase tracking-widest">Inicio</a>
            <a href="#torneos" class="block py-3 text-gray-300 hover:text-[#de9b35] uppercase tracking-widest">Torneos</a>
            <a href="#jugar" class="block py-3 text-gray-300 hover:text-[#39ff14] uppercase tracking-widest">🎮 Jugar</a>
            <a href="#equipos" class="block py-3 text-gray-300 hover:text-[#de9b35] uppercase tracking-widest">Equipos</a>
            <a href="#crear-equipo" class="block py-3 text-gray-300 hover:text-[#de9b35] uppercase tracking-widest">Crear Equipo</a>
            <a href="#minecraft" class="block py-3 text-gray-300 hover:text-[#39ff14] uppercase tracking-widest">⛏️ Minecraft</a>
            <button id="loginBtnMobile" onclick="openLoginModal()" class="mt-4 w-full btn-gamer px-6 py-3 rounded font-bold uppercase">Iniciar Sesión</button>
            <div id="userMenuMobile" class="hidden"></div>
        </div>
    </nav>

    <!-- Hero Section -->
    <section id="inicio" class="min-h-screen flex items-center justify-center relative overflow-hidden">
        <div class="absolute inset-0">
            <div class="absolute top-1/4 left-1/4 w-96 h-96 bg-[#de9b35]/10 rounded-full filter blur-3xl animate-pulse"></div>
            <div class="absolute bottom-1/4 right-1/4 w-96 h-96 bg-[#00fff5]/10 rounded-full filter blur-3xl animate-pulse" style="animation-delay: 1s;"></div>
        </div>
        
        <div class="text-center px-4 z-10 fade-in">
            <div class="mb-6 flex flex-wrap justify-center gap-3">
                <span class="free-badge px-6 py-2 rounded-full text-black font-bold text-lg">
                    🎮 100% GRATIS - SIN COSTOS OCULTOS
                </span>
            </div>
            <h1 class="text-5xl md:text-8xl font-bold mb-4 glitch neon-text" data-text="FRAGX">FRAGX</h1>
            <p class="text-2xl md:text-4xl text-[#00fff5] neon-text-cyan mb-4">TORNEOS DE COUNTER-STRIKE 2</p>
            <p class="text-gray-400 text-lg md:text-xl mb-10 max-w-3xl mx-auto">
                Crea tu equipo, únete a torneos competitivos y demuestra que eres el mejor. 
                <span class="text-[#39ff14] font-bold">Todo completamente gratis.</span> Sin suscripciones, sin pagos, sin límites.
            </p>
            
            <div class="flex flex-col sm:flex-row gap-4 justify-center mb-10">
                <button onclick="scrollToSection('crear-equipo')" class="btn-gamer btn-green px-10 py-4 rounded font-bold uppercase tracking-widest text-lg pulse-glow">
                    🎯 Crear Mi Equipo GRATIS
                </button>
                <button onclick="scrollToSection('torneos')" class="btn-gamer px-10 py-4 rounded font-bold uppercase tracking-widest text-lg">
                    🏆 Ver Torneos Activos
                </button>
            </div>

            <!-- Live Stats -->
            <div class="flex flex-wrap justify-center gap-6 text-sm">
                <div class="flex items-center gap-2 bg-[#12121a] px-4 py-2 rounded-lg border border-[#39ff14]/30">
                    <span class="w-3 h-3 bg-[#39ff14] rounded-full live-dot"></span>
                    <span class="text-[#39ff14]"><span id="onlineCount">1</span> jugador<span id="onlinePlural">es</span> online</span>
                </div>
                <div class="flex items-center gap-2 bg-[#12121a] px-4 py-2 rounded-lg border border-[#de9b35]/30">
                    <span class="text-[#de9b35]">🏆 6 torneos disponibles</span>
                </div>
                <div class="flex items-center gap-2 bg-[#12121a] px-4 py-2 rounded-lg border border-[#00fff5]/30">
                    <span class="text-[#00fff5]">👥 <span id="teamsCount">0</span> equipos registrados</span>
                </div>
            </div>

            <!-- Scroll Indicator -->
            <div class="absolute bottom-10 left-1/2 transform -translate-x-1/2 animate-bounce">
                <span class="text-[#de9b35] text-3xl">⌄</span>
            </div>
        </div>
    </section>

    <!-- Stats Section -->
    <section class="py-16 relative border-y border-[#de9b35]/20">
        <div class="max-w-7xl mx-auto px-4">
            <div class="grid grid-cols-2 md:grid-cols-4 gap-6">
                <div class="text-center p-6 gamer-card rounded-lg">
                    <div class="text-4xl md:text-5xl font-bold text-[#de9b35] neon-text stat-number" id="statTeams">0</div>
                    <p class="text-gray-400 mt-2 uppercase tracking-widest text-sm">Equipos Creados</p>
                    <div class="mt-2 text-2xl">👥</div>
                </div>
                <div class="text-center p-6 gamer-card rounded-lg">
                    <div class="text-4xl md:text-5xl font-bold text-[#00fff5] neon-text-cyan stat-number" id="statPlayers">0</div>
                    <p class="text-gray-400 mt-2 uppercase tracking-widest text-sm">Jugadores Registrados</p>
                    <div class="mt-2 text-2xl">🎮</div>
                </div>
                <div class="text-center p-6 gamer-card rounded-lg">
                    <div class="text-4xl md:text-5xl font-bold text-[#39ff14] neon-text-green stat-number">6</div>
                    <p class="text-gray-400 mt-2 uppercase tracking-widest text-sm">Torneos Disponibles</p>
                    <div class="mt-2 text-2xl">🏆</div>
                </div>
                <div class="text-center p-6 gamer-card rounded-lg">
                    <div class="text-4xl md:text-5xl font-bold text-[#ff00ff] stat-number">$0</div>
                    <p class="text-gray-400 mt-2 uppercase tracking-widest text-sm">Costo Total</p>
                    <div class="mt-2 text-2xl">💚</div>
                </div>
            </div>
        </div>
    </section>

    <!-- Torneos Section -->
    <section id="torneos" class="py-24 relative">
        <div class="max-w-7xl mx-auto px-4">
            <div class="text-center mb-16">
                <span class="inline-block px-4 py-2 bg-[#de9b35]/10 text-[#de9b35] text-sm uppercase tracking-widest rounded mb-4">
                    🏆 Torneos Activos
                </span>
                <h2 class="text-4xl md:text-5xl font-bold text-white mb-4">COMPITE <span class="text-[#de9b35] neon-text">GRATIS</span></h2>
                <p class="text-gray-400 text-lg">Inscribe a tu equipo y demuestra tu skill</p>
            </div>
            
            <div class="grid md:grid-cols-2 lg:grid-cols-3 gap-8">
                <!-- Torneo 1 -->
                <div class="gamer-card rounded-lg overflow-hidden cursor-pointer" onclick="openTournamentModal('weekly')">
                    <div class="h-48 bg-gradient-to-br from-orange-600 to-red-600 flex items-center justify-center relative">
                        <span class="text-7xl">🏆</span>
                        <div class="absolute top-4 left-4 flex items-center gap-2">
                            <span class="w-3 h-3 bg-[#39ff14] rounded-full live-dot"></span>
                            <span class="text-white text-sm font-bold">EN VIVO</span>
                        </div>
                        <div class="absolute top-4 right-4 free-badge px-3 py-1 rounded text-black text-sm font-bold">GRATIS</div>
                    </div>
                    <div class="p-6">
                        <h3 class="text-xl font-bold text-white mb-2">Weekly Championship</h3>
                        <p class="text-gray-400 mb-4">Torneo semanal 5v5 • Formato eliminación</p>
                        <div class="flex justify-between items-center text-sm">
                            <span class="text-[#00fff5]">👥 <span id="count-weekly">0/32 equipos</span></span>
                            <span class="text-[#de9b35]">⏰ Hoy 20:00</span>
                        </div>
                        <button class="mt-4 w-full btn-gamer py-2 rounded font-bold uppercase text-sm">Inscribir Equipo</button>
                    </div>
                </div>

                <!-- Torneo 2 -->
                <div class="gamer-card rounded-lg overflow-hidden cursor-pointer" onclick="openTournamentModal('monthly')">
                    <div class="h-48 bg-gradient-to-br from-purple-600 to-pink-600 flex items-center justify-center relative">
                        <span class="text-7xl">👑</span>
                        <div class="absolute top-4 right-4 free-badge px-3 py-1 rounded text-black text-sm font-bold">GRATIS</div>
                    </div>
                    <div class="p-6">
                        <h3 class="text-xl font-bold text-white mb-2">Monthly Masters</h3>
                        <p class="text-gray-400 mb-4">Torneo mensual 5v5 • Fase de grupos + Playoffs</p>
                        <div class="flex justify-between items-center text-sm">
                            <span class="text-[#00fff5]">👥 <span id="count-monthly">0/64 equipos</span></span>
                            <span class="text-[#de9b35]">📅 15 Dic</span>
                        </div>
                        <button class="mt-4 w-full btn-gamer py-2 rounded font-bold uppercase text-sm">Inscribir Equipo</button>
                    </div>
                </div>

                <!-- Torneo 3 -->
                <div class="gamer-card rounded-lg overflow-hidden cursor-pointer" onclick="openTournamentModal('rookie')">
                    <div class="h-48 bg-gradient-to-br from-green-600 to-teal-600 flex items-center justify-center relative">
                        <span class="text-7xl">🌟</span>
                        <div class="absolute top-4 right-4 free-badge px-3 py-1 rounded text-black text-sm font-bold">GRATIS</div>
                    </div>
                    <div class="p-6">
                        <h3 class="text-xl font-bold text-white mb-2">Rookie League</h3>
                        <p class="text-gray-400 mb-4">Para equipos nuevos • Ambiente amigable</p>
                        <div class="flex justify-between items-center text-sm">
                            <span class="text-[#00fff5]">👥 <span id="count-rookie">0/16 equipos</span></span>
                            <span class="text-[#de9b35]">📅 Domingos</span>
                        </div>
                        <button class="mt-4 w-full btn-gamer py-2 rounded font-bold uppercase text-sm">Inscribir Equipo</button>
                    </div>
                </div>

                <!-- Torneo 4 -->
                <div class="gamer-card rounded-lg overflow-hidden cursor-pointer" onclick="openPlayModal('aim')">
                    <div class="h-48 bg-gradient-to-br from-cyan-600 to-blue-600 flex items-center justify-center relative">
                        <span class="text-7xl">🎯</span>
                        <div class="absolute top-4 right-4 free-badge px-3 py-1 rounded text-black text-sm font-bold">GRATIS</div>
                        <div class="absolute bottom-4 left-4 flex gap-2">
                            <span class="bg-[#39ff14]/20 text-[#39ff14] px-2 py-1 rounded text-xs">🤖 Bots</span>
                            <span class="bg-[#00fff5]/20 text-[#00fff5] px-2 py-1 rounded text-xs">👥 Online</span>
                        </div>
                    </div>
                    <div class="p-6">
                        <h3 class="text-xl font-bold text-white mb-2">Aim Arena 1v1</h3>
                        <p class="text-gray-400 mb-4">Duelos individuales • Demuestra tu aim</p>
                        <div class="flex justify-between items-center text-sm">
                            <span class="text-[#00fff5]">👤 <span id="count-aim">0/128 players</span></span>
                            <span class="text-[#de9b35]">⏰ Diario</span>
                        </div>
                        <button class="mt-4 w-full btn-gamer py-2 rounded font-bold uppercase text-sm">🎮 Jugar Ahora</button>
                    </div>
                </div>

                <!-- Torneo 5 -->
                <div class="gamer-card rounded-lg overflow-hidden cursor-pointer" onclick="openPlayModal('wingman')">
                    <div class="h-48 bg-gradient-to-br from-yellow-600 to-orange-600 flex items-center justify-center relative">
                        <span class="text-7xl">🤝</span>
                        <div class="absolute top-4 right-4 free-badge px-3 py-1 rounded text-black text-sm font-bold">GRATIS</div>
                        <div class="absolute bottom-4 left-4 flex gap-2">
                            <span class="bg-[#39ff14]/20 text-[#39ff14] px-2 py-1 rounded text-xs">🤖 Bots</span>
                            <span class="bg-[#00fff5]/20 text-[#00fff5] px-2 py-1 rounded text-xs">👥 Online</span>
                        </div>
                    </div>
                    <div class="p-6">
                        <h3 class="text-xl font-bold text-white mb-2">Wingman Cup</h3>
                        <p class="text-gray-400 mb-4">Parejas 2v2 • Formato rápido</p>
                        <div class="flex justify-between items-center text-sm">
                            <span class="text-[#00fff5]">👥 <span id="count-wingman">0/32 parejas</span></span>
                            <span class="text-[#de9b35]">📅 Sábados</span>
                        </div>
                        <button class="mt-4 w-full btn-gamer py-2 rounded font-bold uppercase text-sm">🎮 Jugar Ahora</button>
                    </div>
                </div>

                <!-- Torneo 6 -->
                <div class="gamer-card rounded-lg overflow-hidden cursor-pointer" onclick="openPlayModal('retake')">
                    <div class="h-48 bg-gradient-to-br from-red-600 to-pink-600 flex items-center justify-center relative">
                        <span class="text-7xl">💣</span>
                        <div class="absolute top-4 right-4 free-badge px-3 py-1 rounded text-black text-sm font-bold">GRATIS</div>
                        <div class="absolute bottom-4 left-4 flex gap-2">
                            <span class="bg-[#39ff14]/20 text-[#39ff14] px-2 py-1 rounded text-xs">🤖 Bots</span>
                            <span class="bg-[#00fff5]/20 text-[#00fff5] px-2 py-1 rounded text-xs">👥 Online</span>
                        </div>
                    </div>
                    <div class="p-6">
                        <h3 class="text-xl font-bold text-white mb-2">Retake Masters</h3>
                        <p class="text-gray-400 mb-4">Modo retake competitivo • Mejora tu clutch</p>
                        <div class="flex justify-between items-center text-sm">
                            <span class="text-[#00fff5]">👤 <span id="count-retake">0 players</span></span>
                            <span class="text-[#de9b35]">⏰ 24/7</span>
                        </div>
                        <button class="mt-4 w-full btn-gamer py-2 rounded font-bold uppercase text-sm">🎮 Jugar Ahora</button>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Equipos Section -->
    <section id="equipos" class="py-24 bg-[#0d0d14] relative">
        <div class="max-w-7xl mx-auto px-4">
            <div class="text-center mb-16">
                <span class="inline-block px-4 py-2 bg-[#00fff5]/10 text-[#00fff5] text-sm uppercase tracking-widest rounded mb-4">
                    👥 Equipos Destacados
                </span>
                <h2 class="text-4xl md:text-5xl font-bold text-white mb-4">TOP <span class="text-[#00fff5] neon-text-cyan">EQUIPOS</span></h2>
                <p class="text-gray-400 text-lg">Los mejores equipos de la comunidad</p>
            </div>
            
            <div class="grid md:grid-cols-2 lg:grid-cols-4 gap-6" id="teamsGrid">
                <!-- Se llena dinámicamente -->
            </div>
            
            <div id="noTeamsMessage" class="text-center py-12">
                <span class="text-6xl mb-4 block">👥</span>
                <p class="text-gray-400 text-lg mb-2">Aún no hay equipos registrados</p>
                <p class="text-gray-500 mb-4">¡Sé el primero en crear un equipo y aparecer aquí!</p>
                <button onclick="scrollToSection('crear-equipo')" class="btn-gamer btn-green px-8 py-3 rounded font-bold uppercase tracking-widest pulse-glow">
                    🎮 Crear Primer Equipo
                </button>
            </div>

            <div id="showAllTeamsBtn" class="text-center mt-10 hidden">
                <button onclick="showAllTeams()" class="btn-gamer px-8 py-3 rounded font-bold uppercase tracking-widest">
                    Ver Todos los Equipos
                </button>
            </div>
        </div>
    </section>

    <!-- Quick Play Section -->
    <section id="jugar" class="py-24 relative">
        <div class="max-w-7xl mx-auto px-4">
            <div class="text-center mb-16">
                <span class="inline-block px-4 py-2 bg-[#39ff14]/10 text-[#39ff14] text-sm uppercase tracking-widest rounded mb-4">
                    🎮 Juego Rápido
                </span>
                <h2 class="text-4xl md:text-5xl font-bold text-white mb-4">PRACTICA <span class="text-[#39ff14] neon-text-green">AHORA</span></h2>
                <p class="text-gray-400 text-lg">Elige tu modo y empieza a jugar al instante</p>
            </div>
            
            <div class="grid md:grid-cols-2 lg:grid-cols-4 gap-6">
                <!-- Deathmatch -->
                <div class="gamer-card rounded-lg p-6 text-center cursor-pointer hover:scale-105 transition" onclick="openPlayModal('deathmatch')">
                    <span class="text-5xl mb-4 block">💀</span>
                    <h3 class="text-xl font-bold text-white mb-2">Deathmatch</h3>
                    <p class="text-gray-400 text-sm mb-4">Practica tu aim en caos total</p>
                    <p class="text-[#39ff14] text-xs mb-2">🎮 <span id="count-deathmatch">0 players</span> jugando</p>
                    <div class="flex justify-center gap-2 mb-4">
                        <span class="bg-[#39ff14]/20 text-[#39ff14] px-2 py-1 rounded text-xs">🤖 Bots</span>
                        <span class="bg-[#00fff5]/20 text-[#00fff5] px-2 py-1 rounded text-xs">👥 Online</span>
                    </div>
                    <button class="w-full btn-gamer btn-green py-2 rounded font-bold uppercase text-sm">Jugar</button>
                </div>

                <!-- Competitive -->
                <div class="gamer-card rounded-lg p-6 text-center cursor-pointer hover:scale-105 transition" onclick="openPlayModal('competitive')">
                    <span class="text-5xl mb-4 block">🏆</span>
                    <h3 class="text-xl font-bold text-white mb-2">Competitive</h3>
                    <p class="text-gray-400 text-sm mb-4">5v5 clásico competitivo</p>
                    <p class="text-[#39ff14] text-xs mb-2">🎮 <span id="count-competitive">0 players</span> jugando</p>
                    <div class="flex justify-center gap-2 mb-4">
                        <span class="bg-[#39ff14]/20 text-[#39ff14] px-2 py-1 rounded text-xs">🤖 Bots</span>
                        <span class="bg-[#00fff5]/20 text-[#00fff5] px-2 py-1 rounded text-xs">👥 Online</span>
                    </div>
                    <button class="w-full btn-gamer btn-green py-2 rounded font-bold uppercase text-sm">Jugar</button>
                </div>

                <!-- Aim Training -->
                <div class="gamer-card rounded-lg p-6 text-center cursor-pointer hover:scale-105 transition" onclick="openPlayModal('aim')">
                    <span class="text-5xl mb-4 block">🎯</span>
                    <h3 class="text-xl font-bold text-white mb-2">Aim Training</h3>
                    <p class="text-gray-400 text-sm mb-4">Mejora tu puntería</p>
                    <p class="text-[#39ff14] text-xs mb-2">🎮 <span id="count-aim-quick">0 players</span> jugando</p>
                    <div class="flex justify-center gap-2 mb-4">
                        <span class="bg-[#39ff14]/20 text-[#39ff14] px-2 py-1 rounded text-xs">🤖 Bots</span>
                        <span class="bg-[#00fff5]/20 text-[#00fff5] px-2 py-1 rounded text-xs">👥 Online</span>
                    </div>
                    <button class="w-full btn-gamer btn-green py-2 rounded font-bold uppercase text-sm">Jugar</button>
                </div>

                <!-- Retake -->
                <div class="gamer-card rounded-lg p-6 text-center cursor-pointer hover:scale-105 transition" onclick="openPlayModal('retake')">
                    <span class="text-5xl mb-4 block">💣</span>
                    <h3 class="text-xl font-bold text-white mb-2">Retake</h3>
                    <p class="text-gray-400 text-sm mb-4">Practica post-plant</p>
                    <p class="text-[#39ff14] text-xs mb-2">🎮 <span id="count-retake-quick">0 players</span> jugando</p>
                    <div class="flex justify-center gap-2 mb-4">
                        <span class="bg-[#39ff14]/20 text-[#39ff14] px-2 py-1 rounded text-xs">🤖 Bots</span>
                        <span class="bg-[#00fff5]/20 text-[#00fff5] px-2 py-1 rounded text-xs">👥 Online</span>
                    </div>
                    <button class="w-full btn-gamer btn-green py-2 rounded font-bold uppercase text-sm">Jugar</button>
                </div>
            </div>

            <div class="text-center mt-10">
                <p class="text-gray-500 text-sm">💡 Todos los modos abren Counter-Strike 2 automáticamente vía Steam</p>
            </div>
        </div>
    </section>

    <!-- Ranking Section -->
    <section id="ranking" class="py-24 relative">
        <div class="max-w-5xl mx-auto px-4">
            <div class="text-center mb-16">
                <span class="inline-block px-4 py-2 bg-[#ffd700]/10 text-[#ffd700] text-sm uppercase tracking-widest rounded mb-4">
                    📊 Leaderboard
                </span>
                <h2 class="text-4xl md:text-5xl font-bold text-white mb-4">RANKING <span class="text-[#ffd700]">GLOBAL</span></h2>
                <p class="text-gray-400 text-lg">Top jugadores de la comunidad</p>
            </div>
            
            <div class="gamer-card rounded-lg overflow-hidden">
                <div class="bg-[#1a1a2e] p-4 border-b border-gray-700 grid grid-cols-12 gap-4 text-sm font-bold text-gray-400 uppercase">
                    <div class="col-span-1">#</div>
                    <div class="col-span-4">Jugador</div>
                    <div class="col-span-2 text-center">Rango</div>
                    <div class="col-span-2 text-center">K/D</div>
                    <div class="col-span-2 text-center">Win Rate</div>
                    <div class="col-span-1 text-center">ELO</div>
                </div>
                
                <div id="rankingList">
                    <!-- Se mostrará dinámicamente basado en equipos reales -->
                </div>
                <div id="noRankingData" class="p-8 text-center">
                    <span class="text-6xl mb-4 block">🎮</span>
                    <p class="text-gray-400 text-lg mb-2">Aún no hay jugadores en el ranking</p>
                    <p class="text-gray-500">¡Crea tu equipo y sé el primero en aparecer aquí!</p>
                    <button onclick="scrollToSection('crear-equipo')" class="mt-4 btn-gamer btn-green px-6 py-2 rounded font-bold uppercase text-sm">
                        Crear Mi Equipo
                    </button>
                </div>
            </div>

            <div class="text-center mt-8">
                <button onclick="showFullRanking()" class="btn-gamer px-8 py-3 rounded font-bold uppercase tracking-widest">
                    Ver Ranking Completo
                </button>
            </div>
        </div>
    </section>

    <!-- Crear Equipo Section -->
    <section id="crear-equipo" class="py-24 bg-[#0d0d14] relative">
        <div class="max-w-4xl mx-auto px-4">
            <div class="text-center mb-12">
                <span class="free-badge inline-block px-6 py-2 rounded-full text-black font-bold text-lg mb-4">
                    🎮 100% GRATIS - CREA TU EQUIPO AHORA
                </span>
                <h2 class="text-4xl md:text-5xl font-bold text-white mb-4">CREA TU <span class="text-[#39ff14] neon-text-green">EQUIPO</span></h2>
                <p class="text-gray-400 text-lg">Arma tu squad y domina los torneos de CS2</p>
            </div>
            
            <form id="createTeamForm" class="gamer-card rounded-lg p-8 rgb-border">
                <div class="grid md:grid-cols-2 gap-6">
                    <div>
                        <label class="block text-[#de9b35] font-bold mb-2 uppercase text-sm tracking-widest">🏷️ Nombre del Equipo *</label>
                        <input type="text" id="teamName" required class="w-full px-4 py-3 bg-[#0a0a0f] border border-gray-700 rounded text-white focus:border-[#de9b35] focus:ring-1 focus:ring-[#de9b35] outline-none transition placeholder-gray-600" placeholder="Ej: Neon Strikers">
                    </div>
                    <div>
                        <label class="block text-[#de9b35] font-bold mb-2 uppercase text-sm tracking-widest">🔤 Tag del Equipo *</label>
                        <input type="text" id="teamTag" required maxlength="5" class="w-full px-4 py-3 bg-[#0a0a0f] border border-gray-700 rounded text-white focus:border-[#de9b35] focus:ring-1 focus:ring-[#de9b35] outline-none transition placeholder-gray-600 uppercase" placeholder="Ej: NEON">
                    </div>
                </div>

                <div class="mt-6">
                    <label class="block text-[#00fff5] font-bold mb-2 uppercase text-sm tracking-widest">👤 Tu Nombre de Capitán (Steam) *</label>
                    <input type="text" id="captainName" required class="w-full px-4 py-3 bg-[#0a0a0f] border border-gray-700 rounded text-white focus:border-[#00fff5] focus:ring-1 focus:ring-[#00fff5] outline-none transition placeholder-gray-600" placeholder="Tu nombre de Steam">
                </div>

                <div class="mt-6">
                    <label class="block text-[#39ff14] font-bold mb-2 uppercase text-sm tracking-widest">📧 Email de Contacto *</label>
                    <input type="email" id="teamEmail" required class="w-full px-4 py-3 bg-[#0a0a0f] border border-gray-700 rounded text-white focus:border-[#39ff14] focus:ring-1 focus:ring-[#39ff14] outline-none transition placeholder-gray-600" placeholder="tu@email.com">
                </div>

                <div class="mt-6">
                    <label class="block text-[#ff00ff] font-bold mb-2 uppercase text-sm tracking-widest">🌎 Región</label>
                    <select id="teamRegion" class="w-full px-4 py-3 bg-[#0a0a0f] border border-gray-700 rounded text-white focus:border-[#ff00ff] focus:ring-1 focus:ring-[#ff00ff] outline-none transition">
                        <option value="latam">🌎 Latinoamérica</option>
                        <option value="na">🇺🇸 Norteamérica</option>
                        <option value="eu">🇪🇺 Europa</option>
                        <option value="asia">🌏 Asia</option>
                    </select>
                </div>

                <div class="mt-6">
                    <label class="block text-[#9146ff] font-bold mb-3 uppercase text-sm tracking-widest">👥 Miembros del Equipo (opcional)</label>
                    <p class="text-gray-500 text-sm mb-3">Puedes agregar miembros después. Necesitas mínimo 5 para torneos 5v5.</p>
                    <div class="space-y-3" id="membersContainer">
                        <div class="flex gap-2">
                            <input type="text" class="member-input flex-1 px-4 py-2 bg-[#0a0a0f] border border-gray-700 rounded text-white placeholder-gray-600" placeholder="Nombre Steam del jugador 2">
                            <button type="button" onclick="removeMember(this)" class="px-3 py-2 bg-red-600/20 text-red-500 rounded hover:bg-red-600 hover:text-white transition">✕</button>
                        </div>
                        <div class="flex gap-2">
                            <input type="text" class="member-input flex-1 px-4 py-2 bg-[#0a0a0f] border border-gray-700 rounded text-white placeholder-gray-600" placeholder="Nombre Steam del jugador 3">
                            <button type="button" onclick="removeMember(this)" class="px-3 py-2 bg-red-600/20 text-red-500 rounded hover:bg-red-600 hover:text-white transition">✕</button>
                        </div>
                        <div class="flex gap-2">
                            <input type="text" class="member-input flex-1 px-4 py-2 bg-[#0a0a0f] border border-gray-700 rounded text-white placeholder-gray-600" placeholder="Nombre Steam del jugador 4">
                            <button type="button" onclick="removeMember(this)" class="px-3 py-2 bg-red-600/20 text-red-500 rounded hover:bg-red-600 hover:text-white transition">✕</button>
                        </div>
                        <div class="flex gap-2">
                            <input type="text" class="member-input flex-1 px-4 py-2 bg-[#0a0a0f] border border-gray-700 rounded text-white placeholder-gray-600" placeholder="Nombre Steam del jugador 5">
                            <button type="button" onclick="removeMember(this)" class="px-3 py-2 bg-red-600/20 text-red-500 rounded hover:bg-red-600 hover:text-white transition">✕</button>
                        </div>
                    </div>
                    <button type="button" onclick="addMember()" class="mt-3 text-[#39ff14] hover:underline text-sm">+ Agregar más jugadores</button>
                </div>

                <div class="mt-6 p-4 bg-[#39ff14]/10 rounded-lg border border-[#39ff14]/30">
                    <p class="text-[#39ff14] font-bold flex items-center gap-2">
                        <span class="text-2xl">💚</span>
                        <span>Crear equipo es 100% GRATIS. Sin costos ocultos, sin suscripciones.</span>
                    </p>
                </div>

                <button type="submit" id="createTeamBtn" class="mt-8 w-full btn-gamer btn-green py-4 rounded font-bold uppercase tracking-widest text-lg pulse-glow">
                    🎮 Crear Equipo GRATIS
                </button>
            </form>
        </div>
    </section>

    <!-- CTA Section -->
    <section class="py-20 relative">
        <div class="max-w-4xl mx-auto px-4 text-center">
            <div class="gamer-card rounded-lg p-12 border-2 border-[#39ff14]/50">
                <span class="text-6xl mb-6 block">🎯</span>
                <h2 class="text-3xl md:text-4xl font-bold text-white mb-4">¿BUSCAS EQUIPO?</h2>
                <p class="text-gray-400 text-lg mb-8">Si no tienes equipo, puedes buscar uno que necesite jugadores o unirte a partidas públicas.</p>
                <div class="flex flex-col sm:flex-row gap-4 justify-center">
                    <button onclick="openFindTeamModal()" class="btn-gamer px-8 py-4 rounded font-bold uppercase tracking-widest">
                        🔍 Buscar Equipo
                    </button>
                    <button onclick="openPublicMatchesModal()" class="btn-gamer btn-green px-8 py-4 rounded font-bold uppercase tracking-widest">
                        🎮 Partidas Públicas
                    </button>
                </div>
            </div>
        </div>
    </section>

    <!-- ==================== MINECRAFT SECTION ==================== -->
    <section id="minecraft" class="py-24 relative" style="background: linear-gradient(180deg, #0a0a0f 0%, #1a3a1a 50%, #0a0a0f 100%);">
        <div class="absolute inset-0 opacity-20" style="background-image: url('data:image/svg+xml,<svg xmlns=\"http://www.w3.org/2000/svg\" width=\"16\" height=\"16\" viewBox=\"0 0 16 16\"><rect width=\"8\" height=\"8\" fill=\"%23228B22\"/><rect x=\"8\" width=\"8\" height=\"8\" fill=\"%23006400\"/><rect y=\"8\" width=\"8\" height=\"8\" fill=\"%23006400\"/><rect x=\"8\" y=\"8\" width=\"8\" height=\"8\" fill=\"%23228B22\"/></svg>'); background-size: 32px 32px;"></div>
        
        <div class="max-w-7xl mx-auto px-4 relative z-10">
            <!-- Header Minecraft -->
            <div class="text-center mb-16">
                <div class="mb-6 flex flex-wrap justify-center gap-3">
                    <span class="px-6 py-2 rounded-full text-white font-bold text-lg bg-gradient-to-r from-[#228B22] to-[#32CD32]">
                        ⛏️ SERVIDOR ANÁRQUICO
                    </span>
                </div>
                <h2 class="text-5xl md:text-7xl font-bold mb-4 text-[#39ff14]" style="text-shadow: 0 0 20px #39ff14, 0 0 40px #39ff14;">
                    INFECTION.FUN
                </h2>
                <p class="text-2xl md:text-3xl text-white mb-4">☠️ MINECRAFT ANARCHY SERVER ☠️</p>
                <p class="text-gray-400 text-lg md:text-xl mb-6 max-w-3xl mx-auto">
                    Sin reglas. Sin límites. Crea tu clan, domina el servidor y destruye a tus enemigos.
                    <span class="text-[#39ff14] font-bold">100% GRATIS.</span> Puro caos y supervivencia.
                </p>
                
                <!-- Server Info -->
                <div class="flex flex-wrap justify-center gap-4 mb-8">
                    <div class="bg-[#12121a] px-6 py-3 rounded-lg border border-[#39ff14]/50 flex items-center gap-3">
                        <span class="w-3 h-3 bg-[#39ff14] rounded-full live-dot"></span>
                        <span class="text-[#39ff14] font-bold">SERVIDOR ONLINE</span>
                    </div>
                    <div class="bg-[#12121a] px-6 py-3 rounded-lg border border-[#39ff14]/30">
                        <span class="text-white font-mono font-bold">IP: infection.fun</span>
                    </div>
                    <div class="bg-[#12121a] px-6 py-3 rounded-lg border border-[#39ff14]/30">
                        <span class="text-gray-400">Versión: <span class="text-white">1.20.x</span></span>
                    </div>
                </div>

                <button onclick="copyServerIP()" class="btn-gamer btn-green px-10 py-4 rounded font-bold uppercase tracking-widest text-lg pulse-glow">
                    📋 Copiar IP del Servidor
                </button>
            </div>

            <!-- Stats Minecraft -->
            <div class="grid grid-cols-2 md:grid-cols-4 gap-6 mb-16">
                <div class="text-center p-6 gamer-card rounded-lg border border-[#39ff14]/30">
                    <div class="text-4xl md:text-5xl font-bold text-[#39ff14] stat-number" id="statClans">0</div>
                    <p class="text-gray-400 mt-2 uppercase tracking-widest text-sm">Clanes Activos</p>
                    <div class="mt-2 text-2xl">⚔️</div>
                </div>
                <div class="text-center p-6 gamer-card rounded-lg border border-[#39ff14]/30">
                    <div class="text-4xl md:text-5xl font-bold text-[#ff4444] stat-number" id="statMcPlayers">0</div>
                    <p class="text-gray-400 mt-2 uppercase tracking-widest text-sm">Miembros Totales</p>
                    <div class="mt-2 text-2xl">💀</div>
                </div>
                <div class="text-center p-6 gamer-card rounded-lg border border-[#39ff14]/30">
                    <div class="text-4xl md:text-5xl font-bold text-[#ffd700] stat-number">∞</div>
                    <p class="text-gray-400 mt-2 uppercase tracking-widest text-sm">Mapa Sin Límites</p>
                    <div class="mt-2 text-2xl">🗺️</div>
                </div>
                <div class="text-center p-6 gamer-card rounded-lg border border-[#39ff14]/30">
                    <div class="text-4xl md:text-5xl font-bold text-[#ff00ff] stat-number">0</div>
                    <p class="text-gray-400 mt-2 uppercase tracking-widest text-sm">Reglas</p>
                    <div class="mt-2 text-2xl">🔥</div>
                </div>
            </div>

            <!-- Clanes Destacados -->
            <div class="mb-16">
                <div class="text-center mb-10">
                    <span class="inline-block px-4 py-2 bg-[#ff4444]/10 text-[#ff4444] text-sm uppercase tracking-widest rounded mb-4">
                        ⚔️ Clanes del Servidor
                    </span>
                    <h3 class="text-3xl md:text-4xl font-bold text-white">CLANES <span class="text-[#ff4444]">DOMINANTES</span></h3>
                </div>
                
                <div class="grid md:grid-cols-2 lg:grid-cols-4 gap-6" id="clansGrid">
                    <!-- Se llena dinámicamente -->
                </div>
                
                <div id="noClansMessage" class="text-center py-12">
                    <span class="text-6xl mb-4 block">⚔️</span>
                    <p class="text-gray-400 text-lg mb-2">Aún no hay clanes en el servidor</p>
                    <p class="text-gray-500 mb-4">¡Sé el primero en crear un clan y dominar Infection.Fun!</p>
                    <button onclick="scrollToSection('crear-clan')" class="btn-gamer btn-green px-8 py-3 rounded font-bold uppercase tracking-widest pulse-glow">
                        ⚔️ Crear Primer Clan
                    </button>
                </div>
            </div>

            <!-- Características del Servidor -->
            <div class="grid md:grid-cols-3 gap-6 mb-16">
                <div class="gamer-card rounded-lg p-6 text-center border border-[#39ff14]/30 hover:border-[#39ff14]">
                    <span class="text-5xl mb-4 block">💀</span>
                    <h4 class="text-xl font-bold text-white mb-2">SIN REGLAS</h4>
                    <p class="text-gray-400">Griefing, PvP, raiding... todo está permitido. Sobrevive como puedas.</p>
                </div>
                <div class="gamer-card rounded-lg p-6 text-center border border-[#ff4444]/30 hover:border-[#ff4444]">
                    <span class="text-5xl mb-4 block">🏰</span>
                    <h4 class="text-xl font-bold text-white mb-2">BASES ÉPICAS</h4>
                    <p class="text-gray-400">Construye fortalezas impenetrables o destruye las de tus enemigos.</p>
                </div>
                <div class="gamer-card rounded-lg p-6 text-center border border-[#ffd700]/30 hover:border-[#ffd700]">
                    <span class="text-5xl mb-4 block">⚔️</span>
                    <h4 class="text-xl font-bold text-white mb-2">GUERRAS DE CLANES</h4>
                    <p class="text-gray-400">Únete a un clan o crea el tuyo. Conquista territorios y hazte legendario.</p>
                </div>
            </div>

            <!-- Crear Clan Form -->
            <div id="crear-clan" class="max-w-4xl mx-auto">
                <div class="text-center mb-12">
                    <span class="px-6 py-2 rounded-full text-black font-bold text-lg bg-gradient-to-r from-[#39ff14] to-[#00ff88] inline-block mb-4">
                        ⚔️ 100% GRATIS - CREA TU CLAN
                    </span>
                    <h3 class="text-4xl md:text-5xl font-bold text-white mb-4">CREAR <span class="text-[#ff4444]">CLAN</span></h3>
                    <p class="text-gray-400 text-lg">Forma tu ejército y domina Infection.Fun</p>
                </div>
                
                <form id="createClanForm" class="gamer-card rounded-lg p-8" style="border: 2px solid #39ff14; box-shadow: 0 0 30px rgba(57, 255, 20, 0.2);">
                    <div class="grid md:grid-cols-2 gap-6">
                        <div>
                            <label class="block text-[#39ff14] font-bold mb-2 uppercase text-sm tracking-widest">⚔️ Nombre del Clan *</label>
                            <input type="text" id="clanName" required class="w-full px-4 py-3 bg-[#0a0a0f] border border-[#39ff14]/50 rounded text-white focus:border-[#39ff14] focus:ring-1 focus:ring-[#39ff14] outline-none transition placeholder-gray-600" placeholder="Ej: Los Inmortales">
                        </div>
                        <div>
                            <label class="block text-[#39ff14] font-bold mb-2 uppercase text-sm tracking-widest">🏷️ Tag del Clan *</label>
                            <input type="text" id="clanTag" required maxlength="5" class="w-full px-4 py-3 bg-[#0a0a0f] border border-[#39ff14]/50 rounded text-white focus:border-[#39ff14] focus:ring-1 focus:ring-[#39ff14] outline-none transition placeholder-gray-600 uppercase" placeholder="Ej: INMOR">
                        </div>
                    </div>

                    <div class="mt-6">
                        <label class="block text-[#ff4444] font-bold mb-2 uppercase text-sm tracking-widest">👑 Tu Nick de Minecraft (Líder) *</label>
                        <input type="text" id="clanLeader" required class="w-full px-4 py-3 bg-[#0a0a0f] border border-[#ff4444]/50 rounded text-white focus:border-[#ff4444] focus:ring-1 focus:ring-[#ff4444] outline-none transition placeholder-gray-600" placeholder="Tu nombre en Minecraft">
                    </div>

                    <div class="mt-6">
                        <label class="block text-[#ffd700] font-bold mb-2 uppercase text-sm tracking-widest">💬 Discord del Clan (opcional)</label>
                        <input type="text" id="clanDiscord" class="w-full px-4 py-3 bg-[#0a0a0f] border border-[#ffd700]/50 rounded text-white focus:border-[#ffd700] focus:ring-1 focus:ring-[#ffd700] outline-none transition placeholder-gray-600" placeholder="discord.gg/tuservidor">
                    </div>

                    <div class="mt-6">
                        <label class="block text-[#00fff5] font-bold mb-2 uppercase text-sm tracking-widest">🎯 Objetivo del Clan</label>
                        <select id="clanObjective" class="w-full px-4 py-3 bg-[#0a0a0f] border border-[#00fff5]/50 rounded text-white focus:border-[#00fff5] focus:ring-1 focus:ring-[#00fff5] outline-none transition">
                            <option value="pvp">⚔️ PvP y Combate</option>
                            <option value="raiding">💣 Raiding y Griefing</option>
                            <option value="building">🏰 Construcción de Bases</option>
                            <option value="domination">👑 Dominación Total</option>
                            <option value="chaos">🔥 Puro Caos</option>
                        </select>
                    </div>

                    <div class="mt-6">
                        <label class="block text-[#ff00ff] font-bold mb-3 uppercase text-sm tracking-widest">👥 Miembros Iniciales (opcional)</label>
                        <p class="text-gray-500 text-sm mb-3">Agrega los nicks de Minecraft de tus compañeros.</p>
                        <div class="space-y-3" id="clanMembersContainer">
                            <div class="flex gap-2">
                                <input type="text" class="clan-member-input flex-1 px-4 py-2 bg-[#0a0a0f] border border-gray-700 rounded text-white placeholder-gray-600" placeholder="Nick de Minecraft">
                                <button type="button" onclick="removeClanMember(this)" class="px-3 py-2 bg-red-600/20 text-red-500 rounded hover:bg-red-600 hover:text-white transition">✕</button>
                            </div>
                            <div class="flex gap-2">
                                <input type="text" class="clan-member-input flex-1 px-4 py-2 bg-[#0a0a0f] border border-gray-700 rounded text-white placeholder-gray-600" placeholder="Nick de Minecraft">
                                <button type="button" onclick="removeClanMember(this)" class="px-3 py-2 bg-red-600/20 text-red-500 rounded hover:bg-red-600 hover:text-white transition">✕</button>
                            </div>
                        </div>
                        <button type="button" onclick="addClanMember()" class="mt-3 text-[#39ff14] hover:underline text-sm">+ Agregar más miembros</button>
                    </div>

                    <div class="mt-6 p-4 bg-[#ff4444]/10 rounded-lg border border-[#ff4444]/30">
                        <p class="text-[#ff4444] font-bold flex items-center gap-2">
                            <span class="text-2xl">☠️</span>
                            <span>Recuerda: En Infection.Fun NO HAY REGLAS. Tu clan puede ser atacado en cualquier momento.</span>
                        </p>
                    </div>

                    <button type="submit" id="createClanBtn" class="mt-8 w-full py-4 rounded font-bold uppercase tracking-widest text-lg text-black bg-gradient-to-r from-[#39ff14] to-[#00ff88] hover:shadow-[0_0_30px_#39ff14] transition-all">
                        ⚔️ Crear Clan GRATIS
                    </button>
                </form>
            </div>

            <!-- CTA Minecraft -->
            <div class="mt-16 text-center">
                <div class="gamer-card rounded-lg p-12 border-2 border-[#39ff14]/50 max-w-4xl mx-auto">
                    <span class="text-6xl mb-6 block">⛏️</span>
                    <h3 class="text-3xl md:text-4xl font-bold text-white mb-4">¿LISTO PARA EL CAOS?</h3>
                    <p class="text-gray-400 text-lg mb-8">Únete a Infection.Fun y demuestra que eres el más fuerte. Sin reglas, sin piedad.</p>
                    <div class="flex flex-col sm:flex-row gap-4 justify-center">
                        <button onclick="copyServerIP()" class="btn-gamer btn-green px-8 py-4 rounded font-bold uppercase tracking-widest">
                            📋 Copiar IP: infection.fun
                        </button>
                        <button onclick="openMcDiscord()" class="btn-gamer px-8 py-4 rounded font-bold uppercase tracking-widest" style="border-color: #5865f2; color: #5865f2;">
                            💬 Discord del Servidor
                        </button>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer class="bg-[#050508] border-t border-[#de9b35]/20 py-12">
        <div class="max-w-7xl mx-auto px-4">
            <div class="grid md:grid-cols-4 gap-8">
                <div>
                    <div class="flex items-center gap-2 mb-4">
                        <span class="text-2xl">🎯</span>
                        <h3 class="logo text-xl font-bold text-[#de9b35] neon-text">FRAGX</h3>
                    </div>
                    <p class="text-gray-500 mb-4">FRAGX - Plataforma gratuita de torneos de Counter-Strike 2. Crea tu equipo y compite sin límites.</p>
                    <div class="flex items-center gap-2">
                        <span class="w-3 h-3 bg-[#39ff14] rounded-full live-dot"></span>
                        <span class="text-[#39ff14] text-sm">Servidores Online</span>
                    </div>
                </div>
                
                <div>
                    <h4 class="font-bold text-white mb-4 uppercase tracking-widest">Torneos</h4>
                    <ul class="space-y-2 text-gray-500">
                        <li><a href="#" class="hover:text-[#de9b35] transition">▸ Weekly Championship</a></li>
                        <li><a href="#" class="hover:text-[#de9b35] transition">▸ Monthly Masters</a></li>
                        <li><a href="#" class="hover:text-[#de9b35] transition">▸ Rookie League</a></li>
                        <li><a href="#" class="hover:text-[#de9b35] transition">▸ Crear Torneo</a></li>
                    </ul>
                </div>
                
                <div>
                    <h4 class="font-bold text-white mb-4 uppercase tracking-widest">Comunidad</h4>
                    <ul class="space-y-2 text-gray-500">
                        <li><a href="#" onclick="openDiscord()" class="hover:text-[#5865f2] transition">💬 Discord</a></li>
                        <li><a href="#" class="hover:text-[#1da1f2] transition">🐦 Twitter</a></li>
                        <li><a href="#" class="hover:text-[#ff0000] transition">▶️ YouTube</a></li>
                        <li><a href="#" class="hover:text-[#9146ff] transition">📺 Twitch</a></li>
                    </ul>
                </div>
                
                <div>
                    <h4 class="font-bold text-white mb-4 uppercase tracking-widest">Soporte</h4>
                    <ul class="space-y-2 text-gray-500">
                        <li><a href="#" onclick="openFAQ()" class="hover:text-[#de9b35] transition">❓ FAQ</a></li>
                        <li><a href="#" onclick="openRules()" class="hover:text-[#de9b35] transition">📜 Reglas</a></li>
                        <li><a href="#" class="hover:text-[#de9b35] transition">📧 Contacto</a></li>
                        <li><a href="#" onclick="reportBug()" class="hover:text-[#de9b35] transition">🐛 Reportar Bug</a></li>
                    </ul>
                </div>
            </div>
            
            <div class="border-t border-gray-800 mt-8 pt-8 text-center">
                <p class="text-gray-600">© 2024 FRAGX. Plataforma 100% gratuita. <span class="text-[#39ff14]">GG WP 🎮</span></p>
                <p class="text-gray-700 text-sm mt-2">Counter-Strike 2 es marca registrada de Valve Corporation.</p>
            </div>
        </div>
    </footer>

    <!-- Scroll Top Button -->
    <button id="scrollTopBtn" onclick="scrollToTop()" class="fixed bottom-8 right-8 w-14 h-14 bg-[#de9b35] text-black rounded-lg shadow-lg hover:scale-110 transition hidden z-40 text-2xl font-bold pulse-glow">
        ↑
    </button>

    <script>
        // ==================== USER AUTHENTICATION SYSTEM ====================
        // ==================== FRAGX AUTH SYSTEM ====================
        const Auth = {
            currentUser: null,
            
            init() {
                // Cargar usuario guardado
                const savedUser = localStorage.getItem('fragx_user');
                if (savedUser) {
                    this.currentUser = JSON.parse(savedUser);
                    this.updateUI();
                }
            },
            
            // Registro de usuario
            register(userData) {
                const users = this.getUsers();
                
                // Verificar si ya existe
                if (users.find(u => u.email === userData.email)) {
                    return { success: false, message: 'Este email ya está registrado' };
                }
                if (users.find(u => u.username === userData.username)) {
                    return { success: false, message: 'Este nombre de usuario ya existe' };
                }
                
                const newUser = {
                    id: 'user_' + Date.now(),
                    username: userData.username,
                    email: userData.email,
                    password: userData.password, // En producción real esto debería hashearse
                    steamId: userData.steamId || null,
                    minecraftNick: userData.minecraftNick || null,
                    createdAt: new Date().toISOString(),
                    avatar: userData.avatar || this.generateAvatar(userData.username)
                };
                
                users.push(newUser);
                localStorage.setItem('fragx_users', JSON.stringify(users));
                
                // Auto login
                this.login(userData.email, userData.password);
                
                return { success: true, message: '¡Cuenta creada exitosamente!' };
            },
            
            // Login
            login(email, password) {
                const users = this.getUsers();
                const user = users.find(u => u.email === email && u.password === password);
                
                if (user) {
                    this.currentUser = user;
                    localStorage.setItem('fragx_user', JSON.stringify(user));
                    this.updateUI();
                    return { success: true, message: '¡Bienvenido ' + user.username + '!' };
                }
                
                return { success: false, message: 'Email o contraseña incorrectos' };
            },
            
            // Logout
            logout() {
                this.currentUser = null;
                localStorage.removeItem('fragx_user');
                this.updateUI();
                showNotification('Sesión cerrada correctamente', 'info');
            },
            
            // Obtener usuarios
            getUsers() {
                try {
                    return JSON.parse(localStorage.getItem('fragx_users')) || [];
                } catch (e) {
                    return [];
                }
            },
            
            // Verificar si está logueado
            isLoggedIn() {
                return this.currentUser !== null;
            },
            
            // Generar avatar
            generateAvatar(username) {
                const colors = ['de9b35', '39ff14', '00fff5', 'ff00ff', '9146ff', 'ff6a00'];
                const color = colors[Math.floor(Math.random() * colors.length)];
                return `https://ui-avatars.com/api/?name=${encodeURIComponent(username)}&background=${color}&color=fff&bold=true`;
            },
            
            // Actualizar UI según estado de login
            updateUI() {
                const loginBtn = document.getElementById('loginBtn');
                const loginBtnMobile = document.getElementById('loginBtnMobile');
                const userMenu = document.getElementById('userMenu');
                const userMenuMobile = document.getElementById('userMenuMobile');
                
                if (this.isLoggedIn()) {
                    // Desktop
                    if (loginBtn) loginBtn.classList.add('hidden');
                    if (userMenu) {
                        userMenu.classList.remove('hidden');
                        userMenu.innerHTML = `
                            <div class="flex items-center gap-3">
                                <img src="${this.currentUser.avatar}" class="w-8 h-8 rounded-full border-2 border-[#39ff14]" alt="Avatar">
                                <span class="text-[#39ff14] font-bold hidden lg:block">${this.currentUser.username}</span>
                                <button onclick="openUserProfile()" class="text-gray-400 hover:text-[#de9b35] transition" title="Perfil">⚙️</button>
                                <button onclick="Auth.logout()" class="text-gray-400 hover:text-red-500 transition" title="Cerrar sesión">🚪</button>
                            </div>
                        `;
                    }
                    // Mobile
                    if (loginBtnMobile) loginBtnMobile.classList.add('hidden');
                    if (userMenuMobile) {
                        userMenuMobile.classList.remove('hidden');
                        userMenuMobile.innerHTML = `
                            <div class="flex items-center justify-between py-3 border-t border-gray-700 mt-2">
                                <div class="flex items-center gap-3">
                                    <img src="${this.currentUser.avatar}" class="w-10 h-10 rounded-full border-2 border-[#39ff14]" alt="Avatar">
                                    <div>
                                        <p class="text-[#39ff14] font-bold">${this.currentUser.username}</p>
                                        <p class="text-gray-500 text-xs">${this.currentUser.email}</p>
                                    </div>
                                </div>
                                <button onclick="Auth.logout()" class="text-red-500 hover:text-red-400 transition">Salir</button>
                            </div>
                        `;
                    }
                } else {
                    if (loginBtn) loginBtn.classList.remove('hidden');
                    if (userMenu) userMenu.classList.add('hidden');
                    if (loginBtnMobile) loginBtnMobile.classList.remove('hidden');
                    if (userMenuMobile) userMenuMobile.classList.add('hidden');
                }
            },
            
            // Actualizar perfil
            updateProfile(data) {
                if (!this.currentUser) return false;
                
                const users = this.getUsers();
                const index = users.findIndex(u => u.id === this.currentUser.id);
                
                if (index !== -1) {
                    users[index] = { ...users[index], ...data };
                    localStorage.setItem('fragx_users', JSON.stringify(users));
                    this.currentUser = users[index];
                    localStorage.setItem('fragx_user', JSON.stringify(this.currentUser));
                    this.updateUI();
                    return true;
                }
                return false;
            }
        };
        
        // Inicializar Auth
        Auth.init();
        
        // ==================== GAME MODE PLAYERS TRACKER ====================
        const GameTracker = {
            modes: ['weekly', 'monthly', 'rookie', 'aim', 'wingman', 'retake', 'deathmatch', 'competitive'],
            
            init() {
                // Crear canal de comunicación
                if ('BroadcastChannel' in window) {
                    this.channel = new BroadcastChannel('fragx_games');
                    this.channel.onmessage = (event) => {
                        if (event.data.type === 'update') {
                            this.updateAllDisplays();
                        }
                    };
                }
                
                // Limpiar sesiones inactivas cada 10 segundos
                setInterval(() => this.cleanupSessions(), 10000);
                
                // Actualizar displays
                this.updateAllDisplays();
                
                // Detectar cuando el usuario cierra la pestaña
                window.addEventListener('beforeunload', () => this.leaveAllGames());
                window.addEventListener('pagehide', () => this.leaveAllGames());
            },
            
            // Unirse a un modo de juego
            joinGame(mode) {
                const sessions = this.getSessions(mode);
                const sessionId = 'game_' + Date.now() + '_' + Math.random().toString(36).substr(2, 9);
                
                sessions[sessionId] = {
                    timestamp: Date.now(),
                    id: sessionId
                };
                
                localStorage.setItem(`fragx_game_${mode}`, JSON.stringify(sessions));
                localStorage.setItem('fragx_my_game_session', JSON.stringify({ mode, sessionId }));
                
                this.broadcast();
                this.updateAllDisplays();
                
                // Heartbeat para mantener la sesión activa
                this.startHeartbeat(mode, sessionId);
                
                return sessionId;
            },
            
            // Salir de un modo de juego
            leaveGame(mode, sessionId) {
                const sessions = this.getSessions(mode);
                delete sessions[sessionId];
                localStorage.setItem(`fragx_game_${mode}`, JSON.stringify(sessions));
                localStorage.removeItem('fragx_my_game_session');
                this.broadcast();
                this.updateAllDisplays();
            },
            
            // Salir de todos los juegos (al cerrar pestaña)
            leaveAllGames() {
                const mySession = this.getMySession();
                if (mySession) {
                    this.leaveGame(mySession.mode, mySession.sessionId);
                }
            },
            
            // Obtener mi sesión actual
            getMySession() {
                try {
                    return JSON.parse(localStorage.getItem('fragx_my_game_session'));
                } catch (e) {
                    return null;
                }
            },
            
            // Heartbeat para mantener sesión activa
            startHeartbeat(mode, sessionId) {
                if (this.heartbeatInterval) {
                    clearInterval(this.heartbeatInterval);
                }
                
                this.heartbeatInterval = setInterval(() => {
                    const sessions = this.getSessions(mode);
                    if (sessions[sessionId]) {
                        sessions[sessionId].timestamp = Date.now();
                        localStorage.setItem(`fragx_game_${mode}`, JSON.stringify(sessions));
                    }
                }, 5000);
            },
            
            // Obtener sesiones de un modo
            getSessions(mode) {
                try {
                    return JSON.parse(localStorage.getItem(`fragx_game_${mode}`)) || {};
                } catch (e) {
                    return {};
                }
            },
            
            // Contar jugadores en un modo
            getPlayerCount(mode) {
                return Object.keys(this.getSessions(mode)).length;
            },
            
            // Limpiar sesiones inactivas
            cleanupSessions() {
                const now = Date.now();
                const timeout = 30000; // 30 segundos de inactividad
                let changed = false;
                
                this.modes.forEach(mode => {
                    const sessions = this.getSessions(mode);
                    
                    for (const id in sessions) {
                        if (now - sessions[id].timestamp > timeout) {
                            delete sessions[id];
                            changed = true;
                        }
                    }
                    
                    localStorage.setItem(`fragx_game_${mode}`, JSON.stringify(sessions));
                });
                
                if (changed) {
                    this.updateAllDisplays();
                }
            },
            
            // Broadcast a otras pestañas
            broadcast() {
                if (this.channel) {
                    this.channel.postMessage({ type: 'update' });
                }
            },
            
            // Actualizar todos los displays
            updateAllDisplays() {
                // Torneos
                const weeklyCount = this.getPlayerCount('weekly');
                const monthlyCount = this.getPlayerCount('monthly');
                const rookieCount = this.getPlayerCount('rookie');
                const aimCount = this.getPlayerCount('aim');
                const wingmanCount = this.getPlayerCount('wingman');
                const retakeCount = this.getPlayerCount('retake');
                const dmCount = this.getPlayerCount('deathmatch');
                const compCount = this.getPlayerCount('competitive');
                
                // Actualizar elementos del DOM - Torneos
                this.updateElement('count-weekly', `${weeklyCount}/32 equipos`);
                this.updateElement('count-monthly', `${monthlyCount}/64 equipos`);
                this.updateElement('count-rookie', `${rookieCount}/16 equipos`);
                this.updateElement('count-aim', `${aimCount}/128 players`);
                this.updateElement('count-wingman', `${wingmanCount}/32 parejas`);
                this.updateElement('count-retake', `${retakeCount} players`);
                this.updateElement('count-deathmatch', `${dmCount} players`);
                this.updateElement('count-competitive', `${compCount} players`);
                
                // Actualizar elementos del DOM - Juego Rápido
                this.updateElement('count-aim-quick', `${aimCount} players`);
                this.updateElement('count-retake-quick', `${retakeCount} players`);
            },
            
            updateElement(id, text) {
                const el = document.getElementById(id);
                if (el) {
                    el.textContent = text;
                    // Animación de cambio
                    el.style.transform = 'scale(1.1)';
                    el.style.transition = 'transform 0.2s ease';
                    setTimeout(() => {
                        el.style.transform = 'scale(1)';
                    }, 200);
                }
            }
        };
        
        // Inicializar GameTracker
        GameTracker.init();
        
        // Escuchar cambios en localStorage desde otras pestañas
        window.addEventListener('storage', (e) => {
            if (e.key && e.key.startsWith('fragx_game_')) {
                GameTracker.updateAllDisplays();
            }
        });
        
        // ==================== PARTICLES ====================
        function createParticles() {
            const container = document.getElementById('particles');
            const colors = ['#de9b35', '#00fff5', '#39ff14', '#ff6a00'];
            
            for (let i = 0; i < 25; i++) {
                const particle = document.createElement('div');
                particle.className = 'particle';
                particle.style.left = Math.random() * 100 + '%';
                particle.style.animationDelay = Math.random() * 15 + 's';
                particle.style.animationDuration = (15 + Math.random() * 10) + 's';
                particle.style.background = colors[Math.floor(Math.random() * colors.length)];
                particle.style.boxShadow = `0 0 10px ${particle.style.background}`;
                container.appendChild(particle);
            }
        }
        createParticles();

        // ==================== TOURNAMENTS DATA ====================
        const tournamentsData = {
            weekly: {
                name: 'Weekly Championship',
                format: '5v5 Eliminación directa',
                teams: '32 equipos máximo',
                schedule: 'Todos los viernes a las 20:00',
                maps: 'Mirage, Inferno, Dust2, Anubis, Nuke',
                prizes: '🏆 Trofeo virtual + Medallas exclusivas',
                rules: 'Anti-cheat obligatorio, Discord para comunicación'
            },
            monthly: {
                name: 'Monthly Masters',
                format: 'Fase de grupos + Playoffs',
                teams: '64 equipos máximo',
                schedule: 'Tercera semana de cada mes',
                maps: 'Pool competitivo completo',
                prizes: '🏆 Trofeo + Banner exclusivo + Rol especial Discord',
                rules: 'Mínimo 5 partidos previos, Anti-cheat obligatorio'
            },
            rookie: {
                name: 'Rookie League',
                format: 'Liga amigable para nuevos equipos',
                teams: '16 equipos',
                schedule: 'Domingos 18:00',
                maps: 'Mirage, Inferno, Dust2',
                prizes: '🌟 Experiencia + Medallas de participación',
                rules: 'Solo equipos con menos de 10 partidos jugados'
            },
            aim: {
                name: 'Aim Arena 1v1',
                format: 'Duelos individuales',
                teams: '128 jugadores',
                schedule: 'Torneos diarios',
                maps: 'Aim maps especiales',
                prizes: '🎯 Puntos de ranking + Títulos',
                rules: 'Solo pistolas o rifles según modalidad'
            },
            wingman: {
                name: 'Wingman Cup',
                format: '2v2 Eliminación',
                teams: '32 parejas',
                schedule: 'Sábados 19:00',
                maps: 'Mapas Wingman oficiales',
                prizes: '🤝 Medallas de pareja',
                rules: 'Dúos pre-formados'
            },
            retake: {
                name: 'Retake Masters',
                format: 'Competitivo de Retake',
                teams: 'Ilimitado',
                schedule: '24/7 disponible',
                maps: 'Todos los mapas',
                prizes: '💣 Puntos y estadísticas',
                rules: 'Matchmaking automático'
            }
        };

        // ==================== TEAMS DATA (Datos reales desde localStorage) ====================
        // Los equipos ahora se cargan dinámicamente desde localStorage

        // ==================== MODAL FUNCTIONS ====================
        function openModal(title, content) {
            document.getElementById('modalTitle').textContent = title;
            document.getElementById('modalContent').innerHTML = content;
            document.getElementById('modal').classList.remove('hidden');
            document.body.style.overflow = 'hidden';
        }

        function closeModal() {
            document.getElementById('modal').classList.add('hidden');
            document.body.style.overflow = 'auto';
        }

        // Datos de modos de juego
        const playModesData = {
            retake: {
                name: 'Retake Masters',
                icon: '💣',
                description: 'Practica tus retakes y clutches en situaciones reales de post-plant.',
                mapsBots: 'Dust2, Mirage, Inferno, Nuke, Anubis',
                mapsOnline: 'Pool competitivo completo',
                botsConfig: 'map de_dust2; bot_add_ct; bot_add_t; mp_restartgame 1',
                steamCmd: 'steam://rungameid/730//+map de_dust2 +game_mode 0 +game_type 0 +bot_quota 9'
            },
            aim: {
                name: 'Aim Arena 1v1',
                icon: '🎯',
                description: 'Mejora tu puntería en duelos 1v1 intensos.',
                mapsBots: 'aim_botz, training_aim_csgo2',
                mapsOnline: 'Aim maps competitivos',
                botsConfig: 'map aim_botz; sv_cheats 1; bot_kick; sv_infinite_ammo 1',
                steamCmd: 'steam://rungameid/730//+map aim_botz'
            },
            wingman: {
                name: 'Wingman Cup',
                icon: '🤝',
                description: 'Modo 2v2 en mapas compactos.',
                mapsBots: 'Inferno, Overpass, Vertigo (zonas Wingman)',
                mapsOnline: 'Mapas Wingman oficiales',
                botsConfig: 'game_mode 2; game_type 0; map de_inferno',
                steamCmd: 'steam://rungameid/730//+game_mode 2 +game_type 0'
            },
            competitive: {
                name: 'Competitive 5v5',
                icon: '🏆',
                description: 'El modo clásico competitivo de CS2.',
                mapsBots: 'Todos los mapas del pool activo',
                mapsOnline: 'Pool competitivo oficial',
                botsConfig: 'game_mode 1; game_type 0; map de_dust2',
                steamCmd: 'steam://rungameid/730//+game_mode 1 +game_type 0'
            },
            deathmatch: {
                name: 'Deathmatch',
                icon: '💀',
                description: 'Practica tu aim en caos total.',
                mapsBots: 'Todos los mapas',
                mapsOnline: 'Servidores FFA Deathmatch',
                botsConfig: 'game_mode 2; game_type 1; map de_dust2',
                steamCmd: 'steam://rungameid/730//+game_mode 2 +game_type 1'
            }
        };

        function openPlayModal(id) {
            const mode = playModesData[id];
            if (!mode) {
                openTournamentModal(id);
                return;
            }
            
            // Opción especial para Retake: 1v5 con dificultad media
            const retakeSpecialOption = id === 'retake' ? `
                    <!-- Opción 1v5 Especial -->
                    <div class="bg-[#0a0a0f] p-6 rounded-lg border-2 border-[#ff6a00]/30 hover:border-[#ff6a00] transition cursor-pointer" onclick="launchRetake1v5()">
                        <div class="flex items-center gap-4 mb-4">
                            <span class="text-4xl">💀</span>
                            <div>
                                <h4 class="text-xl font-bold text-[#ff6a00]">1 vs 5 BOTS (Clutch Mode)</h4>
                                <p class="text-gray-400 text-sm">Tú solo contra 5 bots - Dificultad Media</p>
                            </div>
                        </div>
                        <div class="space-y-2 text-sm">
                            <p class="text-gray-500">👤 Modo: <span class="text-[#ff6a00] font-bold">1 vs 5</span></p>
                            <p class="text-gray-500">⚡ Dificultad: <span class="text-[#ffd700] font-bold">★★★☆☆ Media</span></p>
                            <p class="text-gray-500">📍 Mapas: <span class="text-white">Dust2, Mirage, Inferno</span></p>
                            <p class="text-gray-500">🎯 Objetivo: <span class="text-white">Practica clutches extremos</span></p>
                        </div>
                        <button class="mt-4 w-full bg-[#ff6a00] text-black py-3 rounded font-bold uppercase hover:shadow-[0_0_20px_#ff6a00] transition">
                            ☠️ Iniciar Modo Clutch 1v5
                        </button>
                    </div>
            ` : '';
            
            const content = `
                <div class="space-y-6">
                    <div class="text-center">
                        <span class="text-6xl">${mode.icon}</span>
                        <p class="text-gray-400 mt-4">${mode.description}</p>
                    </div>
                    
                    <div class="free-badge inline-block px-4 py-2 rounded text-black font-bold w-full text-center">🎮 JUGAR GRATIS</div>
                    
                    ${retakeSpecialOption}
                    
                    <!-- Opción Bots -->
                    <div class="bg-[#0a0a0f] p-6 rounded-lg border-2 border-[#39ff14]/30 hover:border-[#39ff14] transition cursor-pointer" onclick="launchCS2Bots('${id}')">
                        <div class="flex items-center gap-4 mb-4">
                            <span class="text-4xl">🤖</span>
                            <div>
                                <h4 class="text-xl font-bold text-[#39ff14]">Jugar vs BOTS</h4>
                                <p class="text-gray-400 text-sm">Practica offline contra la IA</p>
                            </div>
                        </div>
                        <div class="space-y-2 text-sm">
                            <p class="text-gray-500">📍 Mapas: <span class="text-white">${mode.mapsBots}</span></p>
                            <p class="text-gray-500">⚡ Dificultad: <span class="text-white">Ajustable</span></p>
                            <p class="text-gray-500">🔒 Conexión: <span class="text-[#39ff14]">No requiere internet</span></p>
                        </div>
                        <button class="mt-4 w-full bg-[#39ff14] text-black py-3 rounded font-bold uppercase hover:shadow-[0_0_20px_#39ff14] transition">
                            🚀 Iniciar Partida con Bots
                        </button>
                    </div>
                    
                    <!-- Opción Online -->
                    <div class="bg-[#0a0a0f] p-6 rounded-lg border-2 border-[#00fff5]/30 hover:border-[#00fff5] transition cursor-pointer" onclick="launchCS2Online('${id}')">
                        <div class="flex items-center gap-4 mb-4">
                            <span class="text-4xl">👥</span>
                            <div>
                                <h4 class="text-xl font-bold text-[#00fff5]">Jugar vs PERSONAS</h4>
                                <p class="text-gray-400 text-sm">Compite contra jugadores reales</p>
                            </div>
                        </div>
                        <div class="space-y-2 text-sm">
                            <p class="text-gray-500">📍 Mapas: <span class="text-white">${mode.mapsOnline}</span></p>
                            <p class="text-gray-500">🌐 Servidores: <span class="text-white">Matchmaking oficial</span></p>
                            <p class="text-gray-500">🏆 Ranking: <span class="text-[#ffd700]">Competitivo ELO</span></p>
                        </div>
                        <button class="mt-4 w-full bg-[#00fff5] text-black py-3 rounded font-bold uppercase hover:shadow-[0_0_20px_#00fff5] transition">
                            🎮 Buscar Partida Online
                        </button>
                    </div>
                    
                    <div class="text-center text-gray-500 text-xs">
                        <p>💡 Se abrirá Counter-Strike 2 automáticamente</p>
                        <p>Asegúrate de tener Steam y CS2 instalados</p>
                    </div>
                </div>
            `;
            openModal(mode.icon + ' ' + mode.name, content);
        }

        function launchCS2Bots(modeId) {
            const mode = playModesData[modeId];
            showNotification('🚀 Abriendo CS2 con bots...', 'success');
            
            // Registrar al jugador en este modo
            GameTracker.joinGame(modeId);
            
            // Intentar abrir CS2 con el protocolo steam://
            const steamUrl = mode.steamCmd;
            window.location.href = steamUrl;
            
            setTimeout(() => {
                closeModal();
                openModal('📋 Comandos de Consola', `
                    <div class="space-y-4">
                        <p class="text-gray-400">Si CS2 no se abrió automáticamente, abre el juego y usa estos comandos en la consola (~):</p>
                        
                        <div class="bg-[#0a0a0f] p-4 rounded-lg border border-[#39ff14]/50">
                            <code class="text-[#39ff14] text-sm break-all">${mode.botsConfig}</code>
                        </div>
                        
                        <button onclick="copyConsoleCommand('${mode.botsConfig}')" class="w-full btn-gamer btn-green py-2 rounded font-bold uppercase text-sm">
                            📋 Copiar Comandos
                        </button>
                        
                        <div class="text-center">
                            <a href="steam://rungameid/730" class="text-[#00fff5] hover:underline">🎮 Abrir CS2 manualmente</a>
                        </div>
                    </div>
                `);
            }, 2000);
        }

        function launchCS2Online(modeId) {
            showNotification('🎮 Abriendo CS2 matchmaking...', 'success');
            
            // Registrar al jugador en este modo
            GameTracker.joinGame(modeId);
            
            // Abrir CS2 directamente
            window.location.href = 'steam://rungameid/730';
            
            setTimeout(() => {
                closeModal();
                showNotification('👥 Busca partida desde el menú de CS2', 'info');
            }, 1500);
        }

        function launchRetake1v5() {
            showNotification('☠️ Abriendo CS2 - Modo Clutch 1v5...', 'success');
            
            // Registrar al jugador en modo retake
            GameTracker.joinGame('retake');
            
            // Intentar abrir CS2
            window.location.href = 'steam://rungameid/730';
            
            setTimeout(() => {
                closeModal();
                
                const commands = `// MODO CLUTCH 1v5 - Dificultad Media
// Copia y pega estos comandos en la consola (~)

// Configurar mapa
map de_dust2

// Limpiar bots existentes
bot_kick

// Configurar dificultad MEDIA (0=Fácil, 1=Normal, 2=Difícil, 3=Experto)
bot_difficulty 1

// Unirte a CT (antiterroristas)
jointeam 3

// Agregar 5 bots terroristas
bot_add_t
bot_add_t
bot_add_t
bot_add_t
bot_add_t

// Configuración de práctica
mp_warmup_end
mp_restartgame 1
mp_autoteambalance 0
mp_limitteams 0

// Dinero infinito para comprar
mp_maxmoney 60000
mp_startmoney 60000
mp_afterroundmoney 60000

// Tiempo extra para clutch
mp_roundtime 3
mp_roundtime_defuse 3

// Los bots plantan bomba
mp_bot_ai_bt_plant_bomb 1`;

                openModal('☠️ Modo Clutch 1v5 - Comandos', `
                    <div class="space-y-4">
                        <div class="bg-[#ff6a00]/10 p-4 rounded-lg border border-[#ff6a00]/50">
                            <p class="text-[#ff6a00] font-bold flex items-center gap-2">
                                <span class="text-2xl">💀</span>
                                <span>1 vs 5 BOTS - Dificultad Media</span>
                            </p>
                            <p class="text-gray-400 text-sm mt-2">Tú solo contra 5 terroristas. Practica tus clutches.</p>
                        </div>
                        
                        <p class="text-gray-400">Abre la consola en CS2 (tecla ~) y pega estos comandos:</p>
                        
                        <div class="bg-[#0a0a0f] p-4 rounded-lg border border-[#39ff14]/50 max-h-64 overflow-y-auto">
                            <pre class="text-[#39ff14] text-xs whitespace-pre-wrap font-mono">${commands}</pre>
                        </div>
                        
                        <div class="grid grid-cols-2 gap-3">
                            <button onclick="copyRetakeCommands()" class="btn-gamer btn-green py-3 rounded font-bold uppercase text-sm">
                                📋 Copiar Comandos
                            </button>
                            <button onclick="copyQuickRetake()" class="btn-gamer py-3 rounded font-bold uppercase text-sm">
                                ⚡ Copiar Rápido
                            </button>
                        </div>
                        
                        <div class="bg-[#1a1a2e] p-3 rounded-lg">
                            <p class="text-gray-400 text-xs">
                                <span class="text-[#ffd700]">💡 Tip:</span> Para cambiar de mapa usa: 
                                <code class="text-[#00fff5]">map de_mirage</code> o 
                                <code class="text-[#00fff5]">map de_inferno</code>
                            </p>
                        </div>
                        
                        <div class="text-center">
                            <a href="steam://rungameid/730" class="text-[#00fff5] hover:underline text-sm">🎮 Abrir CS2 nuevamente</a>
                        </div>
                    </div>
                `);
            }, 2000);
        }

        function copyRetakeCommands() {
            const commands = `map de_dust2
bot_kick
bot_difficulty 1
jointeam 3
bot_add_t
bot_add_t
bot_add_t
bot_add_t
bot_add_t
mp_warmup_end
mp_restartgame 1
mp_autoteambalance 0
mp_limitteams 0
mp_maxmoney 60000
mp_startmoney 60000
mp_afterroundmoney 60000
mp_roundtime 3
mp_roundtime_defuse 3`;
            
            navigator.clipboard.writeText(commands).then(() => {
                showNotification('📋 Comandos copiados al portapapeles', 'success');
            }).catch(() => {
                showNotification('Error al copiar. Copia manualmente.', 'error');
            });
        }

        function copyQuickRetake() {
            const quickCmd = 'map de_dust2; bot_kick; bot_difficulty 1; jointeam 3; bot_add_t; bot_add_t; bot_add_t; bot_add_t; bot_add_t; mp_warmup_end; mp_restartgame 1';
            
            navigator.clipboard.writeText(quickCmd).then(() => {
                showNotification('⚡ Comando rápido copiado - Pégalo todo junto', 'success');
            }).catch(() => {
                showNotification('Error al copiar. Copia manualmente.', 'error');
            });
        }

        function copyConsoleCommand(command) {
            navigator.clipboard.writeText(command).then(() => {
                showNotification('📋 Comandos copiados al portapapeles', 'success');
            }).catch(() => {
                showNotification('Comandos: ' + command, 'info');
            });
        }

        function openTournamentModal(id) {
            const t = tournamentsData[id];
            const content = `
                <div class="space-y-4">
                    <div class="free-badge inline-block px-4 py-2 rounded text-black font-bold">🎮 INSCRIPCIÓN GRATIS</div>
                    
                    <div class="grid grid-cols-2 gap-4 mt-4">
                        <div class="bg-[#0a0a0f] p-4 rounded-lg">
                            <p class="text-gray-500 text-sm">Formato</p>
                            <p class="text-white font-bold">${t.format}</p>
                        </div>
                        <div class="bg-[#0a0a0f] p-4 rounded-lg">
                            <p class="text-gray-500 text-sm">Equipos</p>
                            <p class="text-white font-bold">${t.teams}</p>
                        </div>
                        <div class="bg-[#0a0a0f] p-4 rounded-lg">
                            <p class="text-gray-500 text-sm">Horario</p>
                            <p class="text-[#de9b35] font-bold">${t.schedule}</p>
                        </div>
                        <div class="bg-[#0a0a0f] p-4 rounded-lg">
                            <p class="text-gray-500 text-sm">Mapas</p>
                            <p class="text-[#00fff5] font-bold">${t.maps}</p>
                        </div>
                    </div>
                    
                    <div class="bg-[#0a0a0f] p-4 rounded-lg">
                        <p class="text-gray-500 text-sm">Premios</p>
                        <p class="text-[#ffd700] font-bold">${t.prizes}</p>
                    </div>
                    
                    <div class="bg-[#0a0a0f] p-4 rounded-lg">
                        <p class="text-gray-500 text-sm">Reglas</p>
                        <p class="text-gray-300">${t.rules}</p>
                    </div>
                    
                    <div class="grid grid-cols-2 gap-4">
                        <button onclick="openPlayModal('competitive')" class="btn-gamer py-3 rounded font-bold uppercase text-sm">
                            🎮 Practicar Antes
                        </button>
                        <button onclick="inscribeTeam('${t.name}')" class="btn-gamer btn-green py-3 rounded font-bold uppercase">
                            🏆 Inscribir Equipo
                        </button>
                    </div>
                </div>
            `;
            openModal('🏆 ' + t.name, content);
        }

        // Las funciones de equipos ahora usan openCreatedTeamModal con datos reales

        function openLoginModal() {
            const content = `
                <div class="space-y-4">
                    <div class="flex border-b border-gray-700 mb-4">
                        <button onclick="showLoginTab()" id="loginTab" class="flex-1 py-3 text-center font-bold text-[#de9b35] border-b-2 border-[#de9b35] transition">Iniciar Sesión</button>
                        <button onclick="showRegisterTab()" id="registerTab" class="flex-1 py-3 text-center font-bold text-gray-500 hover:text-gray-300 transition">Crear Cuenta</button>
                    </div>
                    
                    <!-- Login Form -->
                    <div id="loginForm">
                        <div class="space-y-4">
                            <div>
                                <label class="block text-[#de9b35] font-bold mb-2 text-sm">📧 Email</label>
                                <input type="email" id="loginEmail" class="w-full px-4 py-3 bg-[#0a0a0f] border border-gray-700 rounded text-white focus:border-[#de9b35] outline-none transition" placeholder="tu@email.com">
                            </div>
                            <div>
                                <label class="block text-[#de9b35] font-bold mb-2 text-sm">🔒 Contraseña</label>
                                <input type="password" id="loginPassword" class="w-full px-4 py-3 bg-[#0a0a0f] border border-gray-700 rounded text-white focus:border-[#de9b35] outline-none transition" placeholder="Tu contraseña">
                            </div>
                            <button onclick="handleLogin()" class="w-full btn-gamer btn-green py-3 rounded font-bold uppercase">
                                🎮 Entrar a FRAGX
                            </button>
                        </div>
                    </div>
                    
                    <!-- Register Form -->
                    <div id="registerForm" class="hidden">
                        <div class="space-y-4">
                            <div>
                                <label class="block text-[#39ff14] font-bold mb-2 text-sm">👤 Nombre de Usuario *</label>
                                <input type="text" id="regUsername" class="w-full px-4 py-3 bg-[#0a0a0f] border border-gray-700 rounded text-white focus:border-[#39ff14] outline-none transition" placeholder="Tu gamertag">
                            </div>
                            <div>
                                <label class="block text-[#39ff14] font-bold mb-2 text-sm">📧 Email *</label>
                                <input type="email" id="regEmail" class="w-full px-4 py-3 bg-[#0a0a0f] border border-gray-700 rounded text-white focus:border-[#39ff14] outline-none transition" placeholder="tu@email.com">
                            </div>
                            <div>
                                <label class="block text-[#39ff14] font-bold mb-2 text-sm">🔒 Contraseña *</label>
                                <input type="password" id="regPassword" class="w-full px-4 py-3 bg-[#0a0a0f] border border-gray-700 rounded text-white focus:border-[#39ff14] outline-none transition" placeholder="Mínimo 6 caracteres">
                            </div>
                            
                            <div class="border-t border-gray-700 pt-4 mt-4">
                                <p class="text-gray-400 text-sm mb-3">Vincula tus cuentas de juego (opcional):</p>
                                <div class="grid grid-cols-2 gap-3">
                                    <div>
                                        <label class="block text-[#1b2838] font-bold mb-1 text-xs bg-gray-700 px-2 py-1 rounded inline-block">🎮 Steam ID</label>
                                        <input type="text" id="regSteamId" class="w-full px-3 py-2 bg-[#0a0a0f] border border-gray-700 rounded text-white text-sm focus:border-[#1b2838] outline-none transition" placeholder="Tu Steam ID">
                                    </div>
                                    <div>
                                        <label class="block text-[#39ff14] font-bold mb-1 text-xs bg-gray-700 px-2 py-1 rounded inline-block">⛏️ Minecraft</label>
                                        <input type="text" id="regMinecraft" class="w-full px-3 py-2 bg-[#0a0a0f] border border-gray-700 rounded text-white text-sm focus:border-[#39ff14] outline-none transition" placeholder="Tu nick MC">
                                    </div>
                                </div>
                            </div>
                            
                            <button onclick="handleRegister()" class="w-full btn-gamer btn-green py-3 rounded font-bold uppercase">
                                🚀 Crear Cuenta GRATIS
                            </button>
                        </div>
                    </div>
                    
                    <div class="text-center text-gray-500 text-sm mt-4 pt-4 border-t border-gray-700">
                        <p class="text-[#39ff14]">✓ 100% Gratis • Sin suscripciones • Sin límites</p>
                        <p class="text-gray-600 text-xs mt-1">Bienvenido a FRAGX 🎮</p>
                    </div>
                </div>
            `;
            openModal('🔐 Acceder a FRAGX', content);
        }
        
        function showLoginTab() {
            document.getElementById('loginTab').classList.add('text-[#de9b35]', 'border-b-2', 'border-[#de9b35]');
            document.getElementById('loginTab').classList.remove('text-gray-500');
            document.getElementById('registerTab').classList.remove('text-[#de9b35]', 'border-b-2', 'border-[#de9b35]');
            document.getElementById('registerTab').classList.add('text-gray-500');
            document.getElementById('loginForm').classList.remove('hidden');
            document.getElementById('registerForm').classList.add('hidden');
        }
        
        function showRegisterTab() {
            document.getElementById('registerTab').classList.add('text-[#de9b35]', 'border-b-2', 'border-[#de9b35]');
            document.getElementById('registerTab').classList.remove('text-gray-500');
            document.getElementById('loginTab').classList.remove('text-[#de9b35]', 'border-b-2', 'border-[#de9b35]');
            document.getElementById('loginTab').classList.add('text-gray-500');
            document.getElementById('registerForm').classList.remove('hidden');
            document.getElementById('loginForm').classList.add('hidden');
        }
        
        function handleLogin() {
            const email = document.getElementById('loginEmail').value;
            const password = document.getElementById('loginPassword').value;
            
            if (!email || !password) {
                showNotification('Por favor completa todos los campos', 'error');
                return;
            }
            
            const result = Auth.login(email, password);
            
            if (result.success) {
                showNotification(result.message, 'success');
                closeModal();
            } else {
                showNotification(result.message, 'error');
            }
        }
        
        function handleRegister() {
            const username = document.getElementById('regUsername').value;
            const email = document.getElementById('regEmail').value;
            const password = document.getElementById('regPassword').value;
            const steamId = document.getElementById('regSteamId').value;
            const minecraftNick = document.getElementById('regMinecraft').value;
            
            if (!username || !email || !password) {
                showNotification('Por favor completa los campos obligatorios', 'error');
                return;
            }
            
            if (password.length < 6) {
                showNotification('La contraseña debe tener al menos 6 caracteres', 'error');
                return;
            }
            
            if (!email.includes('@')) {
                showNotification('Por favor ingresa un email válido', 'error');
                return;
            }
            
            const result = Auth.register({
                username,
                email,
                password,
                steamId: steamId || null,
                minecraftNick: minecraftNick || null
            });
            
            if (result.success) {
                showNotification(result.message, 'success');
                closeModal();
            } else {
                showNotification(result.message, 'error');
            }
        }
        
        function openUserProfile() {
            if (!Auth.isLoggedIn()) {
                openLoginModal();
                return;
            }
            
            const user = Auth.currentUser;
            const content = `
                <div class="text-center mb-6">
                    <img src="${user.avatar}" class="w-24 h-24 rounded-full border-4 border-[#39ff14] mx-auto mb-4" alt="Avatar">
                    <h3 class="text-2xl font-bold text-[#39ff14]">${user.username}</h3>
                    <p class="text-gray-400">${user.email}</p>
                </div>
                
                <div class="space-y-4">
                    <div class="bg-[#0a0a0f] p-4 rounded-lg">
                        <p class="text-gray-500 text-sm">🎮 Steam ID</p>
                        <p class="text-white font-bold">${user.steamId || 'No vinculado'}</p>
                    </div>
                    <div class="bg-[#0a0a0f] p-4 rounded-lg">
                        <p class="text-gray-500 text-sm">⛏️ Minecraft Nick</p>
                        <p class="text-white font-bold">${user.minecraftNick || 'No vinculado'}</p>
                    </div>
                    <div class="bg-[#0a0a0f] p-4 rounded-lg">
                        <p class="text-gray-500 text-sm">📅 Miembro desde</p>
                        <p class="text-white font-bold">${new Date(user.createdAt).toLocaleDateString('es-ES')}</p>
                    </div>
                </div>
                
                <div class="mt-6 space-y-3">
                    <button onclick="openEditProfile()" class="w-full btn-gamer py-2 rounded font-bold uppercase text-sm">
                        ✏️ Editar Perfil
                    </button>
                    <button onclick="Auth.logout(); closeModal();" class="w-full bg-red-600/20 text-red-500 hover:bg-red-600 hover:text-white py-2 rounded font-bold uppercase text-sm transition">
                        🚪 Cerrar Sesión
                    </button>
                </div>
            `;
            openModal('👤 Mi Perfil', content);
        }
        
        function openEditProfile() {
            if (!Auth.isLoggedIn()) return;
            
            const user = Auth.currentUser;
            const content = `
                <div class="space-y-4">
                    <div>
                        <label class="block text-[#39ff14] font-bold mb-2 text-sm">👤 Nombre de Usuario</label>
                        <input type="text" id="editUsername" value="${user.username}" class="w-full px-4 py-3 bg-[#0a0a0f] border border-gray-700 rounded text-white focus:border-[#39ff14] outline-none transition">
                    </div>
                    <div>
                        <label class="block text-[#de9b35] font-bold mb-2 text-sm">🎮 Steam ID</label>
                        <input type="text" id="editSteamId" value="${user.steamId || ''}" class="w-full px-4 py-3 bg-[#0a0a0f] border border-gray-700 rounded text-white focus:border-[#de9b35] outline-none transition" placeholder="Tu Steam ID">
                    </div>
                    <div>
                        <label class="block text-[#39ff14] font-bold mb-2 text-sm">⛏️ Minecraft Nick</label>
                        <input type="text" id="editMinecraft" value="${user.minecraftNick || ''}" class="w-full px-4 py-3 bg-[#0a0a0f] border border-gray-700 rounded text-white focus:border-[#39ff14] outline-none transition" placeholder="Tu nick de Minecraft">
                    </div>
                    
                    <button onclick="saveProfile()" class="w-full btn-gamer btn-green py-3 rounded font-bold uppercase">
                        💾 Guardar Cambios
                    </button>
                </div>
            `;
            openModal('✏️ Editar Perfil', content);
        }
        
        function saveProfile() {
            const username = document.getElementById('editUsername').value;
            const steamId = document.getElementById('editSteamId').value;
            const minecraftNick = document.getElementById('editMinecraft').value;
            
            if (!username) {
                showNotification('El nombre de usuario es obligatorio', 'error');
                return;
            }
            
            const success = Auth.updateProfile({
                username,
                steamId: steamId || null,
                minecraftNick: minecraftNick || null,
                avatar: Auth.generateAvatar(username)
            });
            
            if (success) {
                showNotification('¡Perfil actualizado!', 'success');
                closeModal();
            } else {
                showNotification('Error al actualizar perfil', 'error');
            }
        }
        
        // Función helper para verificar login antes de acciones
        function requireLogin(callback, message = 'Debes iniciar sesión para continuar') {
            if (!Auth.isLoggedIn()) {
                showNotification(message, 'warning');
                setTimeout(() => openLoginModal(), 500);
                return false;
            }
            if (callback) callback();
            return true;
        }

        function openFindTeamModal() {
            const content = `
                <div class="space-y-4">
                    <p class="text-gray-400">Encuentra un equipo que busque jugadores como tú.</p>
                    
                    <div class="bg-[#0a0a0f] p-4 rounded-lg">
                        <label class="block text-[#de9b35] font-bold mb-2 text-sm">Tu Rol Principal</label>
                        <select class="w-full px-4 py-2 bg-[#1a1a2e] border border-gray-700 rounded text-white">
                            <option>Entry Fragger</option>
                            <option>AWPer</option>
                            <option>Support</option>
                            <option>Lurker</option>
                            <option>IGL</option>
                        </select>
                    </div>
                    
                    <div class="bg-[#0a0a0f] p-4 rounded-lg">
                        <label class="block text-[#00fff5] font-bold mb-2 text-sm">Tu Rango</label>
                        <select class="w-full px-4 py-2 bg-[#1a1a2e] border border-gray-700 rounded text-white">
                            <option>Global Elite</option>
                            <option>Supreme</option>
                            <option>LEM</option>
                            <option>LE</option>
                            <option>DMG</option>
                            <option>Otros</option>
                        </select>
                    </div>
                    
                    <button onclick="searchTeams()" class="w-full btn-gamer btn-green py-3 rounded font-bold uppercase">
                        🔍 Buscar Equipos
                    </button>
                </div>
            `;
            openModal('🔍 Buscar Equipo', content);
        }

        function openPublicMatchesModal() {
            const content = `
                <div class="space-y-4">
                    <p class="text-gray-400">Únete a partidas públicas y juega con otros miembros de la comunidad.</p>
                    
                    <div class="space-y-3">
                        <div class="bg-[#0a0a0f] p-4 rounded-lg flex justify-between items-center">
                            <div>
                                <p class="text-white font-bold">🎯 Competitive 5v5</p>
                                <p class="text-gray-500 text-sm">7/10 jugadores</p>
                            </div>
                            <button onclick="joinMatch()" class="btn-gamer px-4 py-2 rounded text-sm">Unirse</button>
                        </div>
                        
                        <div class="bg-[#0a0a0f] p-4 rounded-lg flex justify-between items-center">
                            <div>
                                <p class="text-white font-bold">🔫 Aim Training</p>
                                <p class="text-gray-500 text-sm">12/16 jugadores</p>
                            </div>
                            <button onclick="joinMatch()" class="btn-gamer px-4 py-2 rounded text-sm">Unirse</button>
                        </div>
                        
                        <div class="bg-[#0a0a0f] p-4 rounded-lg flex justify-between items-center">
                            <div>
                                <p class="text-white font-bold">💣 Retake Server</p>
                                <p class="text-gray-500 text-sm">8/10 jugadores</p>
                            </div>
                            <button onclick="joinMatch()" class="btn-gamer px-4 py-2 rounded text-sm">Unirse</button>
                        </div>
                    </div>
                    
                    <p class="text-[#39ff14] text-center text-sm">✓ Todos los servidores son GRATIS</p>
                </div>
            `;
            openModal('🎮 Partidas Públicas', content);
        }

        // ==================== NOTIFICATION ====================
        function showNotification(message, type = 'info') {
            const container = document.getElementById('notifications');
            const notification = document.createElement('div');
            
            const colors = {
                info: 'bg-[#00fff5]',
                success: 'bg-[#39ff14]',
                warning: 'bg-[#ffd700]',
                error: 'bg-[#ff4444]'
            };
            
            notification.className = `notification ${colors[type]} text-black px-6 py-3 rounded-lg shadow-lg font-bold`;
            notification.textContent = message;
            
            container.appendChild(notification);
            
            setTimeout(() => {
                notification.style.animation = 'slideIn 0.5s ease-out reverse';
                setTimeout(() => notification.remove(), 500);
            }, 3000);
        }

        // ==================== FORM HANDLING ====================
        document.getElementById('createTeamForm').addEventListener('submit', function(e) {
            e.preventDefault();
            
            // Verificar si está logueado
            if (!Auth.isLoggedIn()) {
                showNotification('Debes iniciar sesión para crear un equipo', 'warning');
                setTimeout(() => openLoginModal(), 500);
                return;
            }
            
            const teamName = document.getElementById('teamName').value;
            const teamTag = document.getElementById('teamTag').value;
            const captainName = document.getElementById('captainName').value;
            const teamEmail = document.getElementById('teamEmail').value;
            
            const btn = document.getElementById('createTeamBtn');
            btn.textContent = '⏳ Creando equipo...';
            btn.disabled = true;
            
            setTimeout(() => {
                // Guardar equipo en localStorage
                const teams = getTeamsFromStorage();
                const members = [];
                document.querySelectorAll('.member-input').forEach(input => {
                    if (input.value.trim()) members.push(input.value.trim());
                });
                
                const newTeam = {
                    id: 'team_' + Date.now(),
                    name: teamName,
                    tag: teamTag.toUpperCase(),
                    captain: captainName,
                    email: teamEmail,
                    region: document.getElementById('teamRegion').value,
                    members: [captainName, ...members],
                    createdAt: new Date().toISOString(),
                    wins: 0,
                    losses: 0
                };
                
                teams.push(newTeam);
                localStorage.setItem('fragx_teams', JSON.stringify(teams));
                updateTeamsCount();
                renderTeams();
                renderRanking();
                
                showNotification('¡Equipo creado exitosamente!', 'success');
                
                const totalTeams = teams.length;
                
                openModal('🎉 ¡Equipo Creado!', `
                    <div class="text-center">
                        <div class="text-6xl mb-4">🏆</div>
                        <p class="text-2xl font-bold text-white mb-2">${teamName}</p>
                        <p class="text-[#de9b35] mb-4">[${teamTag.toUpperCase()}]</p>
                        <p class="text-gray-400 mb-6">Capitán: <span class="text-[#39ff14]">${captainName}</span></p>
                        
                        <div class="bg-[#0a0a0f] p-4 rounded-lg mb-6">
                            <p class="text-[#39ff14] font-bold">✓ Equipo registrado GRATIS</p>
                            <p class="text-gray-500 text-sm mt-2">Ya puedes inscribirte en torneos</p>
                            <p class="text-[#00fff5] text-sm mt-2">Eres el equipo #${totalTeams} en registrarse</p>
                        </div>
                        
                        <button onclick="closeModal(); scrollToSection('torneos')" class="btn-gamer btn-green px-8 py-3 rounded font-bold uppercase">
                            🏆 Ver Torneos Disponibles
                        </button>
                    </div>
                `);
                
                this.reset();
                btn.textContent = '🎮 Crear Equipo GRATIS';
                btn.disabled = false;
            }, 1500);
        });

        function addMember() {
            const container = document.getElementById('membersContainer');
            const count = container.children.length + 2;
            const div = document.createElement('div');
            div.className = 'flex gap-2';
            div.innerHTML = `
                <input type="text" class="member-input flex-1 px-4 py-2 bg-[#0a0a0f] border border-gray-700 rounded text-white placeholder-gray-600" placeholder="Nombre Steam del jugador ${count}">
                <button type="button" onclick="removeMember(this)" class="px-3 py-2 bg-red-600/20 text-red-500 rounded hover:bg-red-600 hover:text-white transition">✕</button>
            `;
            container.appendChild(div);
        }

        function removeMember(btn) {
            btn.parentElement.remove();
        }

        // ==================== ACTION FUNCTIONS ====================
        function inscribeTeam(tournament) {
            if (!Auth.isLoggedIn()) {
                closeModal();
                showNotification(`Debes iniciar sesión para inscribirte en ${tournament}`, 'warning');
                setTimeout(() => openLoginModal(), 500);
                return;
            }
            
            // Verificar si tiene equipo
            const teams = getTeamsFromStorage();
            const userTeam = teams.find(t => t.email === Auth.currentUser.email || t.captain === Auth.currentUser.username);
            
            if (!userTeam) {
                closeModal();
                showNotification('Primero debes crear un equipo para inscribirte', 'warning');
                setTimeout(() => scrollToSection('crear-equipo'), 500);
                return;
            }
            
            closeModal();
            showNotification(`¡Equipo "${userTeam.name}" inscrito en ${tournament}! 🎮`, 'success');
        }

        function searchTeams() {
            if (!Auth.isLoggedIn()) {
                closeModal();
                showNotification('Debes iniciar sesión para buscar equipos', 'warning');
                setTimeout(() => openLoginModal(), 500);
                return;
            }
            showNotification('Buscando equipos disponibles...', 'info');
            closeModal();
        }

        function joinMatch() {
            if (!Auth.isLoggedIn()) {
                closeModal();
                showNotification('Debes iniciar sesión para unirte a partidas', 'warning');
                setTimeout(() => openLoginModal(), 500);
                return;
            }
            showNotification('Uniéndose a la partida...', 'success');
            closeModal();
        }

        function showAllTeams() {
            showNotification('Cargando todos los equipos...', 'info');
        }

        function showFullRanking() {
            showNotification('Cargando ranking completo...', 'info');
        }

        function openDiscord() {
            event.preventDefault();
            showNotification('Abriendo Discord...', 'info');
            window.open('https://discord.gg', '_blank');
        }

        function openFAQ() {
            event.preventDefault();
            openModal('❓ Preguntas Frecuentes', `
                <div class="space-y-4 text-gray-300">
                    <div class="bg-[#0a0a0f] p-4 rounded-lg">
                        <p class="text-[#de9b35] font-bold">¿Es realmente gratis?</p>
                        <p class="text-sm mt-2">Sí, 100% gratis. Sin costos ocultos, sin suscripciones, sin pay-to-win.</p>
                    </div>
                    <div class="bg-[#0a0a0f] p-4 rounded-lg">
                        <p class="text-[#de9b35] font-bold">¿Cómo creo un equipo?</p>
                        <p class="text-sm mt-2">Ve a la sección "Crear Equipo", llena el formulario y listo. Necesitas mínimo 5 jugadores para torneos 5v5.</p>
                    </div>
                    <div class="bg-[#0a0a0f] p-4 rounded-lg">
                        <p class="text-[#de9b35] font-bold">¿Qué anti-cheat usan?</p>
                        <p class="text-sm mt-2">Usamos VAC + sistema de reportes de la comunidad.</p>
                    </div>
                </div>
            `);
        }

        function openRules() {
            event.preventDefault();
            openModal('📜 Reglas', `
                <div class="space-y-3 text-gray-300">
                    <p class="flex items-center gap-2"><span class="text-[#39ff14]">✓</span> Respeto entre jugadores</p>
                    <p class="flex items-center gap-2"><span class="text-[#39ff14]">✓</span> No cheats ni hacks</p>
                    <p class="flex items-center gap-2"><span class="text-[#39ff14]">✓</span> Puntualidad en los torneos</p>
                    <p class="flex items-center gap-2"><span class="text-[#39ff14]">✓</span> Discord obligatorio para comunicación</p>
                    <p class="flex items-center gap-2"><span class="text-red-500">✕</span> Smurfing prohibido</p>
                    <p class="flex items-center gap-2"><span class="text-red-500">✕</span> Comportamiento tóxico</p>
                </div>
            `);
        }

        function reportBug() {
            event.preventDefault();
            showNotification('Abriendo formulario de reportes...', 'info');
        }

        // ==================== COUNTERS ====================
        function animateCounters() {
            const counters = document.querySelectorAll('.counter');
            counters.forEach(counter => {
                const target = parseInt(counter.dataset.target);
                const duration = 2000;
                const step = target / (duration / 16);
                let current = 0;
                
                const updateCounter = () => {
                    current += step;
                    if (current < target) {
                        counter.textContent = Math.floor(current).toLocaleString();
                        requestAnimationFrame(updateCounter);
                    } else {
                        counter.textContent = target.toLocaleString();
                    }
                };
                updateCounter();
            });
        }

        // ==================== NAVIGATION ====================
        function scrollToTop() {
            window.scrollTo({ top: 0, behavior: 'smooth' });
        }

        function scrollToSection(id) {
            document.getElementById(id).scrollIntoView({ behavior: 'smooth' });
        }

        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function(e) {
                e.preventDefault();
                const target = document.querySelector(this.getAttribute('href'));
                if (target) {
                    target.scrollIntoView({ behavior: 'smooth' });
                }
                document.getElementById('mobileMenu').classList.add('hidden');
            });
        });

        document.getElementById('menuBtn').addEventListener('click', () => {
            document.getElementById('mobileMenu').classList.toggle('hidden');
        });

        window.addEventListener('scroll', () => {
            const navbar = document.getElementById('navbar');
            const scrollBtn = document.getElementById('scrollTopBtn');
            
            if (window.scrollY > 100) {
                navbar.classList.add('bg-[#0a0a0f]/95', 'backdrop-blur-md', 'border-b', 'border-[#de9b35]/20');
                scrollBtn.classList.remove('hidden');
            } else {
                navbar.classList.remove('bg-[#0a0a0f]/95', 'backdrop-blur-md', 'border-b', 'border-[#de9b35]/20');
                scrollBtn.classList.add('hidden');
            }
        });

        document.getElementById('modal').addEventListener('click', (e) => {
            if (e.target.id === 'modal') closeModal();
        });
        
        document.addEventListener('keydown', (e) => {
            if (e.key === 'Escape') closeModal();
        });

        // Observer for animations
        const observerOptions = { threshold: 0.1 };
        const observer = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.classList.add('fade-in');
                    if (entry.target.querySelector('.counter')) {
                        animateCounters();
                    }
                }
            });
        }, observerOptions);

        document.querySelectorAll('section').forEach(section => observer.observe(section));

        // ==================== REAL-TIME ONLINE PLAYERS ====================
        const OnlineTracker = {
            sessionId: null,
            channel: null,
            
            init() {
                // Generar ID único para esta sesión
                this.sessionId = 'session_' + Date.now() + '_' + Math.random().toString(36).substr(2, 9);
                
                // Crear canal de comunicación entre pestañas
                if ('BroadcastChannel' in window) {
                    this.channel = new BroadcastChannel('fragx_online');
                    this.channel.onmessage = (event) => {
                        if (event.data.type === 'update') {
                            this.updateDisplay();
                        }
                    };
                }
                
                // Registrar esta sesión
                this.registerSession();
                
                // Limpiar sesiones inactivas
                this.cleanupSessions();
                
                // Actualizar display
                this.updateDisplay();
                
                // Heartbeat cada 5 segundos para mantener sesión activa
                setInterval(() => this.heartbeat(), 5000);
                
                // Limpiar sesiones inactivas cada 10 segundos
                setInterval(() => this.cleanupSessions(), 10000);
                
                // Detectar cuando el usuario cierra la pestaña
                window.addEventListener('beforeunload', () => this.unregisterSession());
                window.addEventListener('pagehide', () => this.unregisterSession());
                
                // Detectar visibilidad de la página
                document.addEventListener('visibilitychange', () => {
                    if (document.visibilityState === 'visible') {
                        this.registerSession();
                    }
                });
                
                // Mostrar notificación de bienvenida
                setTimeout(() => {
                    const count = this.getOnlineCount();
                    if (count === 1) {
                        showNotification('¡Eres el primer jugador online! 🎮', 'success');
                    } else {
                        showNotification(`¡Bienvenido! Hay ${count} jugadores online 🎮`, 'info');
                    }
                }, 1000);
            },
            
            registerSession() {
                const sessions = this.getSessions();
                sessions[this.sessionId] = {
                    timestamp: Date.now(),
                    id: this.sessionId
                };
                localStorage.setItem('fragx_sessions', JSON.stringify(sessions));
                this.broadcast();
                this.updateDisplay();
            },
            
            unregisterSession() {
                const sessions = this.getSessions();
                delete sessions[this.sessionId];
                localStorage.setItem('fragx_sessions', JSON.stringify(sessions));
                this.broadcast();
            },
            
            heartbeat() {
                const sessions = this.getSessions();
                if (sessions[this.sessionId]) {
                    sessions[this.sessionId].timestamp = Date.now();
                    localStorage.setItem('fragx_sessions', JSON.stringify(sessions));
                } else {
                    this.registerSession();
                }
            },
            
            cleanupSessions() {
                const sessions = this.getSessions();
                const now = Date.now();
                const timeout = 15000; // 15 segundos de inactividad
                let changed = false;
                
                for (const id in sessions) {
                    if (now - sessions[id].timestamp > timeout) {
                        delete sessions[id];
                        changed = true;
                    }
                }
                
                if (changed) {
                    localStorage.setItem('fragx_sessions', JSON.stringify(sessions));
                    this.updateDisplay();
                }
            },
            
            getSessions() {
                try {
                    return JSON.parse(localStorage.getItem('fragx_sessions')) || {};
                } catch (e) {
                    return {};
                }
            },
            
            getOnlineCount() {
                return Object.keys(this.getSessions()).length;
            },
            
            broadcast() {
                if (this.channel) {
                    this.channel.postMessage({ type: 'update' });
                }
            },
            
            updateDisplay() {
                const count = this.getOnlineCount();
                const countEl = document.getElementById('onlineCount');
                const pluralEl = document.getElementById('onlinePlural');
                
                if (countEl) {
                    // Animación de cambio
                    countEl.style.transform = 'scale(1.3)';
                    countEl.style.transition = 'transform 0.2s ease';
                    countEl.textContent = count;
                    
                    setTimeout(() => {
                        countEl.style.transform = 'scale(1)';
                    }, 200);
                }
                
                if (pluralEl) {
                    pluralEl.textContent = count === 1 ? '' : 'es';
                }
            }
        };
        
        // Inicializar tracker de jugadores online
        OnlineTracker.init();
        
        // Escuchar cambios en localStorage desde otras pestañas
        window.addEventListener('storage', (e) => {
            if (e.key === 'fragx_sessions') {
                OnlineTracker.updateDisplay();
            }
            if (e.key === 'fragx_teams') {
                updateTeamsCount();
            }
        });

        // ==================== TEAMS COUNTER ====================
        function getTeamsFromStorage() {
            try {
                return JSON.parse(localStorage.getItem('fragx_teams')) || [];
            } catch (e) {
                return [];
            }
        }
        
        function updateTeamsCount() {
            const teams = getTeamsFromStorage();
            const countEl = document.getElementById('teamsCount');
            const statTeamsEl = document.getElementById('statTeams');
            const statPlayersEl = document.getElementById('statPlayers');
            
            if (countEl) {
                countEl.textContent = teams.length;
            }
            
            // Actualizar stats grandes
            if (statTeamsEl) {
                statTeamsEl.textContent = teams.length;
            }
            
            // Contar total de jugadores (miembros de todos los equipos)
            if (statPlayersEl) {
                let totalPlayers = 0;
                teams.forEach(team => {
                    if (team.members && Array.isArray(team.members)) {
                        totalPlayers += team.members.length;
                    }
                });
                statPlayersEl.textContent = totalPlayers;
            }
        }
        
        // Actualizar contador de equipos al cargar
        updateTeamsCount();
        
        // ==================== RENDER TEAMS ====================
        const teamColors = [
            'from-[#de9b35] to-[#ff6a00]',
            'from-[#9146ff] to-[#ff00ff]',
            'from-[#00fff5] to-[#0099ff]',
            'from-[#39ff14] to-[#00ff88]',
            'from-[#ff6a00] to-[#ff0000]',
            'from-[#ffd700] to-[#ff6a00]'
        ];
        
        const teamEmojis = ['⚡', '👻', '🐺', '⚔️', '🔥', '💎', '🎯', '🚀', '💀', '🦅'];
        
        function renderTeams() {
            const teams = getTeamsFromStorage();
            const grid = document.getElementById('teamsGrid');
            const noTeamsMsg = document.getElementById('noTeamsMessage');
            const showAllBtn = document.getElementById('showAllTeamsBtn');
            
            if (teams.length === 0) {
                grid.innerHTML = '';
                noTeamsMsg.classList.remove('hidden');
                showAllBtn.classList.add('hidden');
                return;
            }
            
            noTeamsMsg.classList.add('hidden');
            if (teams.length > 4) {
                showAllBtn.classList.remove('hidden');
            }
            
            const teamsToShow = teams.slice(0, 4);
            grid.innerHTML = teamsToShow.map((team, index) => {
                const colorClass = teamColors[index % teamColors.length];
                const emoji = teamEmojis[index % teamEmojis.length];
                const rankBadge = index === 0 ? '🏆 #1' : index === 1 ? '🥈 #2' : index === 2 ? '🥉 #3' : `📍 #${index + 1}`;
                const rankColor = index === 0 ? 'text-[#ffd700]' : index === 1 ? 'text-[#c0c0c0]' : index === 2 ? 'text-[#cd7f32]' : 'text-gray-400';
                
                return `
                    <div class="team-card gamer-card rounded-lg p-6 text-center cursor-pointer" onclick="openCreatedTeamModal('${team.id}')">
                        <div class="w-20 h-20 mx-auto mb-4 bg-gradient-to-br ${colorClass} rounded-lg flex items-center justify-center text-3xl">${emoji}</div>
                        <h3 class="text-xl font-bold text-white mb-1">${team.name}</h3>
                        <p class="${rankColor} text-sm mb-3">${rankBadge} Ranking</p>
                        <div class="text-gray-400 text-sm space-y-1">
                            <p>[${team.tag}]</p>
                            <p class="text-[#00fff5]">👥 ${team.members ? team.members.length : 1} miembros</p>
                        </div>
                        <div class="mt-3 text-xs text-gray-500">
                            ${team.region === 'latam' ? '🌎 LATAM' : team.region === 'na' ? '🇺🇸 NA' : team.region === 'eu' ? '🇪🇺 EU' : '🌏 Asia'}
                        </div>
                    </div>
                `;
            }).join('');
        }
        
        function openCreatedTeamModal(teamId) {
            const teams = getTeamsFromStorage();
            const team = teams.find(t => t.id === teamId);
            if (!team) return;
            
            const content = `
                <div class="text-center mb-6">
                    <div class="w-24 h-24 mx-auto mb-4 bg-gradient-to-br from-[#de9b35] to-[#ff6a00] rounded-lg flex items-center justify-center text-4xl">${team.tag.charAt(0)}</div>
                    <p class="text-gray-400">[${team.tag}]</p>
                </div>
                
                <div class="grid grid-cols-2 gap-4">
                    <div class="bg-[#0a0a0f] p-4 rounded-lg text-center">
                        <p class="text-3xl font-bold text-[#00fff5]">${team.members ? team.members.length : 1}</p>
                        <p class="text-gray-500 text-sm">Miembros</p>
                    </div>
                    <div class="bg-[#0a0a0f] p-4 rounded-lg text-center">
                        <p class="text-3xl font-bold text-[#39ff14]">0</p>
                        <p class="text-gray-500 text-sm">Partidas</p>
                    </div>
                </div>
                
                <div class="mt-4 bg-[#0a0a0f] p-4 rounded-lg">
                    <p class="text-gray-500 text-sm mb-2">Región: <span class="text-white">${team.region === 'latam' ? '🌎 Latinoamérica' : team.region === 'na' ? '🇺🇸 Norteamérica' : team.region === 'eu' ? '🇪🇺 Europa' : '🌏 Asia'}</span></p>
                    <p class="text-gray-500 text-sm">Capitán: <span class="text-[#de9b35]">${team.captain}</span></p>
                </div>
                
                <div class="mt-4">
                    <p class="text-gray-500 text-sm mb-2">Miembros del equipo:</p>
                    <div class="flex flex-wrap gap-2">
                        ${team.members ? team.members.map(m => `<span class="px-3 py-1 bg-[#1a1a2e] text-white text-sm rounded">${m}</span>`).join('') : `<span class="px-3 py-1 bg-[#1a1a2e] text-white text-sm rounded">${team.captain}</span>`}
                    </div>
                </div>
                
                <div class="mt-4 p-3 bg-[#39ff14]/10 rounded-lg border border-[#39ff14]/30 text-center">
                    <p class="text-[#39ff14] text-sm">✨ Equipo listo para inscribirse en torneos</p>
                </div>
            `;
            openModal('👥 ' + team.name, content);
        }
        
        // ==================== RENDER RANKING ====================
        function renderRanking() {
            const teams = getTeamsFromStorage();
            const rankingList = document.getElementById('rankingList');
            const noRankingData = document.getElementById('noRankingData');
            
            if (teams.length === 0) {
                rankingList.innerHTML = '';
                noRankingData.classList.remove('hidden');
                return;
            }
            
            noRankingData.classList.add('hidden');
            
            // Obtener todos los jugadores de todos los equipos
            let allPlayers = [];
            teams.forEach(team => {
                if (team.members && Array.isArray(team.members)) {
                    team.members.forEach((member, idx) => {
                        allPlayers.push({
                            name: member,
                            team: team.name,
                            isCaptain: idx === 0
                        });
                    });
                }
            });
            
            const playersToShow = allPlayers.slice(0, 5);
            
            rankingList.innerHTML = playersToShow.map((player, index) => {
                const rankIcon = index === 0 ? '🥇' : index === 1 ? '🥈' : index === 2 ? '🥉' : (index + 1);
                const rankColor = index === 0 ? 'text-[#ffd700]' : index === 1 ? 'text-[#c0c0c0]' : index === 2 ? 'text-[#cd7f32]' : 'text-gray-400';
                const colorClass = teamColors[index % teamColors.length];
                const initials = player.name.substring(0, 2).toUpperCase();
                
                return `
                    <div class="p-4 border-b border-gray-800 grid grid-cols-12 gap-4 items-center hover:bg-[#1a1a2e] transition">
                        <div class="col-span-1 ${rankColor} font-bold text-xl">${rankIcon}</div>
                        <div class="col-span-5 flex items-center gap-3">
                            <div class="w-10 h-10 bg-gradient-to-br ${colorClass} rounded-lg flex items-center justify-center font-bold text-sm">${initials}</div>
                            <div>
                                <p class="font-bold text-white">${player.name} ${player.isCaptain ? '👑' : ''}</p>
                                <p class="text-xs text-gray-500">${player.team}</p>
                            </div>
                        </div>
                        <div class="col-span-2 text-center"><span class="text-gray-400 text-sm">-</span></div>
                        <div class="col-span-2 text-center text-gray-400">-</div>
                        <div class="col-span-2 text-center text-gray-400">Nuevo</div>
                    </div>
                `;
            }).join('');
        }
        
        // Renderizar al cargar
        renderTeams();
        renderRanking();

        // ==================== MINECRAFT CLANS ====================
        function getClansFromStorage() {
            try {
                return JSON.parse(localStorage.getItem('fragx_clans')) || [];
            } catch (e) {
                return [];
            }
        }
        
        function updateClansCount() {
            const clans = getClansFromStorage();
            const statClansEl = document.getElementById('statClans');
            const statMcPlayersEl = document.getElementById('statMcPlayers');
            
            if (statClansEl) {
                statClansEl.textContent = clans.length;
            }
            
            if (statMcPlayersEl) {
                let totalMembers = 0;
                clans.forEach(clan => {
                    if (clan.members && Array.isArray(clan.members)) {
                        totalMembers += clan.members.length;
                    }
                });
                statMcPlayersEl.textContent = totalMembers;
            }
        }
        
        const clanColors = [
            'from-[#ff4444] to-[#ff0000]',
            'from-[#39ff14] to-[#00ff88]',
            'from-[#ffd700] to-[#ff6a00]',
            'from-[#9146ff] to-[#ff00ff]',
            'from-[#00fff5] to-[#0099ff]',
            'from-[#ff6a00] to-[#ff4444]'
        ];
        
        const clanEmojis = ['💀', '⚔️', '🔥', '👑', '☠️', '🗡️', '🏴', '💣', '🐉', '🦅'];
        
        function renderClans() {
            const clans = getClansFromStorage();
            const grid = document.getElementById('clansGrid');
            const noClansMsg = document.getElementById('noClansMessage');
            
            if (clans.length === 0) {
                grid.innerHTML = '';
                noClansMsg.classList.remove('hidden');
                return;
            }
            
            noClansMsg.classList.add('hidden');
            
            const clansToShow = clans.slice(0, 4);
            grid.innerHTML = clansToShow.map((clan, index) => {
                const colorClass = clanColors[index % clanColors.length];
                const emoji = clanEmojis[index % clanEmojis.length];
                const rankBadge = index === 0 ? '👑 #1' : index === 1 ? '⚔️ #2' : index === 2 ? '💀 #3' : `#${index + 1}`;
                const rankColor = index === 0 ? 'text-[#ffd700]' : index === 1 ? 'text-[#c0c0c0]' : index === 2 ? 'text-[#cd7f32]' : 'text-gray-400';
                
                const objectives = {
                    pvp: '⚔️ PvP',
                    raiding: '💣 Raiding',
                    building: '🏰 Building',
                    domination: '👑 Dominación',
                    chaos: '🔥 Caos'
                };
                
                return `
                    <div class="team-card gamer-card rounded-lg p-6 text-center cursor-pointer border border-[#39ff14]/30 hover:border-[#39ff14]" onclick="openClanModal('${clan.id}')">
                        <div class="w-20 h-20 mx-auto mb-4 bg-gradient-to-br ${colorClass} rounded-lg flex items-center justify-center text-3xl">${emoji}</div>
                        <h3 class="text-xl font-bold text-white mb-1">${clan.name}</h3>
                        <p class="${rankColor} text-sm mb-3">${rankBadge} Poder</p>
                        <div class="text-gray-400 text-sm space-y-1">
                            <p>[${clan.tag}]</p>
                            <p class="text-[#ff4444]">☠️ ${clan.members ? clan.members.length : 1} guerreros</p>
                            <p class="text-[#39ff14] text-xs">${objectives[clan.objective] || '🔥 Caos'}</p>
                        </div>
                    </div>
                `;
            }).join('');
        }
        
        function openClanModal(clanId) {
            const clans = getClansFromStorage();
            const clan = clans.find(c => c.id === clanId);
            if (!clan) return;
            
            const objectives = {
                pvp: '⚔️ PvP y Combate',
                raiding: '💣 Raiding y Griefing',
                building: '🏰 Construcción',
                domination: '👑 Dominación Total',
                chaos: '🔥 Puro Caos'
            };
            
            const content = `
                <div class="text-center mb-6">
                    <div class="w-24 h-24 mx-auto mb-4 bg-gradient-to-br from-[#ff4444] to-[#ff0000] rounded-lg flex items-center justify-center text-4xl">⚔️</div>
                    <p class="text-gray-400">[${clan.tag}]</p>
                </div>
                
                <div class="grid grid-cols-2 gap-4">
                    <div class="bg-[#0a0a0f] p-4 rounded-lg text-center border border-[#39ff14]/30">
                        <p class="text-3xl font-bold text-[#ff4444]">${clan.members ? clan.members.length : 1}</p>
                        <p class="text-gray-500 text-sm">Guerreros</p>
                    </div>
                    <div class="bg-[#0a0a0f] p-4 rounded-lg text-center border border-[#39ff14]/30">
                        <p class="text-3xl font-bold text-[#ffd700]">💀</p>
                        <p class="text-gray-500 text-sm">Kills: ???</p>
                    </div>
                </div>
                
                <div class="mt-4 bg-[#0a0a0f] p-4 rounded-lg border border-[#39ff14]/30">
                    <p class="text-gray-500 text-sm mb-2">Objetivo: <span class="text-[#39ff14]">${objectives[clan.objective] || '🔥 Caos'}</span></p>
                    <p class="text-gray-500 text-sm">Líder: <span class="text-[#ffd700]">👑 ${clan.leader}</span></p>
                    ${clan.discord ? `<p class="text-gray-500 text-sm mt-2">Discord: <span class="text-[#5865f2]">${clan.discord}</span></p>` : ''}
                </div>
                
                <div class="mt-4">
                    <p class="text-gray-500 text-sm mb-2">Miembros del clan:</p>
                    <div class="flex flex-wrap gap-2">
                        ${clan.members ? clan.members.map((m, i) => `<span class="px-3 py-1 bg-[#1a1a2e] text-white text-sm rounded border border-[#39ff14]/30">${i === 0 ? '👑 ' : ''}${m}</span>`).join('') : `<span class="px-3 py-1 bg-[#1a1a2e] text-white text-sm rounded">👑 ${clan.leader}</span>`}
                    </div>
                </div>
                
                <div class="mt-4 p-3 bg-[#ff4444]/10 rounded-lg border border-[#ff4444]/30 text-center">
                    <p class="text-[#ff4444] text-sm">☠️ Clan activo en Infection.Fun</p>
                </div>
                
                <button onclick="copyServerIP(); closeModal();" class="w-full mt-4 btn-gamer btn-green py-3 rounded font-bold uppercase">
                    ⛏️ Unirse al Servidor
                </button>
            `;
            openModal('⚔️ ' + clan.name, content);
        }
        
        function addClanMember() {
            const container = document.getElementById('clanMembersContainer');
            const div = document.createElement('div');
            div.className = 'flex gap-2';
            div.innerHTML = `
                <input type="text" class="clan-member-input flex-1 px-4 py-2 bg-[#0a0a0f] border border-gray-700 rounded text-white placeholder-gray-600" placeholder="Nick de Minecraft">
                <button type="button" onclick="removeClanMember(this)" class="px-3 py-2 bg-red-600/20 text-red-500 rounded hover:bg-red-600 hover:text-white transition">✕</button>
            `;
            container.appendChild(div);
        }
        
        function removeClanMember(btn) {
            btn.parentElement.remove();
        }
        
        function copyServerIP() {
            navigator.clipboard.writeText('infection.fun').then(() => {
                showNotification('📋 IP copiada: infection.fun', 'success');
            }).catch(() => {
                showNotification('IP: infection.fun', 'info');
            });
        }
        
        function openMcDiscord() {
            showNotification('Abriendo Discord de Infection.Fun...', 'info');
            window.open('https://discord.gg', '_blank');
        }
        
        // Form de crear clan
        document.getElementById('createClanForm').addEventListener('submit', function(e) {
            e.preventDefault();
            
            // Verificar si está logueado
            if (!Auth.isLoggedIn()) {
                showNotification('Debes iniciar sesión para crear un clan', 'warning');
                setTimeout(() => openLoginModal(), 500);
                return;
            }
            
            const clanName = document.getElementById('clanName').value;
            const clanTag = document.getElementById('clanTag').value;
            const clanLeader = document.getElementById('clanLeader').value;
            const clanDiscord = document.getElementById('clanDiscord').value;
            const clanObjective = document.getElementById('clanObjective').value;
            
            const btn = document.getElementById('createClanBtn');
            btn.textContent = '⏳ Creando clan...';
            btn.disabled = true;
            
            setTimeout(() => {
                const clans = getClansFromStorage();
                const members = [clanLeader];
                document.querySelectorAll('.clan-member-input').forEach(input => {
                    if (input.value.trim()) members.push(input.value.trim());
                });
                
                const newClan = {
                    id: 'clan_' + Date.now(),
                    name: clanName,
                    tag: clanTag.toUpperCase(),
                    leader: clanLeader,
                    discord: clanDiscord,
                    objective: clanObjective,
                    members: members,
                    createdAt: new Date().toISOString()
                };
                
                clans.push(newClan);
                localStorage.setItem('fragx_clans', JSON.stringify(clans));
                updateClansCount();
                renderClans();
                
                showNotification('⚔️ ¡Clan creado exitosamente!', 'success');
                
                openModal('⚔️ ¡Clan Creado!', `
                    <div class="text-center">
                        <div class="text-6xl mb-4">⚔️</div>
                        <p class="text-2xl font-bold text-white mb-2">${clanName}</p>
                        <p class="text-[#39ff14] mb-4">[${clanTag.toUpperCase()}]</p>
                        <p class="text-gray-400 mb-6">Líder: <span class="text-[#ffd700]">👑 ${clanLeader}</span></p>
                        
                        <div class="bg-[#0a0a0f] p-4 rounded-lg mb-6 border border-[#39ff14]/30">
                            <p class="text-[#39ff14] font-bold">✓ Clan registrado para Infection.Fun</p>
                            <p class="text-gray-500 text-sm mt-2">Ahora únete al servidor y domina</p>
                            <p class="text-[#ff4444] text-sm mt-2">☠️ Recuerda: NO HAY REGLAS</p>
                        </div>
                        
                        <button onclick="copyServerIP(); closeModal();" class="btn-gamer btn-green px-8 py-3 rounded font-bold uppercase">
                            ⛏️ Copiar IP y Jugar
                        </button>
                    </div>
                `);
                
                this.reset();
                btn.textContent = '⚔️ Crear Clan GRATIS';
                btn.disabled = false;
            }, 1500);
        });
        
        // Inicializar clans
        updateClansCount();
        renderClans();
        
        // Escuchar cambios en localStorage para clanes
        window.addEventListener('storage', (e) => {
            if (e.key === 'fragx_clans') {
                updateClansCount();
                renderClans();
            }
        });

        console.log('%c🎯 FRAGX - CS2 Torneos GRATIS', 'color: #de9b35; font-size: 20px; font-weight: bold;');
        console.log('%c⛏️ INFECTION.FUN - Minecraft Anarchy', 'color: #39ff14; font-size: 16px; font-weight: bold;');
        console.log('%c100% Gratis - Sin límites - Sin reglas - GG WP', 'color: #39ff14;');
        console.log('%c📡 Sistema de jugadores online en TIEMPO REAL activado', 'color: #00fff5;');
    </script>
</body>
</html>
