<!DOCTYPE html>
<html lang="es" class="light">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title id="page-title">Parasitología Agrícola - Workspace Académico</title>
  <!-- Tailwind CSS -->
  <script src="https://cdn.tailwindcss.com"></script>
  <!-- FontAwesome Icons -->
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
  <!-- Google Fonts -->
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Fira+Code:wght@500;700&family=Inter:wght@300;400;500;600;700&family=Outfit:wght@500;700&family=Poppins:wght@500;700&family=Roboto+Mono:wght@500;700&family=Share+Tech+Mono&family=Space+Grotesk:wght@500;700&family=Space+Mono:wght@700&display=swap" rel="stylesheet">
  
  <script>
    tailwind.config = {
      darkMode: 'class',
    }
  </script>

  <style>
    :root {
      --color-accent: #10b981;
      --color-accent-hover: #059669;
      --color-accent-light: #ecfdf5;
      --font-clock: 'Space Grotesk', sans-serif;
    }

    body { font-family: 'Inter', sans-serif; }
    .font-clock-custom { font-family: var(--font-clock); }

    .bg-accent { background-color: var(--color-accent) !important; }
    .bg-accent:hover { background-color: var(--color-accent-hover) !important; }
    .text-accent { color: var(--color-accent) !important; }
    .border-accent { border-color: var(--color-accent) !important; }
    .bg-accent-light { background-color: var(--color-accent-light) !important; }

    .custom-scrollbar::-webkit-scrollbar { width: 6px; height: 6px; }
    .custom-scrollbar::-webkit-scrollbar-track { background: transparent; }
    .custom-scrollbar::-webkit-scrollbar-thumb { background: rgba(156, 163, 175, 0.4); border-radius: 9999px; }
    .dark .custom-scrollbar::-webkit-scrollbar-thumb { background: rgba(75, 85, 99, 0.4); }

    input[type="color"]::-webkit-color-swatch-wrapper { padding: 0; }
    input[type="color"]::-webkit-color-swatch { border: none; border-radius: 9999px; }

    .edit-mode-active .widget-box {
      outline: 2px dashed rgba(16, 185, 129, 0.5);
      outline-offset: 3px;
    }
  </style>
</head>
<body class="bg-gray-50 text-gray-800 dark:bg-[#181818] dark:text-gray-200 min-h-screen transition-colors duration-200">

  <div class="flex h-screen overflow-hidden">
    <!-- Sidebar / Navegación -->
    <aside class="w-72 bg-white dark:bg-[#202020] border-r border-gray-200 dark:border-neutral-800 flex flex-col justify-between hidden md:flex shrink-0">
      <div class="p-4 space-y-3.5 overflow-y-auto custom-scrollbar flex-1">
        
        <!-- Logo e Identidad -->
        <div class="flex items-center space-x-3 px-1 pb-2 border-b border-gray-100 dark:border-neutral-800">
          <div id="logo-container" class="w-11 h-11 rounded-2xl bg-accent-light dark:bg-neutral-800 border border-gray-200 dark:border-neutral-700 flex items-center justify-center text-2xl shadow-sm shrink-0 overflow-hidden">
            <span id="logo-display">🪲</span>
          </div>
          <div class="overflow-hidden">
            <h1 id="app-title-display" class="font-bold text-xs tracking-wide leading-tight uppercase text-accent truncate">Parasitología</h1>
            <p id="app-sub-display" class="text-[10px] text-gray-500 dark:text-gray-400 truncate">UACh - Sexto Cuatro</p>
            <p id="app-year-display" class="text-[9px] text-gray-400 dark:text-gray-500">2026</p>
          </div>
        </div>

        <!-- Navegación Principal -->
        <nav class="space-y-1">
          <button onclick="switchTab('horario')" id="nav-horario" class="w-full flex items-center justify-between px-3 py-2 text-xs rounded-xl bg-gray-100 dark:bg-neutral-800 font-medium text-accent">
            <div class="flex items-center space-x-2.5">
              <i class="fa-regular fa-calendar-days text-sm"></i>
              <span>Horario semanal</span>
            </div>
            <span id="badge-horario" class="hidden px-1.5 py-0.2 bg-accent text-white text-[9px] font-bold rounded-full">+1</span>
          </button>
          <button onclick="switchTab('tareas')" id="nav-tareas" class="w-full flex items-center justify-between px-3 py-2 text-xs rounded-xl text-gray-600 dark:text-gray-400 hover:bg-gray-100 dark:hover:bg-neutral-800 font-medium">
            <div class="flex items-center space-x-2.5">
              <i class="fa-regular fa-circle-check text-sm"></i>
              <span>Tareas</span>
            </div>
            <span id="badge-tareas" class="hidden px-1.5 py-0.2 bg-accent text-white text-[9px] font-bold rounded-full">+1</span>
          </button>
          <button onclick="switchTab('materias')" id="nav-materias" class="w-full flex items-center justify-between px-3 py-2 text-xs rounded-xl text-gray-600 dark:text-gray-400 hover:bg-gray-100 dark:hover:bg-neutral-800 font-medium">
            <div class="flex items-center space-x-2.5">
              <i class="fa-solid fa-book text-sm"></i>
              <span>Materias</span>
            </div>
            <span id="badge-materias" class="hidden px-1.5 py-0.2 bg-accent text-white text-[9px] font-bold rounded-full">+1</span>
          </button>
          <button onclick="switchTab('profesores')" id="nav-profesores" class="w-full flex items-center justify-between px-3 py-2 text-xs rounded-xl text-gray-600 dark:text-gray-400 hover:bg-gray-100 dark:hover:bg-neutral-800 font-medium">
            <div class="flex items-center space-x-2.5">
              <i class="fa-solid fa-user-graduate text-sm"></i>
              <span>Profesores</span>
            </div>
            <span id="badge-profesores" class="hidden px-1.5 py-0.2 bg-accent text-white text-[9px] font-bold rounded-full">+1</span>
          </button>
        </nav>

        <hr class="border-gray-100 dark:border-neutral-800 my-1.5">

        <div id="sidebar-widgets-container" class="space-y-3">
          
          <!-- WIDGET 1: BUSCADOR GOOGLE -->
          <div data-widget-id="search" class="widget-box group relative space-y-1">
            <div class="edit-controls hidden flex justify-between items-center px-1 mb-1 text-[10px] text-gray-400 font-bold uppercase">
              <span>🔍 Buscador Google</span>
              <div class="space-x-1">
                <button onclick="moveWidget('search', 'up')" class="hover:text-accent p-0.5"><i class="fa-solid fa-chevron-up"></i></button>
                <button onclick="moveWidget('search', 'down')" class="hover:text-accent p-0.5"><i class="fa-solid fa-chevron-down"></i></button>
              </div>
            </div>
            <form onsubmit="googleSearch(event)" class="relative flex items-center">
              <input type="text" id="gsearch-input" placeholder="Buscar en Google..." class="w-full pl-9 pr-3 py-2 text-xs rounded-xl border border-gray-200 dark:border-neutral-700 bg-white dark:bg-neutral-900 text-gray-800 dark:text-gray-200 focus:outline-none focus:ring-1 focus:ring-emerald-500">
              <svg class="absolute left-2.5 w-4 h-4 pointer-events-none" viewBox="0 0 24 24">
                <path fill="#4285F4" d="M22.56 12.25c0-.78-.07-1.53-.2-2.25H12v4.26h5.92c-.26 1.37-1.04 2.53-2.21 3.31v2.77h3.57c2.08-1.92 3.28-4.74 3.28-8.09z"/>
                <path fill="#34A853" d="M12 23c2.97 0 5.46-.98 7.28-2.66l-3.57-2.77c-.98.66-2.23 1.06-3.71 1.06-2.86 0-5.29-1.93-6.16-4.53H2.18v2.84C3.99 20.53 7.7 23 12 23z"/>
                <path fill="#FBBC05" d="M5.84 14.09c-.22-.66-.35-1.36-.35-2.09s.13-1.43.35-2.09V7.06H2.18C1.43 8.55 1 10.22 1 12s.43 3.45 1.18 4.94l2.85-2.22.81-.63z"/>
                <path fill="#EA4335" d="M12 5.38c1.62 0 3.06.56 4.21 1.64l3.15-3.15C17.45 2.09 14.97 1 12 1 7.7 1 3.99 3.47 2.18 7.06l3.66 2.84c.87-2.6 3.3-4.52 6.16-4.52z"/>
              </svg>
            </form>
          </div>

          <!-- WIDGET 2: APLICACIONES -->
          <div data-widget-id="apps" class="widget-box group relative space-y-1.5">
            <div class="edit-controls hidden flex justify-between items-center px-1 mb-1 text-[10px] text-gray-400 font-bold uppercase">
              <span>🚀 Aplicaciones</span>
              <div class="space-x-1">
                <button onclick="moveWidget('apps', 'up')" class="hover:text-accent p-0.5"><i class="fa-solid fa-chevron-up"></i></button>
                <button onclick="moveWidget('apps', 'down')" class="hover:text-accent p-0.5"><i class="fa-solid fa-chevron-down"></i></button>
              </div>
            </div>
            
            <div class="flex items-center space-x-1 px-1">
              <span class="text-xs font-semibold text-gray-700 dark:text-gray-300">Aplicaciones</span>
              <button onclick="openModal('modal-acceso')" title="Agregar Aplicación" class="text-gray-400 hover:text-gray-600 dark:hover:text-gray-200 opacity-60 hover:opacity-100 transition p-0.5">
                <i class="fa-solid fa-plus text-[11px]"></i>
              </button>
            </div>
            
            <div id="quick-links-grid" class="grid grid-cols-2 gap-1.5"></div>
          </div>

          <!-- WIDGET 3: GEMINI IA BOTÓN -->
          <div data-widget-id="gemini" class="widget-box group relative">
            <div class="edit-controls hidden flex justify-between items-center px-1 mb-1 text-[10px] text-gray-400 font-bold uppercase">
              <span>✨ Gemini IA</span>
              <div class="space-x-1">
                <button onclick="moveWidget('gemini', 'up')" class="hover:text-accent p-0.5"><i class="fa-solid fa-chevron-up"></i></button>
                <button onclick="moveWidget('gemini', 'down')" class="hover:text-accent p-0.5"><i class="fa-solid fa-chevron-down"></i></button>
              </div>
            </div>
            <button onclick="switchTab('gemini')" id="nav-gemini" class="w-full p-2.5 rounded-2xl border border-purple-200 dark:border-purple-900/60 bg-gradient-to-r from-purple-50 to-indigo-50 dark:from-purple-950/30 dark:to-indigo-950/30 hover:shadow-sm transition flex items-center justify-between text-xs font-semibold text-purple-900 dark:text-purple-200">
              <div class="flex items-center space-x-2">
                <svg class="w-4 h-4 shrink-0" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
                  <path d="M12 2C12 7.52285 7.52285 12 2 12C7.52285 12 12 16.4771 12 22C12 16.4771 16.4771 12 22 12C16.4771 12 12 7.52285 12 2Z" fill="url(#gemini-gradient)"/>
                  <defs>
                    <linearGradient id="gemini-gradient" x1="2" y1="2" x2="22" y2="22" gradientUnits="userSpaceOnUse">
                      <stop stop-color="#9333EA"/>
                      <stop offset="0.5" stop-color="#4F46E5"/>
                      <stop offset="1" stop-color="#06B6D4"/>
                    </linearGradient>
                  </defs>
                </svg>
                <span>Gemini IA</span>
              </div>
              <span id="badge-gemini" class="hidden px-1.5 py-0.2 bg-purple-600 text-white text-[9px] font-bold rounded-full">+1</span>
            </button>
          </div>

          <!-- WIDGET 4: RELOJ MINIMALISTA -->
          <div data-widget-id="clock" class="widget-box group relative bg-white dark:bg-neutral-900/80 p-3.5 rounded-2xl border border-gray-200 dark:border-neutral-800 space-y-1 shadow-sm text-center">
            <div class="edit-controls hidden flex justify-between items-center px-1 mb-1 text-[10px] text-gray-400 font-bold uppercase">
              <span>🕒 Reloj</span>
              <div class="space-x-1">
                <button onclick="moveWidget('clock', 'up')" class="hover:text-accent p-0.5"><i class="fa-solid fa-chevron-up"></i></button>
                <button onclick="moveWidget('clock', 'down')" class="hover:text-accent p-0.5"><i class="fa-solid fa-chevron-down"></i></button>
              </div>
            </div>
            <div id="sidebar-live-clock" class="font-clock-custom text-xl font-bold tracking-tight text-gray-900 dark:text-gray-100">00:00:00 AM</div>
            <div id="sidebar-live-date" class="font-clock-custom text-[11px] font-medium text-accent truncate">Lunes, 21 Sep 2026</div>
          </div>

          <!-- WIDGET 5: TEMPORIZADOR POMODORO -->
          <div data-widget-id="pomodoro" class="widget-box group relative bg-gray-50 dark:bg-neutral-900 p-3.5 rounded-2xl border border-gray-200 dark:border-neutral-800 text-center space-y-2">
            <div class="edit-controls hidden flex justify-between items-center px-1 mb-1 text-[10px] text-gray-400 font-bold uppercase">
              <span>⏱️ Pomodoro</span>
              <div class="space-x-1">
                <button onclick="moveWidget('pomodoro', 'up')" class="hover:text-accent p-0.5"><i class="fa-solid fa-chevron-up"></i></button>
                <button onclick="moveWidget('pomodoro', 'down')" class="hover:text-accent p-0.5"><i class="fa-solid fa-chevron-down"></i></button>
              </div>
            </div>
            <div class="flex items-center justify-between px-1">
              <span class="text-[11px] font-bold text-gray-700 dark:text-gray-300 uppercase tracking-wider">Temporizador Pomodoro</span>
              <button onclick="togglePomoConfig()" class="text-gray-400 hover:text-accent text-[10px]" title="Ajustes Pomodoro"><i class="fa-solid fa-sliders"></i></button>
            </div>

            <!-- Display de tiempo -->
            <div id="pomo-display" class="font-clock-custom text-xl font-bold text-gray-800 dark:text-gray-100">25:00</div>

            <!-- Panel de Tiempos -->
            <div id="pomo-config-panel" class="hidden p-2.5 rounded-xl bg-white dark:bg-neutral-800 text-[10px] space-y-2 border border-gray-200 dark:border-neutral-700 text-left shadow-md">
              <div>
                <label class="block text-gray-500 font-medium mb-0.5">Estudio / Trabajo (min):</label>
                <input type="number" id="pomo-work-input" value="25" min="1" max="120" class="w-full px-2 py-1 rounded border dark:bg-neutral-900 dark:border-neutral-700 text-xs">
              </div>
              <div>
                <label class="block text-gray-500 font-medium mb-0.5">Descanso (min):</label>
                <input type="number" id="pomo-rest-input" value="5" min="1" max="60" class="w-full px-2 py-1 rounded border dark:bg-neutral-900 dark:border-neutral-700 text-xs">
              </div>
              <button onclick="savePomoCustomConfig()" class="w-full py-1.5 bg-accent text-white font-bold rounded-lg text-[10px] transition">Guardar Tiempos</button>
            </div>

            <div class="flex justify-center space-x-1.5">
              <button onclick="togglePomodoro()" id="pomo-btn" class="text-xs bg-accent text-white px-3 py-1.5 rounded-xl transition w-full font-medium shadow-sm hover:opacity-90">Iniciar</button>
              <button onclick="resetPomodoro()" class="text-xs px-2.5 py-1.5 bg-gray-200 dark:bg-neutral-800 text-gray-600 dark:text-gray-300 rounded-xl hover:bg-gray-300 transition" title="Reiniciar"><i class="fa-solid fa-rotate-right"></i></button>
            </div>
          </div>

        </div>

        <!-- BOTÓN "EDITAR ORDEN DE WIDGETS" DEBAJO DE LOS WIDGETS -->
        <div class="pt-3 pb-1">
          <button onclick="toggleEditMode()" id="edit-mode-btn" class="w-full p-2 rounded-xl text-xs text-gray-500 hover:bg-gray-100 dark:hover:bg-neutral-800 flex items-center justify-center space-x-2 border border-gray-200 dark:border-neutral-800 transition">
            <i class="fa-solid fa-sliders text-xs"></i>
            <span id="edit-mode-text">Editar orden de widgets</span>
          </button>
        </div>

      </div>

      <!-- BARRA INFERIOR DE NAVEGACIÓN DE LA SIDEBAR -->
      <div class="p-2.5 border-t border-gray-200 dark:border-neutral-800 flex items-center justify-between bg-white dark:bg-[#202020] relative text-xs">
        <button onclick="switchTab('ajustes')" id="nav-ajustes" title="Configuración" class="p-2 text-gray-600 dark:text-gray-300 hover:bg-gray-100 dark:hover:bg-neutral-800 rounded-xl transition">
          <i class="fa-solid fa-gear text-sm"></i>
        </button>

        <!-- Calendario Popover Toggle -->
        <button onclick="toggleCalendarPopover()" title="Abrir Calendario" class="px-2.5 py-1.5 text-[11px] font-semibold text-gray-700 dark:text-gray-200 hover:bg-gray-100 dark:hover:bg-neutral-800 rounded-xl transition flex items-center space-x-1 border border-gray-200 dark:border-neutral-700">
          <i class="fa-regular fa-calendar-days text-accent"></i>
          <span>Calendario</span>
        </button>

        <button onclick="toggleDarkMode()" title="Cambiar Tema" class="p-2 text-gray-600 dark:text-gray-300 hover:bg-gray-100 dark:hover:bg-neutral-800 rounded-xl transition">
          <i id="theme-icon" class="fa-solid fa-moon text-sm"></i>
        </button>

        <!-- POPOVER CALENDARIO -->
        <div id="calendar-popover" class="hidden absolute bottom-14 left-2 right-2 bg-white dark:bg-[#202020] border border-gray-200 dark:border-neutral-700 rounded-2xl p-3 shadow-2xl z-50 space-y-2">
          <div class="flex items-center justify-between border-b dark:border-neutral-800 pb-2">
            <span id="cal-month-title" class="text-xs font-bold text-gray-800 dark:text-gray-100">Septiembre 2026</span>
            <div class="space-x-1">
              <button onclick="changeCalMonth(-1)" class="text-xs px-1.5 py-0.5 text-gray-400 hover:text-accent"><i class="fa-solid fa-chevron-left"></i></button>
              <button onclick="changeCalMonth(1)" class="text-xs px-1.5 py-0.5 text-gray-400 hover:text-accent"><i class="fa-solid fa-chevron-right"></i></button>
              <button onclick="toggleCalendarPopover()" class="text-xs px-1.5 py-0.5 text-gray-400 hover:text-red-500 ml-1"><i class="fa-solid fa-xmark"></i></button>
            </div>
          </div>
          <div class="grid grid-cols-7 gap-1 text-center text-[10px] font-bold text-gray-400">
            <div>D</div><div>L</div><div>M</div><div>M</div><div>J</div><div>V</div><div>S</div>
          </div>
          <div id="calendar-days-grid" class="grid grid-cols-7 gap-1 text-center text-xs"></div>
          <p class="text-[9px] text-gray-400 text-center italic mt-1">Haz clic en un día para programar una tarea</p>
        </div>
      </div>
    </aside>

    <main class="flex-1 flex flex-col overflow-hidden bg-gray-50 dark:bg-[#181818]">
      <!-- Header Principal -->
      <header class="h-14 border-b border-gray-200 dark:border-neutral-800 bg-white/80 dark:bg-[#181818]/80 backdrop-blur flex items-center justify-between px-6 shrink-0">
        <div class="flex items-center space-x-4">
          <span id="header-title" class="font-semibold text-sm md:text-base text-gray-900 dark:text-gray-100">Horario semanal</span>
        </div>

        <div class="flex items-center space-x-3">
          <button id="btn-add-clase" onclick="openModal('modal-clase')" class="px-3 py-1.5 bg-accent text-white rounded-xl text-xs font-medium flex items-center space-x-1.5 transition shadow-sm">
            <i class="fa-solid fa-plus"></i><span>Clase</span>
          </button>
          
          <button id="btn-add-tarea" onclick="openModal('modal-tarea')" class="px-3 py-1.5 bg-gray-900 hover:bg-black dark:bg-neutral-200 dark:hover:bg-white dark:text-black text-white rounded-xl text-xs font-medium flex items-center space-x-1.5 transition shadow-sm">
            <i class="fa-solid fa-plus"></i><span>Tarea</span>
          </button>
        </div>
      </header>

      <div class="flex-1 overflow-y-auto custom-scrollbar p-6">
        
        <!-- SECCIÓN: HORARIO -->
        <section id="sec-horario" class="space-y-4">
          <div class="grid grid-cols-1 md:grid-cols-5 gap-4">
            <div id="schedule-container" class="contents"></div>
          </div>
        </section>

        <!-- SECCIÓN: TAREAS -->
        <section id="sec-tareas" class="hidden space-y-4">
          <div class="flex flex-wrap gap-2 items-center bg-white dark:bg-[#202020] p-3 rounded-2xl border border-gray-200 dark:border-neutral-800 text-xs shadow-sm">
            <span class="font-semibold text-gray-500 mr-2"><i class="fa-solid fa-filter mr-1"></i>Filtrar por:</span>
            <select id="filter-priority" onchange="renderTasks()" class="px-2.5 py-1 rounded-lg border bg-white dark:bg-neutral-800 dark:border-neutral-700 text-gray-800 dark:text-gray-200">
              <option value="ALL">Todas las Prioridades</option>
              <option value="Alta">🔴 Alta</option>
              <option value="Media">🟡 Media</option>
              <option value="Baja">🟢 Baja</option>
            </select>
            <select id="filter-type" onchange="renderTasks()" class="px-2.5 py-1 rounded-lg border bg-white dark:bg-neutral-800 dark:border-neutral-700 text-gray-800 dark:text-gray-200">
              <option value="ALL">Todos los Tipos</option>
              <option value="Examen">Examen</option>
              <option value="Reporte de Laboratorio">Reporte de Laboratorio</option>
              <option value="Lectura">Lectura</option>
              <option value="Exposición">Exposición</option>
              <option value="Tarea General">Tarea General</option>
            </select>
          </div>

          <div class="grid grid-cols-1 md:grid-cols-2 gap-6">
            <div class="bg-white dark:bg-[#202020] rounded-2xl border border-gray-200 dark:border-neutral-800 p-4 shadow-sm">
              <div class="flex items-center justify-between mb-4">
                <div class="flex items-center space-x-2">
                  <div class="w-3 h-3 rounded-full bg-amber-500"></div>
                  <h3 class="font-semibold text-sm">Incompletas</h3>
                  <span id="count-pending" class="text-xs bg-gray-100 dark:bg-neutral-800 px-2.5 py-0.5 rounded-full text-gray-500">0</span>
                </div>
              </div>
              <div id="tasks-pending" class="space-y-2.5 min-h-[200px]"></div>
            </div>

            <div class="bg-white dark:bg-[#202020] rounded-2xl border border-gray-200 dark:border-neutral-800 p-4 shadow-sm">
              <div class="flex items-center justify-between mb-4">
                <div class="flex items-center space-x-2">
                  <div class="w-3 h-3 rounded-full bg-emerald-500"></div>
                  <h3 class="font-semibold text-sm">Completadas</h3>
                  <span id="count-completed" class="text-xs bg-gray-100 dark:bg-neutral-800 px-2.5 py-0.5 rounded-full text-gray-500">0</span>
                </div>
              </div>
              <div id="tasks-completed" class="space-y-2.5 min-h-[200px]"></div>
            </div>
          </div>
        </section>

        <!-- SECCIÓN: MATERIAS -->
        <section id="sec-materias" class="hidden space-y-4">
          <div id="subjects-grid" class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-4"></div>
        </section>

        <!-- SECCIÓN: PROFESORES -->
        <section id="sec-profesores" class="hidden space-y-4">
          <div class="flex justify-between items-center mb-2">
            <h3 class="font-bold text-sm">Directorio de Catedráticos</h3>
            <button onclick="openModal('modal-profesor')" class="px-3.5 py-1.5 bg-accent text-white rounded-xl text-xs font-medium transition">
              <i class="fa-solid fa-plus mr-1"></i>Agregar Profesor
            </button>
          </div>
          <div id="teachers-grid" class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-4"></div>
        </section>

        <!-- SECCIÓN: GEMINI IA -->
        <section id="sec-gemini" class="hidden h-full flex flex-col space-y-4">
          <div class="bg-white dark:bg-[#202020] border border-gray-200 dark:border-neutral-800 rounded-2xl p-4 flex-1 flex flex-col shadow-sm">
            <div class="flex flex-wrap items-center justify-between pb-3 border-b border-gray-100 dark:border-neutral-800 mb-4 gap-2">
              <div class="flex items-center space-x-2.5">
                <svg class="w-5 h-5 shrink-0" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
                  <path d="M12 2C12 7.52285 7.52285 12 2 12C7.52285 12 12 16.4771 12 22C12 16.4771 16.4771 12 22 12C16.4771 12 12 7.52285 12 2Z" fill="url(#gemini-gradient-header)"/>
                  <defs>
                    <linearGradient id="gemini-gradient-header" x1="2" y1="2" x2="22" y2="22" gradientUnits="userSpaceOnUse">
                      <stop stop-color="#9333EA"/>
                      <stop offset="0.5" stop-color="#4F46E5"/>
                      <stop offset="1" stop-color="#06B6D4"/>
                    </linearGradient>
                  </defs>
                </svg>
                <div>
                  <h3 class="font-bold text-sm text-gray-900 dark:text-gray-100">Asistente Gemini IA</h3>
                  <p class="text-xs text-gray-400">Responde consultas y propone acciones académicas.</p>
                </div>
              </div>

              <!-- Selector y Key de Gemini -->
              <div class="flex flex-wrap items-center gap-2">
                <select id="gemini-model-select" class="px-2 py-1 text-xs border rounded-lg bg-white dark:bg-neutral-800 dark:border-neutral-700 text-gray-800 dark:text-gray-200">
                  <option value="AUTO">Detección Automática de Modelo</option>
                  <option value="gemini-1.5-flash">gemini-1.5-flash</option>
                  <option value="gemini-2.0-flash">gemini-2.0-flash</option>
                  <option value="gemini-2.5-flash">gemini-2.5-flash</option>
                  <option value="gemini-1.5-pro">gemini-1.5-pro</option>
                </select>
                <input type="password" id="gemini-api-key" placeholder="Pega tu Gemini API Key" class="px-2.5 py-1 text-xs border rounded-lg bg-white dark:bg-neutral-800 dark:border-neutral-700 w-44 focus:outline-none text-gray-800 dark:text-gray-200">
                <button onclick="saveApiKey()" class="px-3 py-1 bg-purple-600 text-white text-xs font-medium rounded-lg hover:bg-purple-700 transition">
                  🔑 Guardar Key
                </button>
                <button onclick="clearChatHistory()" title="Borrar Conversación" class="px-2 py-1 text-xs text-gray-400 hover:text-red-500 border rounded-lg dark:border-neutral-700">
                  <i class="fa-solid fa-trash"></i>
                </button>
              </div>
            </div>

            <div id="ai-confirmation-box" class="hidden bg-purple-50 dark:bg-purple-950/50 border border-purple-200 dark:border-purple-800 p-3.5 rounded-2xl mb-3 space-y-2 text-xs">
              <div class="font-bold text-purple-900 dark:text-purple-300 flex items-center space-x-1.5">
                <i class="fa-solid fa-triangle-exclamation text-amber-500"></i>
                <span>Confirmación requerida de Gemini</span>
              </div>
              <p id="ai-confirm-text" class="text-gray-700 dark:text-gray-300"></p>
              <div class="flex space-x-2 pt-1">
                <button onclick="applyAiAction()" class="px-3 py-1.5 bg-accent text-white rounded-xl font-medium transition">✅ Confirmar y Aplicar</button>
                <button onclick="cancelAiAction()" class="px-3 py-1.5 bg-gray-200 dark:bg-neutral-700 text-gray-700 dark:text-gray-200 rounded-xl hover:bg-gray-300 transition">❌ Cancelar</button>
              </div>
            </div>

            <div id="chat-history" class="flex-1 overflow-y-auto custom-scrollbar space-y-3 p-2 min-h-[250px]"></div>

            <div id="file-preview-bar" class="hidden text-xs bg-gray-100 dark:bg-neutral-800 p-2 rounded-xl flex items-center justify-between mb-2">
              <span id="file-preview-name" class="truncate font-medium"></span>
              <button onclick="removeAttachment()" class="text-red-500 hover:text-red-700"><i class="fa-solid fa-xmark"></i></button>
            </div>

            <form onsubmit="handleChatSubmit(event)" class="mt-2 flex space-x-2">
              <label class="p-2 border rounded-xl bg-white dark:bg-neutral-800 dark:border-neutral-700 text-gray-500 hover:bg-gray-100 dark:hover:bg-neutral-700 cursor-pointer flex items-center justify-center">
                <i class="fa-solid fa-paperclip text-sm"></i>
                <input type="file" id="chat-file-input" onchange="handleFileAttach(event)" class="hidden">
              </label>
              <input type="text" id="gemini-prompt" placeholder="Escribe tu consulta o adjunta un archivo..." class="flex-1 px-3 py-2 text-xs rounded-xl border bg-white dark:bg-neutral-800 dark:border-neutral-700 text-gray-800 dark:text-gray-200 focus:outline-none focus:ring-2 focus:ring-purple-500">
              <button type="submit" class="px-4 py-2 bg-purple-600 hover:bg-purple-700 text-white rounded-xl text-xs font-medium transition">
                Enviar
              </button>
            </form>
          </div>
        </section>

        <!-- SECCIÓN: CONFIGURACIÓN -->
        <section id="sec-ajustes" class="hidden space-y-6">
          <div class="bg-white dark:bg-[#202020] border border-gray-200 dark:border-neutral-800 rounded-3xl p-6 max-w-2xl space-y-6 shadow-sm">
            <h3 class="font-bold text-base flex items-center space-x-2 text-gray-900 dark:text-gray-100">
              <i class="fa-solid fa-gear text-gray-500"></i>
              <span>Configuración del Sistema</span>
            </h3>

            <div class="space-y-4 text-xs">
              <div class="p-4 border dark:border-neutral-800 rounded-2xl space-y-3 bg-gray-50/50 dark:bg-neutral-900/30">
                <h4 class="font-semibold text-gray-800 dark:text-gray-200"><i class="fa-solid fa-clock text-accent mr-1"></i> Plantilla y Fuente del Reloj</h4>
                <div class="grid grid-cols-1 md:grid-cols-2 gap-3">
                  <div>
                    <label class="block text-gray-400 mb-1">Tipografía / Estilo:</label>
                    <select id="cfg-clock-font" onchange="updateClockFont(this.value)" class="w-full px-3 py-1.5 rounded-xl border bg-white dark:bg-neutral-800 dark:border-neutral-700 text-xs text-gray-800 dark:text-gray-200 focus:outline-none">
                      <option value="'Space Grotesk', sans-serif">Space Grotesk (Elegante)</option>
                      <option value="'Roboto Mono', monospace">Roboto Mono (Digital)</option>
                      <option value="'Fira Code', monospace">Fira Code (Digital Mono)</option>
                      <option value="'Inter', sans-serif">Inter (Minimalista)</option>
                      <option value="'Share Tech Mono', monospace">Share Tech Mono (Sci-Fi / Futurista)</option>
                      <option value="'Outfit', sans-serif">Outfit (Modern Bold)</option>
                      <option value="'Poppins', sans-serif">Poppins (Geométrico)</option>
                      <option value="'Space Mono', monospace">Space Mono (Retro Tech)</option>
                    </select>
                  </div>
                </div>
              </div>

              <div class="p-4 border dark:border-neutral-800 rounded-2xl space-y-3 bg-gray-50/50 dark:bg-neutral-900/30">
                <h4 class="font-semibold text-gray-800 dark:text-gray-200">Identidad del Curso</h4>
                <div class="grid grid-cols-1 md:grid-cols-3 gap-2.5">
                  <div>
                    <label class="text-[10px] text-gray-400 font-medium">Título</label>
                    <input type="text" id="cfg-title" onchange="updateIdentity()" class="w-full px-2.5 py-1.5 rounded-xl border bg-white dark:bg-neutral-800 dark:border-neutral-700 text-gray-800 dark:text-gray-200">
                  </div>
                  <div>
                    <label class="text-[10px] text-gray-400 font-medium">Subtítulo / Universidad</label>
                    <input type="text" id="cfg-sub" onchange="updateIdentity()" class="w-full px-2.5 py-1.5 rounded-xl border bg-white dark:bg-neutral-800 dark:border-neutral-700 text-gray-800 dark:text-gray-200">
                  </div>
                  <div>
                    <label class="text-[10px] text-gray-400 font-medium">Año / Periodo</label>
                    <input type="text" id="cfg-year" onchange="updateIdentity()" class="w-full px-2.5 py-1.5 rounded-xl border bg-white dark:bg-neutral-800 dark:border-neutral-700 text-gray-800 dark:text-gray-200">
                  </div>
                </div>
              </div>

              <div class="p-4 border dark:border-neutral-800 rounded-2xl space-y-3 bg-gray-50/50 dark:bg-neutral-900/30">
                <h4 class="font-semibold text-gray-800 dark:text-gray-200">Logo del Workspace</h4>
                <div class="flex flex-wrap items-center gap-3">
                  <select id="cfg-logo-emoji" onchange="updateLogoEmoji(this.value)" class="px-2.5 py-1.5 rounded-xl border bg-white dark:bg-neutral-800 dark:border-neutral-700 text-sm text-gray-800 dark:text-gray-200">
                    <option value="🪲">🪲 Escarabajo</option>
                    <option value="🦟">🦟 Mosquito</option>
                    <option value="🔬">🔬 Microscopio</option>
                    <option value="🌿">🌿 Hoja / Planta</option>
                    <option value="🌻">🌻 Girasol</option>
                    <option value="🧪">🧪 Tubo Ensayo</option>
                    <option value="🧬">🧬 ADN</option>
                    <option value="🐞">🐞 Mariquita</option>
                  </select>
                  <span class="text-gray-400">o sube tu imagen:</span>
                  <input type="file" accept="image/*" onchange="uploadCustomLogo(event)" class="text-xs text-gray-500">
                  <button onclick="resetLogo()" class="text-xs text-red-500 underline font-medium">Restablecer</button>
                </div>
              </div>

              <div class="p-4 border dark:border-neutral-800 rounded-2xl flex items-center justify-between bg-gray-50/50 dark:bg-neutral-900/30">
                <div>
                  <h4 class="font-semibold text-gray-800 dark:text-gray-200">Color de Acento Principal</h4>
                  <p class="text-gray-400 mt-0.5">Afecta botones y relieves.</p>
                </div>
                <input type="color" id="cfg-theme-color" value="#10b981" onchange="setThemeAccentColor(this.value)" class="w-9 h-9 rounded-full border-0 cursor-pointer p-0 bg-transparent shadow-sm">
              </div>

              <div class="p-4 border dark:border-neutral-800 rounded-2xl flex items-center justify-between bg-gray-50/50 dark:bg-neutral-900/30">
                <div>
                  <h4 class="font-semibold text-gray-800 dark:text-gray-200">Restablecer Datos por Defecto</h4>
                  <p class="text-gray-400 mt-0.5">Borra la memoria local y reestablece todo.</p>
                </div>
                <button onclick="if(confirm('¿Restablecer todo?')){ localStorage.clear(); location.reload(); }" class="px-3.5 py-1.5 bg-red-100 text-red-600 rounded-xl font-medium hover:bg-red-200">Restablecer</button>
              </div>
            </div>
          </div>
        </section>

      </div>
    </main>
  </div>

  <!-- MODAL CLASE -->
  <div id="modal-clase" class="fixed inset-0 bg-black/50 backdrop-blur-sm hidden flex items-center justify-center p-4 z-50">
    <div class="bg-white dark:bg-[#202020] border border-gray-200 dark:border-neutral-800 rounded-2xl w-full max-w-md p-6 shadow-2xl">
      <h3 class="text-base font-bold mb-4" id="modal-clase-title">Agregar Clase</h3>
      <form id="form-clase" onsubmit="saveClass(event)" class="space-y-3">
        <input type="hidden" id="clase-id">
        <div>
          <label class="block text-xs font-medium text-gray-500 mb-1">Materia</label>
          <input type="text" id="clase-materia" list="dl-materias" required class="w-full px-3 py-2 text-sm rounded-xl border bg-white dark:bg-neutral-800 dark:border-neutral-700 text-gray-800 dark:text-gray-200">
          <datalist id="dl-materias"></datalist>
        </div>
        <div class="grid grid-cols-2 gap-2">
          <div>
            <label class="block text-xs font-medium text-gray-500 mb-1">Día</label>
            <select id="clase-dia" class="w-full px-3 py-2 text-sm rounded-xl border bg-white dark:bg-neutral-800 dark:border-neutral-700 text-gray-800 dark:text-gray-200">
              <option value="Lunes">Lunes</option>
              <option value="Martes">Martes</option>
              <option value="Miércoles">Miércoles</option>
              <option value="Jueves">Jueves</option>
              <option value="Viernes">Viernes</option>
            </select>
          </div>
          <div>
            <label class="block text-xs font-medium text-gray-500 mb-1">Tipo</label>
            <select id="clase-tipo" class="w-full px-3 py-2 text-sm rounded-xl border bg-white dark:bg-neutral-800 dark:border-neutral-700 text-gray-800 dark:text-gray-200">
              <option value="T">Teoría (T)</option>
              <option value="P">Práctica (P)</option>
              <option value="O">Optativa</option>
            </select>
          </div>
        </div>
        <div class="grid grid-cols-2 gap-2">
          <div>
            <label class="block text-xs font-medium text-gray-500 mb-1">Hora Inicio</label>
            <input type="time" id="clase-inicio" required class="w-full px-3 py-2 text-sm rounded-xl border bg-white dark:bg-neutral-800 dark:border-neutral-700 text-gray-800 dark:text-gray-200">
          </div>
          <div>
            <label class="block text-xs font-medium text-gray-500 mb-1">Hora Fin</label>
            <input type="time" id="clase-fin" required class="w-full px-3 py-2 text-sm rounded-xl border bg-white dark:bg-neutral-800 dark:border-neutral-700 text-gray-800 dark:text-gray-200">
          </div>
        </div>
        <div class="grid grid-cols-2 gap-2">
          <div>
            <label class="block text-xs font-medium text-gray-500 mb-1">Aula</label>
            <input type="text" id="clase-aula" class="w-full px-3 py-2 text-sm rounded-xl border bg-white dark:bg-neutral-800 dark:border-neutral-700 text-gray-800 dark:text-gray-200">
          </div>
          <div>
            <label class="block text-xs font-medium text-gray-500 mb-1">Profesor</label>
            <input type="text" id="clase-profesor" list="dl-profesores" class="w-full px-3 py-2 text-sm rounded-xl border bg-white dark:bg-neutral-800 dark:border-neutral-700 text-gray-800 dark:text-gray-200">
            <datalist id="dl-profesores"></datalist>
          </div>
        </div>
        <div class="flex justify-end space-x-2 pt-4">
          <button type="button" onclick="closeModal('modal-clase')" class="px-4 py-2 text-xs rounded-xl border hover:bg-gray-100 dark:hover:bg-neutral-800">Cancelar</button>
          <button type="submit" class="px-4 py-2 text-xs rounded-xl bg-accent text-white">Guardar</button>
        </div>
      </form>
    </div>
  </div>

  <!-- MODAL TAREA -->
  <div id="modal-tarea" class="fixed inset-0 bg-black/50 backdrop-blur-sm hidden flex items-center justify-center p-4 z-50">
    <div class="bg-white dark:bg-[#202020] border border-gray-200 dark:border-neutral-800 rounded-2xl w-full max-w-md p-6 shadow-2xl">
      <h3 class="text-base font-bold mb-4" id="modal-tarea-title">Nueva Tarea</h3>
      <form id="form-tarea" onsubmit="saveTask(event)" class="space-y-3">
        <input type="hidden" id="tarea-id">
        <div>
          <label class="block text-xs font-medium text-gray-500 mb-1">Título</label>
          <input type="text" id="tarea-titulo" required class="w-full px-3 py-2 text-sm rounded-xl border bg-white dark:bg-neutral-800 dark:border-neutral-700 text-gray-800 dark:text-gray-200">
        </div>
        <div>
          <label class="block text-xs font-medium text-gray-500 mb-1">Materia</label>
          <select id="tarea-materia" required class="w-full px-3 py-2 text-sm rounded-xl border bg-white dark:bg-neutral-800 dark:border-neutral-700 text-gray-800 dark:text-gray-200"></select>
        </div>
        <div class="grid grid-cols-2 gap-2">
          <div>
            <label class="block text-xs font-medium text-gray-500 mb-1">Prioridad</label>
            <select id="tarea-prioridad" class="w-full px-3 py-2 text-sm rounded-xl border bg-white dark:bg-neutral-800 dark:border-neutral-700 text-gray-800 dark:text-gray-200">
              <option value="Alta">🔴 Alta</option>
              <option value="Media" selected>🟡 Media</option>
              <option value="Baja">🟢 Baja</option>
            </select>
          </div>
          <div>
            <label class="block text-xs font-medium text-gray-500 mb-1">Tipo de Actividad</label>
            <select id="tarea-tipo" class="w-full px-3 py-2 text-sm rounded-xl border bg-white dark:bg-neutral-800 dark:border-neutral-700 text-gray-800 dark:text-gray-200">
              <option value="Tarea General">Tarea General</option>
              <option value="Examen">Examen</option>
              <option value="Reporte de Laboratorio">Reporte de Laboratorio</option>
              <option value="Lectura">Lectura</option>
              <option value="Exposición">Exposición</option>
            </select>
          </div>
        </div>
        <div>
          <label class="block text-xs font-medium text-gray-500 mb-1">Fecha de Entrega</label>
          <input type="date" id="tarea-fecha" class="w-full px-3 py-2 text-sm rounded-xl border bg-white dark:bg-neutral-800 dark:border-neutral-700 text-gray-800 dark:text-gray-200">
        </div>
        <div>
          <label class="block text-xs font-medium text-gray-500 mb-1">Notas adicionales</label>
          <textarea id="tarea-notas" rows="2" placeholder="Detalles de la entrega..." class="w-full px-3 py-2 text-sm rounded-xl border bg-white dark:bg-neutral-800 dark:border-neutral-700 text-gray-800 dark:text-gray-200"></textarea>
        </div>
        <div>
          <label class="block text-xs font-medium text-gray-500 mb-1">Adjuntar Archivo</label>
          <input type="file" id="tarea-file" onchange="handleModalTaskFile(event)" class="text-xs text-gray-500">
          <div id="modal-file-display" class="hidden text-xs text-emerald-600 font-medium mt-1"></div>
        </div>
        <div class="flex justify-end space-x-2 pt-4">
          <button type="button" onclick="closeModal('modal-tarea')" class="px-4 py-2 text-xs rounded-xl border hover:bg-gray-100 dark:hover:bg-neutral-800">Cancelar</button>
          <button type="submit" class="px-4 py-2 text-xs rounded-xl bg-accent text-white">Guardar Tarea</button>
        </div>
      </form>
    </div>
  </div>

  <!-- MODAL EDITAR MATERIA -->
  <div id="modal-materia" class="fixed inset-0 bg-black/50 backdrop-blur-sm hidden flex items-center justify-center p-4 z-50">
    <div class="bg-white dark:bg-[#202020] border border-gray-200 dark:border-neutral-800 rounded-2xl w-full max-w-sm p-5 shadow-2xl">
      <h3 class="text-sm font-bold mb-3">Renombrar Materia</h3>
      <form onsubmit="saveSubjectRename(event)" class="space-y-3">
        <input type="hidden" id="sub-old-name">
        <div>
          <label class="block text-xs text-gray-500 mb-1">Nombre Actual</label>
          <input type="text" id="sub-display-name" disabled class="w-full px-2.5 py-1.5 text-xs rounded-xl border bg-gray-100 dark:bg-neutral-800 dark:border-neutral-700 text-gray-800 dark:text-gray-200">
        </div>
        <div>
          <label class="block text-xs text-gray-500 mb-1">Nuevo Nombre</label>
          <input type="text" id="sub-new-name" required class="w-full px-2.5 py-1.5 text-xs rounded-xl border bg-white dark:bg-neutral-800 dark:border-neutral-700 text-gray-800 dark:text-gray-200">
        </div>
        <div class="flex justify-end space-x-2 pt-2">
          <button type="button" onclick="closeModal('modal-materia')" class="px-3 py-1.5 text-xs border rounded-xl">Cancelar</button>
          <button type="submit" class="px-3.5 py-1.5 text-xs bg-accent text-white rounded-xl">Guardar Cambios</button>
        </div>
      </form>
    </div>
  </div>

  <!-- MODAL ACCESO RÁPIDO / APP -->
  <div id="modal-acceso" class="fixed inset-0 bg-black/50 backdrop-blur-sm hidden flex items-center justify-center p-4 z-50">
    <div class="bg-white dark:bg-[#202020] border border-gray-200 dark:border-neutral-800 rounded-2xl w-full max-w-sm p-5 shadow-2xl">
      <h3 class="text-sm font-bold mb-3">Editar Aplicación</h3>
      <form onsubmit="saveQuickLink(event)" class="space-y-3">
        <input type="hidden" id="link-id">
        <div>
          <label class="block text-xs text-gray-500 mb-1">Nombre</label>
          <input type="text" id="link-name" required class="w-full px-2.5 py-1.5 text-xs rounded-xl border bg-white dark:bg-neutral-800 dark:border-neutral-700 text-gray-800 dark:text-gray-200">
        </div>
        <div>
          <label class="block text-xs text-gray-500 mb-1">URL Enlace</label>
          <input type="url" id="link-url" required class="w-full px-2.5 py-1.5 text-xs rounded-xl border bg-white dark:bg-neutral-800 dark:border-neutral-700 text-gray-800 dark:text-gray-200">
        </div>
        <div>
          <label class="block text-xs text-gray-500 mb-1">Icono</label>
          <select id="link-icon" class="w-full px-2.5 py-1.5 text-xs rounded-xl border bg-white dark:bg-neutral-800 dark:border-neutral-700 text-gray-800 dark:text-gray-200">
            <option value="fa-solid fa-envelope text-red-500">Gmail</option>
            <option value="fa-solid fa-paper-plane text-blue-500">Outlook</option>
            <option value="fa-solid fa-hard-drive text-amber-500">Google Drive</option>
            <option value="fa-brands fa-youtube text-red-600">YouTube</option>
            <option value="fa-solid fa-graduation-cap text-emerald-600">Google Classroom</option>
            <option value="fa-solid fa-globe text-emerald-500">Sitio Web / Portal</option>
            <option value="fa-solid fa-book text-purple-500">Biblioteca</option>
            <option value="fa-solid fa-calendar text-blue-600">Google Calendar</option>
          </select>
        </div>
        <div class="flex justify-end space-x-2 pt-2">
          <button type="button" onclick="closeModal('modal-acceso')" class="px-3 py-1.5 text-xs border rounded-xl">Cancelar</button>
          <button type="submit" class="px-3.5 py-1.5 text-xs bg-accent text-white rounded-xl">Guardar</button>
        </div>
      </form>
    </div>
  </div>

  <!-- MODAL PROFESOR -->
  <div id="modal-profesor" class="fixed inset-0 bg-black/50 backdrop-blur-sm hidden flex items-center justify-center p-4 z-50">
    <div class="bg-white dark:bg-[#202020] border border-gray-200 dark:border-neutral-800 rounded-2xl w-full max-w-md p-6 shadow-2xl">
      <h3 class="text-base font-bold mb-4" id="modal-prof-title">Agregar Catedrático</h3>
      <form onsubmit="saveTeacher(event)" class="space-y-3">
        <input type="hidden" id="prof-id">
        <div>
          <label class="block text-xs text-gray-500 mb-1">Nombre Completo</label>
          <input type="text" id="prof-nombre" required class="w-full px-3 py-2 text-sm rounded-xl border bg-white dark:bg-neutral-800 dark:border-neutral-700 text-gray-800 dark:text-gray-200">
        </div>
        <div>
          <label class="block text-xs text-gray-500 mb-1">Materia Principal</label>
          <input type="text" id="prof-materia" list="dl-materias" class="w-full px-3 py-2 text-sm rounded-xl border bg-white dark:bg-neutral-800 dark:border-neutral-700 text-gray-800 dark:text-gray-200">
        </div>
        <div>
          <label class="block text-xs text-gray-500 mb-1">Correo Electrónico / Contacto</label>
          <input type="text" id="prof-contacto" class="w-full px-3 py-2 text-sm rounded-xl border bg-white dark:bg-neutral-800 dark:border-neutral-700 text-gray-800 dark:text-gray-200">
        </div>
        <div class="flex justify-end space-x-2 pt-3">
          <button type="button" onclick="closeModal('modal-profesor')" class="px-4 py-2 text-xs border rounded-xl">Cancelar</button>
          <button type="submit" class="px-4 py-2 text-xs bg-accent text-white rounded-xl">Guardar</button>
        </div>
      </form>
    </div>
  </div>

  <script>
    const defaultSchedule = [
      { id: 1, dia: 'Lunes', materia: 'Biología y Taxonomía de la Maleza', tipo: 'T', inicio: '07:30', fin: '09:00', aula: 'AU 10', profesor: 'Dr. José Alfredo Domínguez Valenzuela' },
      { id: 2, dia: 'Lunes', materia: 'Olericultura', tipo: 'T', inicio: '09:00', fin: '10:30', aula: 'AU 4', profesor: 'Dr. Rogelio Castro Brindis' },
      { id: 3, dia: 'Lunes', materia: 'Estados Inmaduros de los Insectos', tipo: 'T', inicio: '11:30', fin: '13:00', aula: 'AU 1', profesor: 'Dr. Benito Reséndiz García' },
      { id: 4, dia: 'Martes', materia: 'Biología y Taxonomía de la Maleza', tipo: 'T', inicio: '07:30', fin: '09:00', aula: 'AU 2', profesor: 'Dr. José Alfredo Domínguez Valenzuela' },
      { id: 5, dia: 'Martes', materia: 'Bacteriología Agrícola', tipo: 'T', inicio: '09:00', fin: '10:30', aula: 'AU 4', profesor: 'Dr. Camilo Hernández Juárez' },
      { id: 6, dia: 'Martes', materia: 'Estados Inmaduros de los Insectos', tipo: 'P', inicio: '10:30', fin: '12:30', aula: 'Lab Ento', profesor: 'Dr. Benito Reséndiz García' },
      { id: 7, dia: 'Martes', materia: 'Bacteriología Agrícola', tipo: 'P', inicio: '13:30', fin: '15:30', aula: 'Lab Fitobac CAT', profesor: 'Dr. Camilo Hernández Juárez' },
      { id: 8, dia: 'Martes', materia: 'Optativas', tipo: 'O', inicio: '16:30', fin: '18:30', aula: 'Por asignar', profesor: '' },
      { id: 9, dia: 'Miércoles', materia: 'Estados Inmaduros de los Insectos', tipo: 'T', inicio: '07:30', fin: '09:00', aula: 'AU 1', profesor: 'Dr. Benito Reséndiz García' },
      { id: 10, dia: 'Miércoles', materia: 'Biología y Taxonomía de la Maleza', tipo: 'P', inicio: '09:00', fin: '11:00', aula: 'Cam Inmaduros / Lab Ento', profesor: 'Dr. José Alfredo Domínguez Valenzuela' },
      { id: 11, dia: 'Miércoles', materia: 'Olericultura', tipo: 'T', inicio: '11:00', fin: '12:30', aula: 'AU 4', profesor: 'Dr. Rogelio Castro Brindis' },
      { id: 12, dia: 'Miércoles', materia: 'Bacteriología Agrícola', tipo: 'P', inicio: '13:30', fin: '15:30', aula: 'Lab Fitobac CAT', profesor: 'Dr. Camilo Hernández Juárez' },
      { id: 13, dia: 'Miércoles', materia: 'Optativas', tipo: 'O', inicio: '16:30', fin: '18:30', aula: 'Por asignar', profesor: '' },
      { id: 14, dia: 'Jueves', materia: 'Bacteriología Agrícola', tipo: 'T', inicio: '09:00', fin: '10:30', aula: 'AU 3', profesor: 'Dr. Camilo Hernández Juárez' },
      { id: 15, dia: 'Jueves', materia: 'Estados Inmaduros de los Insectos', tipo: 'P', inicio: '10:30', fin: '12:30', aula: 'Lab Ento', profesor: 'Dr. Benito Reséndiz García' },
      { id: 16, dia: 'Viernes', materia: 'Olericultura', tipo: 'P', inicio: '07:30', fin: '09:30', aula: 'Cam Fitotecnia', profesor: 'Dr. Rogelio Castro Brindis' }
    ];

    const defaultTasks = [
      { id: 101, titulo: 'Informe sobre Familias de Malezas', materia: 'Biología y Taxonomía de la Maleza', fecha: '2026-09-25', prioridad: 'Alta', tipo: 'Reporte de Laboratorio', completada: false, notas: '' }
    ];

    const defaultLinks = [
      { id: 1, name: 'Gmail', url: 'https://mail.google.com', icon: 'fa-solid fa-envelope text-red-500' },
      { id: 2, name: 'Outlook', url: 'https://outlook.live.com', icon: 'fa-solid fa-paper-plane text-blue-500' },
      { id: 3, name: 'Drive', url: 'https://drive.google.com', icon: 'fa-solid fa-hard-drive text-amber-500' },
      { id: 4, name: 'YouTube', url: 'https://youtube.com', icon: 'fa-brands fa-youtube text-red-600' }
    ];

    const defaultTeachers = [
      { id: 1, nombre: 'Dr. José Alfredo Domínguez Valenzuela', materia: 'Biología y Taxonomía de la Maleza', contacto: 'jdominguez@uach.mx' },
      { id: 2, nombre: 'Dr. Rogelio Castro Brindis', materia: 'Olericultura', contacto: 'rcastro@uach.mx' },
      { id: 3, nombre: 'Dr. Benito Reséndiz García', materia: 'Estados Inmaduros de los Insectos', contacto: 'bresendiz@uach.mx' },
      { id: 4, nombre: 'Dr. Camilo Hernández Juárez', materia: 'Bacteriología Agrícola', contacto: 'chernandez@uach.mx' }
    ];

    const defaultSubjectColors = {
      'Biología y Taxonomía de la Maleza': '#10b981',
      'Olericultura': '#f59e0b',
      'Estados Inmaduros de los Insectos': '#8b5cf6',
      'Bacteriología Agrícola': '#ef4444',
      'Optativas': '#6366f1'
    };

    let schedule = JSON.parse(localStorage.getItem('academic_schedule')) || defaultSchedule;
    let tasks = JSON.parse(localStorage.getItem('academic_tasks')) || defaultTasks;
    let quickLinks = JSON.parse(localStorage.getItem('academic_links')) || defaultLinks;
    let teachers = JSON.parse(localStorage.getItem('academic_teachers')) || defaultTeachers;
    let subjectColors = JSON.parse(localStorage.getItem('academic_colors')) || defaultSubjectColors;
    
    let chatHistoryData = JSON.parse(localStorage.getItem('gemini_chat_history')) || [
      { sender: 'ai', text: '👋 <strong>¡Hola Diego! Soy tu Asistente Gemini.</strong> ¿En qué te puedo ayudar hoy con tu semestre?' }
    ];

    let widgetOrder = JSON.parse(localStorage.getItem('sidebar_widget_order')) || ['search', 'apps', 'gemini', 'clock', 'pomodoro'];
    let isEditModeActive = false;

    let currentPendingAction = null;
    let attachedFile = null;
    let modalTaskFile = null;
    let currentTab = 'horario';

    let calDisplayDate = new Date(2026, 8, 1);

    const days = ['Lunes', 'Martes', 'Miércoles', 'Jueves', 'Viernes'];

    function init() {
      setInterval(updateClock, 1000);
      updateClock();

      loadIdentity();
      
      const savedAccent = localStorage.getItem('theme_accent') || '#10b981';
      setThemeAccentColor(savedAccent, false);

      const savedFont = localStorage.getItem('theme_clock_font') || "'Space Grotesk', sans-serif";
      updateClockFont(savedFont, false);

      const savedTheme = localStorage.getItem('theme');
      if (savedTheme === 'dark') {
        document.documentElement.classList.add('dark');
        document.documentElement.classList.remove('light');
        updateThemeUI(true);
      } else {
        document.documentElement.classList.remove('dark');
        document.documentElement.classList.add('light');
        updateThemeUI(false);
      }

      renderWidgetLayout();
      renderSchedule();
      renderTasks();
      renderSubjects();
      renderTeachers();
      renderQuickLinks();
      populateDatalists();
      renderChatHistoryUI();
      updateHeaderButtons();

      const savedKey = localStorage.getItem('gemini_api_key');
      if (savedKey && document.getElementById('gemini-api-key')) {
        document.getElementById('gemini-api-key').value = savedKey;
      }
    }

    function updateClock() {
      const now = new Date();
      const timeStr = now.toLocaleTimeString('es-MX', { hour12: true });
      const dateStr = now.toLocaleDateString('es-MX', { weekday: 'long', day: '2-digit', month: 'short', year: 'numeric' });
      const formattedDate = dateStr.charAt(0).toUpperCase() + dateStr.slice(1);

      document.getElementById('sidebar-live-clock').innerText = timeStr;
      document.getElementById('sidebar-live-date').innerText = formattedDate;
    }

    function updateClockFont(fontFamily, save = true) {
      document.documentElement.style.setProperty('--font-clock', fontFamily);
      if(save) localStorage.setItem('theme_clock_font', fontFamily);
      if(document.getElementById('cfg-clock-font')) {
        document.getElementById('cfg-clock-font').value = fontFamily;
      }
    }

    function setThemeAccentColor(hex, save = true) {
      document.documentElement.style.setProperty('--color-accent', hex);
      document.documentElement.style.setProperty('--color-accent-hover', hex + 'cc');
      document.documentElement.style.setProperty('--color-accent-light', hex + '1a');
      if(save) localStorage.setItem('theme_accent', hex);
      if(document.getElementById('cfg-theme-color')) document.getElementById('cfg-theme-color').value = hex;
    }

    function toggleEditMode() {
      isEditModeActive = !isEditModeActive;
      const editBtn = document.getElementById('edit-mode-btn');
      const editText = document.getElementById('edit-mode-text');
      const container = document.getElementById('sidebar-widgets-container');
      
      if(isEditModeActive) {
        if(editBtn) {
          editBtn.classList.add('bg-accent', 'text-white', 'border-transparent');
          editBtn.classList.remove('text-gray-500', 'border-gray-200', 'dark:border-neutral-800');
        }
        if(editText) editText.innerText = 'Listo / Guardar orden';
        container.classList.add('edit-mode-active');
        document.querySelectorAll('.edit-controls').forEach(el => el.classList.remove('hidden'));
      } else {
        if(editBtn) {
          editBtn.classList.remove('bg-accent', 'text-white', 'border-transparent');
          editBtn.classList.add('text-gray-500', 'border-gray-200', 'dark:border-neutral-800');
        }
        if(editText) editText.innerText = 'Editar orden de widgets';
        container.classList.remove('edit-mode-active');
        document.querySelectorAll('.edit-controls').forEach(el => el.classList.add('hidden'));
      }
    }

    function renderWidgetLayout() {
      const container = document.getElementById('sidebar-widgets-container');
      if(!container) return;

      widgetOrder.forEach(id => {
        const el = container.querySelector(`[data-widget-id="${id}"]`);
        if(el) container.appendChild(el);
      });
    }

    function moveWidget(id, direction) {
      const index = widgetOrder.indexOf(id);
      if(index === -1) return;

      if(direction === 'up' && index > 0) {
        const temp = widgetOrder[index - 1];
        widgetOrder[index - 1] = widgetOrder[index];
        widgetOrder[index] = temp;
      } else if(direction === 'down' && index < widgetOrder.length - 1) {
        const temp = widgetOrder[index + 1];
        widgetOrder[index + 1] = widgetOrder[index];
        widgetOrder[index] = temp;
      }

      localStorage.setItem('sidebar_widget_order', JSON.stringify(widgetOrder));
      renderWidgetLayout();
    }

    function loadIdentity() {
      const title = localStorage.getItem('identity_title') || 'Parasitología';
      const sub = localStorage.getItem('identity_sub') || 'UACh - Sexto Cuatro';
      const year = localStorage.getItem('identity_year') || '2026';
      const logo = localStorage.getItem('identity_logo') || '🪲';

      document.getElementById('app-title-display').innerText = title;
      document.getElementById('app-sub-display').innerText = sub;
      document.getElementById('app-year-display').innerText = year;

      if(document.getElementById('cfg-title')) document.getElementById('cfg-title').value = title;
      if(document.getElementById('cfg-sub')) document.getElementById('cfg-sub').value = sub;
      if(document.getElementById('cfg-year')) document.getElementById('cfg-year').value = year;

      if(logo.startsWith('data:image')) {
        document.getElementById('logo-container').innerHTML = `<img src="${logo}" class="w-full h-full object-cover">`;
      } else {
        document.getElementById('logo-container').innerHTML = `<span id="logo-display">${logo}</span>`;
      }
    }

    function updateIdentity() {
      const t = document.getElementById('cfg-title').value;
      const s = document.getElementById('cfg-sub').value;
      const y = document.getElementById('cfg-year').value;
      localStorage.setItem('identity_title', t);
      localStorage.setItem('identity_sub', s);
      localStorage.setItem('identity_year', y);
      loadIdentity();
    }

    function updateLogoEmoji(val) {
      localStorage.setItem('identity_logo', val);
      loadIdentity();
    }

    function uploadCustomLogo(e) {
      const file = e.target.files[0];
      if(!file) return;
      const reader = new FileReader();
      reader.onload = function(evt) {
        localStorage.setItem('identity_logo', evt.target.result);
        loadIdentity();
      };
      reader.readAsDataURL(file);
    }

    function resetLogo() {
      localStorage.setItem('identity_logo', '🪲');
      loadIdentity();
    }

    function googleSearch(e) {
      e.preventDefault();
      const query = document.getElementById('gsearch-input').value.trim();
      if(query) {
        window.open(`https://www.google.com/search?q=${encodeURIComponent(query)}`, '_blank');
      }
    }

    function populateDatalists() {
      const uniqueSubjects = [...new Set(schedule.map(s => s.materia))].sort();
      document.getElementById('dl-materias').innerHTML = uniqueSubjects.map(s => `<option value="${s}">`).join('');

      const uniqueTeachers = [...new Set(teachers.map(t => t.nombre))].sort();
      document.getElementById('dl-profesores').innerHTML = uniqueTeachers.map(t => `<option value="${t}">`).join('');

      const dropdown = document.getElementById('tarea-materia');
      dropdown.innerHTML = uniqueSubjects.map(sub => `<option value="${sub}">${sub}</option>`).join('');
    }

    function renderQuickLinks() {
      const grid = document.getElementById('quick-links-grid');
      grid.innerHTML = quickLinks.map(l => `
        <a href="${l.url}" target="_blank" class="group relative flex items-center space-x-1.5 p-1.5 text-[11px] rounded-xl hover:bg-gray-100 dark:hover:bg-neutral-800 text-gray-700 dark:text-gray-300">
          <i class="${l.icon}"></i>
          <span class="truncate flex-1">${l.name}</span>
          <button onclick="event.preventDefault(); editQuickLink(${l.id})" class="opacity-0 group-hover:opacity-100 text-[10px] text-gray-400 hover:text-accent"><i class="fa-solid fa-pen"></i></button>
        </a>
      `).join('');
    }

    function editQuickLink(id) {
      const link = quickLinks.find(l => l.id === id);
      if(!link) return;
      document.getElementById('link-id').value = link.id;
      document.getElementById('link-name').value = link.name;
      document.getElementById('link-url').value = link.url;
      document.getElementById('link-icon').value = link.icon;
      openModal('modal-acceso');
    }

    function saveQuickLink(e) {
      e.preventDefault();
      const id = document.getElementById('link-id').value;
      const newLink = {
        id: id ? parseInt(id) : Date.now(),
        name: document.getElementById('link-name').value,
        url: document.getElementById('link-url').value,
        icon: document.getElementById('link-icon').value
      };

      if(id) {
        quickLinks = quickLinks.map(l => l.id === parseInt(id) ? newLink : l);
      } else {
        quickLinks.push(newLink);
      }
      localStorage.setItem('academic_links', JSON.stringify(quickLinks));
      closeModal('modal-acceso');
      renderQuickLinks();
    }

    function renderTeachers() {
      const grid = document.getElementById('teachers-grid');
      grid.innerHTML = teachers.map(t => `
        <div class="p-4 rounded-2xl border border-gray-200 dark:border-neutral-800 bg-white dark:bg-[#202020] space-y-2 relative group shadow-sm">
          <div class="flex justify-between items-start">
            <h4 class="font-bold text-sm text-gray-900 dark:text-gray-100">${t.nombre}</h4>
            <div class="opacity-0 group-hover:opacity-100 transition space-x-1">
              <button onclick="editTeacher(${t.id})" class="text-xs text-gray-400 hover:text-accent p-1"><i class="fa-solid fa-pen"></i></button>
              <button onclick="deleteTeacher(${t.id})" class="text-xs text-gray-400 hover:text-red-500 p-1"><i class="fa-solid fa-trash"></i></button>
            </div>
          </div>
          <p class="text-xs font-medium text-accent"><i class="fa-solid fa-book mr-1"></i>${t.materia || 'General'}</p>
          <p class="text-xs text-gray-400 truncate"><i class="fa-solid fa-envelope mr-1"></i>${t.contacto || 'Sin contacto'}</p>
        </div>
      `).join('');
    }

    function editTeacher(id) {
      const prof = teachers.find(t => t.id === id);
      if(!prof) return;
      document.getElementById('prof-id').value = prof.id;
      document.getElementById('prof-nombre').value = prof.nombre;
      document.getElementById('prof-materia').value = prof.materia;
      document.getElementById('prof-contacto').value = prof.contacto;
      document.getElementById('modal-prof-title').innerText = "Editar Catedrático";
      openModal('modal-profesor');
    }

    function saveTeacher(e) {
      e.preventDefault();
      const id = document.getElementById('prof-id').value;
      const newProf = {
        id: id ? parseInt(id) : Date.now(),
        nombre: document.getElementById('prof-nombre').value,
        materia: document.getElementById('prof-materia').value,
        contacto: document.getElementById('prof-contacto').value
      };

      if(id) {
        teachers = teachers.map(t => t.id === parseInt(id) ? newProf : t);
      } else {
        teachers.push(newProf);
      }

      localStorage.setItem('academic_teachers', JSON.stringify(teachers));
      closeModal('modal-profesor');
      renderTeachers();
      populateDatalists();
    }

    function deleteTeacher(id) {
      teachers = teachers.filter(t => t.id !== id);
      localStorage.setItem('academic_teachers', JSON.stringify(teachers));
      renderTeachers();
      populateDatalists();
    }

    function setSubjectColor(subject, color) {
      subjectColors[subject] = color;
      localStorage.setItem('academic_colors', JSON.stringify(subjectColors));
      renderSchedule();
      renderTasks();
      renderSubjects();
      renderCalendarDays();
    }

    function editSubjectName(subName) {
      document.getElementById('sub-old-name').value = subName;
      document.getElementById('sub-display-name').value = subName;
      document.getElementById('sub-new-name').value = subName;
      openModal('modal-materia');
    }

    function saveSubjectRename(e) {
      e.preventDefault();
      const oldName = document.getElementById('sub-old-name').value;
      const newName = document.getElementById('sub-new-name').value.trim();

      if(newName && oldName !== newName) {
        schedule = schedule.map(c => c.materia === oldName ? { ...c, materia: newName } : c);
        tasks = tasks.map(t => t.materia === oldName ? { ...t, materia: newName } : t);
        teachers = teachers.map(tp => tp.materia === oldName ? { ...tp, materia: newName } : tp);
        if(subjectColors[oldName]) {
          subjectColors[newName] = subjectColors[oldName];
          delete subjectColors[oldName];
          localStorage.setItem('academic_colors', JSON.stringify(subjectColors));
        }

        saveAndRefresh();
        renderTeachers();
      }
      closeModal('modal-materia');
    }

    function renderSchedule() {
      const container = document.getElementById('schedule-container');
      container.innerHTML = '';

      days.forEach(day => {
        const dayClasses = schedule.filter(c => c.dia === day).sort((a,b) => a.inicio.localeCompare(b.inicio));
        const dayEl = document.createElement('div');
        dayEl.className = "bg-white dark:bg-[#202020] rounded-2xl border border-gray-200 dark:border-neutral-800 flex flex-col min-h-[450px]";
        
        let classesHTML = dayClasses.map(c => {
          const color = subjectColors[c.materia] || '#10b981';
          return `
            <div style="border-left-color: ${color};" class="group relative bg-gray-50 dark:bg-neutral-900/60 hover:bg-gray-100 dark:hover:bg-neutral-800 border-l-[5px] border-y border-r border-gray-200/80 dark:border-neutral-700/60 p-3.5 rounded-2xl transition">
              <div class="flex justify-between items-start">
                <span style="background-color: ${color};" class="text-[11px] font-bold px-2.5 py-0.5 rounded-full text-white shadow-sm">
                  ${c.inicio} - ${c.fin}
                </span>
                <div class="opacity-0 group-hover:opacity-100 transition space-x-1">
                  <button onclick="deleteClass(${c.id})" class="text-xs text-gray-400 hover:text-red-500 p-1"><i class="fa-solid fa-trash"></i></button>
                </div>
              </div>
              <h4 class="font-semibold text-xs mt-2 text-gray-900 dark:text-gray-100 leading-tight">${c.materia}</h4>
              <div class="text-[11px] text-gray-500 dark:text-gray-400 mt-1 space-y-0.5">
                <div><i class="fa-solid fa-location-dot text-gray-400 mr-1"></i> ${c.aula || 'Sin aula'} (${c.tipo})</div>
                ${c.profesor ? `<div class="truncate"><i class="fa-solid fa-user-graduate text-gray-400 mr-1"></i> ${c.profesor}</div>` : ''}
              </div>
            </div>
          `;
        }).join('');

        dayEl.innerHTML = `
          <div class="p-3.5 border-b border-gray-100 dark:border-neutral-800 flex justify-between items-center bg-gray-50/50 dark:bg-neutral-900/30 rounded-t-2xl">
            <h3 class="font-semibold text-sm text-gray-800 dark:text-gray-200">${day}</h3>
            <span class="text-xs text-gray-400">${dayClasses.length} ${dayClasses.length === 1 ? 'clase' : 'clases'}</span>
          </div>
          <div class="p-2.5 space-y-2.5 flex-1">${classesHTML || '<p class="text-xs text-gray-400 text-center py-6">Sin clases</p>'}</div>
        `;
        container.appendChild(dayEl);
      });
    }

    function renderTasks() {
      const pFilter = document.getElementById('filter-priority')?.value || 'ALL';
      const tFilter = document.getElementById('filter-type')?.value || 'ALL';

      let filteredTasks = tasks.filter(t => {
        const matchP = pFilter === 'ALL' || t.prioridad === pFilter;
        const matchT = tFilter === 'ALL' || t.tipo === tFilter;
        return matchP && matchT;
      });

      const pendingContainer = document.getElementById('tasks-pending');
      const completedContainer = document.getElementById('tasks-completed');

      const pending = filteredTasks.filter(t => !t.completada);
      const completed = filteredTasks.filter(t => t.completada);

      document.getElementById('count-pending').innerText = pending.length;
      document.getElementById('count-completed').innerText = completed.length;

      pendingContainer.innerHTML = pending.map(t => createTaskCard(t)).join('') || '<p class="text-xs text-gray-400 text-center py-4">No hay tareas incompletas</p>';
      completedContainer.innerHTML = completed.map(t => createTaskCard(t)).join('') || '<p class="text-xs text-gray-400 text-center py-4">No hay tareas completadas</p>';
      
      renderCalendarDays();
    }

    function createTaskCard(task) {
      const priorityBadge = task.prioridad === 'Alta' ? '🔴 Alta' : task.prioridad === 'Media' ? '🟡 Media' : '🟢 Baja';
      const color = subjectColors[task.materia] || '#10b981';

      return `
        <div style="border-left-color: ${color};" class="group relative flex items-start justify-between p-3.5 rounded-2xl border-l-[5px] border-y border-r border-gray-100 dark:border-neutral-800 bg-gray-50/50 dark:bg-neutral-900/40 hover:bg-gray-100 dark:hover:bg-neutral-800 transition">
          <div class="flex items-start space-x-3">
            <input type="checkbox" ${task.completada ? 'checked' : ''} onchange="toggleTask('${task.id}')" class="mt-1 h-4 w-4 rounded border-gray-300 text-emerald-600 focus:ring-emerald-500">
            <div>
              <p class="text-xs font-semibold ${task.completada ? 'line-through text-gray-400' : 'text-gray-800 dark:text-gray-200'}">${task.titulo}</p>
              ${task.notas ? `<p class="text-[11px] text-gray-500 mt-0.5">${task.notas}</p>` : ''}
              <div class="flex flex-wrap items-center gap-1.5 mt-1.5">
                <span class="text-[10px] font-semibold px-2 py-0.5 rounded-full bg-gray-200 dark:bg-neutral-700 text-gray-600 dark:text-gray-300">${task.materia}</span>
                <span class="text-[10px] px-2 py-0.5 rounded-full bg-blue-100 text-blue-800 dark:bg-blue-950 dark:text-blue-300">${task.tipo || 'Tarea General'}</span>
                <span class="text-[10px] font-medium">${priorityBadge}</span>
                ${task.fecha ? `<span class="text-[10px] text-gray-400 ml-1"><i class="fa-regular fa-calendar mr-1"></i>${task.fecha}</span>` : ''}
                ${task.attachedFile ? `<a href="${task.attachedFile.data}" download="${task.attachedFile.name}" class="text-[10px] text-emerald-600 underline font-medium"><i class="fa-solid fa-paperclip mr-1"></i>${task.attachedFile.name}</a>` : ''}
              </div>
            </div>
          </div>
          <div class="flex items-center space-x-1 opacity-0 group-hover:opacity-100 transition">
            <button onclick="editTask('${task.id}')" class="text-gray-400 hover:text-accent p-1 text-xs transition"><i class="fa-solid fa-pen"></i></button>
            <button onclick="deleteTask('${task.id}')" class="text-gray-400 hover:text-red-500 p-1 text-xs transition"><i class="fa-solid fa-trash-can"></i></button>
          </div>
        </div>
      `;
    }

    function editTask(id) {
      const task = tasks.find(t => String(t.id) === String(id));
      if(!task) return;
      document.getElementById('tarea-id').value = task.id;
      document.getElementById('tarea-titulo').value = task.titulo;
      document.getElementById('tarea-materia').value = task.materia;
      document.getElementById('tarea-prioridad').value = task.prioridad;
      document.getElementById('tarea-tipo').value = task.tipo || 'Tarea General';
      document.getElementById('tarea-fecha').value = task.fecha || '';
      document.getElementById('tarea-notas').value = task.notas || '';
      
      const disp = document.getElementById('modal-file-display');
      if(task.attachedFile) {
        disp.innerText = `📎 ${task.attachedFile.name}`;
        disp.classList.remove('hidden');
      } else {
        disp.classList.add('hidden');
      }

      document.getElementById('modal-tarea-title').innerText = "Editar Tarea";
      openModal('modal-tarea');
    }

    function handleModalTaskFile(e) {
      const file = e.target.files[0];
      if(!file) return;
      const reader = new FileReader();
      reader.onload = function(evt) {
        modalTaskFile = { name: file.name, data: evt.target.result };
      };
      reader.readAsDataURL(file);
    }

    function renderSubjects() {
      const container = document.getElementById('subjects-grid');
      const uniqueSubjects = [...new Set(schedule.map(s => s.materia))];

      container.innerHTML = uniqueSubjects.map(sub => {
        const subClasses = schedule.filter(s => s.materia === sub);
        const subTasks = tasks.filter(t => t.materia === sub && !t.completada);
        const prof = subClasses.find(c => c.profesor)?.profesor || 'Por asignar';
        const currentColor = subjectColors[sub] || '#10b981';

        return `
          <div style="border-top-color: ${currentColor};" class="p-4 rounded-2xl border-t-[5px] border-x border-b border-gray-200 dark:border-neutral-800 bg-white dark:bg-[#202020] space-y-3 shadow-sm">
            <div class="flex justify-between items-start">
              <h4 class="font-bold text-sm text-gray-900 dark:text-gray-100">${sub}</h4>
              <div class="flex items-center space-x-1.5">
                <label class="relative cursor-pointer p-1 text-gray-500 hover:text-accent transition" title="Cambiar color de materia">
                  <span class="text-sm">🎨</span>
                  <input type="color" value="${currentColor}" onchange="setSubjectColor('${sub}', this.value)" class="absolute inset-0 opacity-0 w-full h-full cursor-pointer">
                </label>
                <button onclick="editSubjectName('${sub}')" title="Renombrar materia" class="text-xs text-gray-400 hover:text-accent p-1"><i class="fa-solid fa-pen"></i></button>
                <span class="text-xs bg-emerald-100 text-emerald-800 dark:bg-emerald-950 dark:text-emerald-300 px-2.5 py-0.5 rounded-full">${subTasks.length} pendientes</span>
              </div>
            </div>
            <p class="text-xs text-gray-500 dark:text-gray-400"><i class="fa-solid fa-user-graduate mr-1"></i>${prof}</p>
            <div class="border-t dark:border-neutral-800 pt-2 text-xs text-gray-400 space-y-1">
              ${subClasses.map(c => `<div>• ${c.dia}: ${c.inicio}-${c.fin} (${c.aula})</div>`).join('')}
            </div>
          </div>
        `;
      }).join('');
    }

    function switchTab(tab) {
      currentTab = tab;
      document.getElementById('sec-horario').classList.add('hidden');
      document.getElementById('sec-tareas').classList.add('hidden');
      document.getElementById('sec-materias').classList.add('hidden');
      document.getElementById('sec-profesores').classList.add('hidden');
      document.getElementById('sec-gemini').classList.add('hidden');
      document.getElementById('sec-ajustes').classList.add('hidden');
      
      document.getElementById(`sec-${tab}`).classList.remove('hidden');

      const titles = {
        horario: 'Horario semanal',
        tareas: 'Tareas',
        materias: 'Materias',
        profesores: 'Directorio de Catedráticos',
        gemini: 'Asistente Gemini IA',
        ajustes: 'Configuración del Sistema'
      };
      document.getElementById('header-title').innerText = titles[tab] || 'Workspace';

      const badge = document.getElementById(`badge-${tab}`);
      if(badge) badge.classList.add('hidden');

      updateHeaderButtons();
    }

    function updateHeaderButtons() {
      const btnClase = document.getElementById('btn-add-clase');
      const btnTarea = document.getElementById('btn-add-tarea');

      if (currentTab === 'horario' || currentTab === 'materias') {
        btnClase.classList.remove('hidden');
      } else {
        btnClase.classList.add('hidden');
      }

      btnTarea.classList.remove('hidden');
    }

    function showBadge(tab) {
      const badge = document.getElementById(`badge-${tab}`);
      if(badge) badge.classList.remove('hidden');
    }

    function toggleTask(id) {
      tasks = tasks.map(t => String(t.id) === String(id) ? { ...t, completada: !t.completada } : t);
      saveAndRefresh();
    }

    function deleteTask(id) {
      tasks = tasks.filter(t => String(t.id) !== String(id));
      saveAndRefresh();
    }

    function deleteClass(id) {
      schedule = schedule.filter(c => String(c.id) !== String(id));
      saveAndRefresh();
    }

    function saveClass(e) {
      e.preventDefault();
      const newClass = {
        id: Date.now(),
        materia: document.getElementById('clase-materia').value,
        dia: document.getElementById('clase-dia').value,
        tipo: document.getElementById('clase-tipo').value,
        inicio: document.getElementById('clase-inicio').value,
        fin: document.getElementById('clase-fin').value,
        aula: document.getElementById('clase-aula').value,
        profesor: document.getElementById('clase-profesor').value,
      };
      schedule.push(newClass);
      closeModal('modal-clase');
      saveAndRefresh();
    }

    function saveTask(e) {
      e.preventDefault();
      const id = document.getElementById('tarea-id').value;
      const newTask = {
        id: id ? parseInt(id) : Date.now(),
        titulo: document.getElementById('tarea-titulo').value,
        materia: document.getElementById('tarea-materia').value,
        prioridad: document.getElementById('tarea-prioridad').value,
        tipo: document.getElementById('tarea-tipo').value,
        fecha: document.getElementById('tarea-fecha').value,
        notas: document.getElementById('tarea-notas').value,
        completada: false,
        attachedFile: modalTaskFile || (id ? tasks.find(t=>String(t.id)===String(id))?.attachedFile : null)
      };

      if(id) {
        tasks = tasks.map(t => String(t.id) === String(id) ? newTask : t);
      } else {
        tasks.push(newTask);
      }

      modalTaskFile = null;
      document.getElementById('tarea-id').value = '';
      closeModal('modal-tarea');
      saveAndRefresh();
    }

    function saveAndRefresh() {
      localStorage.setItem('academic_schedule', JSON.stringify(schedule));
      localStorage.setItem('academic_tasks', JSON.stringify(tasks));
      renderSchedule();
      renderTasks();
      renderSubjects();
      populateDatalists();
      renderCalendarDays();
    }

    function openModal(id, presetDate = null) {
      if(id === 'modal-tarea' && !document.getElementById('tarea-id').value) {
        document.getElementById('form-tarea').reset();
        document.getElementById('modal-tarea-title').innerText = "Nueva Tarea";
        document.getElementById('modal-file-display').classList.add('hidden');
        if(presetDate) {
          document.getElementById('tarea-fecha').value = presetDate;
        }
      }
      document.getElementById(id).classList.remove('hidden');
    }

    function closeModal(id) {
      document.getElementById(id).classList.add('hidden');
      if(id === 'modal-tarea') {
        document.getElementById('tarea-id').value = '';
        modalTaskFile = null;
      }
      if(id === 'modal-profesor') {
        document.getElementById('prof-id').value = '';
      }
    }

    function handleFileAttach(e) {
      const file = e.target.files[0];
      if(!file) return;
      const reader = new FileReader();
      reader.onload = function(evt) {
        attachedFile = { name: file.name, data: evt.target.result };
        document.getElementById('file-preview-name').innerText = `📎 ${file.name}`;
        document.getElementById('file-preview-bar').classList.remove('hidden');
      };
      reader.readAsDataURL(file);
    }

    function removeAttachment() {
      attachedFile = null;
      document.getElementById('file-preview-bar').classList.add('hidden');
      document.getElementById('chat-file-input').value = '';
    }

    function renderChatHistoryUI() {
      const container = document.getElementById('chat-history');
      if(!container) return;
      container.innerHTML = chatHistoryData.map(msg => {
        if (msg.sender === 'user') {
          return `
            <div class="bg-gray-100 dark:bg-neutral-800 p-3 rounded-2xl text-xs text-right text-gray-800 dark:text-gray-200 ml-8 shadow-sm">
              <strong>Tú:</strong> ${msg.text}
            </div>
          `;
        } else {
          return `
            <div class="bg-purple-50 dark:bg-purple-950/40 border border-purple-100 dark:border-purple-900/50 p-3.5 rounded-2xl text-xs text-gray-800 dark:text-gray-200 mr-8 shadow-sm">
              <strong class="text-purple-600 dark:text-purple-400">Gemini IA:</strong><br>${msg.text}
            </div>
          `;
        }
      }).join('');
      container.scrollTop = container.scrollHeight;
    }

    function clearChatHistory() {
      chatHistoryData = [
        { sender: 'ai', text: '👋 <strong>¡Hola Diego! Soy tu Asistente Gemini.</strong> ¿En qué te puedo ayudar hoy?' }
      ];
      localStorage.setItem('gemini_chat_history', JSON.stringify(chatHistoryData));
      renderChatHistoryUI();
    }

    async function handleChatSubmit(e) {
      e.preventDefault();
      const input = document.getElementById('gemini-prompt');
      const prompt = input.value.trim();
      if(!prompt) return;

      const apiKey = document.getElementById('gemini-api-key').value.trim() || localStorage.getItem('gemini_api_key');
      const selectedModelMode = document.getElementById('gemini-model-select').value;
      
      const userText = prompt + (attachedFile ? `<br><span class="text-[10px] text-emerald-600 font-medium">📎 ${attachedFile.name}</span>` : '');
      chatHistoryData.push({ sender: 'user', text: userText });
      localStorage.setItem('gemini_chat_history', JSON.stringify(chatHistoryData));
      renderChatHistoryUI();

      input.value = '';

      if (!apiKey) {
        chatHistoryData.push({ sender: 'ai', text: '⚠️ Por favor ingresa tu Gemini API Key en el campo superior para chatear.' });
        localStorage.setItem('gemini_chat_history', JSON.stringify(chatHistoryData));
        renderChatHistoryUI();
        return;
      }

      const chatHistoryUI = document.getElementById('chat-history');
      const loadingId = 'loading-' + Date.now();
      chatHistoryUI.innerHTML += `<div id="${loadingId}" class="bg-purple-50 dark:bg-purple-950/20 p-3 rounded-2xl text-xs text-gray-500 italic"><i class="fa-solid fa-spinner fa-spin mr-1"></i> Gemini procesando consulta...</div>`;
      chatHistoryUI.scrollTop = chatHistoryUI.scrollHeight;

      // LISTA LIMPIA DE MODELOS GEMINI OFICIALES SIN "models/" PRE-PENDIDO
      let candidateModels = [];
      if (selectedModelMode !== 'AUTO') {
        candidateModels = [selectedModelMode.replace(/^models\//, '')];
      } else {
        candidateModels = ['gemini-1.5-flash', 'gemini-2.0-flash', 'gemini-2.5-flash', 'gemini-1.5-pro'];
      }

      const uniqueSubjects = [...new Set(schedule.map(s => s.materia))].join(', ');
      const systemPrompt = `Eres el asistente escolar de Diego en Parasitología Agrícola.
Materias registradas: [${uniqueSubjects}].
RESPONDE DIRECTAMENTE A LA CONSULTA EN ESPAÑOL. NO INVENTES CAMBIOS SI NO SE SOLICITAN EXPLÍCITAMENTE.

SI Y SOLO SI el usuario te pide crear o modificar tareas o clases, incluye un objeto JSON envuelto estrictamente en <json_action>...</json_action>:
{
  "action_type": "add_task" | "add_class",
  "summary": "Descripción corta",
  "data": { ... }
}
Mensaje: "${prompt}"`;

      let response = null;
      let lastErrorMsg = '';

      for (const rawModelName of candidateModels) {
        try {
          const cleanModel = rawModelName.trim().replace(/^models\//, '');
          const endpoint = `https://generativelanguage.googleapis.com/v1beta/models/${cleanModel}:generateContent?key=${apiKey}`;

          const res = await fetch(endpoint, {
            method: 'POST',
            headers: { 'Content-Type': 'application/json' },
            body: JSON.stringify({
              contents: [{
                parts: [{ text: systemPrompt }]
              }]
            })
          });

          if (res.ok) {
            response = await res.json();
            break;
          } else {
            const errJson = await res.json();
            lastErrorMsg = errJson?.error?.message || `Error HTTP ${res.status}`;
          }
        } catch (err) {
          lastErrorMsg = err.message;
        }
      }

      document.getElementById(loadingId)?.remove();

      if (response && response.candidates && response.candidates[0]?.content?.parts?.[0]?.text) {
        let replyText = response.candidates[0].content.parts[0].text;
        
        const match = replyText.match(/<json_action>([\s\S]*?)<\/json_action>/);
        if (match) {
          try {
            const action = JSON.parse(match[1]);
            if(attachedFile && action.action_type === 'add_task') {
              action.data.attachedFile = attachedFile;
            }
            currentPendingAction = action;
            document.getElementById('ai-confirm-text').innerText = action.summary || 'Gemini propone un cambio.';
            document.getElementById('ai-confirmation-box').classList.remove('hidden');
          } catch(e) { console.error(e); }
          replyText = replyText.replace(/<json_action>[\s\S]*?<\/json_action>/, '').trim();
        }

        replyText = replyText.replace(/\*\*(.*?)\*\*/g, '<strong>$1</strong>');
        replyText = replyText.replace(/\n/g, '<br>');

        chatHistoryData.push({ sender: 'ai', text: replyText });
        localStorage.setItem('gemini_chat_history', JSON.stringify(chatHistoryData));
        renderChatHistoryUI();
        removeAttachment();
      } else {
        chatHistoryData.push({ 
          sender: 'ai', 
          text: `❌ Error al conectar con Gemini (${lastErrorMsg || 'Sin respuesta'}).<br><br>💡 <strong>Recomendación:</strong> Asegúrate de copiar tu API Key completa de Google AI Studio (<a href="https://aistudio.google.com" target="_blank" class="underline font-semibold text-purple-600 dark:text-purple-400">aistudio.google.com</a>) y presionar "🔑 Guardar Key".` 
        });
        localStorage.setItem('gemini_chat_history', JSON.stringify(chatHistoryData));
        renderChatHistoryUI();
      }
    }

    function applyAiAction() {
      if(!currentPendingAction) return;
      if(currentPendingAction.action_type === 'add_task') {
        tasks.push({
          id: Date.now(),
          titulo: currentPendingAction.data.titulo || 'Nueva Tarea',
          materia: currentPendingAction.data.materia || 'Parasitología',
          prioridad: currentPendingAction.data.prioridad || 'Alta',
          tipo: currentPendingAction.data.tipo || 'Tarea General',
          fecha: currentPendingAction.data.fecha || '2026-09-30',
          completada: false,
          attachedFile: currentPendingAction.data.attachedFile || null
        });
        showBadge('tareas');
      } else if(currentPendingAction.action_type === 'add_class') {
        schedule.push({
          id: Date.now(),
          materia: currentPendingAction.data.materia,
          dia: currentPendingAction.data.dia || 'Lunes',
          tipo: currentPendingAction.data.tipo || 'T',
          inicio: currentPendingAction.data.inicio || '09:00',
          fin: currentPendingAction.data.fin || '10:30',
          aula: currentPendingAction.data.aula || 'AU 1',
          profesor: currentPendingAction.data.profesor || ''
        });
        showBadge('horario');
      }
      saveAndRefresh();
      cancelAiAction();
    }

    function cancelAiAction() {
      currentPendingAction = null;
      document.getElementById('ai-confirmation-box').classList.add('hidden');
    }

    function saveApiKey() {
      const key = document.getElementById('gemini-api-key').value.trim();
      localStorage.setItem('gemini_api_key', key);
      alert('API Key de Gemini guardada correctamente.');
    }

    function playAudioTone(type) {
      try {
        const ctx = new (window.AudioContext || window.webkitAudioContext)();
        if (type === 'start') {
          const osc = ctx.createOscillator();
          const gain = ctx.createGain();
          osc.connect(gain);
          gain.connect(ctx.destination);
          osc.frequency.setValueAtTime(600, ctx.currentTime);
          gain.gain.setValueAtTime(0.15, ctx.currentTime);
          gain.gain.exponentialRampToValueAtTime(0.001, ctx.currentTime + 0.3);
          osc.start(ctx.currentTime);
          osc.stop(ctx.currentTime + 0.3);
        } else if (type === 'end') {
          [800, 1000, 1200].forEach((freq, idx) => {
            const osc = ctx.createOscillator();
            const gain = ctx.createGain();
            osc.frequency.setValueAtTime(freq, ctx.currentTime + idx * 0.12);
            gain.gain.setValueAtTime(0.2, ctx.currentTime + idx * 0.12);
            gain.gain.exponentialRampToValueAtTime(0.001, ctx.currentTime + idx * 0.12 + 0.4);
            osc.connect(gain);
            gain.connect(ctx.destination);
            osc.start(ctx.currentTime + idx * 0.12);
            osc.stop(ctx.currentTime + idx * 0.12 + 0.4);
          });
        }
      } catch (e) { console.log(e); }
    }

    let pomoWorkMin = parseInt(localStorage.getItem('pomo_work_min')) || 25;
    let pomoRestMin = parseInt(localStorage.getItem('pomo_rest_min')) || 5;
    let pomoMode = 'work';
    let pomoTime = pomoWorkMin * 60;
    let pomoTimer = null;
    let isPomoRunning = false;

    function togglePomoConfig() {
      const p = document.getElementById('pomo-config-panel');
      if(p) p.classList.toggle('hidden');
    }

    function savePomoCustomConfig() {
      const w = parseInt(document.getElementById('pomo-work-input').value) || 25;
      const r = parseInt(document.getElementById('pomo-rest-input').value) || 5;
      pomoWorkMin = w;
      pomoRestMin = r;
      localStorage.setItem('pomo_work_min', w);
      localStorage.setItem('pomo_rest_min', r);
      resetPomodoro();
      togglePomoConfig();
    }

    function togglePomodoro() {
      const btn = document.getElementById('pomo-btn');
      if (isPomoRunning) {
        clearInterval(pomoTimer);
        isPomoRunning = false;
        btn.innerText = 'Iniciar';
      } else {
        isPomoRunning = true;
        btn.innerText = 'Pausar';
        playAudioTone('start');
        pomoTimer = setInterval(() => {
          if (pomoTime > 0) {
            pomoTime--;
            updatePomoDisplay();
          } else {
            clearInterval(pomoTimer);
            playAudioTone('end');
            if(pomoMode === 'work') {
              pomoMode = 'rest';
              pomoTime = pomoRestMin * 60;
              alert('🔔 ¡Tiempo terminado! Descanso activado.');
            } else {
              pomoMode = 'work';
              pomoTime = pomoWorkMin * 60;
              alert('🧠 ¡Descanso terminado! Bloque de trabajo activado.');
            }
            isPomoRunning = false;
            document.getElementById('pomo-btn').innerText = 'Iniciar';
            updatePomoDisplay();
          }
        }, 1000);
      }
    }

    function resetPomodoro() {
      clearInterval(pomoTimer);
      isPomoRunning = false;
      pomoMode = 'work';
      pomoTime = pomoWorkMin * 60;
      document.getElementById('pomo-btn').innerText = 'Iniciar';
      updatePomoDisplay();
    }

    function updatePomoDisplay() {
      const min = Math.floor(pomoTime / 60);
      const sec = pomoTime % 60;
      document.getElementById('pomo-display').innerText = `${String(min).padStart(2,'0')}:${String(sec).padStart(2,'0')}`;
    }

    /* CALENDARIO POPOVER */
    function toggleCalendarPopover() {
      const popover = document.getElementById('calendar-popover');
      popover.classList.toggle('hidden');
      if (!popover.classList.contains('hidden')) {
        renderCalendarDays();
      }
    }

    function changeCalMonth(offset) {
      calDisplayDate.setMonth(calDisplayDate.getMonth() + offset);
      renderCalendarDays();
    }

    function renderCalendarDays() {
      const grid = document.getElementById('calendar-days-grid');
      const title = document.getElementById('cal-month-title');
      if (!grid || !title) return;

      const year = calDisplayDate.getFullYear();
      const month = calDisplayDate.getMonth();

      const monthNames = ["Enero", "Febrero", "Marzo", "Abril", "Mayo", "Junio", "Julio", "Agosto", "Septiembre", "Octubre", "Noviembre", "Diciembre"];
      title.innerText = `${monthNames[month]} ${year}`;

      const firstDayIndex = new Date(year, month, 1).getDay();
      const daysInMonth = new Date(year, month + 1, 0).getDate();

      let daysHTML = '';

      for (let i = 0; i < firstDayIndex; i++) {
        daysHTML += `<div></div>`;
      }

      for (let d = 1; d <= daysInMonth; d++) {
        const dateStr = `${year}-${String(month + 1).padStart(2, '0')}-${String(d).padStart(2, '0')}`;
        const dayTasks = tasks.filter(t => t.fecha === dateStr && !t.completada);
        
        let indicatorHTML = '';
        if (dayTasks.length > 0) {
          const color = subjectColors[dayTasks[0].materia] || '#10b981';
          indicatorHTML = `<div style="background-color: ${color};" class="w-1.5 h-1.5 rounded-full mx-auto mt-0.5"></div>`;
        }

        daysHTML += `
          <button onclick="openModalWithDate('${dateStr}')" class="p-1.5 rounded-lg hover:bg-gray-100 dark:hover:bg-neutral-800 transition relative flex flex-col items-center justify-center text-xs font-medium text-gray-700 dark:text-gray-300">
            <span>${d}</span>
            ${indicatorHTML}
          </button>
        `;
      }

      grid.innerHTML = daysHTML;
    }

    function openModalWithDate(dateStr) {
      toggleCalendarPopover();
      openModal('modal-tarea', dateStr);
    }

    function toggleDarkMode() {
      const isDark = document.documentElement.classList.contains('dark');
      if (isDark) {
        document.documentElement.classList.remove('dark');
        document.documentElement.classList.add('light');
        localStorage.setItem('theme', 'light');
        updateThemeUI(false);
      } else {
        document.documentElement.classList.add('dark');
        document.documentElement.classList.remove('light');
        localStorage.setItem('theme', 'dark');
        updateThemeUI(true);
      }
    }

    function updateThemeUI(isDark) {
      const icon = document.getElementById('theme-icon');
      if (icon) {
        icon.className = isDark ? 'fa-solid fa-sun text-amber-400 text-sm' : 'fa-solid fa-moon text-sm text-gray-600';
      }
    }

    init();
  </script>
</body>
</html>
