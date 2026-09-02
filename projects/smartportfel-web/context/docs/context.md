# Kontekst: smartportfel-web

> ℹ️ Projekt przykładowy. To realna aplikacja open source (kod publiczny na GitHubie), ale opis poniżej pochodzi z repozytorium i README, **nie zawiera danych biznesowych** (metryk, przychodów, liczby użytkowników). Pola bez danych są oznaczone `TBD`.

**Klient:** produkt własny, publiczna instancja pod adresem smartportfel.app
**Branża:** fintech / finanse osobiste
**Rynek:** Polska (interfejs, podatki, PPK, kursy NBP)
**Model:** aplikacja darmowa, kod na licencji MIT, możliwość self-hostingu. Funkcje AI na własnym kluczu użytkownika (BYOK)
**Data startu:** 12.2025
**Projekt zależny:** [`smartportfel-mobile`](../../../smartportfel-mobile/context/docs/context.md) — klient iOS korzystający z tego samego backendu

---

## Cel biznesowy

Zebrać w jednym miejscu wszystkie finanse osobiste użytkownika w Polsce, które dziś są rozproszone między bankami, brokerami, PPK i arkuszami.

## Problem użytkownika

Finanse osobiste w Polsce są rozproszone: kilka kont bankowych, rachunki maklerskie, lokaty, PPK, kredyt hipoteczny. Żadna aplikacja bankowa nie pokazuje całości, a specyfika polska (PPK, składki, kursy NBP, kalkulatory wynagrodzeń UoP/zlecenie/B2B) nie jest obsługiwana przez narzędzia zagraniczne.

## Zakres produktu (stan implementacji)

- **Wydatki i przychody:** ręcznie albo importem z CSV/XLSX, kategoryzacja, reguły sklepów
- **Konta osobiste:** salda, transfery, wielowalutowość z przeliczeniami po kursach NBP
- **Inwestycje:** portfel aktywów, wyceny w PLN, realny zysk, cena złota z NBP. Bez dostawcy notowań — ceny wpisywane ręcznie lub z wyciągu
- **Oszczędności:** cele, wpłaty, lokaty, rozliczanie odsetek
- **Kredyty hipoteczne:** harmonogramy, nadpłaty, symulacje
- **PPK:** śledzenie Pracowniczych Planów Kapitałowych
- **Budżet i planowanie:** wydatki stałe, subskrypcje, oś czasu płatności
- **Gospodarstwo domowe:** wspólne finanse dla kilku osób
- **Gamifikacja:** serie i odznaki
- **Publiczne kalkulatory:** wynagrodzeń, oszczędności, PPK, zdolności kredytowej, nadpłaty i rat kredytu
- **Serwer MCP:** dostęp do własnych danych z klienta MCP (np. Claude Desktop)
- **AI na kluczu użytkownika:** kategoryzacja transakcji, odczyt wyciągów PDF, import inwestycji, dodawanie wydatków językiem naturalnym

## Ograniczenia

- **Regulacyjne:** brak integracji z bankami przez open banking (PSD2/AIS). Dane wchodzą ręcznie lub z plików, więc produkt nie podlega licencjonowaniu jako TPP. Strony prawne (`/regulamin`, `/polityka-prywatnosci`, `/polityka-cookies`) są celowo pustymi zaślepkami do uzupełnienia przez podmiot prowadzący instancję.
- **Techniczne:** klucze AI użytkowników szyfrowane AES-256-GCM; zmiana `AI_KEY_ENCRYPTION_KEY` unieważnia wszystkie zapisane klucze. Notowania giełdowe poza zakresem repozytorium.
- **Marka:** nazwa „SmartPortfel", logo i identyfikacja wizualna nie są objęte licencją kodu.
- **Zasobowe:** TBD.

## Dostęp do kodu

- Repo: `projects/smartportfel-web/code/` — sklonuj z adresu w [`code/sample.md`](../../code/sample.md)
- Stack: React 18 + TypeScript + Vite + Tailwind (front), Node.js + Express 4 + Prisma (backend), PostgreSQL, Resend (e-mail)
- Struktura monorepo: `apps/server` (API), `apps/web` (SPA i landing), `packages/shared` (logika wspólna), `packages/contracts` (typy kontraktów API)
- Model danych: `apps/server/prisma/schema.prisma`; routing API: `apps/server/src/routes/`
- Testy i CI: `pnpm test` w obu aplikacjach, workflow w `.github/workflows/ci.yml`

## Team
Projekt rozwijany w pojedynkę.
