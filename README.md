
<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<meta name="theme-color" content="#ff758c">
<title>Para Marionn 🩷</title>

<style>
:root {
    --pink: #ff4d6d;
    --dark: #c9184a;
    --light: #fff0f3;
    --text: #590d22;
}

* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
    font-family: 'Segoe UI', sans-serif;
}

body {
    min-height: 100vh;
    min-height: 100dvh;
    background: linear-gradient(135deg,
        #ffb3c1, #ff758c, #ff4d6d);
    color: var(--text);
    display: flex;
    justify-content: center;
    align-items: center;
    padding: 16px;
    overflow-x: hidden;
}

/* CORAZONES FLOTANTES */

.hearts {
    position: fixed;
    inset: 0;
    pointer-events: none;
    overflow: hidden;
    z-index: 0;
}

.heart {
    position: absolute;
    bottom: -50px;
    opacity: 0;
    animation: floatHeart linear infinite;
}

@keyframes floatHeart {
    0% {
        transform: translateY(0) rotate(0deg);
        opacity: 0;
    }
    15% { opacity: .65; }
    85% { opacity: .65; }
    100% {
        transform: translateY(-110vh) rotate(35deg);
        opacity: 0;
    }
}

/* CONTENEDORES */

.container {
    width: 100%;
    max-width: 490px;
    position: relative;
    z-index: 2;
}

/* PANTALLA DE BLOQUEO */

#lock-screen {
    background: rgba(255,255,255,.91);
    backdrop-filter: blur(15px);
    border: 2px solid white;
    border-radius: 28px;
    padding: 35px 22px;
    text-align: center;
    box-shadow: 0 15px 45px rgba(150,20,55,.22);
    animation: appear .8s ease;
}

.lock-icon {
    font-size: 65px;
    cursor: pointer;
    margin-bottom: 15px;
    user-select: none;
    transition: transform .3s;
}

.lock-icon:active {
    transform: scale(1.15);
}

h1 {
    color: var(--dark);
    font-size: 1.8rem;
    margin-bottom: 10px;
}

.subtitle {
    color: #880d1e;
    margin-bottom: 27px;
}

.countdown {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    gap: 7px;
    margin-bottom: 22px;
}

.time-box {
    background: var(--light);
    border: 1px solid #ffccd5;
    border-radius: 14px;
    padding: 12px 4px;
}

.time-box span {
    display: block;
    font-size: clamp(1.3rem, 6vw, 1.8rem);
    font-weight: 800;
    color: var(--dark);
    font-variant-numeric: tabular-nums;
}

.time-box small {
    font-size: .65rem;
    color: var(--pink);
    font-weight: bold;
    text-transform: uppercase;
}

.hint {
    font-size: .82rem;
    color: #a4133c;
    line-height: 1.5;
}

.primary-btn {
    background: var(--pink);
    color: white;
    border: none;
    padding: 12px 22px;
    border-radius: 25px;
    font-weight: bold;
    font-size: .9rem;
    margin-top: 20px;
    cursor: pointer;
}

/* PRESENTACIÓN */

#surprise-screen {
    display: none;
    width: 100%;
    background: rgba(255,255,255,.96);
    backdrop-filter: blur(15px);
    padding: 20px;
    border-radius: 27px;
    border: 2px solid white;
    box-shadow: 0 20px 50px rgba(150,20,55,.25);
    animation: appear .8s ease;
}

.top-decoration {
    text-align: center;
    font-size: 23px;
    margin-bottom: 15px;
}

/* DIAPOSITIVAS */

.slide {
    display: none;
    min-height: 340px;
    flex-direction: column;
    justify-content: center;
}

.slide.active {
    display: flex;
    animation: slideIn .45s ease;
}

.slide-card {
    background: linear-gradient(145deg, #fff0f3, #ffe5ec);
    border: 1px solid #ffccd5;
    border-radius: 21px;
    padding: 27px 19px;
    text-align: center;
    box-shadow: 0 5px 15px rgba(201,24,74,.06);
}

.slide-card h2 {
    color: var(--dark);
    font-size: 1.4rem;
    margin-bottom: 17px;
    line-height: 1.4;
}

.slide-card p {
    color: var(--text);
    font-size: 1.02rem;
    line-height: 1.85;
    overflow-wrap: anywhere;
}

.big-heart {
    font-size: 55px;
    margin-bottom: 15px;
    animation: heartbeat 1.8s infinite;
}

@keyframes heartbeat {
    0%, 100% { transform: scale(1); }
    50% { transform: scale(1.12); }
}

/* ÍNDICE */

.index-list {
    list-style: none;
    text-align: left;
}

.index-list li {
    background: white;
    border-left: 4px solid var(--pink);
    padding: 13px 12px;
    margin: 10px 0;
    border-radius: 10px;
    color: #880d1e;
    font-weight: 600;
    font-size: .91rem;
}

/* REPRODUCTOR */

.music-player {
    background: white;
    border: 1px solid #ffccd5;
    border-radius: 16px;
    padding: 17px 12px;
    margin-top: 15px;
}

.music-icon {
    font-size: 35px;
    margin-bottom: 8px;
}

.music-player strong {
    display: block;
    color: var(--dark);
    margin-bottom: 5px;
}

.music-player audio {
    width: 100%;
    margin-top: 12px;
}

.song-note {
    background: white;
    padding: 13px;
    border-radius: 12px;
    margin-top: 15px;
    font-style: italic;
    line-height: 1.7;
    font-size: .9rem;
}

/* NAVEGACIÓN */

.slide-nav {
    display: flex;
    justify-content: space-between;
    align-items: center;
    gap: 8px;
    margin-top: 20px;
}

.nav-btn {
    background: var(--pink);
    color: white;
    border: none;
    border-radius: 25px;
    padding: 12px 16px;
    font-size: .85rem;
    font-weight: bold;
    cursor: pointer;
    min-height: 44px;
    transition: .2s;
}

.nav-btn:active {
    transform: scale(.95);
}

.nav-btn:disabled {
    background: #ffccd5;
    cursor: not-allowed;
}

.slide-counter {
    font-size: .85rem;
    font-weight: bold;
    color: var(--dark);
    white-space: nowrap;
}

/* INDICADORES */

.progress {
    height: 5px;
    width: 100%;
    background: #ffe5ec;
    border-radius: 10px;
    margin-top: 17px;
    overflow: hidden;
}

.progress-bar {
    height: 100%;
    width: 11.11%;
    background: var(--pink);
    border-radius: 10px;
    transition: width .35s;
}

/* AUDIO DE FONDO */

.audio-notice {
    display: none;
    text-align: center;
    margin-top: 14px;
    font-size: .82rem;
    color: #880d1e;
}

.audio-notice button {
    background: var(--dark);
    color: white;
    border: none;
    padding: 9px 16px;
    border-radius: 20px;
    margin-top: 8px;
    font-weight: bold;
}

@keyframes appear {
    from { opacity: 0; transform: translateY(20px); }
    to { opacity: 1; transform: translateY(0); }
}

@keyframes slideIn {
    from {
        opacity: 0;
        transform: translateX(15px);
    }
    to {
        opacity: 1;
        transform: translateX(0);
    }
}

@media(max-width: 380px) {
    #surprise-screen {
        padding: 14px;
    }

    .slide {
        min-height: 320px;
    }

    .slide-card {
        padding: 22px 13px;
    }

    .nav-btn {
        padding: 11px 12px;
        font-size: .78rem;
    }
}

@media(prefers-reduced-motion: reduce) {
    *, *::before, *::after {
        animation-duration: .01ms !important;
        transition-duration: .01ms !important;
    }
}
</style>
</head>

<body>

<div class="hearts" id="hearts"></div>

<!-- AUDIO DE FONDO -->
<audio id="bg-audio" src="cancion.aac" loop preload="auto"></audio>

<div class="container">

<!-- PANTALLA DE BLOQUEO -->

<section id="lock-screen">

    <div class="lock-icon" id="secret-btn">🔒</div>

    <h1>Sorpresa en camino 🩷</h1>

    <p class="subtitle">
        Este pequeño rincón es solamente para ti. 💞
    </p>

    <div class="countdown">
        <div class="time-box">
            <span id="days">00</span>
            <small>Días</small>
        </div>

        <div class="time-box">
            <span id="hours">00</span>
            <small>Horas</small>
        </div>

        <div class="time-box">
            <span id="minutes">00</span>
            <small>Minutos</small>
        </div>

        <div class="time-box">
            <span id="seconds">00</span>
            <small>Segundos</small>
        </div>
    </div>

    <p class="hint">
        Guarda este enlace y vuelve cuando llegue el día.
        Hay algo especial esperándote. 💖
    </p>

    <button class="primary-btn" onclick="unlockSurprise()">
        🔍 Probar sorpresa
    </button>

    <p class="hint" style="margin-top:12px">
        También puedes tocar dos veces el candado.
    </p>

</section>


<!-- PRESENTACIÓN DE 9 DIAPOSITIVAS -->

<main id="surprise-screen">

    <div class="top-decoration">
        💗 ✨ 💞 ✨ 💗
    </div>


    <!-- DIAPOSITIVA 1 -->

    <section class="slide active">
        <div class="slide-card">

            <div class="big-heart">💝</div>

            <h2>Para Marionn 🩷</h2>

            <p>
                Una pequeña sorpresa hecha especialmente
                para ti, con muchísimo cariño. 💘
            </p>

            <p style="margin-top:20px">
                Porque hay personas que hacen
                que los días sean más bonitos. 💞
            </p>

        </div>
    </section>


    <!-- DIAPOSITIVA 2 -->

    <section class="slide">
        <div class="slide-card">

            <div class="big-heart">💖</div>

            <h2>¡Feliz primer mes!</h2>

            <p style="font-size:1.25rem;font-weight:bold;color:#c9184a">
                Te amo 3 millones. 💞
            </p>

            <p style="margin-top:18px">
                Un mes de momentos, sonrisas,
                recuerdos y muchas cosas bonitas
                que todavía nos quedan por vivir.
            </p>

        </div>
    </section>


    <!-- DIAPOSITIVA 3: ÍNDICE -->

    <section class="slide">
        <div class="slide-card">

            <h2>Un pequeño viaje por nosotros 💗</h2>

            <ul class="index-list">
                <li>💞 1. ¿Quién es Marionn?</li>
                <li>💖 2. ¿Cómo te conocí?</li>
                <li>💝 3. ¿Por qué me gustaste?</li>
                <li>🩷 4. ¿Por qué tú?</li>
                <li>💘 5. ¿Cuánto te amo?</li>
            </ul>

        </div>
    </section>


    <!-- DIAPOSITIVA 4 -->

    <section class="slide">
        <div class="slide-card">

            <div class="big-heart">💞</div>

            <h2>1. ¿Quién es Marionn?</h2>

            <p>
                Aquí escribe cómo la describirías,
                qué significa para ti y qué cosas
                hacen que sea una persona tan especial.
            </p>

        </div>
    </section>


    <!-- DIAPOSITIVA 5 -->

    <section class="slide">
        <div class="slide-card">

            <div class="big-heart">💖</div>

            <h2>2. ¿Cómo te conocí?</h2>

            <p>
                Cuenta cómo comenzó todo:
                aquel primer encuentro, las primeras
                conversaciones y cómo comenzó esta historia.
            </p>

        </div>
    </section>


    <!-- DIAPOSITIVA 6 -->

    <section class="slide">
        <div class="slide-card">

            <div class="big-heart">💝</div>

            <h2>3. ¿Por qué me gustaste?</h2>

            <p>
                Habla de sus detalles, su personalidad,
                sus ocurrencias, su sonrisa y esas
                pequeñas cosas que te hacen quererla.
            </p>

        </div>
    </section>


    <!-- DIAPOSITIVA 7 -->

    <section class="slide">
        <div class="slide-card">

            <div class="big-heart">🩷</div>

            <h2>4. ¿Por qué tú?</h2>

            <p>
                Explica qué hace diferente lo que
                tienes con ella, qué valoras de su
                compañía y por qué elegiste compartir
                esta historia a su lado.
            </p>

        </div>
    </section>


    <!-- DIAPOSITIVA 8 -->

    <section class="slide">
        <div class="slide-card">

            <div class="big-heart">💘</div>

            <h2>5. ¿Cuánto te amo?</h2>

            <p>
                Aquí va ese mensaje que no siempre
                resulta fácil expresar con palabras.
                Cuéntale cuánto la quieres y lo
                importante que es para ti.
            </p>

        </div>
    </section>


    <!-- DIAPOSITIVA 9: SEGUNDA CANCIÓN -->

    <section class="slide">
        <div class="slide-card">

            <div class="big-heart">🎵</div>

            <h2>Una canción para ti 💗</h2>

            <p>
                Hay sentimientos que también
                pueden expresarse a través de la música.
            </p>

            <div class="music-player">

                <div class="music-icon">🎧</div>

                <strong>Nombre de la canción</strong>

                <p style="font-size:.85rem">
                    Nombre del artista
                </p>

                <audio controls preload="metadata"
                    style="width:100%;margin-top:12px">
                    <source src="cancion2.aac" type="audio/aac">
                    Tu navegador no soporta este audio.
                </audio>

            </div>

            <div class="song-note">
                "Aquí puedes escribir un mensaje
                especial inspirado en esta canción.
                Unas palabras que solamente ustedes
                dos puedan comprender. 💞"
            </div>

        </div>
    </section>


    <!-- NAVEGACIÓN -->

    <div class="slide-nav">

        <button class="nav-btn" id="prev-btn"
            onclick="changeSlide(-1)" disabled>
            ← Anterior
        </button>

        <span class="slide-counter" id="slide-counter">
            1 / 9
        </span>

        <button class="nav-btn" id="next-btn"
            onclick="changeSlide(1)">
            Siguiente →
        </button>

    </div>

    <div class="progress">
        <div class="progress-bar" id="progress-bar"></div>
    </div>

    <div class="audio-notice" id="audio-notice">
        <p>La música está esperando tu permiso. 🎵</p>
        <button onclick="playBackgroundMusic()">
            ▶ Activar música
        </button>
    </div>

    <p style="text-align:center;font-size:.75rem;
        color:#c9184a;margin-top:15px">
        Hecho con cariño para Marionn 🩷
    </p>

</main>

</div>


<script>

/* =================================
   CONFIGURACIÓN DE FECHA
================================= */

// 28 de noviembre de 2026 a las 00:00
// Utiliza la hora local del dispositivo.

const targetDate = new Date(2026, 10, 28, 0, 0, 0).getTime();


/* =================================
   ELEMENTOS
================================= */

const lockScreen = document.getElementById("lock-screen");
const surpriseScreen = document.getElementById("surprise-screen");
const bgAudio = document.getElementById("bg-audio");

let unlocked = false;


/* =================================
   CUENTA REGRESIVA
================================= */

function updateCountdown() {

    const now = Date.now();
    const distance = targetDate - now;

    if (distance <= 0) {
        unlockSurprise();
        return;
    }

    const days = Math.floor(
        distance / (1000 * 60 * 60 * 24)
    );

    const hours = Math.floor(
        (distance % (1000 * 60 * 60 * 24)) /
        (1000 * 60 * 60)
    );

    const minutes = Math.floor(
        (distance % (1000 * 60 * 60)) /
        (1000 * 60)
    );

    const seconds = Math.floor(
        (distance % (1000 * 60)) / 1000
    );

    document.getElementById("days").textContent =
        String(days).padStart(2, "0");

    document.getElementById("hours").textContent =
        String(hours).padStart(2, "0");

    document.getElementById("minutes").textContent =
        String(minutes).padStart(2, "0");

    document.getElementById("seconds").textContent =
        String(seconds).padStart(2, "0");
}

updateCountdown();

const timer = setInterval(updateCountdown, 1000);


/* =================================
   DESBLOQUEO
================================= */

function unlockSurprise() {

    if (unlocked) return;

    unlocked = true;

    lockScreen.style.display = "none";
    surpriseScreen.style.display = "block";

    playBackgroundMusic();

    window.scrollTo({
        top: 0,
        behavior: "smooth"
    });

    clearInterval(timer);
}


/* =================================
   MÚSICA DE FONDO
================================= */

function playBackgroundMusic() {

    bgAudio.play()
        .then(() => {
            document.getElementById("audio-notice")
                .style.display = "none";
        })
        .catch(() => {
            document.getElementById("audio-notice")
                .style.display = "block";
        });
}


/* =================================
   DOBLE TOQUE EN EL CANDADO
================================= */

let lastTap = 0;

document.getElementById("secret-btn")
    .addEventListener("click", function() {

        const currentTap = Date.now();

        if (currentTap - lastTap < 450) {
            unlockSurprise();
        }

        lastTap = currentTap;
    });


/* =================================
   DIAPOSITIVAS
================================= */

let currentSlide = 0;

const slides = document.querySelectorAll(".slide");
const totalSlides = slides.length;

function updateSlideNav() {

    slides.forEach((slide, index) => {
        slide.classList.toggle(
            "active",
            index === currentSlide
        );
    });

    document.getElementById("slide-counter")
        .textContent = `${currentSlide + 1} / ${totalSlides}`;

    document.getElementById("prev-btn").disabled =
        currentSlide === 0;

    const nextBtn = document.getElementById("next-btn");

    nextBtn.textContent =
        currentSlide === totalSlides - 1
        ? "Finalizar 💕"
        : "Siguiente →";

    document.getElementById("progress-bar").style.width =
        ((currentSlide + 1) / totalSlides * 100) + "%";

}

function changeSlide(direction) {

    const next = currentSlide + direction;

    if (next < 0 || next >= totalSlides) return;

    currentSlide = next;

    updateSlideNav();

    window.scrollTo({
        top: 0,
        behavior: "smooth"
    });
}


/* =================================
   CORAZONES ANIMADOS
================================= */

const heartContainer = document.getElementById("hearts");

const heartSymbols = [
    "💗", "💖", "💕", "💘", "💝", "🩷"
];

for (let i = 0; i < 16; i++) {

    const heart = document.createElement("div");

    heart.className = "heart";

    heart.textContent =
        heartSymbols[
            Math.floor(Math.random() * heartSymbols.length)
        ];

    heart.style.left = Math.random() * 100 + "%";

    heart.style.fontSize =
        (15 + Math.random() * 17) + "px";

    heart.style.animationDuration =
        (9 + Math.random() * 10) + "s";

    heart.style.animationDelay =
        (Math.random() * 12) + "s";

    heartContainer.appendChild(heart);
}


/* INICIAR NAVEGACIÓN */

updateSlideNav();

</script>

</body>
</html>
