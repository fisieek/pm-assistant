# PM-Assistant

Cześć, z tej strony Filip! 🙋🏽‍♂️ Jeśli pracujesz jako produktowiec/PM w software house'ie i szukasz narzędzi, które realnie będą Cię wspierać w Twojej pracy, to jesteś w dobrym miejscu. Przez ostatnie miesiące testowałem różne sposoby na jak najlepsze wykorzystanie AI w codzienności Product Ownera i tak powstał **PM-Assistant** - agent, który zna Twoje projekty i rozumie kontekst branży. Nie jest to żadna aplikacja, a zestaw reguł, dzięki którym Twoja praca będzie bardziej poukładana 🚀

Cieszę się, że asystent w tej formie Cię zainteresował i mam nadzieję, że będzie przydatny w Twojej pracy!

## Jak to działa?

1. Pobierz tę przestrzeń na swój komputer i uruchom w Claude Code. Reguły z `AGENTS.md` przeczyta też Cursor czy Codex, ale **skille z `.claude/skills/` ładują się tylko w Claude Code**.
2. Edytuj plik **AGENTS.md** według własnego stylu pracy. Miejsca do zmiany są oznaczone ✏️ - opisz siebie, branże, w których pracujesz, wszystko to, o czym Twój asystent powinien pamiętać w każdej sesji (rozmowie). Uwaga: kontekst nie może być zbyt duży, by rozmowy nie zużywały zbyt dużych zasobów (tokenów). Warto to regularnie weryfikować, sprawdzając zużycie sesji.
3. W folderze **projects** znajdują się przykładowe projekty - pełnią one wyłącznie rolę demonstracyjną. Zanim zaczniesz rozmawiać z asystentem, przygotuj przynajmniej jeden własny projekt według schematu folderów i plików z przykładów. Pomoże Ci w tym **README** w folderze **projects** oraz skill `/new-project`.

---

## Wymagania

- Zainstalowany [Claude Code](https://claude.com/claude-code) i konto z dostępem do niego. Nie trzeba umieć programować - potrzebny jest tylko terminal.
- Git, żeby pobrać repozytorium (i ewentualnie sklonować kod swoich projektów do `projects/<nazwa>/code/`).
- Opcjonalnie [Obsidian](https://obsidian.md) - repozytorium jest jednocześnie vaultem, więc dokumenty możesz czytać i edytować w Obsidianie, a Claude pracuje na tych samych plikach.

---

## Szybki start

```bash
git clone https://github.com/fisieek/pm-assistant.git
```

```bash
cd pm-assistant && claude
```

Claude Code sam znajduje `.claude/skills/`.

Możesz wywołać skill wprost, np.:

```
/prd
```

lub po prostu opisz swój problem - skille ładują się same, gdy pasują do tego, o co pytasz.

### Jak wygląda typowa sesja

```
> /new-project
  (asystent zadaje pytania o klienta, branżę, zakres i tworzy strukturę projektu)

> Wrzucam transkrypcję z wczorajszego spotkania do meetings/. Zrób notatkę dla klienta.
  (skill meeting-transcript-summary: decyzje, action pointy z osobami, plik obok transkrypcji)

> Klient chce dodać czat w aplikacji do MVP. Challenge'uj ten pomysł.
  (skill challenge: 5 pytań na bazie PRD, roadmapy i kodu, bez pytań o rzeczy już ustalone)

> Rozpisz to jako user stories.
  (skill user-stories: tytuł, story, kryteria akceptacji, z uwzględnieniem stanu implementacji)
```

---

## Co jest w środku

Skille w folderze `.claude/skills/` pozwalają na szybkie wykonywanie powtarzalnych zadań według instrukcji zapisanych w plikach `SKILL.md`. Każdy skill jest jednocześnie komendą `/nazwa`. Przygotowałem te, które są szczególnie przydatne w pracy produktowca/PM w software housie.

**Uwaga: skille możesz dopasować do siebie i swojego modelu pracy.** W `user-stories` jest miejsce na nazwę Twojego narzędzia do backlogu.

### Start

| Skill | Do czego |
| --- | --- |
| `new-project` | Zakłada strukturę nowego projektu w `projects/` po serii pytań o klienta, branżę i zakres. Od tego zaczynasz. |

### Discovery - warsztaty, badania, definiowanie produktu

| Skill | Do czego |
| --- | --- |
| `pd-workshops` | Porządkuje materiały z warsztatów discovery w raport według 9-punktowego szablonu (cel biznesowy, wizja, użytkownicy, konkurencja, monetyzacja, ograniczenia, zakres, MVP, wersja docelowa). |
| `users` | 3-5 person użytkowników na podstawie warsztatów i rozmów: bóle, potrzeby, jobs to be done, korzyści. |
| `IDI` | Scenariusz wywiadów pogłębionych (IDI) z użytkownikami, z pytaniami niesugerującymi odpowiedzi. |
| `swot-analysis` | Analiza SWOT produktu na podstawie dokumentacji i kodu, z wnioskami. |
| `prd` | PRD na podstawie materiałów z `docs/` i kodu. Braki oznacza jako TBD, nie wymyśla. |
| `challenge` | Sparing partner: 5 pytań podważających pomysł lub wymaganie, bez pytań o rzeczy już ustalone w dokumentacji. |

### Delivery - backlog, spotkania, iteracje

| Skill | Do czego |
| --- | --- |
| `user-stories` | User stories z kryteriami akceptacji, z uwzględnieniem kontekstu projektu i stanu kodu. |
| `meeting-transcript-summary` | Transkrypcja spotkania → notatka do udostępnienia klientowi i zespołowi, z action pointami i osobami odpowiedzialnymi. |
| `sprint-review` | Lista funkcjonalności ze sprintu → notatka na sprint review: co dowieziono, jaką wartość, co zostało. |

---

### Własny skill

Jeden folder, jeden plik:

```
.claude/skills/<nazwa-skilla>/SKILL.md
```

Na górze pliku frontmatter z `name` i `description`:

```markdown
---
name: nazwa-skilla
description: Co robi ten skill i kiedy go użyć.
---
```

**Struktura powinna być płaska.** Nie twórz podfolderów grupujących kilka skilli. Claude Code czyta `.claude/skills/<nazwa>/SKILL.md`. Nazwa folderu = nazwa komendy, więc `name` w pliku powinno być takie samo jak nazwa folderu.

---

## Kod projektów jest tylko do odczytu

Folder `projects/<nazwa>/code/` służy do analizy, nie do programowania. Dwa zabezpieczenia:

- `.gitignore` nie wpuszcza zawartości `code/` do tego repozytorium.
- `.claude/settings.json` blokuje asystentowi edycję plików wewnątrz sklonowanego repo oraz komendy `git add`, `git commit` i `git push`. Jeśli chcesz, żeby Claude commitował Twoją dokumentację, usuń odpowiednie linie z sekcji `deny`.

---

## Licencja

MIT. Możesz z tego korzystać, zmieniać i udostępniać dalej, jak chcesz. Jeśli coś Ci się przyda albo masz pomysł na lepszy skill, daj znać.
