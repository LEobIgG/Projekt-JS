Obsah
Úvod
Požadavky
Instalace
Struktura Projektu
Použití
Vývoj a Nasazení
Testování
Licence
Kontakt
Úvod
Tento projekt je jednoduchá webová aplikace pro vyhledávání aut. Umožňuje uživatelům zadat název auta a zobrazit základní informace o daném voze. Projekt je určený pro výuku základů frontendového vývoje a je navržen tak, aby byl snadno pochopitelný a použitelný jako základ pro další vývoj.
Požadavky
Webový prohlížeč (doporučeno Google Chrome nebo Mozilla Firefox)
Textový editor (doporučeno Visual Studio Code)
Instalace
Klonování repozitáře
bash
Zkopírovat kód
git clone https://github.com/uzivatelske_jmeno/Projekt JS.git
cd Projekt JS
Otevření souboru main.html Otevřete soubor main.html ve svém webovém prohlížeči.
Struktura Projektu
Zkopírovat kód
Projekt JS/
├── index.html
style.css
script.js

index.html: Hlavní HTML soubor obsahující strukturu webové stránky.
style.css: CSS soubor pro stylování webové stránky.
script.js: JavaScript je zakompovaný v main.html obsahující funkce pro vyhledávání aut a zobrazení výsledků.
Použití
Otevření projektu v prohlížeči Otevřete soubor main.html ve svém webovém prohlížeči.
Vyhledávání aut
Do vyhledávacího pole zadejte název auta (např. BMW, Audi, Mercedes) a klikněte na tlačítko "Hledat".
Výsledky vyhledávání se zobrazí pod vyhledávacím formulářem.
Vývoj a Nasazení
Úpravy HTML, CSS a JavaScriptu
Pro úpravy otevřete soubory main.html, style.css ve vašem textovém editoru.
Nasazení na webový server
Nahrajte soubory main.html, style.css na svůj webový server.
Testování
Manuální testování
Otevřete soubor main.html v různých webových prohlížečích a ověřte, že vyhledávání aut funguje správně.
Ujistěte se, že všechny prvky stránky jsou správně zobrazeny a stylovány.
Licence
Tento projekt je licencován pod MIT licencí.
Kontakt
Máte-li jakékoliv dotazy nebo potřebujete pomoc, kontaktujte nás na leosek.kristek@gmail.com.

Kód HTML
html
Zkopírovat kód
<!DOCTYPE html>
<html>

<head>
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <link rel="stylesheet" type="text/css" href="./style.css">
    <script src="script.js"></script>
</head>

<body>
    <h1>Vyhledávač aut</h1>
    <form id="carSearchForm">
        <input type="text" id="searchInput" placeholder="Zadejte jedno ze tří aut">
        <button type="button" onclick="searchCars()">Hledat</button>
    </form>
    <div id="searchResults"></div>
</body>

</html>

Kód JavaScript
javascript
Zkopírovat kód
function searchCars() {
    const searchInput = document.getElementById("searchInput");
    const searchResults = document.getElementById("searchResults");
    const fakeResults = [
        { name: "BMW", parameters: "Motor: 4.4L Twin-Turbo V8, Výkon: 627 HP", photo: "bmw.jpg" },
        { name: "Audi", parameters: "Motor: 4.0L V8 TFSI, Výkon: 600 HP", photo: "audi.jpg" },
        { name: "Mercedes", parameters: "Motor: 4.0L V8 Twin-Turbo, Výkon: 604 HP", photo: "mercedes.jpg" },
    ];

    const searchQuery = searchInput.value;
    const filteredResults = fakeResults.filter(car => car.name.toLowerCase().includes(searchQuery.toLowerCase()));

    const resultsContainer = document.getElementById("searchResults");
    resultsContainer.innerHTML = "";

    filteredResults.forEach(car => {
        const resultItem = document.createElement("div");
        resultItem.classList.add("car-result");

        const carName = document.createElement("h2");
        carName.textContent = car.name;
        resultItem.appendChild(carName);

        const carParameters = document.createElement("p");
        carParameters.textContent = `Parametry: ${car.parameters}`;
        resultItem.appendChild(carParameters);

        const carPhoto = document.createElement("img");
        carPhoto.src = car.photo;
        carPhoto.alt = car.name;
        resultItem.appendChild(carPhoto);

        resultsContainer.appendChild(resultItem);
    });
}

Kód CSS
css
Zkopírovat kód
body {
    font-family: Arial, sans-serif;
}

.car-result {
    border: 1px solid #ccc;
    padding: 10px;
    margin-bottom: 10px;
}

.car-result img {
    max-width: 100%;
    height: auto;
}

Dodatečné HTML komponenty
html
Zkopírovat kód
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Vyhledávač aut</title>
</head>

<body>
    <div class="container">
        <div class="header">
            <ul class="seznam">
                <li><a href="./main.html">VYHLEDÁVAČ</a></li>
                <li><a href="./hodina4.html">MERCEDES E63S</a></li>
                <li><a href="./index.html">BMW M5 COMP</a></li>
                <li><a href="./float.html">AUDI RS6 AVANT</a></li>
            </ul>
        </div>
        <div class="imgback main_img"></div>
        <h1></h1>
        <footer>
            <p>Author: Leoš Křístek</p>
            <p><a href="mailto:hege@example.com">leosek.kristek@gmail.com</a></p>
        </footer>
    </div>
</body>

</html>

