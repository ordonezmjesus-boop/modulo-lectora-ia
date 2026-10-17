# modulo-lectora-ia
<!DOCTYPE html>
<html lang="es" class="h-full bg-slate-50">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Módulo Lector IA - I.E. Rafael Núñez</title>
    <!-- Tailwind CSS CDN -->
    <script src="https://cdn.tailwindcss.com"></script>
    <!-- FontAwesome Icons CDN -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <!-- Chart.js CDN -->
    <script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
    <script>
        tailwind.config = {
            theme: {
                extend: {
                    colors: {
                        brand: {
                            50: '#f0f7ff',
                            100: '#e0effe',
                            500: '#2563eb',
                            600: '#1d4ed8',
                            700: '#1e40af',
                            800: '#1e3a8a',
                            900: '#172554',
                        }
                    }
                }
            }
        }
    </script>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700&display=swap');
        body { font-family: 'Inter', sans-serif; }
        .tab-active {
            border-bottom: 3px solid #2563eb;
            color: #2563eb;
            font-weight: 600;
        }
    </style>
</head>
<body class="h-full flex flex-col text-slate-800 bg-slate-100">

    <!-- HEADER / ENCABEZADO INSTITUCIONAL -->
    <header class="bg-brand-900 text-white shadow-lg sticky top-0 z-50">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 py-3">
            <div class="flex flex-wrap justify-between items-center gap-4">
                <div class="flex items-center space-x-3">
                    <div class="p-2 bg-brand-700 rounded-lg text-white">
                        <i class="fa-solid fa-book-open-reader text-2xl"></i>
                    </div>
                    <div>
                        <h1 class="text-xl font-bold leading-tight">I.E. Rafael Núñez <span class="text-xs bg-brand-700 text-brand-100 px-2 py-0.5 rounded-full font-normal">Sincelejo, Sucre</span></h1>
                        <p class="text-xs text-slate-300">Módulo Curricular con IA para Comprensión Lectora en Primaria (Piloto 6 Semanas)</p>
                    </div>
                </div>
                <div class="flex items-center space-x-3 text-xs bg-brand-800/80 px-3 py-2 rounded-lg border border-brand-700">
                    <div>
                        <span class="block text-slate-400">Grupo Piloto:</span>
                        <span class="font-semibold text-white">Grados 4.º y 5.º (N=36)</span>
                    </div>
                    <div class="h-8 w-px bg-brand-700"></div>
                    <div>
                        <span class="block text-slate-400">Recursos:</span>
                        <span class="font-semibold text-brand-100"><i class="fa-solid fa-laptop text-xs mr-1"></i>4 PCs / 2 Tabs</span>
                    </div>
                    <div class="h-8 w-px bg-brand-700"></div>
                    <div>
                        <span class="block text-slate-400">Conectividad:</span>
                        <span class="inline-flex items-center px-1.5 py-0.5 rounded text-xs font-medium bg-amber-500/20 text-amber-300 border border-amber-500/30">
                            <span class="w-1.5 h-1.5 mr-1 bg-amber-400 rounded-full animate-pulse"></span>
                            Intermitente (Híbrida)
                        </span>
                    </div>
                </div>
            </div>
        </div>
    </header>

    <!-- BARRA DE NAVEGACIÓN Y PESTAÑAS -->
    <nav class="bg-white shadow-sm border-b border-slate-200">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="flex space-x-8 overflow-x-auto">
                <button onclick="switchTab('caracterizacion')" id="tab-caracterizacion" class="tab-btn py-4 px-1 inline-flex items-center text-sm font-medium border-b-2 border-transparent text-slate-500 hover:text-brand-600 whitespace-nowrap tab-active">
                    <i class="fa-solid fa-school mr-2"></i> 1. Caracterización & Contexto
                </button>
                <button onclick="switchTab('diagnostico')" id="tab-diagnostico" class="tab-btn py-4 px-1 inline-flex items-center text-sm font-medium border-b-2 border-transparent text-slate-500 hover:text-brand-600 whitespace-nowrap">
                    <i class="fa-solid fa-robot mr-2"></i> 2. Diagnóstico & Análisis IA
                </button>
                <button onclick="switchTab('intervencion')" id="tab-intervencion" class="tab-btn py-4 px-1 inline-flex items-center text-sm font-medium border-b-2 border-transparent text-slate-500 hover:text-brand-600 whitespace-nowrap">
                    <i class="fa-solid fa-layer-group mr-2"></i> 3. Ruta Diferenciada
                </button>
                <button onclick="switchTab('rubrica')" id="tab-rubrica" class="tab-btn py-4 px-1 inline-flex items-center text-sm font-medium border-b-2 border-transparent text-slate-500 hover:text-brand-600 whitespace-nowrap">
                    <i class="fa-solid fa-clipboard-check mr-2"></i> 4. Rúbrica & Seguimiento
                </button>
                <button onclick="switchTab('impacto')" id="tab-impacto" class="tab-btn py-4 px-1 inline-flex items-center text-sm font-medium border-b-2 border-transparent text-slate-500 hover:text-brand-600 whitespace-nowrap">
                    <i class="fa-solid fa-chart-line mr-2"></i> 5. Panel de Impacto
                </button>
            </div>
        </div>
    </nav>

    <!-- CONTENIDO PRINCIPAL -->
    <main class="flex-1 max-w-7xl w-full mx-auto px-4 sm:px-6 lg:px-8 py-6">

        <!-- TAB 1: CARACTERIZACIÓN Y CONTEXTO INSTITUCIONAL -->
        <section id="sec-caracterizacion" class="tab-content space-y-6">
            <div class="bg-amber-50 border-l-4 border-amber-500 p-4 rounded-r-lg shadow-sm">
                <div class="flex">
                    <div class="flex-shrink-0">
                        <i class="fa-solid fa-triangle-exclamation text-amber-600 text-xl"></i>
                    </div>
                    <div class="ml-3">
                        <h3 class="text-sm font-medium text-amber-800">Regla Metodológica Central del Módulo</h3>
                        <div class="mt-1 text-sm text-amber-700">
                            <p><strong>La IA analiza y sugiere; el docente verifica, interpreta y decide.</strong> La tecnología actúa únicamente como un asistente organizador para la identificación de patrones en respuestas de comprensión lectora, manteniendo intacta la autonomía del docente.</p>
                        </div>
                    </div>
                </div>
            </div>

            <!-- Ficha de Caracterización Resumen -->
            <div class="grid grid-cols-1 md:grid-cols-3 gap-6">
                <!-- Ficha Contexto -->
                <div class="bg-white p-5 rounded-xl shadow-sm border border-slate-200 col-span-2">
                    <div class="flex items-center justify-between mb-4 border-b pb-2">
                        <h2 class="text-lg font-bold text-slate-900 flex items-center">
                            <i class="fa-solid fa-id-card text-brand-600 mr-2"></i> Ficha de Caracterización del Grupo Piloto
                        </h2>
                        <span class="text-xs font-semibold px-2.5 py-0.5 rounded bg-brand-50 text-brand-700 border border-brand-200">6 Semanas de Intervención</span>
                    </div>
                    <div class="grid grid-cols-1 sm:grid-cols-2 gap-4 text-sm">
                        <div class="p-3 bg-slate-50 rounded-lg">
                            <span class="text-xs font-semibold text-slate-500 uppercase block">Población & Edad</span>
                            <p class="font-medium text-slate-800 mt-1">Grados 4.º y 5.º de Primaria (~9 años)</p>
                            <p class="text-xs text-slate-500 mt-0.5">36 estudiantes matriculados</p>
                        </div>
                        <div class="p-3 bg-slate-50 rounded-lg">
                            <span class="text-xs font-semibold text-slate-500 uppercase block">Infraestructura Tecnológica</span>
                            <p class="font-medium text-slate-800 mt-1">4 PCs + 2 Tabletas</p>
                            <p class="text-xs text-slate-500 mt-0.5">Estrategia híbrida / offline-first con fichas impresas</p>
                        </div>
                        <div class="p-3 bg-slate-50 rounded-lg sm:col-span-2">
                            <span class="text-xs font-semibold text-slate-500 uppercase block">Características del Grupo</span>
                            <p class="text-slate-700 mt-1 text-xs leading-relaxed">
                                Grupo heterogéneo con ritmos de aprendizaje diversos. Mientras un subgrupo localiza adecuadamente información explícita, persisten dificultades notorias para realizar inferencias, estructurar la idea principal y argumentar respuestas apoyándose en evidencias textuales.
                            </p>
                        </div>
                    </div>
                </div>

                <!-- Metas e Indicadores Clave -->
                <div class="bg-white p-5 rounded-xl shadow-sm border border-slate-200">
                    <h2 class="text-lg font-bold text-slate-900 mb-4 border-b pb-2 flex items-center">
                        <i class="fa-solid fa-bullseye text-brand-600 mr-2"></i> Componentes Evaluados
                    </h2>
                    <ul class="space-y-3 text-xs">
                        <li class="flex items-start">
                            <span class="w-2 h-2 mt-1.5 bg-blue-500 rounded-full mr-2 flex-shrink-0"></span>
                            <div>
                                <strong class="text-slate-800">Localización Explícita:</strong> Identificar datos explícitos directos.
                            </div>
                        </li>
                        <li class="flex items-start">
                            <span class="w-2 h-2 mt-1.5 bg-indigo-500 rounded-full mr-2 flex-shrink-0"></span>
                            <div>
                                <strong class="text-slate-800">Inferencias & Deducción:</strong> Conectar pistas textuales para deducir implicaciones.
                            </div>
                        </li>
                        <li class="flex items-start">
                            <span class="w-2 h-2 mt-1.5 bg-purple-500 rounded-full mr-2 flex-shrink-0"></span>
                            <div>
                                <strong class="text-slate-800">Idea Principal:</strong> Distinguir la tesis central de detalles secundarios.
                            </div>
                        </li>
                        <li class="flex items-start">
                            <span class="w-2 h-2 mt-1.5 bg-teal-500 rounded-full mr-2 flex-shrink-0"></span>
                            <div>
                                <strong class="text-slate-800">Relaciones Causa-Efecto:</strong> Conectar eventos e ideas del texto.
                            </div>
                        </li>
                        <li class="flex items-start">
                            <span class="w-2 h-2 mt-1.5 bg-amber-500 rounded-full mr-2 flex-shrink-0"></span>
                            <div>
                                <strong class="text-slate-800">Justificación & Argumentación:</strong> Citar evidencias textuales válidas.
                            </div>
                        </li>
                    </ul>
                </div>
            </div>

            <!-- Fases Metodológicas -->
            <div class="bg-white p-6 rounded-xl shadow-sm border border-slate-200">
                <h3 class="text-md font-bold text-slate-900 mb-4">Secuencia Didáctica Integrada (7 Momentos)</h3>
                <div class="grid grid-cols-1 sm:grid-cols-2 md:grid-cols-4 lg:grid-cols-7 gap-3 text-center">
                    <div class="p-3 bg-brand-50 border border-brand-200 rounded-lg">
                        <div class="w-7 h-7 bg-brand-600 text-white rounded-full flex items-center justify-center font-bold text-xs mx-auto mb-2">1</div>
                        <h4 class="font-semibold text-xs text-brand-900">Diagnóstico</h4>
                        <p class="text-[10px] text-slate-500 mt-1">Prueba inicial sin IA directa</p>
                    </div>
                    <div class="p-3 bg-brand-50 border border-brand-200 rounded-lg">
                        <div class="w-7 h-7 bg-brand-600 text-white rounded-full flex items-center justify-center font-bold text-xs mx-auto mb-2">2</div>
                        <h4 class="font-semibold text-xs text-brand-900">Análisis IA</h4>
                        <p class="text-[10px] text-slate-500 mt-1">Clasificación de patrones de error</p>
                    </div>
                    <div class="p-3 bg-brand-50 border border-brand-200 rounded-lg">
                        <div class="w-7 h-7 bg-brand-600 text-white rounded-full flex items-center justify-center font-bold text-xs mx-auto mb-2">3</div>
                        <h4 class="font-semibold text-xs text-brand-900">Intervención</h4>
                        <p class="text-[10px] text-slate-500 mt-1">Rutas diferenciadas por perfil</p>
                    </div>
                    <div class="p-3 bg-brand-50 border border-brand-200 rounded-lg">
                        <div class="w-7 h-7 bg-brand-600 text-white rounded-full flex items-center justify-center font-bold text-xs mx-auto mb-2">4</div>
                        <h4 class="font-semibold text-xs text-brand-900">Práctica</h4>
                        <p class="text-[10px] text-slate-500 mt-1">Ejercitación progresiva</p>
                    </div>
                    <div class="p-3 bg-brand-50 border border-brand-200 rounded-lg">
                        <div class="w-7 h-7 bg-brand-600 text-white rounded-full flex items-center justify-center font-bold text-xs mx-auto mb-2">5</div>
                        <h4 class="font-semibold text-xs text-brand-900">Retroalimentación</h4>
                        <p class="text-[10px] text-slate-500 mt-1">Preguntas guiadas docente</p>
                    </div>
                    <div class="p-3 bg-brand-50 border border-brand-200 rounded-lg">
                        <div class="w-7 h-7 bg-brand-600 text-white rounded-full flex items-center justify-center font-bold text-xs mx-auto mb-2">6</div>
                        <h4 class="font-semibold text-xs text-brand-900">Evaluación</h4>
                        <p class="text-[10px] text-slate-500 mt-1">Prueba final equivalente</p>
                    </div>
                    <div class="p-3 bg-brand-50 border border-brand-200 rounded-lg">
                        <div class="w-7 h-7 bg-brand-600 text-white rounded-full flex items-center justify-center font-bold text-xs mx-auto mb-2">7</div>
                        <h4 class="font-semibold text-xs text-brand-900">Reflexión</h4>
                        <p class="text-[10px] text-slate-500 mt-1">Análisis pedagógico final</p>
                    </div>
                </div>
            </div>
        </section>

        <!-- TAB 2: DIAGNÓSTICO Y SIMULADOR DE ANÁLISIS IA -->
        <section id="sec-diagnostico" class="tab-content hidden space-y-6">
            <div class="bg-white p-6 rounded-xl shadow-sm border border-slate-200">
                <div class="flex justify-between items-center mb-4 pb-2 border-b">
                    <div>
                        <h2 class="text-lg font-bold text-slate-900">Simulador de Análisis de Respuestas de Estudiantes (Momento 2)</h2>
                        <p class="text-xs text-slate-500">Seleccione un estudiante o ingrese una respuesta abierta corta para clasificar con la ayuda del motor IA.</p>
                    </div>
                    <span class="text-xs bg-emerald-100 text-emerald-800 font-medium px-2.5 py-1 rounded-full border border-emerald-300">
                        <i class="fa-solid fa-user-shield mr-1"></i> Anonimización Activa (Código Interno)
                    </span>
                </div>

                <!-- Formulario / Selección -->
                <div class="grid grid-cols-1 md:grid-cols-3 gap-6">
                    <div class="space-y-4">
                        <div>
                            <label class="block text-xs font-semibold text-slate-700 mb-1">Código Estudiante (Ej. EST-401)</label>
                            <select id="select-estudiante" onchange="cargarEstudiante()" class="w-full text-sm border-slate-300 rounded-lg shadow-sm focus:border-brand-500 focus:ring-brand-500 p-2 border">
                                <option value="0">EST-401 - Carlos M. (Dificultad Inferencia)</option>
                                <option value="1">EST-402 - Ana R. (Dificultad Justificación)</option>
                                <option value="2">EST-403 - Luis G. (Dificultad Idea Principal)</option>
                                <option value="3">EST-404 - María S. (Desempeño Avanzado)</option>
                            </select>
                        </div>
                        <div>
                            <label class="block text-xs font-semibold text-slate-700 mb-1">Texto de Lectura Leído</label>
                            <input type="text" readonly value="«El viaje del manatí en las aguas del río San Jorge»" class="w-full text-xs bg-slate-100 border-slate-300 rounded-lg p-2 border text-slate-600 font-medium">
                        </div>
                        <div>
                            <label class="block text-xs font-semibold text-slate-700 mb-1">Pregunta Evaluada</label>
                            <input id="input-pregunta" type="text" readonly value="¿Por qué se afirma que el manatí ayuda a mantener limpios los ríos?" class="w-full text-xs bg-slate-100 border-slate-300 rounded-lg p-2 border text-slate-600">
                        </div>
                    </div>

                    <div class="md:col-span-2 space-y-4 flex flex-col justify-between">
                        <div>
                            <label class="block text-xs font-semibold text-slate-700 mb-1">Respuesta Abierta Registrada del Estudiante</label>
                            <textarea id="textarea-respuesta" rows="4" class="w-full text-sm border-slate-300 rounded-lg shadow-sm focus:border-brand-500 focus:ring-brand-500 p-3 border font-normal" placeholder="Escriba o modifique la respuesta..."></textarea>
                        </div>

                        <div class="flex justify-end space-x-3">
                            <button onclick="analizarConIA()" class="bg-brand-600 hover:bg-brand-700 text-white font-medium text-sm px-5 py-2.5 rounded-lg shadow transition flex items-center">
                                <i class="fa-solid fa-wand-magic-sparkles mr-2"></i> Analizar Respuesta con IA
                            </button>
                        </div>
                    </div>
                </div>

                <!-- RESULTADO DE ANÁLISIS IA (DESPLEGABLE / DINÁMICO) -->
                <div id="box-resultado-ia" class="mt-6 pt-6 border-t border-slate-200 hidden">
                    <div class="bg-slate-50 border border-slate-200 rounded-xl p-5">
                        <div class="flex items-center justify-between mb-3">
                            <div class="flex items-center space-x-2">
                                <span class="p-1.5 bg-brand-100 text-brand-700 rounded-lg text-sm">
                                    <i class="fa-solid fa-microchip"></i>
                                </span>
                                <h3 class="font-bold text-slate-800 text-sm">Resultado Preliminar de la IA</h3>
                                <span class="text-[11px] bg-amber-100 text-amber-800 font-semibold px-2 py-0.5 rounded border border-amber-300">
                                    Sugerencia IA (Pendiente Validación Docente)
                                </span>
                            </div>
                            <span id="score-ia" class="text-xs font-bold px-2.5 py-1 rounded-full bg-slate-200 text-slate-700">Dificultad Detectada</span>
                        </div>

                        <div class="grid grid-cols-1 md:grid-cols-2 gap-4 text-xs">
                            <div class="p-3 bg-white rounded-lg border border-slate-200">
                                <span class="font-semibold text-slate-500 block mb-1">Categoría Sugerida:</span>
                                <p id="categoria-ia" class="font-bold text-brand-700 text-sm">Dificultad en Inferencias & Deducción</p>
                            </div>
                            <div class="p-3 bg-white rounded-lg border border-slate-200">
                                <span class="font-semibold text-slate-500 block mb-1">Patrón de Error Observado:</span>
                                <p id="patron-ia" class="text-slate-700">El estudiante repite fragmentos literales sin establecer la relación causal implícita en el texto.</p>
                            </div>
                        </div>

                        <!-- Panel de Decisión Docente -->
                        <div class="mt-4 pt-4 border-t border-slate-200 flex flex-wrap items-center justify-between gap-3">
                            <div class="text-xs text-slate-600">
                                <i class="fa-solid fa-user-check text-brand-600 mr-1"></i>
                                <strong>Decisión Docente:</strong> ¿Desea validar la clasificación de la IA?
                            </div>
                            <div class="flex space-x-2">
                                <button onclick="validarSugerencia(false)" class="px-3 py-1.5 bg-slate-200 hover:bg-slate-300 text-slate-700 rounded-md text-xs font-medium transition">
                                    <i class="fa-solid fa-pen-to-square mr-1"></i> Modificar Criterio
                                </button>
                                <button onclick="validarSugerencia(true)" class="px-4 py-1.5 bg-emerald-600 hover:bg-emerald-700 text-white rounded-md text-xs font-medium shadow transition">
                                    <i class="fa-solid fa-check mr-1"></i> Confirmar y Asignar Ruta
                                </button>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <!-- TAB 3: MATRIZ DE INTERVENCIÓN DIFERENCIADA -->
        <section id="sec-intervencion" class="tab-content hidden space-y-6">
            <div class="bg-white p-6 rounded-xl shadow-sm border border-slate-200">
                <div class="mb-4 pb-2 border-b flex justify-between items-center">
                    <div>
                        <h2 class="text-lg font-bold text-slate-900">Matriz de Actividades Diferenciadas (Momentos 3 y 4)</h2>
                        <p class="text-xs text-slate-500">Rutas pedagógicas asignadas según el perfil de dificultad validado por el docente.</p>
                    </div>
                </div>

                <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-4">
                    <!-- Ruta 1: Localización -->
                    <div class="p-4 border rounded-xl bg-slate-50 border-slate-200 flex flex-col justify-between">
                        <div>
                            <div class="flex justify-between items-center mb-2">
                                <span class="px-2 py-0.5 rounded text-[11px] font-bold bg-blue-100 text-blue-800">Comprensión Literal</span>
                                <i class="fa-solid fa-magnifying-glass text-blue-500"></i>
                            </div>
                            <h3 class="font-bold text-slate-800 text-sm mb-1">Dificultad: Localización Explícita</h3>
                            <p class="text-xs text-slate-600 mb-3">Estudiantes con dificultad para hallar datos explícitos directos.</p>
                            <div class="bg-white p-3 rounded-lg border text-xs space-y-2">
                                <div>
                                    <strong class="text-slate-700 block">Estrategia Pedagógica:</strong>
                                    Lectura con subrayado de palabras clave y rastreo de oraciones expresas.
                                </div>
                                <div>
                                    <strong class="text-slate-700 block">Evidencia Esperada:</strong>
                                    Señala el fragmento pertinente en el texto impreso o digital.
                                </div>
                            </div>
                        </div>
                        <button class="mt-4 w-full py-2 bg-slate-800 hover:bg-slate-900 text-white text-xs font-medium rounded-lg transition">
                            Ver Guía Impresible <i class="fa-solid fa-file-pdf ml-1"></i>
                        </button>
                    </div>

                    <!-- Ruta 2: Inferencia -->
                    <div class="p-4 border rounded-xl bg-slate-50 border-slate-200 flex flex-col justify-between">
                        <div>
                            <div class="flex justify-between items-center mb-2">
                                <span class="px-2 py-0.5 rounded text-[11px] font-bold bg-indigo-100 text-indigo-800">Comprensión Inferencial</span>
                                <i class="fa-solid fa-lightbulb text-indigo-500"></i>
                            </div>
                            <h3 class="font-bold text-slate-800 text-sm mb-1">Dificultad: Inferencias & Deducción</h3>
                            <p class="text-xs text-slate-600 mb-3">Dificultad para conectar información no explícita en el texto.</p>
                            <div class="bg-white p-3 rounded-lg border text-xs space-y-2">
                                <div>
                                    <strong class="text-slate-700 block">Estrategia Pedagógica:</strong>
                                    Taller de detectives de texto: combinación de pistas y contexto.
                                </div>
                                <div>
                                    <strong class="text-slate-700 block">Evidencia Esperada:</strong>
                                    Formula una deducción coherente explicando las pistas usadas.
                                </div>
                            </div>
                        </div>
                        <button class="mt-4 w-full py-2 bg-slate-800 hover:bg-slate-900 text-white text-xs font-medium rounded-lg transition">
                            Ver Guía Impresible <i class="fa-solid fa-file-pdf ml-1"></i>
                        </button>
                    </div>

                    <!-- Ruta 3: Idea Principal -->
                    <div class="p-4 border rounded-xl bg-slate-50 border-slate-200 flex flex-col justify-between">
                        <div>
                            <div class="flex justify-between items-center mb-2">
                                <span class="px-2 py-0.5 rounded text-[11px] font-bold bg-purple-100 text-purple-800">Estructura Textual</span>
                                <i class="fa-solid fa-sitemap text-purple-500"></i>
                            </div>
                            <h3 class="font-bold text-slate-800 text-sm mb-1">Dificultad: Idea Principal</h3>
                            <p class="text-xs text-slate-600 mb-3">Confunde el tema central con detalles secundarios del relato.</p>
                            <div class="bg-white p-3 rounded-lg border text-xs space-y-2">
                                <div>
                                    <strong class="text-slate-700 block">Estrategia Pedagógica:</strong>
                                    Matriz de descarte: eliminar detalles secundarias para sintetizar.
                                </div>
                                <div>
                                    <strong class="text-slate-700 block">Evidencia Esperada:</strong>
                                    Escribe en una frase el núcleo temático central del párrafo.
                                </div>
                            </div>
                        </div>
                        <button class="mt-4 w-full py-2 bg-slate-800 hover:bg-slate-900 text-white text-xs font-medium rounded-lg transition">
                            Ver Guía Impresible <i class="fa-solid fa-file-pdf ml-1"></i>
                        </button>
                    </div>

                    <!-- Ruta 4: Justificación -->
                    <div class="p-4 border rounded-xl bg-slate-50 border-slate-200 flex flex-col justify-between">
                        <div>
                            <div class="flex justify-between items-center mb-2">
                                <span class="px-2 py-0.5 rounded text-[11px] font-bold bg-amber-100 text-amber-800">Argumentación</span>
                                <i class="fa-solid fa-quote-right text-amber-500"></i>
                            </div>
                            <h3 class="font-bold text-slate-800 text-sm mb-1">Dificultad: Argumentación/Evidencia</h3>
                            <p class="text-xs text-slate-600 mb-3">Responde con opiniones sin citar o usar datos del texto.</p>
                            <div class="bg-white p-3 rounded-lg border text-xs space-y-2">
                                <div>
                                    <strong class="text-slate-700 block">Estrategia Pedagógica:</strong>
                                    Ficha «Mi respuesta respaldada»: cita textual obligatoria entre comillas.
                                </div>
                                <div>
                                    <strong class="text-slate-700 block">Evidencia Esperada:</strong>
                                    Justifica su postura citando una frase concreta del texto.
                                </div>
                            </div>
                        </div>
                        <button class="mt-4 w-full py-2 bg-slate-800 hover:bg-slate-900 text-white text-xs font-medium rounded-lg transition">
                            Ver Guía Impresible <i class="fa-solid fa-file-pdf ml-1"></i>
                        </button>
                    </div>

                    <!-- Ruta 5: Avanzado -->
                    <div class="p-4 border rounded-xl bg-slate-50 border-slate-200 flex flex-col justify-between md:col-span-2 lg:col-span-2">
                        <div>
                            <div class="flex justify-between items-center mb-2">
                                <span class="px-2 py-0.5 rounded text-[11px] font-bold bg-emerald-100 text-emerald-800">Nivel Avanzado</span>
                                <i class="fa-solid fa-award text-emerald-500"></i>
                            </div>
                            <h3 class="font-bold text-slate-800 text-sm mb-1">Profundización Lector Autónomo</h3>
                            <p class="text-xs text-slate-600 mb-3">Estudiantes con desempeño satisfactorio que requieren mayor reto crítico.</p>
                            <div class="bg-white p-3 rounded-lg border text-xs space-y-2">
                                <div>
                                    <strong class="text-slate-700 block">Estrategia Pedagógica:</strong>
                                    Análisis comparativo de dos textos distintos sobre el mismo tema y juicio crítico sobre la intención del autor.
                                </div>
                                <div>
                                    <strong class="text-slate-700 block">Evidencia Esperada:</strong>
                                    Elabora un breve escrito argumentativo contrastando posturas.
                                </div>
                            </div>
                        </div>
                        <button class="mt-4 py-2 bg-slate-800 hover:bg-slate-900 text-white text-xs font-medium rounded-lg transition">
                            Ver Guía Impresible <i class="fa-solid fa-file-pdf ml-1"></i>
                        </button>
                    </div>
                </div>
            </div>
        </section>

        <!-- TAB 4: RÚBRICA Y FICHA DE SEGUIMIENTO INDIVIDUAL -->
        <section id="sec-rubrica" class="tab-content hidden space-y-6">
            <!-- Rúbrica Pedagógica de 4 Niveles -->
            <div class="bg-white p-6 rounded-xl shadow-sm border border-slate-200">
                <h2 class="text-lg font-bold text-slate-900 mb-3">Rúbrica Pedagógica del Módulo (Instrumento 2)</h2>
                <div class="overflow-x-auto">
                    <table class="w-full text-xs text-left border-collapse">
                        <thead>
                            <tr class="bg-slate-100 border-b border-slate-300 text-slate-700 uppercase font-semibold">
                                <th class="p-3">Criterio</th>
                                <th class="p-3 bg-red-50 text-red-800">Inicial</th>
                                <th class="p-3 bg-amber-50 text-amber-800">Básico</th>
                                <th class="p-3 bg-blue-50 text-blue-800">Satisfactorio</th>
                                <th class="p-3 bg-emerald-50 text-emerald-800">Avanzado</th>
                            </tr>
                        </thead>
                        <tbody class="divide-y divide-slate-200">
                            <tr>
                                <td class="p-3 font-bold text-slate-800 bg-slate-50">Comprensión Literal</td>
                                <td class="p-3 text-slate-600">Dificultad para localizar información explícita.</td>
                                <td class="p-3 text-slate-600">Localiza información explícita con apoyo directo.</td>
                                <td class="p-3 text-slate-600">Localiza información explícita pertinente.</td>
                                <td class="p-3 text-slate-600">Localiza y relaciona información explícita compleja.</td>
                            </tr>
                            <tr>
                                <td class="p-3 font-bold text-slate-800 bg-slate-50">Comprensión Inferencial</td>
                                <td class="p-3 text-slate-600">No logra realizar inferencias simples.</td>
                                <td class="p-3 text-slate-600">Realiza inferencias sencillas con guía.</td>
                                <td class="p-3 text-slate-600">Realiza inferencias adecuadas del texto.</td>
                                <td class="p-3 text-slate-600">Realiza inferencias y las justifica con pistas textuales.</td>
                            </tr>
                            <tr>
                                <td class="p-3 font-bold text-slate-800 bg-slate-50">Idea Principal</td>
                                <td class="p-3 text-slate-600">Confunde ideas principales y detalles secundarios.</td>
                                <td class="p-3 text-slate-600">Identifica parcialmente el núcleo temático.</td>
                                <td class="p-3 text-slate-600">Identifica correctamente la idea principal.</td>
                                <td class="p-3 text-slate-600">Explica y relaciona ideas principales del escrito.</td>
                            </tr>
                            <tr>
                                <td class="p-3 font-bold text-slate-800 bg-slate-50">Argumentación</td>
                                <td class="p-3 text-slate-600">No logra justificar sus opiniones.</td>
                                <td class="p-3 text-slate-600">Presenta justificaciones limitadas o vagas.</td>
                                <td class="p-3 text-slate-600">Justifica adecuadamente usando el texto.</td>
                                <td class="p-3 text-slate-600">Argumenta con claridad citando evidencias válidas.</td>
                            </tr>
                        </tbody>
                    </table>
                </div>
            </div>

            <!-- Ficha de Seguimiento Individual -->
            <div class="bg-white p-6 rounded-xl shadow-sm border border-slate-200">
                <div class="flex justify-between items-center mb-4">
                    <h2 class="text-lg font-bold text-slate-900">Ficha de Seguimiento Individual (Instrumento 3)</h2>
                    <span class="text-xs text-slate-500">Historial longitudinal por estudiante</span>
                </div>

                <div class="overflow-x-auto">
                    <table class="w-full text-xs text-left">
                        <thead>
                            <tr class="bg-slate-50 text-slate-600 border-b">
                                <th class="p-2">Código</th>
                                <th class="p-2">Dificultad Inicial</th>
                                <th class="p-2">Actividad Asignada</th>
                                <th class="p-2">Avance Observado</th>
                                <th class="p-2">Estado Actual</th>
                            </tr>
                        </thead>
                        <tbody class="divide-y divide-slate-100">
                            <tr>
                                <td class="p-2.5 font-bold text-brand-700">EST-401</td>
                                <td class="p-2.5"><span class="px-2 py-0.5 rounded bg-amber-100 text-amber-800 font-medium">Inferencia</span></td>
                                <td class="p-2.5">Taller "Detectives de Pistas Textuales"</td>
                                <td class="p-2.5 text-slate-600">Identifica pistas explícitas para deducir causas.</td>
                                <td class="p-2.5"><span class="px-2 py-0.5 bg-emerald-100 text-emerald-800 rounded font-bold">En Progreso Sat.</span></td>
                            </tr>
                            <tr>
                                <td class="p-2.5 font-bold text-brand-700">EST-402</td>
                                <td class="p-2.5"><span class="px-2 py-0.5 rounded bg-red-100 text-red-800 font-medium">Justificación</span></td>
                                <td class="p-2.5">Ficha "Citación Directa con Comillas"</td>
                                <td class="p-2.5 text-slate-600">Pasa de respuestas de una palabra a incluir fragmentos del texto.</td>
                                <td class="p-2.5"><span class="px-2 py-0.5 bg-blue-100 text-blue-800 rounded font-bold">En Progreso Sat.</span></td>
                            </tr>
                            <tr>
                                <td class="p-2.5 font-bold text-brand-700">EST-403</td>
                                <td class="p-2.5"><span class="px-2 py-0.5 rounded bg-purple-100 text-purple-800 font-medium">Idea Principal</span></td>
                                <td class="p-2.5">Matriz de Descarte de Detalles</td>
                                <td class="p-2.5 text-slate-600">Distingue el tema central en 3 de 4 párrafos evaluados.</td>
                                <td class="p-2.5"><span class="px-2 py-0.5 bg-emerald-100 text-emerald-800 rounded font-bold">Alcanzado</span></td>
                            </tr>
                        </tbody>
                    </table>
                </div>
            </div>
        </section>

        <!-- TAB 5: PANEL DE IMPACTO Y COMPARACIÓN ANTES VS DESPUÉS -->
        <section id="sec-impacto" class="tab-content hidden space-y-6">
            <div class="bg-white p-6 rounded-xl shadow-sm border border-slate-200">
                <div class="flex justify-between items-center mb-6 pb-2 border-b">
                    <div>
                        <h2 class="text-lg font-bold text-slate-900">Panel de Resultados y Cambio Observado (Momento 6 y 7)</h2>
                        <p class="text-xs text-slate-500">Comparación cuantitativa entre Evaluación Inicial vs Evaluación Final (Puntos Porcentuales)</p>
                    </div>
                    <span class="text-xs bg-brand-50 text-brand-700 px-3 py-1 rounded-full font-bold border border-brand-200">
                        N = 36 Estudiantes Piloto
                    </span>
                </div>

                <!-- Gráfico Chart.js + Tabla Resumen -->
                <div class="grid grid-cols-1 lg:grid-cols-2 gap-8 items-center">
                    <div class="relative w-full h-64 sm:h-80">
                        <canvas id="chartImpacto"></canvas>
                    </div>

                    <div class="space-y-4">
                        <h3 class="text-sm font-bold text-slate-800 uppercase tracking-wider">Métricas de Progresión</h3>
                        
                        <div class="overflow-x-auto">
                            <table class="w-full text-xs text-left">
                                <thead>
                                    <tr class="bg-slate-100 text-slate-700">
                                        <th class="p-2">Componente</th>
                                        <th class="p-2 text-center">Inicial</th>
                                        <th class="p-2 text-center">Final</th>
                                        <th class="p-2 text-right">Cambio Observado</th>
                                    </tr>
                                </thead>
                                <tbody class="divide-y divide-slate-200 font-medium">
                                    <tr>
                                        <td class="p-2 text-slate-800">Comprensión Literal</td>
                                        <td class="p-2 text-center text-slate-500">52%</td>
                                        <td class="p-2 text-center text-slate-800 font-bold">78%</td>
                                        <td class="p-2 text-right text-emerald-600 font-bold">+26 pts %</td>
                                    </tr>
                                    <tr>
                                        <td class="p-2 text-slate-800">Comprensión Inferencial</td>
                                        <td class="p-2 text-center text-slate-500">38%</td>
                                        <td class="p-2 text-center text-slate-800 font-bold">68%</td>
                                        <td class="p-2 text-right text-emerald-600 font-bold">+30 pts %</td>
                                    </tr>
                                    <tr>
                                        <td class="p-2 text-slate-800">Identificación Idea Principal</td>
                                        <td class="p-2 text-center text-slate-500">42%</td>
                                        <td class="p-2 text-center text-slate-800 font-bold">72%</td>
                                        <td class="p-2 text-right text-emerald-600 font-bold">+30 pts %</td>
                                    </tr>
                                    <tr>
                                        <td class="p-2 text-slate-800">Argumentación / Evidencia</td>
                                        <td class="p-2 text-center text-slate-500">30%</td>
                                        <td class="p-2 text-center text-slate-800 font-bold">60%</td>
                                        <td class="p-2 text-right text-emerald-600 font-bold">+30 pts %</td>
                                    </tr>
                                </tbody>
                            </table>
                        </div>

                        <div class="p-3 bg-brand-50 rounded-lg border border-brand-200 text-xs text-brand-900 leading-relaxed">
                            <i class="fa-solid fa-circle-info text-brand-600 mr-1"></i>
                            <strong>Nota Metodológica:</strong> El cambio observado expresa la diferencia directa entre la evaluación inicial y final. Los resultados reflejan el esfuerzo combinado de la enseñanza presencial, las guías impresas y la personalización oportuna facilitada por la IA.
                        </div>
                    </div>
                </div>
            </div>
        </section>

    </main>

    <!-- FOOTER -->
    <footer class="bg-white border-t border-slate-200 mt-auto py-4 text-center text-xs text-slate-500">
        <p>Prototipo del Módulo Curricular apoyado en IA para Comprensión Lectora | I.E. Rafael Núñez (Sincelejo, Sucre) &copy; 2026</p>
    </footer>

    <!-- JAVASCRIPT LOGIC -->
    <script>
        // Datos simulados de estudiantes
        const estudiantes = [
            {
                codigo: "EST-401",
                pregunta: "¿Por qué se afirma que el manatí ayuda a mantener limpios los ríos?",
                respuesta: "Porque el manatí es un animal grande y nada por las aguas del río San Jorge todos los días.",
                categoria: "Dificultad en Inferencias & Deducción",
                patron: "El estudiante menciona un dato literal (es grande y nada), pero no deduce la causa real expresada implícitamente (consume plantas acuáticas que tapan el flujo).",
                score: "Inferencia Incompleta"
            },
            {
                codigo: "EST-402",
                pregunta: "¿Qué evidencia del texto apoya la idea de que los manatíes están en peligro?",
                respuesta: "Porque a mí me parece que la gente los caza mucho.",
                categoria: "Dificultad en Argumentación / Justificación",
                patron: "El estudiante responde desde su opinión previa sin utilizar citas o evidencia explícita presentada en el texto leído.",
                score: "Sin Evidencia Textual"
            },
            {
                codigo: "EST-403",
                pregunta: "¿Cuál es la idea principal del segundo párrafo?",
                respuesta: "Que los ríos tienen peces de colores y muchas plantas verdes.",
                categoria: "Dificultad en Identificación de Idea Principal",
                patron: "Confunde un detalle secundario de la descripción del entorno con el tema central del párrafo.",
                score: "Detalle Secundario"
            },
            {
                codigo: "EST-404",
                pregunta: "¿Por qué el manatí es clave en el ecosistema acuático?",
                respuesta: "Porque al comer hierbas acuáticas evita que los canales se tapen, tal como dice en el párrafo 2 'limpian los cauces de manera natural'.",
                categoria: "Desempeño Satisfactorio / Avanzado",
                patron: "El estudiante conecta adecuadamente la causa con el efecto e incluye una cita textual explicativa válida.",
                score: "Respuesta Satisfactoria"
            }
        ];

        // Función para cambiar pestañas
        function switchTab(tabId) {
            document.querySelectorAll('.tab-content').forEach(el => el.classList.add('hidden'));
            document.querySelectorAll('.tab-btn').forEach(el => el.classList.remove('tab-active'));
            
            document.getElementById('sec-' + tabId).classList.remove('hidden');
            document.getElementById('tab-' + tabId).classList.add('tab-active');

            if (tabId === 'impacto') {
                renderChart();
            }
        }

        // Cargar datos del estudiante en la pestaña de diagnóstico
        function cargarEstudiante() {
            const index = document.getElementById('select-estudiante').value;
            const est = estudiantes[index];
            document.getElementById('input-pregunta').value = est.pregunta;
            document.getElementById('textarea-respuesta').value = est.respuesta;
            document.getElementById('box-resultado-ia').classList.add('hidden');
        }

        // Analizar respuesta con IA (Simulación)
        function analizarConIA() {
            const index = document.getElementById('select-estudiante').value;
            const est = estudiantes[index];

            document.getElementById('categoria-ia').textContent = est.categoria;
            document.getElementById('patron-ia').textContent = est.patron;
            document.getElementById('score-ia').textContent = est.score;

            document.getElementById('box-resultado-ia').classList.remove('hidden');
        }

        // Validar/Aprobar decisión docente
        function validarSugerencia(aprobado) {
            if (aprobado) {
                alert("¡Sugerencia validada con éxito por el docente! Se ha actualizado la ficha de seguimiento del estudiante y asignado la ruta correspondiente.");
            } else {
                alert("Modo de edición activado: Puede reasignar manualmente la categoría en la ficha de seguimiento.");
            }
        }

        // Renderizar Gráfico de Impacto con Chart.js
        let chartInstance = null;
        function renderChart() {
            const ctx = document.getElementById('chartImpacto').getContext('2d');
            
            if (chartInstance) {
                chartInstance.destroy();
            }

            chartInstance = new Chart(ctx, {
                type: 'bar',
                data: {
                    labels: ['Literal', 'Inferencial', 'Idea Principal', 'Argumentación'],
                    datasets: [
                        {
                            label: 'Evaluación Inicial (%)',
                            data: [52, 38, 42, 30],
                            backgroundColor: 'rgba(148, 163, 184, 0.7)',
                            borderColor: 'rgba(148, 163, 184, 1)',
                            borderWidth: 1,
                            borderRadius: 4
                        },
                        {
                            label: 'Evaluación Final (%)',
                            data: [78, 68, 72, 60],
                            backgroundColor: 'rgba(37, 99, 235, 0.85)',
                            borderColor: 'rgba(37, 99, 235, 1)',
                            borderWidth: 1,
                            borderRadius: 4
                        }
                    ]
                },
                options: {
                    responsive: true,
                    maintainAspectRatio: false,
                    plugins: {
                        legend: {
                            position: 'bottom'
                        },
                        title: {
                            display: true,
                            text: 'Comparación de Desempeño por Componente (%)'
                        }
                    },
                    scales: {
                        y: {
                            beginAtZero: true,
                            max: 100,
                            ticks: {
                                callback: function(value) { return value + "%"; }
                            }
                        }
                    }
                }
            });
        }

        // Cargar datos por defecto al iniciar
        window.onload = function() {
            cargarEstudiante();
        };
    </script>
</body>
</html>
