<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Клуб убийц</title>
    <style>
        body {
            background-color: #111;
            color: white;
            font-family: Arial, sans-serif;
            text-align: center;
            margin: 0;
            padding: 0;
        }
        header {
            background-color: #222;
            padding: 20px;
        }
        nav {
            display: flex;
            justify-content: center;
            gap: 20px;
        }
        nav a, .btn, .menu button {
            color: white;
            text-decoration: none;
            padding: 10px 15px;
            background-color: #333;
            border-radius: 5px;
            transition: 0.3s;
            border: none;
            cursor: pointer;
        }
        nav a:hover, .btn:hover, .menu button:hover {
            background-color: #555;
        }
        section {
            padding: 40px;
            border-bottom: 1px solid #333;
        }
        .menu {
            position: fixed;
            top: 20px;
            right: 20px;
            background-color: #222;
            padding: 10px;
            border-radius: 5px;
        }
        .menu-content {
            display: none;
            background-color: #333;
            padding: 10px;
            position: absolute;
            right: 0;
            top: 30px;
            width: 150px;
            border-radius: 5px;
        }
        .menu-content a {
            display: block;
            color: white;
            text-decoration: none;
            padding: 5px 0;
        }
        .menu-content a:hover {
            background-color: #444;
        }
        .player {
            margin-top: 20px;
        }
        select {
            padding: 10px;
            border-radius: 5px;
            border: none;
            background: #333;
            color: white;
            cursor: pointer;
        }
    </style>
</head>
<body>

 <header>
        <h1>Клуб убийц</h1>
        <nav>
            <a href="#concerts">Дата концертів</a>
            <a href="#shop">Магазин</a>
            <a href="#releases">Релізи</a>
            <a href="#contacts">Контакти</a>
        </nav>
    </header>

 <section id="concerts">
        <h2>Дата концертів</h2>
        <p>Скоро</p>
    </section>

<section id="shop">
        <h2>Магазин</h2>
        <p>Скоро</p>
        <button class="btn">Перейти в магазин</button>
    </section>

 <section id="releases">
        <h2>Релізи</h2>
        <p>Скоро</p>
    </section>

 <section id="contacts">
        <h2>Контакти</h2>
        <p>Email: <a href="mailto:ubijcklub@gmail.com" style="color: white; text-decoration: none;">ubijcklub@gmail.com</a></p>
        <p>Телефон: Скоро</p>
    </section>

 <div class="menu">
        <button onclick="toggleMenu()">☰</button>
        <div class="menu-content" id="menuContent">
            <a href="#">Профіль</a>
            <a href="#">Магазин</a>
            <a href="#">Техпідтримка</a>
        </div>
    </div>

<section>
        <h2>Музичний плеєр</h2>
        <audio controls class="player">
            <source src="спокойный вечерний плейлист #2 2.mp3" type="audio/mpeg">
            Ваш браузер не підтримує аудіо.
        </audio>
    </section>

 <section>
        <h2>Вибір мови</h2>
        <select id="language">
            <option>Англійська</option>
            <option>Українська</option>
            <option>Російська</option>
            <option>Французька</option>
            <option>Іспанська</option>
            <option>Німецька</option>
            <option>Італійська</option>
            <option>Китайська</option>
            <option>Японська</option>
            <option>КореЙська</option>
  <!-- Додай ще інші мови, якщо потрібно -->
        </select>
    </section>

 <section>
        <h2>Вибір країни проживання</h2>
        <select id="country">
            <option>Україна</option>
            <option>США</option>
            <option>Велика Британія</option>
            <option>Канада</option>
            <option>Німеччина</option>
            <option>Франція</option>
            <option>Іспанія</option>
            <option>Китай</option>
            <option>Японія</option>
            <option>Корея</option>
            <!-- Додай ще країни, якщо потрібно -->
        </select>
    </section>

 <script>
        function toggleMenu() {
            var menu = document.getElementById("menuContent");
            if (menu.style.display === "block") {
                menu.style.display = "none";
            } else {
                menu.style.display = "block";
            }
        }
    </script>

</body>
</html>
