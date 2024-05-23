# Syntezator-Mowy

Realizacja syntezatora mowy

### Wymagania

* Google-colaboratory
* Python 3.10
* TTS 0.22.0
* IPython
* librosa 0.10.1
* matplotlib 3.8.2
* numpy 1.26.3

### Instalacja

1. Sklonuj repozytorium:
    ```
    git clone https://github.com/Weisjan/Import-adresow.git
    ```
    
2. W notatniku `Train_model.ipynb`
   - Ustal ścieżkę wyjściową
   - Dostosuj wybrane parametry konfiguracyjne modelu
   - Dostosuj parametry datasetu w funkcji `BaseDatasetConfig()`
   - Uruchom notatnik

3. W notatniku `Run_model.ipynb`
   - Wprowadź tekst, który będzie poddany syntezie
   - Dostosuj ścieżkę do wytrenowanego modelu oraz do pliku konfiguracyjnego, lub wybierz jeden z gotowych modeli
   - Uruchom notatnik
     
4. W notatniku `mel_spectogram.ipynb`
   - Ustal ścieżkę do wygenerowanego pliku `out.wav`
   - Uruchom notatnik
     
### Struktura plików

| No | File Name | Details 
|----|------------|-------|
| 1  | Train_model.ipynb | Pobieranie oraz przygotowanie datasetu, konfiguracja oraz trening modelu
| 2 | Run_model.ipynb | Sprawdzenie działania modelu, odtwarzanie pliku wyjściowego
| 3  | mel_spectogram.ipynb | Generowanie mel-spektogramów na podstawie pliku wyjściowego
| 4 | audio | Folder z wyjściowymi plikami .wav wygenerowanymi przez autora
| 5 | Readme.md | Plik Readme
  
### Opis działania

System konfiguruje i pobiera zestaw danych LJSpeech, który jest używany do trenowania modelu syntezy
mowy. Po skonfigurowaniu zestawu danych, inicjalizowany jest model GlowTTS, ustawiając odpowiednie
parametry i przygotowuje procesor audio oraz tokenizer tekstu. Kolejnym krokiem jest wczytanie próbek
danych do treningu i walidacji, po czym następuje proces trenowania modelu przy użyciu tych danych.
Po zakończeniu treningu, następuje pobranie wyuczonego modelu oraz plików konfiguracyjnych. Uży-
wając modelu, można przekształcić wprowadzony tekst w syntetyzowaną mowę, którą następnie można
odtworzyć i usłyszeć za pomocą narzędzi wbudowanych w środowisko IPython. Opcjonalnie, 
użytkownik może wygenerować wykresy sygnału pliku wyjściowego.

### Uwagi

Architektura modelu TTS może być modyfikowana w zależności od wymagań projektowych. Użytkownik
może dostosować parametry takie jak rozmiar wektora ukrytego, udział warstwy porzucenia, dwukie-
runkowość sieci, długość pojedynczej epoki, oraz maksymalną liczbę epok. Coqui TTS oferuje szeroki
zakres możliwości konfiguracji modelu, co pozwala na eksperymentowanie z różnymi architekturami i
ustawieniami.

### Autor

[Jan Weis](https://github.com/Weisjan)

