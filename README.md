# Sistem de sortare a obiectelor pe baza de culori - Arduino

## Descriere generală

Acest proiect implementează un sistem automat de sortare a pieselor în funcție de culoare, folosind un microcontroler Arduino. Sistemul detectează prezența obiectelor, identifică nuanța acestora cu ajutorul unui senzor optic, apoi dirijează fiecare piesă către compartimentul corespunzător.

Procesul este complet autonom, de la detectarea inițială și calibrarea optică până la distribuția fizică în compartimente și la actualizarea statisticilor pe ecran.

---

## Scopul proiectului

Sistemul are rolul de a automatiza separarea pieselor după culoare, reducând intervenția umană și crescând viteza și precizia procesului. Este potrivit pentru aplicații în sortare, control de calitate, asamblare sau identificare rapidă a culorilor.

---

## Funcționare

1. Detectarea pieselor  
   Sistemul pornește automat atunci când o piesă este detectată pe banda de alimentare, prin intermediul unui senzor de mișcare / prezență.

2. Achiziția culorii  
   Un senzor RGB avansat (TCS3200 / TCS34725) analizează spectrul culorii obiectului și filtrează informațiile pentru a obține o citire stabilă.

3. Clasificarea  
   Fiecare piesă este repartizată într-una dintre următoarele categorii:
   - Roșu
   - Galben
   - Verde
   - Albastru
   - Alte culori (canal adaptiv pentru nuanțe intermediare, precum mov sau portocaliu)

4. Direcționarea mecanică  
   Un servomotor micro SG90 poziționează clapeta de ghidare la unghiul corespunzător, asigurând devierea precisă în compartimentul asociat.

5. Semnalizare și monitorizare  
   - LED-uri monocromatice indică instantaneu culorile de bază
   - Un LED RGB reproduce nuanța exactă pentru piesele atipice
   - Un LCD 1602 (I2C) afișează statisticile în timp real
   - Un buzzer emite tonuri diferite pentru fiecare categorie
   - Un buton multifuncțional permite calibrarea și resetarea contoarelor

---

## Caracteristici cheie

### Automatizare
- Inițierea automată a fluxului de sortare la detectarea piesei.
- Întregul proces este autonom, de la detectare până la distribuția finală.

### Senzorică optică precisă
- Utilizarea unui senzor cromatic avansat pentru achiziția și filtrarea spectrului RGB.
- Detectare fiabilă a nuanțelor și a tonurilor intermediare.

### Direcționare mecanică servo-asistată
- Control precis al clapetei de ghidare.
- 5 unghiuri specifice pentru distribuția către compartimentele dorite.

### Sistem inteligent de semnalizare optică
- 4 canale standard cu LED-uri monocromatice dedicate.
- Canal adaptiv PWM pentru reproducerea cromatică exactă a nuanței detectate.

### Interfață om-mașină (HMI)
- Afișaj LCD 1602 (I2C): monitorizare și contorizare în timp real.
- Feedback acustic: buzzer activ pentru fiecare categorie.
- Calibrare și reset: buton multifuncțional pentru ajustarea pragurilor la lumina ambientală și resetarea contoarelor.

---

## Structura funcțională

- Senzor de prezență / mișcare: declanșează procesul
- Senzor de culoare: identifică nuanța piesei
- Microcontroler Arduino: procesează informațiile și comandă sistemul
- Servomotor: orientează clapeta de ghidare
- LED-uri: semnalizează rezultatul detectării
- LCD: afișează datele de sortare
- Buzzer: semnal sonor de confirmare
- Compartimente de sortare: stocarea finală a pieselor

---

## Flux de lucru

```text
[Detectare piesă]
        ↓
[Citire senzor cromatic]
        ↓
[Calibrare și comparație cu praguri]
        ↓
[Identificare culoare]
        ↓
[Selectare compartiment]
        ↓
[Acționare servomotor]
        ↓
[Sortare fizică]
        ↓
[Actualizare statistică și afișare]
```

---

## Cerințe hardware

- Arduino Uno / variantă compatibilă
- Senzor de culoare TCS3200 sau TCS34725
- Senzor de mișcare / prezență
- Servomotor SG90
- LED-uri RGB și monocromatice
- Afișaj LCD 1602 I2C
- Buzzer
- Buton multifuncțional
- Bandă de alimentare și compartimente de sortare

---

## Aplicații posibile

- sortarea pieselor colorate dintr-o linie de producție;
- clasificarea obiectelor mici în laboratoare;
- automatizarea proceselor de selecție rapidă;
- educație practică în robotică și electronică.

---

## Concluzie

Proiectul reprezintă o aplicație practică și educațională în domeniul automatizării, roboticii și electronicii. Prin combinarea senzorilor optici, a acționării mecanice și a interfeței utilizator, sistemul oferă o soluție eficientă pentru sortarea automată a obiectelor după culoare.

---

## Note

Acest proiect poate fi extins prin:
- adăugarea unei interfețe seriale pentru monitorizare pe calculator;
- implementarea unei calibrații automate cu mai multe scenarii de iluminare;
- integrarea unei baze de date pentru statistici istorice;
- extinderea sistemului pentru mai multe categorii de culori sau obiecte de dimensiuni diferite.

---

