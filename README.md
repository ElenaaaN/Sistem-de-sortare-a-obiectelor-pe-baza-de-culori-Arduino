# Sistem-de-sortare-a-obiectelor-pe-baza-de-culori-Arduino
Descriere Generală:
Sistemul detectează automat prezența pieselor și clasifică fiecare obiect analizat în una dintre cele 5 categorii definite:
  ~4 culori de bază: Roșu, Galben, Verde, Albastru.
  ~1 canal adaptiv („Alte culori”): Piesele cu tonuri intermediare (ex. mov, portocaliu) sunt grupate într-un compartiment comun, fiind însoțite de reproducerea cromatică exactă a nuanței prin sinteză optică.
Procesul este complet autonom, de la detectarea inițială și calibrarea optică până la distribuția fizică în compartimente și actualizarea statisticilor pe ecran.

Caracteristici CheieActivare 
  ~Automată: Inițierea fluxului de sortare este declanșată prin detectarea pieselor pe banda de alimentare cu ajutorul unui senzor de mișcare/prezență.
  ~Senzistică Optică Precisă: Utilizarea unui senzor cromatic avansat (TCS3200 / TCS34725) pentru achiziția și filtrarea spectrului RGB.
  ~Direcționare Mecanică Servo-Asistată: Un servomotor micro SG90 orientează clapeta de ghidare la 5 unghiuri specifice , 
asigurând devierea precisă în compartimentul asociat.
  ~Sistem Inteligent de Semnalizare Optică:
    ~Canale standard: 4 LED-uri monocromatice dedicate confirmă instantaneu detecția culorilor de bază.
    ~Canal adaptiv PWM: Un LED RGB reproduce dinamic nuanța exactă a obiectului detectat pentru piesele atipice.
  ~Interfață Om-Mașină (HMI):
    ~Afișaj LCD 1602 (I2C): Monitorizare și contorizare în timp real a pieselor sortate pe fiecare canal.
    ~Feedback Acustic: Buzzer activ care emite tonuri diferențiate pentru fiecare categorie.
    ~Calibrare & Reset: Buton multifuncțional pentru ajustarea pragurilor la lumina ambientală și resetarea contoarelor.
