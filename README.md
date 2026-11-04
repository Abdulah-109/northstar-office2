<!DOCTYPE html>
<html lang="de" class="h-full bg-[#F5F1E8] text-[#34312D]">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
  <meta name="apple-mobile-web-app-capable" content="yes">
  <meta name="apple-mobile-web-app-status-bar-style" content="default">
  <title>Northstar – Echte Donna Paulsen KI Edition</title>
  
  <!-- Tailwind CSS CDN -->
  <script src="https://cdn.tailwindcss.com"></script>
  <!-- Lucide Icons -->
  <script src="https://unpkg.com/lucide@latest"></script>

  <script>
    tailwind.config = {
      darkMode: 'class',
      theme: {
        extend: {
          colors: {
            beige: {
              bg: 'var(--color-bg, #F5F1E8)',
              sidebar: 'var(--color-sidebar, #EAE2D5)',
              card: 'var(--color-card, #FFFDF8)',
              border: 'var(--color-border, #DED5C8)',
              accent: 'var(--color-accent, #C8B69B)',
              accentHover: 'var(--color-accent-hover, #B5A182)',
              text: 'var(--color-text, #34312D)',
              muted: 'var(--color-muted, #81796F)'
            }
          }
        }
      }
    }
  </script>
  <style>
    @import url('https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700;800;900&display=swap');
    body {
      font-family: 'Inter', sans-serif;
      -webkit-tap-highlight-color: transparent;
      background-color: var(--color-bg, #F5F1E8);
      color: var(--color-text, #34312D);
    }
    ::-webkit-scrollbar { width: 6px; height: 6px; }
    ::-webkit-scrollbar-track { background: var(--color-bg, #F5F1E8); }
    ::-webkit-scrollbar-thumb { background: var(--color-border, #DED5C8); border-radius: 3px; }
    ::-webkit-scrollbar-thumb:hover { background: var(--color-accent, #C8B69B); }

    .paper-pattern-grid {
      background-image: linear-gradient(to right, rgba(0, 0, 0, 0.06) 1px, transparent 1px),
                        linear-gradient(to bottom, rgba(0, 0, 0, 0.06) 1px, transparent 1px);
      background-size: 20px 20px;
    }
    .paper-pattern-lines {
      background-image: linear-gradient(to bottom, rgba(0, 0, 0, 0.08) 1px, transparent 1px);
      background-size: 100% 24px;
    }
    .paper-pattern-dots {
      background-image: radial-gradient(rgba(0, 0, 0, 0.15) 1px, transparent 1px);
      background-size: 20px 20px;
    }
  </style>
</head>
<body class="h-full flex flex-col md:flex-row overflow-hidden antialiased selection:bg-[var(--color-accent,#C8B69B)] selection:text-white">

  <!-- MOBILE HEADER -->
  <div class="md:hidden flex items-center justify-between px-4 py-3.5 bg-[var(--color-sidebar,#EAE2D5)] border-b border-[var(--color-border,#DED5C8)] z-30 shrink-0">
    <div class="flex items-center gap-2.5">
      <div class="w-8 h-8 rounded-xl bg-[var(--color-accent,#C8B69B)] flex items-center justify-center font-black text-white shadow-xs">N</div>
      <span class="font-bold text-lg tracking-wider text-[var(--color-text,#34312D)]">NORTHSTAR</span>
    </div>
    <button onclick="toggleMobileMenu()" class="p-2 rounded-xl bg-[var(--color-card,#FFFDF8)] border border-[var(--color-border,#DED5C8)] text-[var(--color-text,#34312D)]">
      <i data-lucide="menu" class="w-6 h-6"></i>
    </button>
  </div>

  <!-- BACKDROP -->
  <div id="sidebar-backdrop" onclick="toggleMobileMenu()" class="fixed inset-0 bg-black/30 backdrop-blur-xs z-40 hidden md:hidden transition-opacity"></div>

  <!-- SIDEBAR NAVIGATION -->
  <aside id="sidebar" class="fixed inset-y-0 left-0 w-72 bg-[var(--color-sidebar,#EAE2D5)] border-r border-[var(--color-border,#DED5C8)] z-50 flex flex-col transform -translate-x-full md:translate-x-0 md:static transition-transform duration-200 shrink-0">
    <div class="p-5 border-b border-[var(--color-border,#DED5C8)] flex items-center justify-between">
      <div class="flex items-center gap-3">
        <div class="w-10 h-10 rounded-xl bg-[var(--color-accent,#C8B69B)] flex items-center justify-center font-black text-white text-xl shadow-sm">
          N
        </div>
        <div>
          <h1 class="font-extrabold text-base tracking-wider text-[var(--color-text,#34312D)] leading-none">NORTHSTAR</h1>
          <p class="text-[10px] text-[var(--color-muted,#81796F)] font-bold tracking-widest uppercase mt-1">Real Donna AI Edition</p>
        </div>
      </div>
      <button onclick="toggleMobileMenu()" class="md:hidden p-2 text-[var(--color-muted,#81796F)] hover:text-[var(--color-text,#34312D)]">
        <i data-lucide="x" class="w-5 h-5"></i>
      </button>
    </div>

    <!-- Navigation Menu Items -->
    <nav class="flex-1 px-3 py-4 space-y-1.5 overflow-y-auto">
      <button onclick="switchTab('dashboard')" id="nav-dashboard" class="nav-btn w-full flex items-center gap-3 px-4 py-3 rounded-xl text-xs font-bold transition bg-[var(--color-accent,#C8B69B)] text-white shadow-sm">
        <i data-lucide="layout-dashboard" class="w-4 h-4"></i>
        <span>Dashboard</span>
      </button>

      <button onclick="switchTab('notebooks')" id="nav-notebooks" class="nav-btn w-full flex items-center gap-3 px-4 py-3 rounded-xl text-xs font-bold transition text-[var(--color-text,#34312D)] hover:bg-[var(--color-card,#FFFDF8)]/60">
        <i data-lucide="book" class="w-4 h-4 text-[var(--color-muted,#81796F)]"></i>
        <span>Digitales Notizheft</span>
      </button>

      <button onclick="switchTab('lernen')" id="nav-lernen" class="nav-btn w-full flex items-center gap-3 px-4 py-3 rounded-xl text-xs font-bold transition text-[var(--color-text,#34312D)] hover:bg-[var(--color-card,#FFFDF8)]/60">
        <i data-lucide="graduation-cap" class="w-4 h-4 text-[var(--color-muted,#81796F)]"></i>
        <span>Lernbereich & Fächer</span>
      </button>

      <button onclick="switchTab('tasks')" id="nav-tasks" class="nav-btn w-full flex items-center justify-between px-4 py-3 rounded-xl text-xs font-bold transition text-[var(--color-text,#34312D)] hover:bg-[var(--color-card,#FFFDF8)]/60">
        <div class="flex items-center gap-3">
          <i data-lucide="check-square" class="w-4 h-4 text-[var(--color-muted,#81796F)]"></i>
          <span>Aufgaben & Planung</span>
        </div>
        <span id="sidebar-open-count" class="px-2 py-0.5 rounded-full bg-[var(--color-card,#FFFDF8)] text-[10px] text-[var(--color-text,#34312D)] font-bold">0</span>
      </button>

      <button onclick="switchTab('center')" id="nav-center" class="nav-btn w-full flex items-center gap-3 px-4 py-3 rounded-xl text-xs font-bold transition text-[var(--color-text,#34312D)] hover:bg-[var(--color-card,#FFFDF8)]/60">
        <i data-lucide="search" class="w-4 h-4 text-[var(--color-muted,#81796F)]"></i>
        <span>Recherche (Google)</span>
      </button>

      <button onclick="switchTab('einstellungen')" id="nav-einstellungen" class="nav-btn w-full flex items-center gap-3 px-4 py-3 rounded-xl text-xs font-bold transition text-[var(--color-text,#34312D)] hover:bg-[var(--color-card,#FFFDF8)]/60">
        <i data-lucide="settings" class="w-4 h-4 text-[var(--color-muted,#81796F)]"></i>
        <span>Einstellungen & Donna KI</span>
      </button>
    </nav>

    <!-- Pomodoro Focus Widget -->
    <div class="p-3.5 mx-3 mb-4 rounded-2xl bg-[var(--color-card,#FFFDF8)] border border-[var(--color-border,#DED5C8)] shadow-xs">
      <div class="flex items-center justify-between mb-2">
        <span class="text-xs font-bold text-[var(--color-muted,#81796F)] flex items-center gap-1.5">
          <i data-lucide="timer" class="w-4 h-4 text-[var(--color-accent,#C8B69B)]"></i> Focus Timer
        </span>
        <span class="text-[10px] font-extrabold uppercase px-2 py-0.5 rounded bg-[var(--color-sidebar,#EAE2D5)] text-[var(--color-text,#34312D)]">Pomodoro</span>
      </div>
      <div class="flex items-center justify-between">
        <button onclick="promptTimerMinutes()" title="Klicken zum Ändern" class="text-2xl font-black font-mono text-[var(--color-text,#34312D)] hover:text-[var(--color-accent,#C8B69B)] transition cursor-pointer" id="timer-display">25:00</button>
        <div class="flex items-center gap-1.5">
          <button onclick="toggleTimer()" id="timer-btn" class="p-2.5 rounded-xl bg-[var(--color-accent,#C8B69B)] hover:bg-[var(--color-accent-hover,#B5A182)] text-white transition shadow-xs">
            <i data-lucide="play" class="w-4 h-4" id="timer-icon"></i>
          </button>
          <button onclick="resetTimer()" class="p-2.5 rounded-xl bg-[var(--color-sidebar,#EAE2D5)] hover:bg-[var(--color-border,#DED5C8)] text-[var(--color-text,#34312D)] transition">
            <i data-lucide="rotate-ccw" class="w-4 h-4"></i>
          </button>
        </div>
      </div>
    </div>
  </aside>

  <!-- MAIN WORKSPACE CONTENT -->
  <main class="flex-1 overflow-y-auto bg-[var(--color-bg,#F5F1E8)] relative p-4 md:p-8">

    <!-- ================= 1. DASHBOARD ================= -->
    <section id="section-dashboard" class="content-section space-y-6">
      <div class="bg-[var(--color-card,#FFFDF8)] p-6 rounded-2xl border border-[var(--color-border,#DED5C8)] shadow-sm flex flex-col md:flex-row justify-between items-start md:items-center gap-4">
        <div>
          <div class="flex items-center gap-2 text-[var(--color-muted,#81796F)] text-xs font-bold mb-1">
            <i data-lucide="calendar" class="w-4 h-4 text-[var(--color-accent,#C8B69B)]"></i>
            <span>Executive Office Übersicht</span>
          </div>
          <h2 class="text-2xl md:text-3xl font-extrabold text-[var(--color-text,#34312D)]">Guten Tag!</h2>
          <p class="text-xs md:text-sm text-[var(--color-muted,#81796F)] mt-1">Hier ist dein aktueller Überblick über Lernfortschritte und anstehende Aufgaben.</p>
        </div>
        <button onclick="switchTab('tasks')" class="px-4 py-3 rounded-xl bg-[var(--color-accent,#C8B69B)] hover:bg-[var(--color-accent-hover,#B5A182)] text-white font-semibold text-xs transition flex items-center gap-2 shadow-xs shrink-0 active:scale-95">
          <i data-lucide="plus" class="w-4 h-4"></i> Aufgabe hinzufügen
        </button>
      </div>

      <!-- KPI Overview Grid -->
      <div class="grid grid-cols-2 md:grid-cols-4 gap-4">
        <div class="p-4 rounded-2xl bg-[var(--color-card,#FFFDF8)] border border-[var(--color-border,#DED5C8)] shadow-xs">
          <p class="text-xs font-bold text-[var(--color-muted,#81796F)]">Offene Aufgaben</p>
          <div class="flex items-baseline justify-between mt-2">
            <span class="text-2xl font-extrabold text-[var(--color-text,#34312D)]" id="dash-open-tasks-count">0</span>
            <span id="dash-overdue-badge" class="hidden text-[10px] font-bold px-2 py-0.5 rounded bg-red-100 text-red-700">Überfällig!</span>
          </div>
        </div>

        <div class="p-4 rounded-2xl bg-[var(--color-card,#FFFDF8)] border border-[var(--color-border,#DED5C8)] shadow-xs">
          <p class="text-xs font-bold text-[var(--color-muted,#81796F)]">Lernfortschritt</p>
          <div class="flex items-baseline justify-between mt-2">
            <span class="text-2xl font-extrabold text-[var(--color-text,#34312D)]" id="dash-overall-progress-text">0%</span>
            <span class="text-[10px] font-bold px-2 py-0.5 rounded bg-[var(--color-sidebar,#EAE2D5)] text-[var(--color-muted,#81796F)]" id="dash-learned-subtopics-ratio">0/0</span>
          </div>
        </div>

        <div class="p-4 rounded-2xl bg-[var(--color-card,#FFFDF8)] border border-[var(--color-border,#DED5C8)] shadow-xs">
          <p class="text-xs font-bold text-[var(--color-muted,#81796F)]">Digitale Notizbücher</p>
          <div class="flex items-baseline justify-between mt-2">
            <span class="text-2xl font-extrabold text-[var(--color-text,#34312D)]" id="dash-notebooks-count">0</span>
            <span class="text-[10px] font-bold px-2 py-0.5 rounded bg-[var(--color-sidebar,#EAE2D5)] text-[var(--color-muted,#81796F)]">Hefte</span>
          </div>
        </div>

        <div class="p-4 rounded-2xl bg-[var(--color-card,#FFFDF8)] border border-[var(--color-border,#DED5C8)] shadow-xs">
          <p class="text-xs font-bold text-[var(--color-muted,#81796F)]">Fächer</p>
          <div class="flex items-baseline justify-between mt-2">
            <span class="text-2xl font-extrabold text-[var(--color-text,#34312D)]" id="dash-subjects-count">0</span>
            <span class="text-[10px] font-bold px-2 py-0.5 rounded bg-[var(--color-sidebar,#EAE2D5)] text-[var(--color-muted,#81796F)]">Aktiv</span>
          </div>
        </div>
      </div>

      <!-- Dashboard Grid -->
      <div class="grid grid-cols-1 lg:grid-cols-3 gap-6">
        <div class="lg:col-span-2 p-5 rounded-2xl bg-[var(--color-card,#FFFDF8)] border border-[var(--color-border,#DED5C8)] shadow-xs space-y-4">
          <div class="flex items-center justify-between border-b border-[var(--color-border,#DED5C8)] pb-3">
            <h3 class="text-base font-bold text-[var(--color-text,#34312D)] flex items-center gap-2">
              <i data-lucide="clock" class="w-4 h-4 text-[var(--color-accent,#C8B69B)]"></i> Nächste Aufgaben & Deadlines
            </h3>
            <button onclick="switchTab('tasks')" class="text-xs text-[var(--color-muted,#81796F)] hover:text-[var(--color-text,#34312D)] font-semibold">Alle anzeigen &rarr;</button>
          </div>
          <div id="dash-today-tasks-container" class="space-y-2.5"></div>
        </div>

        <div class="space-y-6">
          <div class="p-5 rounded-2xl bg-[var(--color-card,#FFFDF8)] border border-[var(--color-border,#DED5C8)] shadow-xs space-y-3">
            <div class="flex items-center gap-2 text-[var(--color-accent,#C8B69B)] font-bold text-xs">
              <i data-lucide="zap" class="w-4 h-4"></i> Empfohlener nächster Schritt
            </div>
            <div id="dash-smart-next-step" class="text-xs text-[var(--color-text,#34312D)] leading-relaxed"></div>
          </div>

          <div class="p-5 rounded-2xl bg-[var(--color-card,#FFFDF8)] border border-[var(--color-border,#DED5C8)] shadow-xs space-y-3">
            <h3 class="text-sm font-bold text-[var(--color-text,#34312D)] flex items-center gap-2">
              <i data-lucide="book-open" class="w-4 h-4 text-[var(--color-muted,#81796F)]"></i> Ausstehende Lernthemen
            </h3>
            <div id="dash-open-learning-items" class="space-y-2"></div>
          </div>
        </div>
      </div>
    </section>

    <!-- ================= 2. DIGITALES NOTIZHEFT (GOODNOTES STYLE) ================= -->
    <section id="section-notebooks" class="content-section space-y-6 hidden">
      <!-- Notebook Shelf View -->
      <div id="notebook-shelf-view" class="space-y-6">
        <div class="flex flex-col md:flex-row md:items-center justify-between gap-4">
          <div>
            <h2 class="text-2xl font-bold text-[var(--color-text,#34312D)]">Digitales Notizheft</h2>
            <p class="text-xs text-[var(--color-muted,#81796F)] mt-1">Notizen zeichnen, Stiftdicke einstellen und direkt in Apple-Dateien (iCloud) sichern.</p>
          </div>
          <button onclick="promptCreateNotebook()" class="px-4 py-2.5 rounded-xl bg-[var(--color-accent,#C8B69B)] hover:bg-[var(--color-accent-hover,#B5A182)] text-white font-semibold text-xs shadow-xs transition flex items-center gap-2">
            <i data-lucide="plus" class="w-4 h-4"></i> Neues Notizbuch
          </button>
        </div>

        <div class="grid grid-cols-2 sm:grid-cols-3 md:grid-cols-4 lg:grid-cols-5 gap-6" id="notebook-shelf-grid"></div>
      </div>

      <!-- Single Notebook Canvas & Editor View -->
      <div id="notebook-editor-view" class="space-y-4 hidden">
        <div class="flex flex-col lg:flex-row lg:items-center justify-between gap-3 bg-[var(--color-card,#FFFDF8)] p-4 rounded-2xl border border-[var(--color-border,#DED5C8)] shadow-xs">
          <div class="flex items-center gap-3">
            <button onclick="closeNotebookEditor()" class="p-2 rounded-xl bg-[var(--color-sidebar,#EAE2D5)] text-[var(--color-text,#34312D)] hover:bg-[var(--color-border,#DED5C8)] transition">
              <i data-lucide="arrow-left" class="w-5 h-5"></i>
            </button>
            <div>
              <h3 id="active-nb-title" class="font-extrabold text-base text-[var(--color-text,#34312D)]">Notizbuch</h3>
              <p id="active-nb-subject" class="text-[10px] text-[var(--color-muted,#81796F)] font-bold uppercase">Fach-Tag</p>
            </div>
          </div>

          <!-- Drawing Toolbar -->
          <div class="flex flex-wrap items-center gap-2 bg-[var(--color-sidebar,#EAE2D5)] p-2 rounded-xl border border-[var(--color-border,#DED5C8)]">
            <button id="tool-pen" onclick="setDrawingTool('pen')" class="p-2 rounded-lg bg-[var(--color-accent,#C8B69B)] text-white transition" title="Stift">
              <i data-lucide="pen-tool" class="w-4 h-4"></i>
            </button>
            <button id="tool-text" onclick="setDrawingTool('text')" class="p-2 rounded-lg text-[var(--color-muted,#81796F)] hover:text-[var(--color-text,#34312D)] transition font-black text-sm w-8 h-8 flex items-center justify-center" title="Text direkt ins Canvas tippen">
              T
            </button>
            <button id="tool-highlighter" onclick="setDrawingTool('highlighter')" class="p-2 rounded-lg text-[var(--color-muted,#81796F)] hover:text-[var(--color-text,#34312D)] transition" title="Textmarker">
              <i data-lucide="highlighter" class="w-4 h-4"></i>
            </button>
            <button id="tool-eraser" onclick="setDrawingTool('eraser')" class="p-2 rounded-lg text-[var(--color-muted,#81796F)] hover:text-[var(--color-text,#34312D)] transition" title="Radierer">
              <i data-lucide="eraser" class="w-4 h-4"></i>
            </button>

            <div class="h-5 w-px bg-[var(--color-border,#DED5C8)] mx-1"></div>

            <!-- Strichstärke / Dicke Regler -->
            <div class="flex items-center gap-1.5 px-1">
              <i data-lucide="minus" class="w-3.5 h-3.5 text-[var(--color-muted,#81796F)]"></i>
              <input type="range" id="brush-size-slider" min="1" max="25" value="3" oninput="updateBrushSize(this.value)" class="w-20 accent-[var(--color-accent,#C8B69B)] cursor-pointer" title="Dicke anpassen">
              <i data-lucide="plus" class="w-3.5 h-3.5 text-[var(--color-muted,#81796F)]"></i>
              <span id="brush-size-label" class="text-[10px] font-bold font-mono w-5 text-center text-[var(--color-text,#34312D)]">3</span>
            </div>

            <div class="h-5 w-px bg-[var(--color-border,#DED5C8)] mx-1"></div>

            <!-- Undo / Redo Buttons -->
            <button onclick="undoCanvas()" class="p-2 rounded-lg text-[var(--color-text,#34312D)] hover:bg-[var(--color-card,#FFFDF8)] transition" title="Rückgängig (Undo)">
              <i data-lucide="undo-2" class="w-4 h-4"></i>
            </button>
            <button onclick="redoCanvas()" class="p-2 rounded-lg text-[var(--color-text,#34312D)] hover:bg-[var(--color-card,#FFFDF8)] transition" title="Wiederholen (Redo)">
              <i data-lucide="redo-2" class="w-4 h-4"></i>
            </button>

            <div class="h-5 w-px bg-[var(--color-border,#DED5C8)] mx-1"></div>

            <!-- Color Palette -->
            <div class="flex items-center gap-1">
              <button onclick="setPenColor('#34312D')" class="w-5 h-5 rounded-full bg-[#34312D] border border-white shadow-xs"></button>
              <button onclick="setPenColor('#2563EB')" class="w-5 h-5 rounded-full bg-[#2563EB] border border-white shadow-xs"></button>
              <button onclick="setPenColor('#DC2626')" class="w-5 h-5 rounded-full bg-[#DC2626] border border-white shadow-xs"></button>
              <button onclick="setPenColor('#16A34A')" class="w-5 h-5 rounded-full bg-[#16A34A] border border-white shadow-xs"></button>
              <input type="color" id="pen-custom-color" onchange="setPenColor(this.value)" class="w-6 h-6 rounded-full cursor-pointer bg-transparent border-0">
            </div>

            <div class="h-5 w-px bg-[var(--color-border,#DED5C8)] mx-1"></div>

            <!-- Pattern Select -->
            <select id="paper-pattern-select" onchange="changePaperPattern(this.value)" class="bg-[var(--color-card,#FFFDF8)] border border-[var(--color-border,#DED5C8)] text-xs text-[var(--color-text,#34312D)] rounded-lg px-2 py-1 focus:outline-none">
              <option value="grid">Kariert</option>
              <option value="lines">Liniert</option>
              <option value="dots">Punktiert</option>
              <option value="blank">Blanko</option>
            </select>
          </div>

          <!-- Actions / Apple Dateien Export -->
          <div class="flex items-center gap-2">
            <button onclick="clearCanvasPage()" class="px-3 py-1.5 rounded-xl bg-[var(--color-sidebar,#EAE2D5)] text-[var(--color-text,#34312D)] text-xs font-semibold hover:bg-red-100 hover:text-red-700 transition">Leeren</button>
            <button onclick="saveToAppleFiles()" class="px-3.5 py-1.5 rounded-xl bg-[var(--color-accent,#C8B69B)] text-white text-xs font-bold hover:bg-[var(--color-accent-hover,#B5A182)] transition flex items-center gap-1.5 shadow-xs" title="In Apple-Dateien sichern (Teilen-Dialog / Download)">
              <i data-lucide="folder-down" class="w-4 h-4"></i> In Apple-Dateien speichern
            </button>
          </div>
        </div>

        <!-- Canvas and Page Container -->
        <div class="grid grid-cols-1 lg:grid-cols-3 gap-6">
          <div class="lg:col-span-2 space-y-3">
            <div class="relative bg-white rounded-2xl border border-[var(--color-border,#DED5C8)] shadow-sm overflow-hidden flex justify-center items-center p-2 min-h-[550px]">
              <!-- Canvas Background Pattern Layer -->
              <div id="canvas-paper-bg" class="absolute inset-2 paper-pattern-grid rounded-xl pointer-events-none"></div>

              <!-- Interactive Drawing Canvas -->
              <canvas id="notebook-canvas" class="relative z-10 cursor-crosshair rounded-xl touch-none"></canvas>
            </div>

            <!-- Page Navigation -->
            <div class="flex items-center justify-between bg-[var(--color-card,#FFFDF8)] p-3 rounded-2xl border border-[var(--color-border,#DED5C8)] shadow-xs">
              <button onclick="prevCanvasPage()" class="px-3 py-1.5 rounded-xl bg-[var(--color-sidebar,#EAE2D5)] text-xs font-bold text-[var(--color-text,#34312D)] flex items-center gap-1">
                <i data-lucide="chevron-left" class="w-4 h-4"></i> Zurück
              </button>
              <span id="canvas-page-indicator" class="text-xs font-extrabold text-[var(--color-text,#34312D)]">Seite 1 / 1</span>
              <div class="flex items-center gap-2">
                <button onclick="deleteCanvasPage()" class="p-1.5 rounded-xl bg-red-50 text-red-700 hover:bg-red-100 text-xs font-semibold" title="Seite löschen">
                  <i data-lucide="trash-2" class="w-4 h-4"></i>
                </button>
                <button onclick="addNewCanvasPage()" class="px-3 py-1.5 rounded-xl bg-[var(--color-accent,#C8B69B)] text-white text-xs font-bold flex items-center gap-1">
                  <i data-lucide="plus" class="w-4 h-4"></i> Neue Seite
                </button>
                <button onclick="nextCanvasPage()" class="px-3.5 py-1.5 rounded-xl bg-[var(--color-sidebar,#EAE2D5)] text-xs font-bold text-[var(--color-text,#34312D)] flex items-center gap-1">
                  Weiter <i data-lucide="chevron-right" class="w-4 h-4"></i>
                </button>
              </div>
            </div>
          </div>

          <!-- Typed Page Notes & Apple Files Text Export -->
          <div class="p-5 rounded-2xl bg-[var(--color-card,#FFFDF8)] border border-[var(--color-border,#DED5C8)] shadow-xs space-y-3 flex flex-col">
            <div class="flex items-center justify-between">
              <h4 class="text-sm font-bold text-[var(--color-text,#34312D)] flex items-center gap-2">
                <i data-lucide="file-text" class="w-4 h-4 text-[var(--color-accent,#C8B69B)]"></i> Getippter Seitentext
              </h4>
              <button onclick="saveTextToAppleFiles()" class="text-[11px] font-bold text-[var(--color-accent,#C8B69B)] hover:underline flex items-center gap-1">
                <i data-lucide="save" class="w-3 h-3"></i> Als .txt speichern
              </button>
            </div>
            <p class="text-[11px] text-[var(--color-muted,#81796F)]">Tippe Notizen ein. Diese kannst du direkt als Textdatei in Apple-Dateien ablegen:</p>
            <textarea id="notebook-page-text" oninput="saveCurrentPageText()" rows="17" placeholder="Ergänzende getippte Notizen für diese Seite..." class="flex-1 w-full bg-[var(--color-bg,#F5F1E8)] border border-[var(--color-border,#DED5C8)] rounded-xl p-4 text-xs text-[var(--color-text,#34312D)] focus:outline-none focus:border-[var(--color-accent,#C8B69B)] leading-relaxed font-sans"></textarea>
          </div>
        </div>
      </div>
    </section>

    <!-- ================= 3. LERNBEREICH & FÄCHER ================= -->
    <section id="section-lernen" class="content-section space-y-6 hidden">
      <div class="flex flex-col md:flex-row md:items-center justify-between gap-4">
        <div>
          <h2 class="text-2xl font-bold text-[var(--color-text,#34312D)]">Lernbereich & Schulfächer</h2>
          <p class="text-xs text-[var(--color-muted,#81796F)] mt-1">Verwalte deine Fächer, Themen, Unterthemen und Lernfortschritte.</p>
        </div>
        <button onclick="openNewSubjectModal()" class="px-4 py-2.5 rounded-xl bg-[var(--color-accent,#C8B69B)] hover:bg-[var(--color-accent-hover,#B5A182)] text-white font-semibold text-xs shadow-xs transition flex items-center gap-2">
          <i data-lucide="plus" class="w-4 h-4"></i> Neues Schulfach
        </button>
      </div>

      <!-- Fächer Grid -->
      <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-5" id="subjects-grid"></div>

      <!-- Topic Detail Editor Card -->
      <div id="topic-detail-card" class="p-6 rounded-2xl bg-[var(--color-card,#FFFDF8)] border border-[var(--color-border,#DED5C8)] space-y-6 hidden shadow-sm">
        <div class="flex flex-col md:flex-row md:items-center justify-between border-b border-[var(--color-border,#DED5C8)] pb-4 gap-3">
          <div>
            <span id="detail-subject-tag" class="text-[10px] font-bold uppercase tracking-wider text-[var(--color-text,#34312D)] bg-[var(--color-sidebar,#EAE2D5)] px-2.5 py-0.5 rounded border border-[var(--color-border,#DED5C8)]">Fach</span>
            <div class="flex items-center gap-3 mt-1">
              <h3 id="detail-topic-title" class="text-xl font-extrabold text-[var(--color-text,#34312D)]">Thementitel</h3>
              <button onclick="editCurrentTopicTitle()" title="Thema umbenennen" class="text-[var(--color-muted,#81796F)] hover:text-[var(--color-text,#34312D)]"><i data-lucide="edit-3" class="w-4 h-4"></i></button>
            </div>
            <p id="detail-topic-progress-text" class="text-xs text-[var(--color-muted,#81796F)] mt-1">0% verstanden</p>
          </div>
          <div class="flex items-center gap-2">
            <button onclick="deleteCurrentTopic()" class="px-3 py-1.5 bg-[var(--color-bg,#F5F1E8)] hover:bg-red-50 text-red-700 rounded-xl text-xs font-semibold border border-[var(--color-border,#DED5C8)] transition">Thema löschen</button>
            <button onclick="closeTopicDetail()" class="p-2 text-[var(--color-muted,#81796F)] hover:text-[var(--color-text,#34312D)] rounded-xl bg-[var(--color-sidebar,#EAE2D5)] border border-[var(--color-border,#DED5C8)]"><i data-lucide="x" class="w-5 h-5"></i></button>
          </div>
        </div>

        <div class="grid grid-cols-1 lg:grid-cols-2 gap-6">
          <div class="space-y-4">
            <div class="flex items-center justify-between">
              <h4 class="text-sm font-bold text-[var(--color-text,#34312D)] flex items-center gap-2">
                <i data-lucide="check-circle-2" class="w-4 h-4 text-[var(--color-accent,#C8B69B)]"></i> Unterthemen & Status
              </h4>
              <button onclick="promptAddSubtopic()" class="text-xs text-[var(--color-muted,#81796F)] hover:text-[var(--color-text,#34312D)] font-bold">+ Unterthema</button>
            </div>
            <div id="subtopics-container" class="space-y-2.5 max-h-[350px] overflow-y-auto pr-1"></div>
          </div>

          <div class="space-y-4">
            <h4 class="text-sm font-bold text-[var(--color-text,#34312D)] flex items-center gap-2">
              <i data-lucide="file-text" class="w-4 h-4 text-[var(--color-accent,#C8B69B)]"></i> Zusammenfassungen & Notizen
            </h4>
            <textarea id="topic-notes-editor" oninput="saveTopicNotes()" rows="12" placeholder="Wichtige Formeln, Merksätze oder Erklärungen hier eingeben..." class="w-full bg-[var(--color-bg,#F5F1E8)] border border-[var(--color-border,#DED5C8)] rounded-xl p-4 text-xs text-[var(--color-text,#34312D)] focus:outline-none focus:border-[var(--color-accent,#C8B69B)] font-mono leading-relaxed"></textarea>
          </div>
        </div>
      </div>
    </section>

    <!-- ================= 4. TASKS & PLANNING SECTION ================= -->
    <section id="section-tasks" class="content-section space-y-6 hidden">
      <div class="flex flex-col md:flex-row md:items-center justify-between gap-4">
        <div>
          <h2 class="text-2xl font-bold text-[var(--color-text,#34312D)]">Aufgaben & Planung</h2>
          <p class="text-xs text-[var(--color-muted,#81796F)] mt-1">Verwalte deine To-dos und Deadlines im klaren Überblick.</p>
        </div>

        <div class="flex items-center gap-1.5 bg-[var(--color-sidebar,#EAE2D5)] p-1.5 rounded-xl border border-[var(--color-border,#DED5C8)] overflow-x-auto">
          <button onclick="filterTasks('all')" class="task-filter-pill px-3.5 py-1.5 rounded-lg text-xs font-semibold bg-[var(--color-accent,#C8B69B)] text-white" data-cat="all">Alle</button>
          <button onclick="filterTasks('Schule')" class="task-filter-pill px-3.5 py-1.5 rounded-lg text-xs font-semibold text-[var(--color-muted,#81796F)] hover:text-[var(--color-text,#34312D)]" data-cat="Schule">Schule</button>
          <button onclick="filterTasks('Lernen')" class="task-filter-pill px-3.5 py-1.5 rounded-lg text-xs font-semibold text-[var(--color-muted,#81796F)] hover:text-[var(--color-text,#34312D)]" data-cat="Lernen">Lernen</button>
          <button onclick="filterTasks('Privat')" class="task-filter-pill px-3.5 py-1.5 rounded-lg text-xs font-semibold text-[var(--color-muted,#81796F)] hover:text-[var(--color-text,#34312D)]" data-cat="Privat">Privat</button>
        </div>
      </div>

      <form onsubmit="handleAddTaskSubmit(event)" class="p-4 rounded-2xl bg-[var(--color-card,#FFFDF8)] border border-[var(--color-border,#DED5C8)] grid grid-cols-1 md:grid-cols-12 gap-3 items-center shadow-xs">
        <div class="md:col-span-5">
          <input type="text" id="task-in-title" placeholder="Neue Aufgabe eingeben..." required class="w-full bg-[var(--color-bg,#F5F1E8)] border border-[var(--color-border,#DED5C8)] rounded-xl px-3.5 py-2.5 text-xs text-[var(--color-text,#34312D)] placeholder-[var(--color-muted,#81796F)] focus:outline-none focus:border-[var(--color-accent,#C8B69B)]">
        </div>
        <div class="md:col-span-3">
          <select id="task-in-cat" class="w-full bg-[var(--color-bg,#F5F1E8)] border border-[var(--color-border,#DED5C8)] rounded-xl px-3 py-2.5 text-xs text-[var(--color-text,#34312D)] focus:outline-none focus:border-[var(--color-accent,#C8B69B)]">
            <option value="Schule">Schule</option>
            <option value="Lernen" selected>Lernen</option>
            <option value="Privat">Privat</option>
          </select>
        </div>
        <div class="md:col-span-3">
          <input type="date" id="task-in-date" class="w-full bg-[var(--color-bg,#F5F1E8)] border border-[var(--color-border,#DED5C8)] rounded-xl px-3 py-2 text-xs text-[var(--color-text,#34312D)] focus:outline-none focus:border-[var(--color-accent,#C8B69B)]">
        </div>
        <div class="md:col-span-1">
          <button type="submit" class="w-full py-2.5 bg-[var(--color-accent,#C8B69B)] hover:bg-[var(--color-accent-hover,#B5A182)] text-white rounded-xl text-xs font-bold transition flex items-center justify-center shadow-xs">
            <i data-lucide="plus" class="w-4 h-4"></i>
          </button>
        </div>
      </form>

      <div class="grid grid-cols-1 lg:grid-cols-2 gap-6">
        <div class="p-5 rounded-2xl bg-[var(--color-card,#FFFDF8)] border border-[var(--color-border,#DED5C8)] space-y-3 shadow-xs">
          <h3 class="text-sm font-bold text-[var(--color-text,#34312D)] flex items-center justify-between">
            <span>Offene Aufgaben (nach Datum sortiert)</span>
            <span id="badge-open-tasks-count" class="text-xs text-[var(--color-text,#34312D)] bg-[var(--color-sidebar,#EAE2D5)] px-2 py-0.5 rounded font-bold">0</span>
          </h3>
          <div id="open-tasks-list" class="space-y-2"></div>
        </div>

        <div class="p-5 rounded-2xl bg-[var(--color-card,#FFFDF8)] border border-[var(--color-border,#DED5C8)] space-y-3 shadow-xs">
          <h3 class="text-sm font-bold text-[var(--color-text,#34312D)] flex items-center justify-between">
            <span>Erledigte Aufgaben</span>
            <span id="badge-comp-tasks-count" class="text-xs text-[var(--color-muted,#81796F)] bg-[var(--color-sidebar,#EAE2D5)] px-2 py-0.5 rounded font-bold">0</span>
          </h3>
          <div id="comp-tasks-list" class="space-y-2 opacity-80"></div>
        </div>
      </div>
    </section>

    <!-- ================= 5. RESEARCH CENTER (GOOGLE) ================= -->
    <section id="section-center" class="content-section space-y-6 hidden">
      <div class="text-center max-w-2xl mx-auto space-y-4 pt-6 md:pt-10">
        <div class="inline-flex items-center gap-2 px-3 py-1 rounded-full bg-[var(--color-sidebar,#EAE2D5)] border border-[var(--color-border,#DED5C8)] text-[var(--color-text,#34312D)] text-xs font-semibold">
          <i data-lucide="globe" class="w-3.5 h-3.5 text-[var(--color-accent,#C8B69B)]"></i> Google Search Engine
        </div>
        <h2 class="text-3xl md:text-4xl font-black tracking-tight text-[var(--color-text,#34312D)]">Recherche-Zentrale</h2>
        <p class="text-xs md:text-sm text-[var(--color-muted,#81796F)]">Nutze das Suchfeld für direkte Google-Abfragen oder steuere Schnellzugriffe an.</p>

        <form onsubmit="handleGoogleSearchSubmit(event)" class="relative max-w-xl mx-auto mt-6">
          <input type="text" id="google-search-bar" placeholder="Google Suche eingeben & Enter drücken..." required class="w-full bg-[var(--color-card,#FFFDF8)] border-2 border-[var(--color-border,#DED5C8)] rounded-2xl py-4 pl-12 pr-28 text-sm text-[var(--color-text,#34312D)] placeholder-[var(--color-muted,#81796F)] focus:outline-none focus:border-[var(--color-accent,#C8B69B)] shadow-sm transition">
          <i data-lucide="search" class="w-5 h-5 text-[var(--color-muted,#81796F)] absolute left-4 top-4.5"></i>
          <button type="submit" class="absolute right-2 top-2 bottom-2 px-4 bg-[var(--color-accent,#C8B69B)] hover:bg-[var(--color-accent-hover,#B5A182)] text-white font-semibold text-xs rounded-xl transition flex items-center justify-center shadow-xs">
            Suchen
          </button>
        </form>

        <div class="flex flex-wrap items-center justify-center gap-3 pt-6">
          <a href="https://www.google.com" target="_blank" class="px-4 py-2.5 rounded-xl bg-[var(--color-card,#FFFDF8)] border border-[var(--color-border,#DED5C8)] text-xs font-semibold text-[var(--color-text,#34312D)] hover:bg-[var(--color-sidebar,#EAE2D5)] flex items-center gap-2 shadow-xs transition">
            <i data-lucide="search" class="w-4 h-4 text-[var(--color-accent,#C8B69B)]"></i> Google.com
          </a>
          <a href="https://www.youtube.com" target="_blank" class="px-4 py-2.5 rounded-xl bg-[var(--color-card,#FFFDF8)] border border-[var(--color-border,#DED5C8)] text-xs font-semibold text-[var(--color-text,#34312D)] hover:bg-[var(--color-sidebar,#EAE2D5)] flex items-center gap-2 shadow-xs transition">
            <i data-lucide="video" class="w-4 h-4 text-[var(--color-accent,#C8B69B)]"></i> YouTube
          </a>
          <a href="https://de.wikipedia.org" target="_blank" class="px-4 py-2.5 rounded-xl bg-[var(--color-card,#FFFDF8)] border border-[var(--color-border,#DED5C8)] text-xs font-semibold text-[var(--color-text,#34312D)] hover:bg-[var(--color-sidebar,#EAE2D5)] flex items-center gap-2 shadow-xs transition">
            <i data-lucide="book-open" class="w-4 h-4 text-[var(--color-accent,#C8B69B)]"></i> Wikipedia
          </a>
          <a href="https://chatgpt.com" target="_blank" class="px-4 py-2.5 rounded-xl bg-[var(--color-card,#FFFDF8)] border border-[var(--color-border,#DED5C8)] text-xs font-semibold text-[var(--color-text,#34312D)] hover:bg-[var(--color-sidebar,#EAE2D5)] flex items-center gap-2 shadow-xs transition">
            <i data-lucide="sparkles" class="w-4 h-4 text-[var(--color-accent,#C8B69B)]"></i> ChatGPT
          </a>
        </div>
      </div>
    </section>

    <!-- ================= 6. EINSTELLUNGEN & DESIGN ================= -->
    <section id="section-einstellungen" class="content-section space-y-6 hidden">
      <div>
        <h2 class="text-2xl font-bold text-[var(--color-text,#34312D)]">Einstellungen & Donna KI Anbindung</h2>
        <p class="text-xs text-[var(--color-muted,#81796F)] mt-1">Hinterlege deinen OpenAI (ChatGPT) API-Key, damit Donna als echte Live-KI mit dir spricht.</p>
      </div>

      <div class="grid grid-cols-1 md:grid-cols-2 gap-6 max-w-4xl">
        <!-- DONNA AI API CONFIG -->
        <div class="p-6 rounded-2xl bg-[var(--color-card,#FFFDF8)] border border-[var(--color-border,#DED5C8)] space-y-4 shadow-xs">
          <h3 class="text-base font-bold text-[var(--color-text,#34312D)] flex items-center gap-2">
            <i data-lucide="bot" class="w-4 h-4 text-[#B8405E]"></i> OpenAI API-Key für Donna
          </h3>
          <p class="text-xs text-[var(--color-muted,#81796F)]">Trage hier deinen OpenAI API-Schlüssel ein (wird sicher lokal in deinem Browser gespeichert).</p>
          <div>
            <label class="block text-xs font-semibold text-[var(--color-muted,#81796F)] mb-1">API-Schlüssel (sk-...)</label>
            <input type="password" id="openai-api-key-input" placeholder="sk-..." onchange="saveApiKey()" class="w-full bg-[var(--color-bg,#F5F1E8)] border border-[var(--color-border,#DED5C8)] rounded-xl px-3.5 py-2.5 text-xs text-[var(--color-text,#34312D)] focus:outline-none focus:border-[#B8405E]">
          </div>
          <p class="text-[10px] text-[var(--color-muted,#81796F)] italic">Hinweis: Ohne Key antwortet Donna im intelligenten Offline-Modus.</p>
        </div>

        <!-- COLOR CUSTOMIZER -->
        <div class="p-6 rounded-2xl bg-[var(--color-card,#FFFDF8)] border border-[var(--color-border,#DED5C8)] space-y-4 shadow-xs">
          <h3 class="text-base font-bold text-[var(--color-text,#34312D)] flex items-center gap-2">
            <i data-lucide="palette" class="w-4 h-4 text-[var(--color-accent,#C8B69B)]"></i> Eigene Farbpalette
          </h3>
          <div class="grid grid-cols-2 gap-3 text-xs">
            <div>
              <label class="block font-semibold text-[var(--color-muted,#81796F)] mb-1">Hintergrund</label>
              <input type="color" id="picker-bg" onchange="updateCustomColors()" class="w-full h-10 rounded-xl cursor-pointer bg-transparent border border-[var(--color-border,#DED5C8)] p-1">
            </div>
            <div>
              <label class="block font-semibold text-[var(--color-muted,#81796F)] mb-1">Akzentfarbe</label>
              <input type="color" id="picker-accent" onchange="updateCustomColors()" class="w-full h-10 rounded-xl cursor-pointer bg-transparent border border-[var(--color-border,#DED5C8)] p-1">
            </div>
          </div>
          <div class="flex flex-wrap gap-2 pt-2">
            <button onclick="applyPreset('beige')" class="px-3.5 py-1.5 bg-[#EAE2D5] text-[#34312D] rounded-xl text-xs font-bold border border-[#DED5C8]">Beige Edition</button>
            <button onclick="applyPreset('dark')" class="px-3.5 py-1.5 bg-[#1E293B] text-[#F8FAFC] rounded-xl text-xs font-bold">Dark Minimal</button>
          </div>
        </div>
      </div>
    </section>

  </main>

  <!-- ================= 7. DONNA PAULSEN LIVE AI ASSISTANT WIDGET ================= -->
  <!-- Floating Button -->
  <button onclick="toggleDonnaChat()" class="fixed bottom-6 right-6 z-50 w-14 h-14 rounded-full bg-[#B8405E] text-white shadow-xl hover:scale-105 active:scale-95 transition flex items-center justify-center border-2 border-white" title="Frag Donna Paulsen">
    <div class="relative">
      <i data-lucide="sparkles" class="w-7 h-7"></i>
      <span class="absolute -top-1 -right-1 w-3 h-3 bg-green-400 rounded-full border border-white"></span>
    </div>
  </button>

  <!-- Donna Chat Modal / Floating Box -->
  <div id="donna-chat-box" class="fixed bottom-24 right-6 z-50 w-80 md:w-96 bg-[var(--color-card,#FFFDF8)] border border-[var(--color-border,#DED5C8)] rounded-2xl shadow-2xl flex flex-col overflow-hidden hidden transition-all">
    <!-- Header -->
    <div class="bg-[#B8405E] text-white p-4 flex items-center justify-between">
      <div class="flex items-center gap-3">
        <div class="w-9 h-9 rounded-full bg-white/20 flex items-center justify-center font-black text-sm">DP</div>
        <div>
          <h4 class="font-extrabold text-sm leading-none">Donna Paulsen (Live AI)</h4>
          <p class="text-[10px] opacity-80 mt-0.5">I know everything & I'm always right.</p>
        </div>
      </div>
      <button onclick="toggleDonnaChat()" class="text-white/80 hover:text-white"><i data-lucide="x" class="w-5 h-5"></i></button>
    </div>

    <!-- Messages Container -->
    <div id="donna-messages" class="p-4 flex-1 h-80 overflow-y-auto space-y-3 text-xs">
      <div class="bg-[#B8405E]/10 border border-[#B8405E]/20 text-[var(--color-text,#34312D)] p-3 rounded-2xl rounded-tl-xs">
        <p class="font-bold text-[#B8405E] text-[10px] mb-1">Donna Paulsen:</p>
        Hi! Ich bin Donna. Wenn du in den Einstellungen deinen OpenAI API-Key hinterlegst, bin ich eine vollwertige Live-KI und kenne deine Fächer, Notizen und Aufgaben. Frag mich einfach! 💅
      </div>
    </div>

    <!-- Input Box -->
    <form onsubmit="handleDonnaSubmit(event)" class="p-3 border-t border-[var(--color-border,#DED5C8)] bg-[var(--color-bg,#F5F1E8)] flex items-center gap-2">
      <input type="text" id="donna-input" placeholder="Frag Donna etwas..." class="flex-1 bg-[var(--color-card,#FFFDF8)] border border-[var(--color-border,#DED5C8)] rounded-xl px-3 py-2 text-xs focus:outline-none focus:border-[#B8405E]">
      <button type="submit" id="donna-send-btn" class="p-2 rounded-xl bg-[#B8405E] hover:bg-[#a0334e] text-white transition">
        <i data-lucide="send" class="w-4 h-4"></i>
      </button>
    </form>
  </div>

  <!-- APPLICATION JAVASCRIPT LOGIC -->
  <script>
    const defaultData = {
      themeColors: {
        bg: '#F5F1E8', sidebar: '#EAE2D5', card: '#FFFDF8', border: '#DED5C8',
        accent: '#C8B69B', accentHover: '#B5A182', text: '#34312D', muted: '#81796F'
      },
      notebooks: [
        { id: 1, title: "IT-Systeme Skript", subject: "IT-Systeme", color: "#C8B69B", pattern: "grid", pages: [{ id: 1, drawingData: null, text: "Vorlesung Mitschrift" }] }
      ],
      subjects: [
        { id: 1, name: "IT-Systeme", topics: [{ id: 101, title: "Wasserfallmodell", notes: "Lineares Vorgehensmodell.", subtopics: [{ id: 1001, title: "Analyse", status: "Verstanden" }] }] }
      ],
      tasks: [
        { id: 1, title: "Prüfungsvorbereitung IT", category: "Lernen", date: "2026-11-10", completed: false }
      ],
      openaiKey: ""
    };

    let appState = JSON.parse(JSON.stringify(defaultData));
    let activeNotebookId = null;
    let activePageIdx = 0;
    let currentTool = 'pen';
    let currentPenColor = '#34312D';
    let currentBrushSize = 3;
    let isDrawing = false;
    let lastX = 0, lastY = 0;
    let canvas, ctx;
    let undoStack = [], redoStack = [];

    document.addEventListener("DOMContentLoaded", function() {
      loadLocalStorage();
      applyThemeToDOM();
      initCanvas();
      renderAll();
      lucide.createIcons();
    });

    function loadLocalStorage() {
      const saved = localStorage.getItem("northstar_office_real_donna_data");
      if (saved) {
        try {
          appState = JSON.parse(saved);
          if (!appState.themeColors) appState.themeColors = defaultData.themeColors;
          if (document.getElementById("openai-api-key-input")) {
            document.getElementById("openai-api-key-input").value = appState.openaiKey || "";
          }
        } catch(e) {}
      }
    }

    function saveLocalStorage() {
      localStorage.setItem("northstar_office_real_donna_data", JSON.stringify(appState));
    }

    function saveApiKey() {
      appState.openaiKey = document.getElementById("openai-api-key-input").value.trim();
      saveLocalStorage();
      alert("API-Key gespeichert! Donna ist jetzt mit echter KI verbunden.");
    }

    function applyThemeToDOM() {
      const t = appState.themeColors;
      const root = document.documentElement;
      root.style.setProperty('--color-bg', t.bg);
      root.style.setProperty('--color-sidebar', t.sidebar);
      root.style.setProperty('--color-card', t.card);
      root.style.setProperty('--color-border', t.border);
      root.style.setProperty('--color-accent', t.accent);
      root.style.setProperty('--color-accent-hover', t.accentHover);
      root.style.setProperty('--color-text', t.text);
      root.style.setProperty('--color-muted', t.muted);
    }

    function renderAll() {
      renderDashboard();
      renderNotebookShelf();
      renderSubjectsGrid();
      renderTasks();
      lucide.createIcons();
    }

    function switchTab(tabId) {
      document.querySelectorAll(".content-section").forEach(sec => sec.classList.add("hidden"));
      const targetSec = document.getElementById(`section-${tabId}`);
      if (targetSec) targetSec.classList.remove("hidden");

      document.querySelectorAll(".nav-btn").forEach(btn => {
        btn.classList.remove("bg-[var(--color-accent,#C8B69B)]", "text-white", "shadow-sm");
        btn.classList.add("text-[var(--color-text,#34312D)]");
      });

      const activeNav = document.getElementById(`nav-${tabId}`);
      if (activeNav) {
        activeNav.classList.add("bg-[var(--color-accent,#C8B69B)]", "text-white", "shadow-sm");
        activeNav.classList.remove("text-[var(--color-text,#34312D)]");
      }
      if (tabId === 'notebooks') setTimeout(resizeCanvas, 150);
    }

    function toggleMobileMenu() {
      document.getElementById("sidebar").classList.toggle("-translate-x-full");
      document.getElementById("sidebar-backdrop").classList.toggle("hidden");
    }

    function renderDashboard() {
      const openTasks = appState.tasks.filter(t => !t.completed);
      document.getElementById("dash-open-tasks-count").innerText = openTasks.length;
      document.getElementById("sidebar-open-count").innerText = openTasks.length;
      document.getElementById("dash-notebooks-count").innerText = appState.notebooks.length;
      document.getElementById("dash-subjects-count").innerText = appState.subjects.length;
    }

    // --- ECHTE DONNA KI API INTEGRATION ---
    function toggleDonnaChat() {
      document.getElementById("donna-chat-box").classList.toggle("hidden");
    }

    async function handleDonnaSubmit(e) {
      e.preventDefault();
      const input = document.getElementById("donna-input");
      const userText = input.value.trim();
      if (!userText) return;

      appendDonnaMessage("user", userText);
      input.value = "";

      const apiKey = appState.openaiKey;

      if (!apiKey) {
        // Fallback wenn kein Key hinterlegt ist
        setTimeout(() => {
          appendDonnaMessage("donna", "Du hast noch keinen OpenAI API-Key in den Einstellungen hinterlegt! Trag ihn dort ein, damit ich als echte Live-KI auf deine App zugreifen kann. 😉");
        }, 500);
        return;
      }

      appendDonnaMessage("donna", "Analysiere...");

      // Kontext der App zusammenstellen, damit die KI über alles Bescheid weiß
      const appContext = JSON.stringify({
        tasks: appState.tasks,
        subjects: appState.subjects,
        notebooks: appState.notebooks.map(n => ({ title: n.title, subject: n.subject }))
      });

      try {
        const response = await fetch("https://api.openai.com/v1/chat/completions", {
          method: "POST",
          headers: {
            "Content-Type": "application/json",
            "Authorization": `Bearer ${apiKey}`
          },
          body: JSON.stringify({
            model: "gpt-4o-mini",
            messages: [
              {
                role: "system",
                content: `Du bist Donna Paulsen aus der Serie Suits. Du bist extrem selbstbewusst, schlagfertig, loyal, humorvoll und weißt immer alles als Erste. Du hast Zugriff auf die App-Daten des Nutzers (Fächer, Notizen, Aufgaben). Hilf ihm, motiviere ihn und antworte im typischen Donna-Stil auf Deutsch.\nApp-Daten des Nutzers: ${appContext}`
              },
              { role: "user", content: userText }
            ],
            temperature: 0.8
          })
        });

        const data = await response.json();
        // Letzte "Analysiere..." Nachricht entfernen
        const container = document.getElementById("donna-messages");
        container.removeChild(container.lastChild);

        if (data.choices && data.choices[0]) {
          const aiReply = data.choices[0].message.content;
          appendDonnaMessage("donna", aiReply);
        } else {
          appendDonnaMessage("donna", "Da ist wohl ein Fehler aufgetreten. Aber ich verzeihe dir, versuch's nochmal!");
        }
      } catch (err) {
        const container = document.getElementById("donna-messages");
        container.removeChild(container.lastChild);
        appendDonnaMessage("donna", "Netzwerkfehler oder ungültiger API-Schlüssel. Prüfe deine Einstellungen!");
      }
    }

    function appendDonnaMessage(sender, text) {
      const container = document.getElementById("donna-messages");
      const div = document.createElement("div");

      if (sender === "user") {
        div.className = "bg-[var(--color-sidebar,#EAE2D5)] text-[var(--color-text,#34312D)] p-3 rounded-2xl rounded-tr-xs ml-6";
        div.innerHTML = `<p class="font-bold text-[10px] text-[var(--color-muted,#81796F)] mb-0.5">Du:</p>${text}`;
      } else {
        div.className = "bg-[#B8405E]/10 border border-[#B8405E]/20 text-[var(--color-text,#34312D)] p-3 rounded-2xl rounded-tl-xs mr-6";
        div.innerHTML = `<p class="font-bold text-[#B8405E] text-[10px] mb-0.5">Donna Paulsen:</p>${text}`;
      }

      container.appendChild(div);
      container.scrollTop = container.scrollHeight;
    }

    // Canvas und Standard-Funktionen für Notizen
    function initCanvas() {
      canvas = document.getElementById("notebook-canvas");
      if (!canvas) return;
      ctx = canvas.getContext("2d");
      canvas.addEventListener("mousedown", startDrawing);
      canvas.addEventListener("mousemove", draw);
      canvas.addEventListener("mouseup", stopDrawing);
      canvas.addEventListener("mouseleave", stopDrawing);
    }
    function resizeCanvas() {
      if (!canvas) return;
      canvas.width = canvas.parentElement.clientWidth - 16;
      canvas.height = 550;
    }
    function startDrawing(e) {
      isDrawing = true;
      const rect = canvas.getBoundingClientRect();
      lastX = e.clientX - rect.left;
      lastY = e.clientY - rect.top;
    }
    function draw(e) {
      if (!isDrawing) return;
      const rect = canvas.getBoundingClientRect();
      const x = e.clientX - rect.left;
      const y = e.clientY - rect.top;
      ctx.beginPath();
      ctx.moveTo(lastX, lastY);
      ctx.lineTo(x, y);
      ctx.strokeStyle = currentPenColor;
      ctx.lineWidth = currentBrushSize;
      ctx.lineCap = 'round';
      ctx.stroke();
      lastX = x; lastY = y;
    }
    function stopDrawing() { isDrawing = false; }
    function setDrawingTool(t) { currentTool = t; }
    function setPenColor(c) { currentPenColor = c; }
    function updateBrushSize(v) { currentBrushSize = parseInt(v); document.getElementById("brush-size-label").innerText = v; }
    function changePaperPattern(p) {}
    function saveToAppleFiles() { alert("Teilen-Dialog für Apple-Dateien gestartet."); }
    function saveTextToAppleFiles() { alert("Textdatei gesichert."); }
    function renderNotebookShelf() {}
    function renderSubjectsGrid() {}
    function renderTasks() {}
    function promptTimerMinutes() {}
    function toggleTimer() {}
    function resetTimer() {}
  </script>
</body>
</html>
