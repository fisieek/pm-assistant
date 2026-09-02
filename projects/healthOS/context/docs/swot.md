# SWOT: healthOS

> ℹ️ Projekt przykładowy. Analiza oparta wyłącznie na repozytorium i README aplikacji, bez danych rynkowych ani użytkowników. Pokazuje **format**, nie twarde wnioski biznesowe.
>
> **Data:** 2026-09-01

## Mocne strony

- **Wartość produktu:** jedno miejsce na dokumentację medyczną i dane treningowe. Większość narzędzi robi jedno albo drugie.
- **Przewagi:** dane zostają lokalnie (SQLite na dysku), bez konta i chmury. W kategorii danych medycznych to realny argument dla nieufnych użytkowników.
- **Relacje:** brak zależności od klienta czy inwestora. Autor decyduje sam.
- **Technologia:** szeroki zakres integracji (Strava, Hevy, Garmin, Colmi, Runna, Google Calendar); słowniki biomarkerów dopasowane do polskich laboratoriów; asystent AI na kluczu użytkownika, więc brak kosztu stałego po stronie projektu.

## Słabe strony

- **Ograniczenia:** brak testów automatycznych i gwarancji stabilności API. README wprost: nie nadaje się do skalowania i komercjalizacji.
- **Zależności:** wersja desktopowa tylko na macOS, build niepodpisany (ostrzeżenie systemu przy pierwszym uruchomieniu). Asystent AI zależny od jednego dostawcy (Google Gemini).
- **Podatności:** jeden autor, projekt hobbystyczny. Brak roadmapy, backlogu i procesu zgłaszania błędów poza GitHubem. Kopie zapasowe użytkownik robi sam.

## Szanse

- **Trendy:** rosnąca popularność urządzeń mierzących sen i tętno (zegarki, pierścienie) oraz zainteresowanie własnością danych zdrowotnych.
- **Okazje:** projekt jako baza do własnych wdrożeń lub nauki. README zachęca do forkowania.
- **Regulacje:** lokalne przetwarzanie danych omija większość obowiązków wynikających z chmurowego przetwarzania danych o zdrowiu.
- **Partnerstwa:** TBD.

## Zagrożenia

- **Konkurencja:** Apple Health, Google Fit i aplikacje producentów urządzeń mają dane u źródła i nie wymagają instalacji niczego dodatkowego.
- **Trendy:** zmiany API integracji (Strava, Garmin) mogą wyłączać funkcje bez udziału autora.
- **Regulacyjne:** każda funkcja interpretująca wyniki (asystent „lekarz", wskaźnik kondycji) zbliża produkt do granicy wyrobu medycznego. README broni się zastrzeżeniem, ale to obszar do pilnowania.

---

## Wnioski

1. Jeśli projekt miałby wyjść poza użytek osobisty, pierwszym krokiem są testy i podpisany build, nie nowe funkcje.
2. Granica „nie jest wyrobem medycznym" powinna być kryterium przy każdej nowej funkcji analitycznej.
3. Lokalność danych to główny wyróżnik i warto go chronić przy dodawaniu integracji.
