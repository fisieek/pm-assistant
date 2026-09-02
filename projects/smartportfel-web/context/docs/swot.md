# SWOT: smartportfel-web

> ℹ️ Projekt przykładowy. Analiza oparta wyłącznie na repozytorium i README aplikacji, bez danych o użytkownikach i rynku. Pokazuje **format**, nie twarde wnioski biznesowe.
>
> **Data:** 2026-09-01

## Mocne strony

- **Wartość produktu:** całość finansów osobistych w jednym miejscu, z elementami specyficznie polskimi (PPK, kredyt hipoteczny, kalkulatory wynagrodzeń, kursy NBP), których nie mają narzędzia zagraniczne.
- **Przewagi:** open source z możliwością self-hostingu; AI na kluczu użytkownika, więc brak kosztu stałego po stronie instancji; serwer MCP jako nietypowy kanał dostępu do własnych danych.
- **Relacje:** produkt własny, krótki cykl decyzyjny. Wspólny backend z aplikacją mobilną.
- **Technologia:** monorepo z testami i CI, kontrakty API w osobnym pakiecie, szyfrowanie kluczy AI, publiczne kalkulatory jako kanał wejścia z wyszukiwarek.

## Słabe strony

- **Ograniczenia:** brak integracji bankowej (open banking). Każda transakcja wchodzi ręcznie lub z pliku, co jest główną barierą utrzymania nawyku w tej kategorii.
- **Zależności:** notowania giełdowe poza zakresem, ceny wpisywane ręcznie. E-mail zależny od Resend, kursy od API NBP.
- **Podatności:** strony prawne puste, do uzupełnienia przed udostępnieniem instancji komukolwiek. Brak danych w repozytorium o zespole i tempie rozwoju.

## Szanse

- **Trendy:** rosnąca liczba osób z PPK, IKE/IKZE i inwestycjami detalicznymi, dla których aplikacje bankowe są za wąskie.
- **Okazje:** kalkulatory publiczne jako źródło ruchu organicznego; serwer MCP jako wyróżnik dla użytkowników pracujących z asystentami AI.
- **Regulacje:** brak dostępu do PSD2 oznacza brak obowiązków licencyjnych; przy ewentualnej integracji przez licencjonowanego dostawcę AIS można to zmienić bez własnej licencji.
- **Partnerstwa:** TBD.

## Zagrożenia

- **Konkurencja:** banki dodają agregację i kategoryzację we własnych aplikacjach; zagraniczne narzędzia budżetowe z integracją bankową.
- **Trendy:** aplikacje do finansów osobistych mają reputację porzucanych po kilku tygodniach, zwłaszcza przy ręcznym wprowadzaniu danych.
- **Regulacyjne:** przetwarzanie danych finansowych wymaga regulaminu i polityki prywatności dopasowanych do podmiotu prowadzącego instancję.

---

## Wnioski

1. Największa dźwignia produktowa to obniżenie kosztu wprowadzania danych (import, AI, mobile), bo brak integracji bankowej jest strukturalny.
2. Publiczne kalkulatory i MCP to dwa wyróżniki, które warto mierzyć osobno jako kanały pozyskania.
3. Przed jakąkolwiek publiczną instancją: uzupełnić strony prawne.
