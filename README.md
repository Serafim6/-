<!DOCTYPE html>
<html lang="uk">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Мій сайт</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background: #111;
            color: white;
            text-align: center;
            margin: 0;
            padding: 20px;
        }

  /* ===== Меню ===== */
        .menu {
            background: #222;
            padding: 10px;
            border-radius: 10px;
            display: flex;
            justify-content: center;
            gap: 10px;
            flex-wrap: wrap;
        }
        .menu button {
            background: #333;
            color: white;
            border: none;
            padding: 10px 15px;
            font-size: 16px;
            cursor: pointer;
            border-radius: 5px;
            transition: 0.3s;
        }
        .menu button:hover {
            background: #1db954;
        }

/* ===== Музичний плеєр ===== */
        .player {
            background: #222;
            padding: 20px;
            border-radius: 10px;
            display: inline-block;
            text-align: center;
            margin-top: 20px;
        }
        .progress-bar {
            width: 100%;
            height: 5px;
            background: #444;
            margin: 10px 0;
            cursor: pointer;
        }
        .progress {
            height: 5px;
            background: #1db954;
            width: 0%;
        }
        input[type="range"] {
            width: 100px;
    }    
  /* ===== Селектор мов ===== */
        .language-selector {
            margin-top: 20px;
        }
        select {
            padding: 5px;
            font-size: 16px;
            border-radius: 5px;
        }

   /* ===== Донат ===== */
        .donate {
            margin-top: 20px;
        }
        .donate a {
            background: #ffcc00;
            color: black;
            padding: 10px 15px;
            text-decoration: none;
            font-weight: bold;
            border-radius: 5px;
            transition: 0.3s;
        }
        .donate a:hover {
            background: #ffaa00;
        }
    </style>
</head>
<body>

 <h1>🎵 Мій музичний сайт 🎵</h1>
<!-- Меню -->
    <div class="menu">
        <button onclick="goTo('home')">🏠 Головна</button>
        <button onclick="goTo('concerts')">🎤 Дата концертів</button>
        <button onclick="goTo('store')">🛒 Магазин</button>
        <button onclick="goTo('releases')">🎶 Релізи</button>
        <button onclick="goTo('contacts')">📞 Контакти</button>
        <button onclick="goTo('support')">🔧 Техпідтримка</button>
        <button onclick="goTo('profile')">👤 Профіль</button>
    </div>
 <!-- Музичний плеєр -->
    <div class="player">
        <h2 id="track-title">Трек 1</h2>
        <audio id="audio" src="спокойный вечерний плейлист #2 2.mp3"></audio>

   <div class="progress-bar" onclick="setProgress(event)">
            <div class="progress" id="progress"></div>
        </div>

 <div>
            <button onclick="prevTrack()">⏮</button>
            <button onclick="togglePlayPause()">⏯</button>
            <button onclick="nextTrack()">⏭</button>
        </div>

 <br>
        <label>🔊 Гучність: <input type="range" id="volume" min="0" max="1" step="0.1" onchange="changeVolume(this.value)"></label>
    </div>
 <!-- Вибір мови -->
    <div class="language-selector">
        <h3>🌍 Виберіть мову:</h3>
        <select id="language" onchange="changeLanguage(this.value)">
            <option value="uk">Українська</option>
            <option value="en">English</option>
            <option value="ru">Русский</option>
            <option value="de">Deutsch</option>
            <option value="fr">Français</option>
            <option value="es">Español</option>
            <!-- Додати інші мови зі списку -->
        </select>
    </div>
  <!-- Донат -->
    <div class="donate">
        <h3>❤️ Підтримати проект:</h3>
        <a href="https://www.donationalerts.com/r/tenicumerek" target="_blank">💰 Донат</a>
    </div>
 <script>
        // ======= Музичний плеєр =======
        const tracks = [
            { title: "Трек 1", src: "спокойный вечерний плейлист #2 2.mp3" },
            { title: "Трек 2", src: "track2.mp3" }, // Можна додати ще файли
            { title: "Трек 3", src: "track3.mp3" }
        ];
        let currentTrack = 0;

  const audio = document.getElementById("audio");
        const trackTitle = document.getElementById("track-title");
        const progress = document.getElementById("progress");

 function togglePlayPause() {
            if (audio.paused) {
                audio.play();
            } else {
                audio.pause();
            }
        }

 function nextTrack() {
            currentTrack = (currentTrack + 1) % tracks.length;
            loadTrack();
            audio.play();
        }

 function prevTrack() {
            currentTrack = (currentTrack - 1 + tracks.length) % tracks.length;
            loadTrack();
            audio.play();
        }

 function loadTrack() {
            audio.src = tracks[currentTrack].src;
            trackTitle.innerText = tracks[currentTrack].title;
        }

function setProgress(event) {
            const width = event.target.clientWidth;
            const clickX = event.offsetX;
            const duration = audio.duration;
            audio.currentTime = (clickX / width) * duration;
        }

function changeVolume(value) {
            audio.volume = value;
        }

audio.addEventListener("timeupdate", () => {
            const progressPercent = (audio.currentTime / audio.duration) * 100; progress.style.width
            
            
`${progressPercent}%`        });

audio.addEventListener("ended", nextTrack);

// ======= Меню =======
        function goTo(page) {
            alert("Перехід на сторінку: " + page);
        }

// ======= Зміна мови =======
        function changeLanguage(lang) {
            alert("Змінено мову на: " + lang);
        }
    </script>

</body>
</html>
