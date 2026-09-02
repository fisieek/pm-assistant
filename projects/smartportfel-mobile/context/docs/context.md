# Kontekst: smartportfel-mobile

> ℹ️ Projekt przykładowy. To realna aplikacja open source (kod publiczny na GitHubie). Opis pochodzi z repozytorium i README, **bez danych biznesowych**. Pola bez danych są oznaczone `TBD`.

**Klient:** produkt własny
**Branża:** fintech / finanse osobiste
**Rynek:** Polska
**Model:** klient iOS do SmartPortfela, ta sama baza użytkowników co web. Kod na licencji MIT
**Data startu:** 06.2026
**Status:** wersja 1.0.0

---

## ⚠️ Projekt zależny

**Ta aplikacja nie działa samodzielnie.** To klient, nie osobny produkt. Backend to część webowa projektu, w repozytorium [`smartportfel-web`](../../../smartportfel-web/context/docs/context.md), katalog `apps/server`.

| Co wspólne | Gdzie źródło prawdy | Konsekwencja |
|------------|---------------------|--------------|
| Backend i API | `smartportfel-web/code/`, `apps/server` | Zmiana kontraktu API dotyka obu projektów |
| Model danych | `smartportfel-web` | Mobile trzyma **kopie** typów w `src/shared-types/`, nie współdzieloną paczkę. Przy zmianie API trzeba je przenieść ręcznie |
| Konta i logowanie | `smartportfel-web` | Jedno konto, web i mobile |

**Zasada:** decyzje o modelu danych i API zapadają w `smartportfel-web`. Tutaj zapadają decyzje o tym, co i jak robi się na telefonie.

## Cel biznesowy

TBD — README nie opisuje celów komercyjnych. Cel produktowy: dostęp do finansów osobistych z telefonu, z naciskiem na szybkie działania (dodanie wydatku głosem lub z ekranu głównego, opłacenie wydatku stałego z widgetu).

## Problem użytkownika

Wydatki powstają poza domem. Aplikacja webowa wymaga otwarcia przeglądarki i zalogowania, więc wpis odkłada się na później albo nie powstaje. Klient mobilny skraca ten dystans: szybkie dodanie, dodanie głosem, widget z akcją „Opłać".

## Zakres produktu (stan implementacji)

Zakładki: **Budżet**, **Oszczędności**, **Inwestycje**, **Więcej**.

- Budżet: salda kont, łączny stan, struktura wydatków miesiąca, historia transakcji z wyszukiwarką i filtrami
- Dodawanie wydatku: formularz, szybkie dodanie (`quick-add`), dodanie głosem (`voice-add`)
- Subskrypcje i wydatki stałe: lista do opłacenia i rozliczone; zaznaczenie tworzy wydatek
- Oszczędności: konta oszczędnościowe, lokaty z odliczaniem do końca promocji, cele i transfery
- Inwestycje: portfel, konta maklerskie, dodawanie i sprzedaż pozycji
- PPK, kredyty hipoteczne z symulacją nadpłaty, gospodarstwo domowe, osiągnięcia
- Bezpieczeństwo: blokada PIN / Face ID, logowanie Google i Apple
- Widget WidgetKit z interaktywnym App Intentem „Opłać" (opcjonalny, wymaga konta Apple Developer)

## Ograniczenia

- **Platforma:** tylko iOS. Build wymaga macOS, Xcode 26.x i dev clienta (moduły natywne, nie działa w Expo Go).
- **Zależność od backendu:** bez działającej instancji serwera aplikacja zatrzymuje się na ekranie logowania. Publiczna produkcja nie jest przeznaczona do podłączania własnych buildów.
- **Cykl wydawniczy:** recenzja App Store wydłuża poprawki z godzin do dni. Build EAS wymaga zmiennych `EXPO_OWNER` i `EAS_PROJECT_ID`, bez nich celowo pada.
- **Kontrakty API:** kopie typów w `src/shared-types/` rozjeżdżają się z backendem bez ostrzeżenia w czasie kompilacji.
- **Marka:** nazwa „SmartPortfel", logo i identyfikacja wizualna nie są objęte licencją kodu.

## Dostęp do kodu

- Repo: `projects/smartportfel-mobile/code/` — sklonuj z adresu w [`code/sample.md`](../../code/sample.md)
- Stack: React Native, Expo SDK 54 (New Architecture), expo-router, TanStack Query, Sentry, Swift (widget)
- Struktura: `app/` ekrany, `components/` UI po obszarach, `context/` (Auth, Lock, Currency), `lib/` transport HTTP i keychain, `src/utils/` logika czysta z testami, `modules/widget-bridge/` i `targets/widget/` widget
- Testy i CI: `npx tsc --noEmit`, `pnpm lint`, `pnpm test`, workflow w `.github/workflows/ci.yml`

## Team

TBD — ten sam autor co `smartportfel-web`.
