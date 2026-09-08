# Interaktywne wyprawy miejskie — Toruń 2027

Demo platformy do gier miejskich. Materiał pokazowy: jeden plik HTML, bez frameworków,
bez backendu, bez kont. Stan tylko w pamięci przeglądarki.

**Demo na żywo:** https://lucid-academy.github.io/wyprawy-torun-2027/

## Co jest w środku

Trzy zakładki w kolumnie szerokości telefonu:

- **Mapa** — statyczny render nocny Torunia z nakładkami: winieta, mgła wojny z otworami
  wokół punktów, dryfujące chmury, animowane trasy i markery trzech wypraw.
- **Profil** — karta postaci, osiem osiągnięć (pięć zdobytych, trzy pod kłódką)
  i przełącznik stylu, który przestawia **cały portal**, nie tylko kartę.
- **O projekcie** — pitch, zakres na 2027, makieta panelu organizatora z wykresami
  rysowanymi ręcznie w SVG, podział ról.

Wejście przez intro wideo z pominięciem; po filmie klikalna kartka prowadzi do portalu.

## Trzy motywy

Historyczny (bazowy), cyberpunk, fantasy. Motyw to wyłącznie podmiana zmiennych CSS
w `:root` — żadna reguła niżej nie jest duplikowana. Wybór zapisuje się w `localStorage`.

## Struktura

```
docs/            witryna publikowana przez GitHub Pages
  index.html     całe demo
  assets/        wideo, render mapy, ikony, okładki
tools/
  map-export.html  jednorazowe narzędzie do wycięcia podkładu mapowego (nigdzie niepodpięte)
  serve.js         lokalny serwer podglądu
```

## Podgląd lokalny

Otwarcie `docs/index.html` prosto z dysku pokaże układ, ale przeglądarka zablokuje wideo
i część grafik. Do klikania:

```bash
node tools/serve.js
```

Potem `http://localhost:4321/docs/`.

## Kalibracja pozycji na mapie

Pozycje trzech punktów są w `CONFIG.MAPA.punkty`, w procentach kontenera. Żeby je zmienić,
dopisz `?cal=1` do adresu i kliknij w mapę — dostaniesz gotową linijkę configu, od razu
w schowku.

## Uwagi

- Wszystkie liczby w panelu organizatora są przykładowe i tak są opisane w interfejsie.
- Podkład mapowy to render, nie kartografia. Pod mapą jest podpis „mapa poglądowa".
- Platforma nie zbiera danych o wieku uczestników — świadomie nie ma ich ani w opisach
  wypraw, ani w panelu.

---

Lucid Academy
