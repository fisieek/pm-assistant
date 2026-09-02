# SWOT: smartportfel-mobile

> ℹ️ Projekt przykładowy. Analiza oparta wyłącznie na repozytorium i README aplikacji, bez danych o użytkownikach. Dotyczy **wyłącznie klienta mobilnego**; pozycja produktu jako całości → [`smartportfel-web/swot.md`](../../../smartportfel-web/context/docs/swot.md).
>
> **Data:** 2026-09-01

## Mocne strony

- **Wartość produktu:** skraca drogę do wpisania wydatku (szybkie dodanie, głos, widget z akcją „Opłać"). To jedyne rzeczy, których web nie zrobi równie dobrze.
- **Przewagi:** natywne mechanizmy iOS niedostępne dla przeglądarki: widget WidgetKit, quick actions, Face ID, keychain.
- **Relacje:** ten sam backend i to samo konto co web. Zero osobnej infrastruktury.
- **Technologia:** Expo z New Architecture, testy logiki w `src/utils`, CI bez wymogu macOS, jedna zmienna do zmiany bundle id.

## Słabe strony

- **Ograniczenia:** tylko iOS. Build wymaga macOS i Xcode, więc próg wejścia dla współtwórców jest wysoki.
- **Zależności:** bez backendu aplikacja jest bezużyteczna. Widget wymaga konta Apple Developer i konfiguracji App Group.
- **Podatności:** typy API to ręczne kopie z backendu. Rozjazd wychodzi dopiero w czasie działania. Recenzja App Store spowalnia poprawki.

## Szanse

- **Trendy:** użytkownicy coraz częściej zarządzają finansami wyłącznie z telefonu; widgety i skróty systemowe stają się standardem w fintechu.
- **Okazje:** dodanie głosem i widget jako wyróżniki, które łatwo pokazać w sklepie; wersja Android jako naturalne rozszerzenie (Expo to ułatwia, ale moduły natywne trzeba przepisać).
- **Regulacje:** brak własnych integracji bankowych, więc brak dodatkowych obowiązków względem weba.
- **Partnerstwa:** TBD.

## Zagrożenia

- **Konkurencja:** aplikacje bankowe mają szybkie notowanie wydatków bliżej użytkownika, bez dodatkowej instalacji.
- **Trendy:** zmiany w Expo SDK i iOS (np. wymagania Xcode) wymuszają regularne aktualizacje niezależnie od roadmapy produktu.
- **Zasobowe:** dwa produkty na jednym backendzie i jednym autorze. Każda zmiana API to praca w dwóch repozytoriach.

---

## Wnioski

1. Pilnować spójności `src/shared-types/` z backendem przy każdej zmianie API. To najczęstsze źródło błędów w tej architekturze.
2. Rozwijać w mobile tylko to, co korzysta z bycia w kieszeni (dodanie, głos, widget). Resztę zostawić webowi.
3. Android dopiero po potwierdzeniu, że iOS ma użytkowników, bo koszt utrzymania podwaja się razem z modułami natywnymi.
