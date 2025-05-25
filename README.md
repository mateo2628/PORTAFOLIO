# PORTAFOLIO
<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Portafolio de Análisis de Puestos de Trabajo</title>
    <style>
        /* Estilos CSS (optimizado .modal-link para mayor claridad) */
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 0;
            background-color: #f0f4f8;
            color: #333;
        }
        header {
            background: linear-gradient(135deg, #2e7d32, #0288d1);
            color: white;
            text-align: center;
            padding: 2rem;
        }
        .sticky-nav {
            position: sticky;
            top: 0;
            background-color: #0288d1;
            padding: 1rem;
            z-index: 100;
        }
        .sticky-nav ul {
            list-style: none;
            margin: 0;
            padding: 0;
            display: flex;
            justify-content: center;
        }
        .sticky-nav li {
            margin: 0 1rem;
        }
        .sticky-nav a {
            color: white;
            text-decoration: none;
            font-weight: bold;
        }
        .sticky-nav a:hover {
            color: #ff9800;
        }
        .theme-toggle {
            background-color: #ff9800;
            color: white;
            border: none;
            padding: 0.5rem 1rem;
            cursor: pointer;
        }
        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 2rem;
        }
        .section {
            margin-bottom: 2rem;
        }
        .portada-img {
            width: 100%;
            max-width: 300px;
            height: auto;
            margin: 1rem auto;
            display: block;
        }
        .robot-img {
            width: 100%;
            max-width: 200px;
            height: auto;
            margin: 0;
        }
        .robot-container {
            display: flex;
            align-items: center;
            justify-content: center;
            margin: 1rem 0;
        }
        .speech-bubble {
            position: relative;
            background-color: white;
            color: #333;
            padding: 1rem;
            border-radius: 10px;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
            max-width: 300px;
            margin-left: 1rem;
            font-size: 0.9rem;
        }
        .speech-bubble::before {
            content: '';
            position: absolute;
            left: -10px;
            top: 50%;
            transform: translateY(-50%);
            border-width: 10px;
            border-style: solid;
            border-color: transparent white transparent transparent;
        }
        .methodology-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2rem;
        }
        .methodology-card {
            background-color: white;
            border-radius: 10px;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
        }
        .methodology-card img {
            width: 100%;
            height: 150px;
            object-fit: cover;
            border-top-left-radius: 10px;
            border-top-right-radius: 10px;
        }
        .methodology-card h3 {
            margin: 1rem;
            color: #0288d1;
        }
        .methodology-card p {
            margin: 0 1rem 1rem;
        }
        .methodology-card a {
            display: block;
            padding: 1rem;
            background-color: #2e7d32;
            color: white;
            text-align: center;
            text-decoration: none;
            border-bottom-left-radius: 10px;
            border-bottom-right-radius: 10px;
        }
        .quiz-section, .results-section {
            background-color: white;
            padding: 2rem;
            border-radius: 10px;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
        }
        .quiz-question {
            margin-bottom: 1rem;
        }
        .quiz-question select {
            width: 100%;
            max-width: 400px;
            padding: 0.5rem;
            border-radius: 5px;
            border: 1px solid #ccc;
        }
        .submit-button {
            background-color: #0288d1;
            color: white;
            border: none;
            padding: 1rem 2rem;
            cursor: pointer;
            border-radius: 5px;
        }
        .contact-section {
            text-align: center;
        }
        .social-links a {
            margin: 0 1rem;
            color: #0288d1;
            text-decoration: none;
        }
        .contact-section form {
            margin-top: 1rem;
        }
        .contact-section input, .contact-section textarea {
            display: block;
            width: 100%;
            max-width: 400px;
            margin: 0.5rem auto;
            padding: 0.5rem;
            border-radius: 5px;
            border: 1px solid #ccc;
        }
        .filter-section {
            margin-bottom: 1rem;
        }
        .filter-section select {
            padding: 0.5rem;
            border-radius: 5px;
            border: 1px solid #ccc;
        }
        .dark-mode {
            background-color: #333;
            color: white;
        }
        .dark-mode header {
            background: linear-gradient(135deg, #1b5e20, #01579b);
        }
        .dark-mode .sticky-nav {
            background-color: #01579b;
        }
        .dark-mode .methodology-card, .dark-mode .quiz-section, .dark-mode .results-section {
            background-color: #444;
        }
        .dark-mode .speech-bubble {
            background-color: #444;
            color: white;
        }
        .dark-mode .speech-bubble::before {
            border-color: transparent #444 transparent transparent;
        }
        .modal {
            display: none;
            position: fixed;
            z-index: 1000;
            left: 0;
            top: 0;
            width: 100%;
            height: 100%;
            overflow: auto;
            background-color: rgba(0,0,0,0.4);
            justify-content: center;
            align-items: center;
        }
        .modal-content {
            background-color: #fefefe;
            margin: auto;
            padding: 20px;
            border: 1px solid #888;
            width: 80%;
            max-width: 600px;
            border-radius: 10px;
        }
        .close-button {
            color: #aaa;
            float: right;
            font-size: 28px;
            font-weight: bold;
        }
        .close-button:hover,
        .close-button:focus {
            color: black;
            text-decoration: none;
            cursor: pointer;
        }
        .dark-mode .modal-content {
            background-color: #555;
            color: white;
        }
        .modal-link {
            display: block;
            margin-top: 2rem;
            color: #0288d1;
            text-decoration: none;
            font-weight: bold;
            font-size: 1.1rem;
            text-align: center;
            padding: 0.5rem;
            border-radius: 5px;
            transition: background-color 0.2s;
        }
        .modal-link:hover {
            background-color: #e3f2fd;
            text-decoration: underline;
        }
        .dark-mode .modal-link {
            color: #90caf9;
        }
        .dark-mode .modal-link:hover {
            background-color: #37474f;
        }
        footer {
            text-align: center;
            padding: 1rem;
            background-color: #e0e0e0;
        }
        .hidden {
            display: none;
        }
        .share-button {
            background-color: #ff9800;
            color: white;
            border: none;
            padding: 0.5rem 1rem;
            cursor: pointer;
            border-radius: 5px;
            margin-top: 1rem;
        }
        @media (max-width: 768px) {
            .container {
                padding: 1rem;
            }
            .methodology-grid {
                grid-template-columns: 1fr;
            }
            .sticky-nav ul {
                flex-direction: column;
                align-items: center;
            }
            .sticky-nav li {
                margin: 0.5rem 0;
            }
            .robot-container {
                flex-direction: column;
                align-items: center;
            }
            .speech-bubble {
                margin-left: 0;
                margin-top: 1rem;
                max-width: 250px;
                font-size: 0.8rem;
            }
            .speech-bubble::before {
                left: 50%;
                top: -10px;
                transform: translateX(-50%);
                border-color: transparent transparent white transparent;
            }
            .dark-mode .speech-bubble::before {
                border-color: transparent transparent #444 transparent;
            }
            .modal-content {
                width: 90%;
                padding: 15px;
            }
            .modal-link {
                font-size: 1rem;
                margin-top: 1.5rem;
            }
        }
    </style>
</head>
<body>
    <header>
        <h1>Portafolio de Análisis de Puestos de Trabajo</h1>
        <button class="theme-toggle" id="theme-toggle">Modo Oscuro</button>
    </header>

    <nav class="sticky-nav">
        <ul>
            <li><a href="#portada">Inicio</a></li>
            <li><a href="#quiz">Quiz</a></li>
            <li><a href="#metodologias">Metodologías</a></li>
            <li><a href="#contacto">Contacto</a></li>
        </ul>
    </nav>

    <div class="container">
        <section id="portada" class="section">
            <h2>Bienvenido al Portafolio de Ergonomía</h2>
            <div class="robot-container">
                <img src="https://m.media-amazon.com/images/I/51DBd7O6GEL.jpg" alt="Doctor Mateo Robot" class="robot-img">
                <div class="speech-bubble">
                    ¡Hola! Soy el Doctor Mateo, tu asistente virtual ergonómico. Estoy aquí para guiarte en la mejora de tu puesto de trabajo.
                </div>
            </div>
            <img src="https://www.quironprevencion.com/portal-client/cm/images?locale=es_ES&idMmedia=43449" alt="Análisis de Puestos de Trabajo" class="portada-img">
            <p>Haz clic para empezar el quiz y descubrir cómo optimizar tu entorno laboral.</p>
            <button id="start-quiz" class="submit-button">Iniciar Quiz</button>
            <button id="share-link" class="share-button">Compartir Portafolio</button>
            <p id="share-message" style="display: none; color: green;">¡Enlace copiado al portapapeles!</p>
        </section>

        <section id="quiz" class="quiz-section" style="display: none;">
            <h2>Quiz de Ergonomía</h2>
            <form id="quiz-form">
                <div class="quiz-question">
                    <p>1. ¿Cuántas horas al día utilizas el computador?</p>
                    <select name="q1" required>
                        <option value="" disabled selected>Selecciona una opción</option>
                        <option value="a">Menos de 2 horas</option>
                        <option value="b">2-4 horas</option>
                        <option value="c">4-6 horas</option>
                        <option value="d">Más de 6 horas</option>
                    </select>
                </div>
                <div class="quiz-question">
                    <p>2. ¿Con qué frecuencia levantas objetos pesados?</p>
                    <select name="q2" required>
                        <option value="" disabled selected>Selecciona una opción</option>
                        <option value="a">Nunca</option>
                        <option value="b">Ocasionalmente</option>
                        <option value="c">Frecuentemente</option>
                        <option value="d">Siempre</option>
                    </select>
                </div>
                <div class="quiz-question">
                    <p>3. ¿Realizas pausas activas durante tu jornada laboral?</p>
                    <select name="q5" required>
                        <option value="" disabled selected>Selecciona una opción</option>
                        <option value="a">Cada hora</option>
                        <option value="b">Cada 2-3 horas</option>
                        <option value="c">Rara vez</option>
                        <option value="d">Nunca</option>
                    </select>
                </div>
                <div class="quiz-question">
                    <p>4. ¿Sientes dolor o molestias en el cuello o espalda después de trabajar?</p>
                    <select name="q6" required>
                        <option value="" disabled selected>Selecciona una opción</option>
                        <option value="a">Nunca</option>
                        <option value="b">Ocasionalmente</option>
                        <option value="c">Frecuentemente</option>
                        <option value="d">Siempre</option>
                    </select>
                </div>
                <div class="quiz-question">
                    <p>5. ¿Tu espacio de trabajo tiene iluminación adecuada?</p>
                    <select name="q8" required>
                        <option value="" disabled selected>Selecciona una opción</option>
                        <option value="a">Sí, sin reflejos</option>
                        <option value="b">Sí, pero con reflejos</option>
                        <option value="c">No, es muy oscuro</option>
                        <option value="d">No, es muy brillante</option>
                    </select>
                </div>
                <div class="quiz-question">
                    <p>6. ¿Tu postura al sentarte mantiene los pies planos en el suelo?</p>
                    <select name="q9" required>
                        <option value="" disabled selected>Selecciona una opción</option>
                        <option value="a">Siempre</option>
                        <option value="b">A veces</option>
                        <option value="c">Rara vez</option>
                        <option value="d">Nunca</option>
                    </select>
                </div>
                <div class="quiz-question">
                    <p>7. ¿Realizas tareas que requieren movimientos repetitivos de manos o brazos?</p>
                    <select name="q10" required>
                        <option value="" disabled selected>Selecciona una opción</option>
                        <option value="a">Nunca</option>
                        <option value="b">Ocasionalmente</option>
                        <option value="c">Frecuentemente</option>
                        <option value="d">Siempre</option>
                    </select>
                </div>
                <button type="submit" class="submit-button">Enviar Respuestas</button>
            </form>
        </section>

        <section id="resultados" class="results-section" style="display: none;">
            <h2>Resultados y Recomendaciones</h2>
            <p id="recomendaciones"></p>
            <p id="metodologias-sugeridas"></p>
        </section>

        <section id="metodologias" class="section">
            <h2>Metodologías de Análisis</h2>
            <div class="filter-section">
                <label for="methodology-filter">Filtrar metodologías: </label>
                <select id="methodology-filter">
                    <option value="all">Todas</option>
                    <option value="repetitividad">Repetitividad</option>
                    <option value="carga-postural">Carga Postural</option>
                    <option value="manipulacion-cargas">Manipulación de Cargas</option>
                    <option value="puestos-oficina">Puestos de Oficina</option>
                </select>
            </div>
            <div class="methodology-grid" id="methodology-grid">
                <div class="methodology-card" data-category="repetitividad">
                    <img src="https://www.ergoibv.com/wp-content/uploads/2023/07/Metodo-Ocra-Index.jpg" alt="OCRA">
                    <h3>Checklist OCRA</h3>
                    <p>Evalúa riesgos por movimientos repetitivos de extremidades superiores.</p>
                    <a href="#" data-method="ocra">Más info</a>
                </div>
                <div class="methodology-card" data-category="carga-postural">
                    <img src="https://ergonomiaweb.com/wp-content/uploads/2018/09/RULA.png" alt="RULA">
                    <h3>RULA</h3>
                    <p>Rapid Upper Limb Assessment: Analiza posturas en tareas repetitivas o estáticas.</p>
                    <a href="#" data-method="rula">Más info</a>
                </div>
                <div class="methodology-card" data-category="carga-postural">
                    <img src="https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEh84xkrtS3M52CXcBgALDVn9zLkG6Hy-bm_yOhgSU0d9JlvrlYlKKThd1MxnBau7mC5p5LYdmUJQBXn56GWbIBeXtLdGplv7Q7uhM5xncyHvScV_UosUa0wRxWSyIVhwjROlFp_k7I4cIiJ/s1600/carga+postural.jpg" alt="REBA">
                    <h3>REBA</h3>
                    <p>Rapid Entire Body Assessment: Evalúa riesgos posturales en todo el cuerpo.</p>
                    <a href="#" data-method="reba">Más info</a>
                </div>
                <div class="methodology-card" data-category="carga-postural">
                    <img src="https://ergonomiaweb.com/wp-content/uploads/2018/09/OWAS.png" alt="OWAS">
                    <h3>OWAS</h3>
                    <p>Owako Working Posture Analysis System: Identifica posturas de trabajo perjudiciales.</p>
                    <a href="#" data-method="owas">Más info</a>
                </div>
                <div class="methodology-card" data-category="carga-postural">
                    <img src="https://0701.static.prezi.com/preview/v2/v355zl6yh2szynj4t2p2l7blu76jc3sachvcdoaizecfr3dnitcq_3_0.png" alt="EPR">
                    <h3>EPR</h3>
                    <p>Evaluación de Posturas Repetitivas: Evalúa riesgos por posturas prolongadas.</p>
                    <a href="#" data-method="epr">Más info</a>
                </div>
                <div class="methodology-card" data-category="manipulacion-cargas">
                    <img src="https://www.satirnet.com/satirnet/wp-content/uploads/2018/01/levantamiento.jpg" alt="NIOSH">
                    <h3>NIOSH</h3>
                    <p>Ecuación de Levantamiento NIOSH: Calcula riesgos en levantamiento de cargas.</p>
                    <a href="#" data-method="niosh">Más info</a>
                </div>
                <div class="methodology-card" data-category="puestos-oficina">
                    <img src="https://hse.software/wp-content/uploads/2022/09/Metodo-Rosa-SST.webp" alt="ROSA">
                    <h3>ROSA</h3>
                    <p>Rapid Office Strain Assessment: Evalúa riesgos en trabajos de oficina.</p>
                    <a href="#" data-method="rosa">Más info</a>
                </div>
                <div class="methodology-card" data-category="carga-postural">
                    <img src="https://static.docsity.com/documents_first_pages/2019/07/06/e204fe65627b9d2343655c4f634d4ade.png" alt="LEST">
                    <h3>LEST</h3>
                    <p>Método LEST: Analiza condiciones de trabajo, incluyendo carga postural.</p>
                    <a href="#" data-method="lest">Más info</a>
                </div>
                <div class="methodology-card" data-category="manipulacion-cargas">
                    <img src="https://www.auracapacitaciones.com/wp-content/uploads/2022/10/ergonomia2.jpg" alt="LCE">
                    <h3>LCE</h3>
                    <p>Límite de Carga Evaluado: Evalúa carga física en tareas dinámicas.</p>
                    <a href="#" data-method="lce">Más info</a>
                </div>
            </div>
        </section>

        <section id="contacto" class="contact-section section">
            <h2>Contacto</h2>
            <p>Síguenos en redes o envíanos un mensaje:</p>
            <div class="social-links">
                <a href="https://facebook.com" target="_blank">Facebook</a>
                <a href="https://tiktok.com" target="_blank">TikTok</a>
                <a href="https://wa.me/3127615894" target="_blank">WhatsApp</a>
            </div>
            <form>
                <input type="email" placeholder="Tu correo" required>
                <textarea placeholder="Tu mensaje" required></textarea>
                <button type="submit" class="submit-button">Enviar</button>
            </form>
        </section>
    </div>

    <footer>
        <p>© 2025 Portafolio de Ergonomía</p>
    </footer>

    <div id="methodologyModal" class="modal">
        <div class="modal-content">
            <span class="close-button">×</span>
            <h3 id="modalTitle"></h3>
            <div id="modalContent"></div>
        </div>
    </div>

    <script>
        // Data for the methodologies (enlaces editables con comentarios claros)
        const methodologiesData = {
            // Enlace para OCRA
            ocra: {
                title: "1. OCRA (Occupational Repetitive Actions)",
                description: `
                    <p>De qué habla:</p>
                    <p>El método OCRA evalúa los riesgos asociados a movimientos repetitivos de los miembros superiores, que pueden derivar en trastornos musculoesqueléticos (TMEs) como tendinitis o síndrome del túnel carpiano. La versión "Check-List OCRA" es una herramienta simplificada que permite una evaluación rápida de tareas repetitivas, analizando factores como la frecuencia de los movimientos, la fuerza ejercida, las posturas adoptadas y la duración de las tareas.</p>
                    <p>Objetivo:</p>
                    <p>Identificar y cuantificar el nivel de riesgo de TMEs en los miembros superiores debido a tareas repetitivas, proporcionando un índice numérico que refleja el grado de exposición al riesgo. Este índice ayuda a determinar si es necesario implementar medidas correctivas para reducir el riesgo.</p>
                    <p>Enfoque: </p>
                    <ul>
                        <li><strong>Observacional y semicuantitativo:</strong> Se basa en la observación de las tareas y la recopilación de datos como la frecuencia de movimientos, la fuerza aplicada, las posturas y los tiempos de recuperación.</li>
                        <li><strong>Factores evaluados:</strong> Repetitividad, fuerza, posturas incómodas, falta de pausas y factores adicionales como vibraciones o temperatura.</li>
                        <li><strong>Aplicación:</strong> Ideal para trabajos industriales.</li>
                    </ul>
                `,
                ergonautasLink: "https://www.ergonautas.upv.es/metodos/ocra/ocra-ayuda.php"
            },
            // Enlace para RULA
            rula: {
                title: "2. RULA (Rapid Upper Limb Assessment)",
                description: `
                    <p>De qué habla:</p>
                    <p>RULA es un método diseñado para evaluar los riesgos ergonómicos asociados a posturas de trabajo que afectan principalmente a los miembros superiores (cuello, hombros, brazos). Analiza posturas estáticas o repetitivas, la fuerza ejercida y la duración de las tareas para determinar el riesgo de lesiones musculoesqueléticas.</p>
                    <p>Objetivo:</p>
                    <p>Proporcionar una evaluación rápida y sistemática de los factores de riesgo postural en los miembros superiores, generando una puntuación que indica el nivel de riesgo y la necesidad de intervención ergonómica.</p>
                    <p>Enfoque: </p>
                    <ul>
                        <li><strong>Observacional:</strong> Se basa en la observación de una postura específica en un momento dado, asignando puntuaciones a diferentes partes del cuerpo (brazos, muñecas, cuello, tronco).</li>
                        <li><strong>Factores evaluados:</strong> Postura, fuerza, repetitividad y duración.</li>
                        <li><strong>Aplicación:</strong> Útil en entornos como oficinas, líneas de montaje o tareas manuales donde los movimientos repetitivos o posturas forzadas son comunes. La puntuación final indica el nivel de acción requerido (de "aceptable" a "intervención inmediata").</li>
                        <li><strong>Ventaja:</strong> Es rápido y no requiere equipo sofisticado, ideal para evaluaciones iniciales.</li>
                    </ul>
                `,
                ergonautasLink: "https://www.ergonautas.upv.es/metodos/rula/rula-ayuda.php"
            },
            // Enlace para REBA
            reba: {
                title: "3. REBA (Rapid Entire Body Assessment)",
                description: `
                    <p>De qué habla:</p>
                    <p>REBA evalúa los riesgos ergonómicos relacionados con posturas de trabajo que involucran todo el cuerpo, no solo los miembros superiores. Analiza la postura del tronco, cuello, piernas, brazos y muñecas, así como la carga manipulada y la actividad muscular.</p>
                    <p>Objetivo:</p>
                    <p>Determinar el nivel de riesgo de TMEs asociado a posturas de trabajo, proporcionando una puntuación que guía la necesidad de medidas correctivas o rediseño del puesto.</p>
                    <p>Enfoque: </p>
                    <ul>
                        <li><strong>Observacional:</strong> Similar a RULA, pero con un enfoque más amplio que incluye todo el cuerpo, no solo los miembros superiores.</li>
                        <li><strong>Factores evaluados:</strong> Posturas de diferentes segmentos corporales, carga manipulada, tipo de actividad (estática, dinámica, repetitiva) y factores adicionales como vibraciones.</li>
                        <li><strong>Aplicación:</strong> Adecuado para tareas que implican movimientos corporales completos, como levantamiento de cargas o posturas dinámicas en sectores como construcción, salud o industria.</li>
                        <li><strong>Ventaja:</strong> Proporciona una visión integral del riesgo postural en tareas complejas.</li>
                    </ul>
                `,
                ergonautasLink: "https://www.ergonautas.upv.es/metodos/reba/reba-ayuda.php"
            },
            // Enlace para OWAS
            owas: {
                title: "4. OWAS (Ovako Working Posture Analysis System)",
                description: `
                    <p>De qué habla:</p>
                    <p>OWAS es un método observacional que evalúa la carga postural global del trabajador durante la realización de una tarea, clasificando las posturas en 252 combinaciones posibles según la posición de la espalda, brazos, piernas y la carga manipulada.</p>
                    <p>Objetivo:</p>
                    <p>Evaluar el riesgo ergonómico derivado de las posturas adoptadas durante el trabajo, asignando una categoría de riesgo (de 1 a 4) para determinar si se requiere intervención.</p>
                    <p>Enfoque: </p>
                    <ul>
                        <li><strong>Observacional y global:</strong> Analiza todas las posturas adoptadas a intervalos regulares durante una tarea, no solo una postura específica.</li>
                        <li><strong>Factores evaluados:</strong> Posición de la espalda, brazos, piernas y magnitud de la carga manipulada.</li>
                        <li><strong>Aplicación:</strong> Ideal para tareas dinámicas en sectores como agricultura, construcción o manufactura, donde los trabajadores adoptan múltiples posturas.</li>
                        <li><strong>Ventaja:</strong> Su enfoque global permite evaluar el impacto acumulado de posturas durante una jornada laboral.</li>
                    </ul>
                `,
                ergonautasLink: "https://www.ergonautas.upv.es/metodos/owas/owas-ayuda.php"
            },
            // Enlace para NIOSH
            niosh: {
                title: "5. NIOSH (Ecuación de Levantamiento de Cargas del NIOSH)",
                description: `
                    <p>De qué habla:</p>
                    <p>La ecuación de NIOSH evalúa los riesgos asociados a la manipulación manual de cargas (levantamiento, descenso, transporte). Analiza factores como el peso de la carga, la distancia vertical y horizontal, la frecuencia de levantamiento y la postura del cuerpo.</p>
                    <p>Objetivo:</p>
                    <p>Calcular el índice de levantamiento (LI) para determinar si una tarea de manipulación de cargas presenta un riesgo aceptable o requiere modificaciones para reducir el riesgo de lesiones lumbares.</p>
                    <p>Enfoque: </p>
                    <ul>
                        <li><strong>Cuantitativo:</strong> Utiliza una fórmula matemática que combina factores biomecánicos, fisiológicos y psicofísicos para calcular el límite de peso recomendado (RWL) y el índice de levantamiento (LI = peso real / RWL).</li>
                        <li><strong>Factores evaluados:</strong> Peso, distancia, frecuencia, postura, agarre y duración.</li>
                        <li><strong>Aplicación:</strong> Común en almacenes, logística o industrias donde el levantamiento manual es frecuente.</li>
                        <li><strong>Ventaja:</strong> Proporciona un enfoque basado en datos para establecer límites seguros de manipulación de cargas.</li>
                    </ul>
                `,
                ergonautasLink: "https://www.ergonautas.upv.es/metodos/niosh/niosh-ayuda.php"
            },
            // Enlace para LCE (página principal, actualizar si se encuentra URL específica)
            lce: {
                title: "6. LCE (Guía Técnica de Levantamiento de Cargas del INSHT)",
                description: `
                    <p>De qué habla:</p>
                    <p>La LCE (Levantamiento de Cargas según el Instituto Nacional de Seguridad e Higiene en el Trabajo) es una guía técnica para evaluar los riesgos derivados del levantamiento manual de cargas, enfocándose en factores como el peso, la postura y la frecuencia.</p>
                    <p>Objetivo:</p>
                    <p>Identificar riesgos asociados al levantamiento de cargas y proponer medidas preventivas para minimizar lesiones musculoesqueléticas, especialmente en la zona lumbar.</p>
                    <p>Enfoque: </p>
                    <ul>
                        <li><strong>Cualitativo y semicuantitativo:</strong> Combina observación con criterios técnicos para evaluar el riesgo.</li>
                        <li><strong>Factores evaluados:</strong> Peso de la carga, postura, frecuencia, distancia de transporte y condiciones del entorno.</li>
                        <li><strong>Aplicación:</strong> Similar a NIOSH, pero con un enfoque más práctico y adaptado a normativas locales, usado en sectores industriales y de logística.</li>
                        <li><strong>Ventaja:</strong> Es más accesible para evaluadores con menos experiencia técnica que NIOSH.</li>
                    </ul>
                `,
                ergonautasLink: "https://www.ergonautas.upv.es/metodos/lce/lce-ayuda.php" // Sin página específica, usa página principal
            },
            // Enlace para LEST
            lest: {
                title: "7. LEST (Laboratoire d’Economie et de Sociologie du Travail)",
                description: `
                    <p>De qué habla:</p>
                    <p>LEST es un método global que evalúa las condiciones ergonómicas de un puesto de trabajo considerando múltiples dimensiones: entorno físico (ruido, iluminación, temperatura), carga física, carga mental, aspectos psicosociales y tiempo de trabajo. Evalúa 14 variables (en su versión simplificada en Ergonautas) para obtener una visión integral.</p>
                    <p>Objetivo:</p>
                    <p>Proporcionar un diagnóstico global de las condiciones de trabajo, identificando los factores más desfavorables para establecer prioridades de intervención ergonómica.</p>
                    <p>Enfoque: </p>
                    <ul>
                        <li><strong>Global y observacional:</strong> Analiza múltiples factores de riesgo de manera general, sin profundizar en cada uno.</li>
                        <li><strong>Factores evaluados:</strong> 14 variables agrupadas en cinco dimensiones (entorno físico, carga física, carga mental, aspectos psicosociales, tiempo de trabajo).</li>
                        <li><strong>Aplicación:</strong> Adecuado para evaluaciones iniciales en cualquier tipo de puesto de trabajo, desde oficinas hasta entornos industriales.</li>
                        <li><strong>Ventaja:</strong> Su enfoque holístico permite una visión general, aunque requiere métodos específicos para análisis más profundos.</li>
                    </ul>
                `,
                ergonautasLink: "https://www.ergonautas.upv.es/metodos/lest/lest-ayuda.php"
            },
            // Enlace para EPR (página principal, actualizar si se encuentra URL específica)
            epr: {
                title: "8. EPR (Evaluación de Puestos de Trabajo Repetitivos)",
                description: `
                    <p>De qué habla:</p>
                    <p>El método EPR se centra en evaluar los riesgos ergonómicos en tareas repetitivas, analizando factores como la frecuencia de movimientos, la postura, la fuerza aplicada y los tiempos de recuperación.</p>
                    <p>Objetivo:</p>
                    <p>Identificar y cuantificar el riesgo de trastornos musculoesqueléticos asociados a movimientos repetitivos en tareas específicas.</p>
                    <p>Enfoque:</p>
                    <ul>
                        <li><strong>Observacional y cuantitativo:</strong> Se basa en la observación directa y en la medición de la duración y frecuencia de los ciclos de trabajo y las posturas adoptadas.</li>
                        <li><strong>Factores evaluados:</strong> Repetitividad de movimientos, posturas forzadas, uso de fuerza y duración de la exposición.</li>
                        <li><strong>Aplicación:</strong> Ideal para evaluar tareas que implican ciclos de trabajo cortos y movimientos repetitivos, como en líneas de producción o embalaje.</li>
                        <li><strong>Ventaja:</strong> Proporciona una evaluación específica para tareas repetitivas, lo que ayuda a diseñar intervenciones precisas.</li>
                    </ul>
                `,
                ergonautasLink: "https://www.ergonautas.upv.es/metodos/epr/epr-ayuda.php" // Sin página específica, usa página principal
            },
            // Enlace para ROSA
            rosa: {
                title: "9. ROSA (Rapid Office Strain Assessment)",
                description: `
                    <p>De qué habla:</p>
                    <p>ROSA es una herramienta específica para evaluar el riesgo de trastornos musculoesqueléticos en <strong>puestos de trabajo de oficina</strong>. Se enfoca en la configuración ergonómica del mobiliario y equipo de oficina, como la silla, el teclado, el ratón, el monitor y el teléfono.</p>
                    <p>Objetivo:</p>
                    <p>Evaluar rápidamente la postura y el uso del equipo en entornos de oficina para identificar áreas de riesgo y proponer ajustes ergonómicos para mejorar la comodidad y prevenir lesiones.</p>
                    <p>Enfoque:</p>
                    <ul>
                        <li><strong>Observacional y checklist:</strong> Utiliza una lista de verificación con puntuaciones para diferentes componentes del puesto de trabajo.</li>
                        <li><strong>Factores evaluados:</strong> Altura y ajuste de la silla, posición del monitor, teclado, ratón, reposamuñecas, y uso del teléfono.</li>
                        <li><strong>Aplicación:</strong> Exclusivamente para puestos de trabajo con computador y tareas de oficina.</li>
                        <li><strong>Ventaja:</strong> Es un método rápido y sencillo de aplicar en entornos de oficina, permitiendo identificar rápidamente los puntos de mejora.</li>
                    </ul>
                `,
                ergonautasLink: "https://www.ergonautas.upv.es/metodos/rosa/rosa-ayuda.php"
            }
        };

        // Get the modal elements
        const modal = document.getElementById("methodologyModal");
        const modalTitle = document.getElementById("modalTitle");
        const modalContent = document.getElementById("modalContent");
        const closeButton = document.getElementsByClassName("close-button")[0];

        // When the user clicks on <span> (x), close the modal
        closeButton.onclick = function() {
            modal.style.display = "none";
        }

        // When the user clicks anywhere outside of the modal, close it
        window.onclick = function(event) {
            if (event.target == modal) {
                modal.style.display = "none";
            }
        }

        // Function to display the modal
        function showModal(methodKey) {
            const data = methodologiesData[methodKey];
            if (data) {
                modalTitle.textContent = data.title;
                modalContent.innerHTML = `
                    ${data.description}
                    <p><a href="${data.ergonautasLink}" class="modal-link" target="_blank">Más información en Ergonautas</a></p>
                `;
                modal.style.display = "flex";
            }
        }

        // Add event listeners to all "Más info" links
        document.querySelectorAll('.methodology-card a').forEach(link => {
            link.addEventListener('click', function(e) {
                e.preventDefault();
                const method = this.getAttribute('data-method');
                showModal(method);
            });
        });

        // Modo oscuro/claro
        document.getElementById('theme-toggle').addEventListener('click', function() {
            document.body.classList.toggle('dark-mode');
            this.textContent = document.body.classList.contains('dark-mode') ? 'Modo Claro' : 'Modo Oscuro';
        });

        // Iniciar quiz
        document.getElementById('start-quiz').addEventListener('click', function() {
            document.getElementById('portada').style.display = 'none';
            document.getElementById('quiz').style.display = 'block';
        });

        // Compartir enlace
        document.getElementById('share-link').addEventListener('click', function() {
            const url = window.location.href;
            navigator.clipboard.writeText(url).then(() => {
                const message = document.getElementById('share-message');
                message.style.display = 'block';
                setTimeout(() => {
                    message.style.display = 'none';
                }, 2000);
            }).catch(err => {
                console.error('Error al copiar el enlace: ', err);
                alert('No se pudo copiar el enlace. Por favor, cópialo manualmente: ' + url);
            });
        });

        // Procesar respuestas del quiz
        document.getElementById('quiz-form').addEventListener('submit', function(e) {
            e.preventDefault();
            const respuestas = {
                q1: document.querySelector('select[name="q1"]').value,
                q2: document.querySelector('select[name="q2"]').value,
                q5: document.querySelector('select[name="q5"]').value,
                q6: document.querySelector('select[name="q6"]').value,
                q8: document.querySelector('select[name="q8"]').value,
                q9: document.querySelector('select[name="q9"]').value,
                q10: document.querySelector('select[name="q10"]').value
            };

            let recomendaciones = "Te recomendamos: ";
            let metodologiasArray = [];

            // Lógica para las recomendaciones
            if (respuestas.q1 === 'c' || respuestas.q1 === 'd') {
                recomendaciones += "tomar descansos frecuentes al usar el computador y ajustar tu postura. ";
                metodologiasArray.push("ROSA", "RULA");
            } else {
                recomendaciones += "mantener una buena postura al trabajar. ";
            }

            if (respuestas.q2 === 'c' || respuestas.q2 === 'd') {
                recomendaciones += "Usar técnicas de levantamiento seguras y evaluar riesgos de carga. ";
                metodologiasArray.push("NIOSH", "LCE");
            }

            if (respuestas.q5 === 'c' || respuestas.q5 === 'd') {
                recomendaciones += "Incorpora pausas activas cada hora para reducir la fatiga. ";
                metodologiasArray.push("EPR");
            }

            if (respuestas.q6 === 'c' || respuestas.q6 === 'd') {
                recomendaciones += "Consulta a un especialista por molestias frecuentes en cuello o espalda. ";
                metodologiasArray.push("RULA", "REBA");
            }

            if (respuestas.q8 === 'b' || respuestas.q8 === 'c' || respuestas.q8 === 'd') {
                recomendaciones += "Mejora la iluminación de tu espacio para evitar reflejos o fatiga visual. ";
                metodologiasArray.push("LEST");
            }

            if (respuestas.q9 === 'b' || respuestas.q9 === 'c' || respuestas.q9 === 'd') {
                recomendaciones += "Asegúrate de que tus pies estén planos en el suelo para mantener una postura adecuada. ";
                metodologiasArray.push("REBA", "OWAS");
            }

            if (respuestas.q10 === 'c' || respuestas.q10 === 'd') {
                recomendaciones += "Evalúa los movimientos repetitivos para prevenir lesiones. ";
                metodologiasArray.push("OCRA", "RULA");
            }

            // Eliminar metodologías duplicadas
            const metodologiasUnicas = [...new Set(metodologiasArray)];
            const metodologiasTexto = metodologiasUnicas.length > 0 
                ? `Consulta las metodologías: ${metodologiasUnicas.join(', ')}.`
                : "No se sugieren metodologías específicas.";

            // Mostrar resultados
            document.getElementById('recomendaciones').textContent = recomendaciones;
            document.getElementById('metodologias-sugeridas').textContent = metodologiasTexto;
            document.getElementById('quiz').style.display = 'none';
            document.getElementById('resultados').style.display = 'block';
        });

        // Filtrar metodologías
        document.getElementById('methodology-filter').addEventListener('change', function() {
            const filterValue = this.value;
            const cards = document.querySelectorAll('.methodology-card');
            cards.forEach(card => {
                if (filterValue === 'all' || card.getAttribute('data-category') === filterValue) {
                    card.classList.remove('hidden');
                } else {
                    card.classList.add('hidden');
                }
            });
        });
    </script>
</body>
</html>
