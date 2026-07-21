# Sensor Check

Webowa aplikacja (HTML + JS, bez zależności) do **sprawdzania danych z fizycznych czujników telefonu** z możliwością **nagrywania** próbek i eksportu do CSV. Działa na **Androidzie i iPhonie**.

## Co robi

- **Telefon w pudełku (3D)** — animowana scena 3D: telefonik siedzi w przezroczystym pudełku i **porusza się fizycznie** zgodnie z akcelerometrem (np. gdy urządzenie leci w dół, telefonik przemieszcza się w dół pudełka i odbija się od ścianek) oraz **obraca się** zgodnie z orientacją. Dodatkowo wykrywa zasłonięcie na podstawie czujnika zbliżeniowego i natężenia światła (ciemno → „w pudełku").
- **Akcelerometr** — przyspieszenie X/Y/Z (m/s²).
- **Żyroskop** — prędkość obrotowa α/β/γ (°/s).
- **Orientacja / kompas** — kierunek i pochylenie (na iPhone przez `webkitCompassHeading`).
- **Nagrywanie** — zapis próbek w czasie i eksport do pliku `.csv`.
- **Diagnostyka** — pokazuje, które API czujników faktycznie udostępnia dana przeglądarka.

## Ważne (fizyczne czujniki)

- Prawdziwe odczyty pojawią się tylko na **fizycznym telefonie** — nie na desktopie.
- **iPhone / iOS 13+** wymaga zgody: przycisk **„Włącz czujniki"** wywołuje systemowe okno zezwolenia na ruch i orientację.
- Strona musi być serwowana przez **HTTPS** (wymóg iOS i Generic Sensor API).
- Czujnik światła (`AmbientLightSensor`) i zbliżeniowy (`deviceproximity`/`userproximity`) są dostępne tylko w niektórych przeglądarkach — aplikacja sama sprawdza dostępność i informuje w sekcji Diagnostyka.

## Uruchomienie

Otwórz `index.html` na telefonie przez HTTPS (np. hosting statyczny lub lokalny serwer z certyfikatem), kliknij **Włącz czujniki**, poruszaj telefonem lub zasłoń ekran / schowaj telefon.
