<!DOCTYPE html>
<html lang="uk">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Мій Сайт</title>
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
        nav a {
            color: white;
            text-decoration: none;
            padding: 10px 15px;
            background-color: #333;
            border-radius: 5px;
            transition: 0.3s;
        }
        nav a:hover {
            background-color: #555;
        }
        section {
            padding: 40px;
            border-bottom: 1px solid #333;
        }
        .btn {
            display: inline-block;
            padding: 10px 20px;
            margin: 10px;
            background-color: #444;
            color: white;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            transition: 0.3s;
        }
        .btn:hover {
            background-color: #666;
        }
        .menu {
            position: fixed;
            top: 20px;
            right: 20px;
            background-color: #222;
            padding: 10px;
            border-radius: 5px;
        }
        .menu button {
            background: none;
            border: none;
            color: white;
            font-size: 18px;
            cursor: pointer;
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
    </style>
</head>
<body>

    <header>
        <h1>клуб убийц</h1>
        <nav>
            <a href="#concerts">Дата концертів</a>
            <a href="#shop">Магазин</a>
            <a href="#releases">Релізи</a>
            <a href="#contacts">Контакти</a>
        </nav>
    </header>

    <section id="concerts">
        <h2>Дата концертів</h2>
        <p>Тут будуть дати твоїх концертів.</p>
    </section>

    <section id="shop">
        <h2>Магазин</h2>
        <p>Тут буде магазин із твоїми товарами.</p>
        <button class="btn">Перейти в магазин</button>
    </section>

    <section id="releases">
        <h2>Релізи</h2>
        <p>Список останніх релізів.</p>
    </section>

    <section id="contacts">
        <h2>Контакти</h2>
        <p>Email: example@email.com</p>
        <p>Телефон: +380 12 345 6789</p>
    </section>

    <div class="menu">
        <button onclick="toggleMenu()">☰</button>
        <div class="menu-content" id="menuContent">
            <a href="#">Профіль</a>
            <a href="#">Магазин</a>
            <a href="#">Техпідтримка</a>
        </div>
    </div>

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
