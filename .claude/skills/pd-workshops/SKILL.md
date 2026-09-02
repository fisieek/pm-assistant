---
name: pd-workshops
description: Bazując na szablonach z folderu references (szablon frameworku warsztatów oraz szablon raportu po warsztatach) oraz dostarczonych treściach (podsumowaniach, wynikach rozmów, transkrypcjach, notatkach itd.) podsumuj i uporządkuj warsztat discovery wypełniając w miarę możliwości (jeśli posiadasz takie dane) wszystkie elementy i uzupełniając szablon raportu. Nie wymyślaj własnych wniosków, problemów, czy użytkowników. Zawsze opieraj się na dostarczonych materiałach.
---

# Warsztat discovery (9 obszarów)

## Cel
Warsztaty Product Discovery wykonywane są na początku projektu, tuż przed jego startem lub przed startem kolejnej fazy (jeśli projekt już istnieje). Domyślnie zakładamy scenariusz, w którym są to pierwsze pozyskane od klienta informacje o projekcie stanowiące jego podstawę do dalszej realizacji, planowaniu i projektowaniu rozwiązań. 

## Zadanie
Skill polega na wypełnieniu szablonu raportu po warsztatach discovery i dostarczeniu go użytkownikowi do odpowiedniego projektu, do pliku `projects/{nazwa-projektu}/context/docs/podsumowanie-warsztatow.md`, bazując na `references/discovery-summary-report.md`. Lista obszarów do przejścia na samym warsztacie jest w `references/product-discovery-workshops-template.md` — użyj jej, gdy użytkownik dopiero przygotowuje warsztat, a nie ma jeszcze materiałów. 
Obszary, dla których nie ma danych w materiałach, oznacz jako `TBD` — nie uzupełniaj ich własnymi domysłami. 
## Struktura odpowiedzi
W podsumowaniu przekaż użytkownikowi potencjalne kolejne kroki, tj.: 
- Podlinkowanie utworzonego pliku w celu jego przejrzenia i akceptacji 
- Lista obszarów oznaczonych `TBD`, które trzeba dopytać u klienta 
- Utworzenie person użytkowników bazując na skillu `users`
- Utworzenie PRD i zakresu funkcjonalności fazy projektu bazując na skillu `prd`
