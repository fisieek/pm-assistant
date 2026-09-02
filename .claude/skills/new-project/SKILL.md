---
name: new-project
description: Stwórz nowy projekt w tej przestrzeni w folderze /projects. Weź pod uwagę strukturę tj. foldery i pliki, które powinny zostać utworzone automatycznie w folderze głównym projektu. Nazwa folderu głównego projektu powinna być tożsama z nazwą projektu.
---

# Nowy projekt - Onboarding

## Cel   
SKILL stanowi proces tworzenia projektu w tej przestrzeni. 
Cel: Użytkownik od razu po informacji o nowym kliencie powinien za pomocą tego skilla otrzymać pełną strukturę projektową, w której może uzupełniać informacje o kliencie, branży, czy produkcie i jego wymaganiach. 
## Zadanie   
Zanim założysz foldery, zadaj pytania użytkownikowi, które pozwolą Ci zrozumienie podstaw: 

- [ ] Nazwa projektu 
- [ ] Nazwa klienta - nazwa firmy lub imię i nazwisko klienta 
- [ ] Branża - podpowiedz te z `AGENTS.md`, jeśli inna, poproś o wskazanie
- [ ] Rynek - podpowiedz te z `AGENTS.md`, jeśli inny, poproś o wskazanie
- [ ] Zakres projektu - aplikacja webowa, mobilna, landing page (jeśli inny, wskaż jaki)
- [ ] Główny problem, który to narzędzie rozwiązuje
- [ ] Cel biznesowy 
- [ ] Role użytkowników
- [ ] Zespół 
- [ ] Szacowana data startu i końca obecnej fazy projektu 

Jeśli użytkownik nie odpowie na wszystkie pytania (może nie mieć wiedzy, projekt może być na wczesnym etapie), to i tak stwórz pełen zakres projektu, pełną strukturę. W pustych plikach, dla których nie masz informacji zapisz tylko jedno słowo "TBD", nic więcej. 

---

## Struktura folderów

```
projects/<nazwa-projektu>/
├── context/
│   ├── docs/
│   │   ├── context.md      ← zacznij tutaj
│   │   ├── team.md
│   │   ├── glossary.md
│   │   ├── roadmap.md
│   │   ├── prd.md
│   │   ├── swot.md
│   │   └── users.md
│   ├── design/             makiety, linki do Figmy
│   └── meetings/           notatki: YYYY-MM-DD-temat.md, transkrypcje: YYYY-MM-DD-temat-transkrypcja.md
└── code/
    └── sample.md           link do repo aplikacji i wskazówka, od czego zacząć czytanie
```

Foldery `design/` i `meetings/` utwórz z pustym plikiem `.gitkeep`, inaczej nie trafią do gita. W `code/sample.md` zapisz nazwę projektu i miejsce na link do repozytorium (`TBD`, jeśli go jeszcze nie ma). Zawartość `code/` poza `sample.md` jest ignorowana przez git.

Pełny opis znajduje się w pliku → [`projects/README.md`](../../../projects/README.md).

### `context.md` — szkielet

```markdown
# Kontekst: [Nazwa Projektu]

**Klient:** · **Branża:** · **Rynek:**
**Data startu:** · **Szacowany koniec obecnej wersji:**

## Cel biznesowy
[Co klient chce osiągnąć — biznesowo, nie technicznie]

## Problem użytkownika
[Jaki problem rozwiązujemy dla end-userów]

## Ograniczenia
- Czasowe: · Budżetowe: · Regulacyjne: · Techniczne:

## Team
- Tech Lead: · UX/UI: · Dev:
```

`team.md` i `glossary.md` — patrz opis w `projects/README.md`; przykładowe `context.md` i `swot.md` — w projektach w `projects/`.

---

## Struktura odpowiedzi

Po wykonaniu zadania wyślij odpowiedź: 

```
Nowy projekt: <nazwa>.
Status wykonanego zadania: Dodane foldery i pliki
Kontekst: projects/<nazwa>/context/docs/context.md
Kod: projects/<nazwa>/code/ — sklonuj tu repo aplikacji (np. do code/app/) i uzupełnij link w code/sample.md.
Zadaj mi pytania do discovery kick-off.
```
