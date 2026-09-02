# Przykładowe projekty

> ## ⚠️ W folderze **projects** znajdują się trzy **przykładowe projekty**. To moje realne aplikacje open source, zbudowane z pomocą AI (kod jest publiczny na GitHubie, linki w `code/sample.md`). Dokumentacja w `context/` jest wypełniona tylko częściowo (`context.md`, `swot.md`) i nie zawiera żadnych danych biznesowych — służy wyłącznie jako demonstracja struktury.
>
> Stwórz własny podział na projekty, nad którymi pracujesz. Każdy folder to osobny projekt.

---

## Struktura

```
projects/<nazwa-projektu>/
├── context/
│   ├── docs/
│   │   ├── context.md      kontekst projektu — zacznij tutaj
│   │   ├── team.md         kto jest kim w zespole, jak się komunikujemy
│   │   ├── glossary.md     terminologia używana w projekcie, specyficzna dla branży klienta
│   │   ├── roadmap.md      co, kiedy, dlaczego w tej kolejności
│   │   ├── prd.md          zakres bieżącej wersji
│   │   ├── swot.md         pozycja produktu na rynku
│   │   ├── users.md        persony użytkowników (tworzy skill /users)
│   │   └── podsumowanie-warsztatow.md   raport z warsztatów discovery (tworzy skill /pd-workshops)
│   ├── design/             makiety, linki do Figmy
│   └── meetings/           notatki i transkrypcje: YYYY-MM-DD-temat.md, YYYY-MM-DD-temat-transkrypcja.md
└── code/                   kod aplikacji, do wglądu i zrozumienia działania funkcjonalności
```

Powyższa struktura pozwala na zachowanie szczegółowych informacji o projekcie. Dzięki temu nie musisz w każdej sesji tłumaczyć branży, produktu i występujących zależności, tylko rozpoczynasz wiedząc, że Twój PM-Assistant zna kontekst. Ale po kolei.

- **Context** - krótki opis klienta, branży, problemu, który rozwiązujesz, globalnej wizji.
- **PRD** - serce systemu, dokładny opis Twojego produktu (lub aktualnej wersji, nad którą pracujesz), wymagań biznesowych. Idealnie, gdyby znalazło się tam wszystko, co pojawiło się podczas procesu discovery, zarówno podczas rozmów z klientem, jak i podczas analizy rynku.
- **Roadmap** - cele i wizja produktu na kolejne miesiące i lata. Otwiera szerszy kontekst dla asystenta.
- **SWOT** - krótka analiza SWOT, która daje dodatkową wartość przy ocenie potencjalnych rozwiązań.
- **Glossary** - szczególnie ważny plik dla projektów w niszowych branżach, które wymagają uszczegółowienia. Warto zawrzeć wszystkie słówka, których używacie w projekcie wraz z krótkim wyjaśnieniem, by nie trzeba było za każdym razem opisowo tłumaczyć, co masz na myśli.
- **Team** - dodatkowy plik, w którym opisujesz dla asystenta swój zespół, czy osoby od strony klienta. Warto dla lepszego zrozumienia zależności.
- **Users** - persony użytkowników z bólami, potrzebami i celami. Powstaje z materiałów z warsztatów i wywiadów.
- **Design** - folder, który możesz traktować jako wizualny kontekst dla asystenta.
- **Meetings** - folder z plikami, w których znajdują się transkrypcje lub podsumowania spotkań. Przydatne, gdy chcesz na ich podstawie przedyskutować potencjalne rozwiązania lub upewnić się, że w ten sam sposób rozumiesz wymagania biznesowe. Konwencja nazw: transkrypcja `YYYY-MM-DD-temat-transkrypcja.md`, notatka ze spotkania `YYYY-MM-DD-temat.md`, notatka przygotowana przed sprint review `YYYY-MM-DD-sprint-review-przygotowanie.md`. Dzięki temu skille nie nadpisują sobie nawzajem plików.
- **Code** - dla każdego projektu zakładam dostęp do kodu. Nareszcie my, produktowcy, mamy w rękach narzędzie pozwalające nam, poprzez rozmowy z np. Claude, omówić i przygotować potencjalne rozwiązania i dobudowywać prototypy funkcjonalności do istniejącej wersji. Folder jest ignorowany przez git — sklonuj do niego repo aplikacji (np. do `code/app/`), a w `code/sample.md` zostaw link i wskazówkę, od czego zacząć czytanie.

Jak widzisz, lista jest dość długa, ale uzupełnienie jej na początku daje Ci pewność, że Twój PM-Assistant podąża za Tobą i jest w tym samym miejscu projektu, co Ty.
Nie musisz wypełniać wszystkich plików i folderów, to od Ciebie zależy, jak dużo elementów przekażesz asystentowi. Puste miejsca oznaczaj jako `TBD`.

Skill, który tworzy nowy projekt z folderami i plikami na start → `/new-project`.
