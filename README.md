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
            display: flex;
            justify-content: space-between;
            align-items: center;
        }
        nav {
            display: flex;
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
        .language-menu {
            position: relative;
            display: inline-block;
        }
        .language-menu button {
            background: none;
            border: none;
            color: white;
            font-size: 20px;
            cursor: pointer;
        }
        .language-dropdown {
            display: none;
            position: absolute;
            right: 0;
            background-color: #333;
            border-radius: 5px;
            padding: 5px;
        }
        .language-dropdown button {
            display: block;
            background: none;
            border: none;
            color: white;
            padding: 5px 10px;
            cursor: pointer;
            width: 100%;
            text-align: left;
        }
        .language-dropdown button:hover {
            background-color: #555;
        }
    </style>
</head>
<body>

  <header>
        <h1 id="site-title">Клуб убийц</h1>
        <nav>
            <a href="#concerts" id="nav-concerts">Дата концертов</a>
            <a href="#shop" id="nav-shop">Магазин</a>
            <a href="#releases" id="nav-releases">Релизы</a>
            <a href="#contacts" id="nav-contacts">Контакты</a>
        </nav>
        <div class="language-menu">
            <button onclick="toggleLanguageMenu()">🌍</button>
            <div class="language-dropdown" id="languageDropdown">
                <button onclick="changeLanguage('ru')">Русский</button>
                <button onclick="changeLanguage('uk')">Українська</button>
                <button onclick="changeLanguage('en')">English</button>
                <button onclick="changeLanguage('de')">Deutsch</button>
            </div>
        </div>
    </header>

<section id="concerts">
        <h2 id="concerts-title">Дата концертов</h2>
        <p id="concerts-text">Скоро</p>
    </section>

<section id="shop">
        <h2 id="shop-title">Магазин</h2>
        <p id="shop-text">Скоро</p>
        <button id="shop-btn">Перейти в магазин</button>
    </section>

<section id="releases">
        <h2 id="releases-title">Релизы</h2>
        <p id="releases-text">Скоро</p>
    </section>

<section id="contacts">
        <h2 id="contacts-title">Контакты</h2>
        <p>Email: <a href="mailto:ubijcklub@gmail.com" style="color: white; text-decoration: none;">ubijcklub@gmail.com</a></p>
        <p id="phone-text">Телефон: Скоро</p>
    </section>

 <script>
        function toggleLanguageMenu() {
            var menu = document.getElementById("languageDropdown");
            menu.style.display = (menu.style.display === "block") ? "none" : "block";
        }

        function changeLanguage(lang) {
            const translations = {
                ru: { title: "Клуб убийц", navConcerts: "Дата концертов", navShop: "Магазин", navReleases: "Релизы", navContacts: "Контакты", concertsTitle: "Дата концертов", concertsText: "Скоро", shopTitle: "Магазин", shopText: "Скоро", shopBtn: "Перейти в магазин", releasesTitle: "Релизы", releasesText: "Скоро", contactsTitle: "Контакты", phoneText: "Телефон: Скоро" },
                uk: { title: "Клуб убивць", navConcerts: "Дата концертів", navShop: "Магазин", navReleases: "Релізи", navContacts: "Контакти", concertsTitle: "Дата концертів", concertsText: "Скоро", shopTitle: "Магазин", shopText: "Скоро", shopBtn: "Перейти в магазин", releasesTitle: "Релізи", releasesText: "Скоро", contactsTitle: "Контакти", phoneText: "Телефон: Скоро" },
                en: { title: "Killers Club", navConcerts: "Concert Dates", navShop: "Shop", navReleases: "Releases", navContacts: "Contacts", concertsTitle: "Concert Dates", concertsText: "Coming Soon", shopTitle: "Shop", shopText: "Coming Soon", shopBtn: "Go to Shop", releasesTitle: "Releases", releasesText: "Coming Soon", contactsTitle: "Contacts", phoneText: "Phone: Coming Soon" },
                de: { title: "Mörderclub", navConcerts: "Konzerttermine", navShop: "Shop", navReleases: "Veröffentlichungen", navContacts: "Kontakt", concertsTitle: "Konzerttermine", concertsText: "Bald verfügbar", shopTitle: "Shop", shopText: "Bald verfügbar", shopBtn: "Zum Shop", releasesTitle: "Veröffentlichungen", releasesText: "Bald verfügbar", contactsTitle: "Kontakt", phoneText: "Telefon: Bald verfügbar" }
            };

            let t = translations[lang];
            document.getElementById("site-title").innerText = t.title;
            document.getElementById("nav-concerts").innerText = t.navConcerts;
            document.getElementById("nav-shop").innerText = t.navShop;
            document.getElementById("nav-releases").innerText = t.navReleases;
            document.getElementById("nav-contacts").innerText = t.navContacts;
            document.getElementById("concerts-title").innerText = t.concertsTitle;
            document.getElementById("concerts-text").innerText = t.concertsText;
            document.getElementById("shop-title").innerText = t.shopTitle;
            document.getElementById("shop-text").innerText = t.shopText;
            document.getElementById("shop-btn").innerText = t.shopBtn;
            document.getElementById("releases-title").innerText = t.releasesTitle;
            document.getElementById("releases-text").innerText = t.releasesText;
            document.getElementById("contacts-title").innerText = t.contactsTitle;
            document.getElementById("phone-text").innerText = t.phoneText;

            document.getElementById("languageDropdown").style.display = "none";
        }

        document.addEventListener("click", function(event) {
            var menu = document.getElementById("languageDropdown");
            if (!event.target.closest(".language-menu")) {
                menu.style.display = "none";
            }
        });
    </script>

</body>
</html>
