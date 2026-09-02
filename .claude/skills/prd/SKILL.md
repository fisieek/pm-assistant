---
name: prd
description: Bazując na dostarczonych materiałach w /docs w folderze projektu, szczególnie z warsztatów, ale również notatki, czy transkrypcje rozmów (oraz, jeśli istnieje, kodzie w folderze /code) napisz PRD według zapisanego szablonu.
---

# Tworzenie PRD

## Cel

Posiadanie rozbudowanego opisu produktu, który stanowi podstawę dla wszystkich interesariuszy i członków zespołu. Posiadanie jasnych informacji czym jest tworzony produkt, jakie problemy rozwiązuje, w jaki sposób oraz jak to wypełnia wizję produktu i cele biznesowe określane na początku projektu.  

## Zadanie

1. Przeanalizuj pliki w folderze /projects/{nazwa-projektu}/context/docs
2. Przeanalizuj (jeśli istnieje) kod produktu w folderze /projects/{nazwa-projektu}/code
3. Nic nie wymyślaj samemu - wypełnij szablon bazując na danych. Jeśli nie masz wystarczających zadaj pytania użytkownikowi prowadzące do uzupełnienia pliku. 
4. Brak informacji użytkownika na wybrane pytania NIE jest blockerem do powstania dokumentu. Zaznacz jakich informacji brakuje i że należy je uzupełnić później (poprzez "TBD"). 
5. Utwórz plik w folderze /projects/{nazwa-projektu}/context/docs/prd.md. Jeśli plik już istnieje, zapytaj, czy go nadpisać, czy utworzyć nowy (np. `prd-v2.md`). 
6. Bądź maksymalnie precyzyjny. To jest plik informacyjny, nie potrzebuje długich tłumaczeń, a konkretne dane pisane w punktach i krótkich zdaniach. 

## Struktura    

   **1. Wstęp** 
   - Czym jest ten dokument, jaką pełni rolę, dla kogo jest skierowany, w czym ma pomóc. Krótko w 3 zdaniach, informacyjnie. 

   **2. Kontekst biznesowy**
   - Jakiej branży dotyczy projekt?
   - Jakie problemy użytkowników rozwiązuje? 
   - Kim są użytkownicy systemu, dla których jest projektowane rozwiązanie? 
   - Jaka jest nisza na rynku, która spowodowała powstanie tego produktu? 
   - Jaki jest cel biznesowy i wizja produktu? 
   - Jaka jest unikalna wartość produktu? 
   - Jakie są potencjalne zagrożenia i ograniczenia wynikające z branży, czy użytkowników? 
   - Jaki jest model biznesowy? 
   - Jak duża jest konkurencja? 
   - Czym produkt wyróżnia się na tle konkurencji?  
   - Szacowany czas trwania projektu? 
   - Czy coś poza głównych produktem wchodzi w zakres projektu? 

   **3. Użytkownicy i role**
   - Jakie role występują w systemie i co każda z nich może zrobić? 
   - Które persony (jeśli istnieje `users.md`) są główne, a które drugorzędne? 

   **4. Zakres funkcjonalny**
   - Lista funkcjonalności (epików) w podziale na: MVP / obecna wersja oraz kolejne fazy. 
   - Przy każdej: jaki problem użytkownika rozwiązuje i dla której roli. 
   - Jeśli istnieje kod: co jest już zaimplementowane, a co dopiero planowane. 

   **5. Poza zakresem**
   - Czego świadomie nie robimy w tej wersji i dlaczego (odrzucone prośby klienta, odłożone pomysły). 

   **6. Wymagania niefunkcjonalne i ograniczenia**
   - Regulacje (np. RODO, branżowe), bezpieczeństwo, integracje z systemami zewnętrznymi, platformy, języki, dostępność. 
   - Ograniczenia czasowe, budżetowe i techniczne. 

   **7. Metryki sukcesu**
   - Po czym poznamy, że ta wersja spełniła cel biznesowy? Konkretne mierniki, jeśli są ustalone; jeśli nie — `TBD` z pytaniem do klienta. 

   **8. Otwarte pytania i ryzyka**
   - Lista pytań bez odpowiedzi: kto ma odpowiedzieć, do kiedy. 
   - Główne ryzyka projektu i ich wpływ na zakres. 
