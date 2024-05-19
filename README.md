# When do songs go viral? - Czynniki wpływające na pozycję utworu w rankingu Spotify „Weekly Top Songs Global”

## Spis treści
- [Opis projektu](#opis-projektu)
- [Dane](#dane)
- [Model](#model)
- [Wyniki](#wyniki)
- [Diagnostyka modelu](#diagnostyka-modelu)
- [Wymagania](#wymagania)
- [Instrukcja instalacji](#instrukcja-instalacji)
- [Użycie](#użycie)
- [Wkład](#wkład)
- [Licencja](#licencja)

## Opis projektu
Projekt ten bada czynniki wpływające na popularność utworów muzycznych na platformie Spotify. Celem jest zidentyfikowanie cech utworów, które wpływają na ich pozycję w rankingu „Weekly Top Songs Global”.

## Dane
Analizowane dane pochodzą z platformy Spotify i obejmują utwory, które znalazły się w rankingu „Top 200 Weekly (Global)” w latach 2020-2021. Dodatkowo uwzględniono popularność utworów na TikTok oraz informacje o treściach oznaczonych jako wulgarne.

### Opis zmiennych
- **Highest charting position**: Najwyższa pozycja w rankingu
- **TikTok track popularity**: Popularność na TikTok
- **Explicit**: Oznaczenie utworu jako wulgarnego (1 - tak, 0 - nie)
- **Danceability**: Taneczność utworu
- **Energy**: Energetyczność utworu
- **Loudness**: Głośność utworu w decybelach
- **Speechiness**: Ilość mowy w utworze
- **Liveness**: Poziom obecności widowni
- **Duration**: Długość utworu w minutach
- **Valence**: Poziom pozytywności utworu

## Model
Konstrukcja modelu opiera się na regresji liniowej, gdzie zmienną objaśnianą jest najwyższa pozycja utworu w rankingu. W modelu uwzględniono zmienne takie jak długość utworu, popularność na TikTok, oznaczenie utworu jako wulgarnego oraz poziom pozytywności.

### Równanie modelu
\[ \text{chart\_peak} = -40.736 + 22.129 \cdot \text{Duration} - 0.365 \cdot \text{TikTok} + 58.902 \cdot \text{Explicit} + 89.004 \cdot \text{Valence} - 112.217 \cdot \text{Explicit} \cdot \text{Valence} \]

## Wyniki
- **R²**: 0.152
- **Istotne zmienne**: Duration, Valence, Explicit

Model wykazał, że:
- Wzrost długości utworu o minutę przekłada się na spadek pozycji w rankingu.
- Wzrost poziomu pozytywności utworu wpływa różnie w zależności od oznaczenia wulgarności.

## Diagnostyka modelu
Model przeszedł testy na poprawność formy funkcyjnej, ale wykazał problemy z homoskedastycznością i autokorelacją reszt. Założenie o normalności rozkładu składnika losowego również nie zostało spełnione.

## Wymagania
- Python 3.7+
- Jupyter Notebook
- Biblioteki: pandas, numpy, statsmodels, matplotlib

## Instrukcja instalacji
1. Sklonuj repozytorium:
    ```bash
    git clone https://github.com/twoj-repozytorium.git
    ```
2. Zainstaluj wymagane biblioteki:
    ```bash
    pip install -r requirements.txt
    ```

## Użycie
1. Uruchom Jupyter Notebook:
    ```bash
    jupyter notebook
    ```
2. Otwórz i uruchom plik `Spotify_model.ipynb`.

## Wkład
Wszelkie sugestie dotyczące ulepszeń projektu są mile widziane. Możesz otworzyć zgłoszenie lub utworzyć pull request.

## Licencja
Projekt jest licencjonowany na zasadach licencji MIT. Szczegóły można znaleźć w pliku `LICENSE`.
