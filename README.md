# Warsztaty analizy danych

[![Otwórz w Colabie](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/bajon1/Data-Analysis-Workshop/blob/main/notebooks/workshop.ipynb)

Kliknij **Open In Colab**, a następnie uruchom komórkę pomocniczą nad tytułem kursu. Pobierze ona wszystkie pliki repozytorium do Twojego środowiska Colaba, w tym moduły pomocnicze. Każda osoba pracuje niezależnie; nie trzeba ręcznie kopiować plików, aby zacząć.

Warsztaty analizy danych dla osób związanych z psychologią, przygotowane na [Brainhack Kraków 2026](https://brainhackkrakow.org). Zakładamy znajomość podstaw rozumowania statystycznego. Wcześniejsze doświadczenie w programowaniu nie jest wymagane.

Kurs wykorzystuje Google Colab i publiczną [ankietę OSMI dotyczącą zdrowia psychicznego w branży technologicznej](https://www.kaggle.com/datasets/osmi/mental-health-in-tech-survey). Notebook pobiera plik `survey.csv` z Kaggle podczas zajęć; repozytorium nie zawiera zbioru danych. Autorzy opisują zbiór jako ankietę z 2014 roku i udostępniają go na licencji CC BY-SA 4.0.

Ćwiczenia dotyczą sześciu pytań o miejsce pracy: `remote_work`, `self_employed`, `benefits`, `care_options`, `wellness_program` i `seek_help`. Płeć, dane demograficzne, historia rodzinna, historia leczenia i komentarze tekstowe nie wchodzą do tabeli ćwiczeniowej. Pełny słownik opisuje wszystkie kolumny źródłowe.

Kurs zaczyna się od **części 0: przygotowanie**. **Część 1** pokazuje, jak czytać krótkie polecenia, rozumieć nawiasy i wybierać dane z tabeli. **Część 2** dotyczy czyszczenia, a **część 3** — wykresów opisowych. Każde ćwiczenie praktyczne opiera się na pokazanym przykładzie, zawiera konkretną podpowiedź i zwijaną odpowiedź do samodzielnego sprawdzenia. Dalsze części omawiają ryzyko wycieku danych przy przewidywaniu szukania leczenia, pomoc LLM w pisaniu kodu oraz maskowanie i przetwarzanie wymyślonego tekstu.

## Wymagania

- laptop;
- stabilne połączenie z internetem;
- konto Google;
- współczesna przeglądarka internetowa.

Nie trzeba instalować Pythona na własnym komputerze.

## Materiały

- [Notebook uczestnika](notebooks/workshop.ipynb)

Materiały można też udostępniać przez wspólny [folder materiałów warsztatowych](https://drive.google.com/drive/folders/1ijaY-LXx4DGp8ZrUz9KOmUY6Drk4mSBJ?usp=sharing).

## Uruchomienie w Google Colab

1. Kliknij **Open In Colab** u góry tego README.
2. W razie potrzeby zaloguj się na własne konto Google.
3. Uruchom komórkę pomocniczą nad tytułem kursu, aby pobrać repozytorium. Następnie przechodź przez kurs od tytułu, wykonując komórki po kolei przyciskiem obok nich lub skrótem `Shift+Enter`.

Komórka przygotowawcza pobiera pliki potrzebne do warsztatów. Dzięki temu możemy korzystać także z kodu pomocniczego, np. pliku `nbutils.py`, przez zapis `import nbutils`. Pobierana jest wersja z gałęzi `main` na GitHubie. Ponowne uruchomienie komórki zachowuje pliki istniejące już w danej sesji.

Aby zachować własne zmiany po zakończeniu sesji, możesz wybrać **Plik → Zapisz kopię na Dysku** (**File → Save a copy in Drive** w angielskim interfejsie). Otwarcie notebooka z GitHuba nie zapisuje automatycznie kopii na Twoim Dysku.

Osobna komórka w części 0 instaluje `kagglehub`, pobiera `survey.csv` z Kaggle i odczytuje go do tabeli pandas. Następna komórka wybiera wyłącznie sześć kolumn ćwiczeniowych, zanim wyświetli jakiekolwiek wiersze. Ponowne uruchomienie lub odłączenie środowiska usuwa pliki tymczasowe, dlatego po połączeniu uruchom ponownie przygotowanie modułów i pobieranie danych.

Presidio i sentence-transformers są demonstracjami opcjonalnymi. Jeśli pobieranie lub instalacja są niedostępne, osoba prowadząca może omówić wymyślone przykłady bez wykonywania tych komórek.

## Sprawdzenie przed zajęciami

Przed wydarzeniem uruchom nowe środowisko Colaba i sprawdź, czy:

1. pobieranie z Kaggle kończy się bez żądania danych logowania lub niespodziewanej dodatkowej zgody;
2. plik `survey.csv` się wczytuje i zawiera sześć kolumn ćwiczeniowych;
3. części 0–3 działają: wybieranie danych, obsługa braków, liczebności, procenty i wykresy grupowe;
4. biblioteki potrzebne do opcjonalnych demonstracji Presidio i sentence-transformers nadal dają się zainstalować.

## Ochrona danych i granice interpretacji

Dane z Kaggle służą wyłącznie jako publiczny materiał warsztatowy. Uczestnicy zgłaszali się do ankiety samodzielnie: wykresy opisują ich odpowiedzi i nie ustalają częstości występowania zaburzeń w populacji, diagnoz ani skutków przyczynowych. `treatment` oznacza deklarowane szukanie leczenia, a nie diagnozę. Wcześniejsze doświadczenia związane z leczeniem mogły wpływać na opinie o wsparciu w miejscu pracy, dlatego zadanie przewidywania szukania leczenia wymaga określenia kolejności dostępności informacji i sprawdzenia ryzyka wycieku danych.

Praca z rzeczywistymi danymi badawczymi wymaga osobnej decyzji dotyczącej zgód, zasad instytucji, zatwierdzonej infrastruktury, uprawnień dostępu, czasu przechowywania i ryzyka ujawnienia. Ani pseudonimizacja, ani automatyczne wykrywanie danych identyfikujących nie sprawiają automatycznie, że zbiór można bezpiecznie przesłać do zewnętrznego LLM. Przykłady tekstowe są wymyślone i nigdy nie wykorzystują komentarzy respondentów.
