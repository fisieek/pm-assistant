# Kontekst: healthOS

> ℹ️ Projekt przykładowy. To realna aplikacja open source (kod publiczny na GitHubie), ale **bez klienta, zespołu i danych biznesowych**. Opis poniżej pochodzi z repozytorium i README aplikacji. Pola bez danych są oznaczone `TBD` — tak samo wyglądałby Twój projekt tuż po założeniu.

**Klient:** brak, projekt na użytek własny
**Branża:** zdrowie i aktywność fizyczna (personal health, sport, fitness)
**Rynek:** Polska (interfejs, słowniki medyczne i nazewnictwo badań dopasowane do polskich laboratoriów)
**Model:** brak monetyzacji — open source, licencja MIT
**Data startu:** TBD
**Status:** aplikacja stabilna, użytkowana lokalnie

---

## Cel biznesowy

Narzędzie do własnego użytku, opublikowane „jako inspirację lub produkt do własnego rozwoju". README wprost zaznacza, że aplikacja powstała w całości przy użyciu AI i nie nadaje się do skalowania ani komercjalizacji.

Cel produktowy: jedno lokalne miejsce na całą historię zdrowia i aktywności użytkownika, bez konta w cudzej usłudze i bez chmury.

## Problem użytkownika

Dane o zdrowiu i aktywności są rozproszone: wyniki badań w PDF-ach, treningi w Stravie i Hevy, sen i tętno w aplikacji zegarka lub pierścienia, wizyty lekarskie w kalendarzu albo w pamięci. Nie ma jednego widoku, który łączy dokumentację medyczną z danymi treningowymi, a użytkownik nie chce oddawać danych medycznych zewnętrznej usłudze.

## Zakres produktu (stan implementacji)

Aplikacja webowa Next.js, pakowana także jako aplikacja desktopowa na macOS (Electron). Cała baza to plik SQLite na dysku użytkownika.

**Zdrowie**
- Dokumentacja medyczna: wgrywanie PDF-ów z wynikami, automatyczne wyciąganie biomarkerów i śledzenie ich w czasie
- Wizyty lekarskie ze słownikami lekarzy, placówek i części ciała
- Epizody leczenia łączące wizyty, skierowania i dokumenty w jedną oś czasu
- Skierowania z terminami ważności i przypomnieniami
- Karta stomatologiczna
- Leki i suplementy ze składem i dziennikiem przyjmowania

**Aktywność**
- Aktywności z importu (bieganie, rower, pływanie i inne)
- Treningi siłowe z podziałem na ćwiczenia, serie i partie mięśniowe
- Plany biegowe i porównanie planu z wykonaniem
- Sen, tętno, pomiary ciała, wpisy samopoczucia, nawyki z dziennikiem

**Analiza**
- Pulpit z podsumowaniem dnia i agendą zdrowotną
- Wykresy trendów dla biomarkerów i metryk, wskaźnik kondycji
- Asystent AI w dwóch rolach („lekarz", „trener") z dostępem do danych użytkownika, na kluczu API użytkownika

**Integracje (wszystkie opcjonalne):** Strava, Hevy, Garmin, Colmi R02, Runna, Google Calendar.

## Ograniczenia

- **Regulacyjne:** aplikacja przetwarza dane medyczne, ale wyłącznie lokalnie, na komputerze użytkownika. README zawiera wyraźne zastrzeżenie: to **nie jest wyrób medyczny**, nie służy do diagnozowania ani leczenia. Każda funkcja interpretująca wyniki powinna być oceniana pod kątem tej granicy.
- **Techniczne:** brak testów automatycznych i gwarancji stabilności API. Wersja desktopowa testowana tylko na macOS, build niepodpisany certyfikatem Apple. Własny skrypt migracji zamiast `prisma migrate`.
- **Prywatność:** dane wychodzą na zewnątrz tylko przez włączone integracje oraz rozmowy z asystentem AI (Google Gemini).
- **Zasobowe:** jeden autor, projekt hobbystyczny. Brak roadmapy i backlogu w repozytorium.

## Dostęp do kodu

- Repo: `projects/healthOS/code/` — sklonuj z adresu w [`code/sample.md`](../../code/sample.md)
- Stack: Next.js (App Router), React, TypeScript, Prisma + SQLite, Auth.js, Tailwind, shadcn/ui, Recharts, Vercel AI SDK + Google Gemini, Electron
- Główne obszary w kodzie: `app/zdrowie`, `app/health`, `app/activities`, `app/strength`, `app/bieg`, `app/plan`, `app/asystent`, `app/settings`; API w `app/api/*`; model danych w `prisma/schema.prisma`

## Team

TBD — projekt jednoosobowy.
