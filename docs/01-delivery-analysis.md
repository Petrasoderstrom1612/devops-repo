## Värdeflödesanalys

| Steg | Bearbetningstid | Väntetid |
|---|---:|---:|
| Utveckling | 3 d | 0 d |
| Granskning | 20 min (0,04 d) | 4 d |
| Bygge för hand | 45 min (0,09 d) | 0 d |
| Test | 2 d | 3 d (testmiljön upptagen) |
| Vänta på releasefönstret | 0 d | 11 d |
| Driftsättning | 4 h (0,5 d) | 0 d |
| **Summa** | **ungefär 5,6 d** | **18 d** |

**Total ledtid:** ungefär 23,6 arbetsdagar, alltså nästan fem veckor.

**Andel värdeskapande tid:** 5,6 / 23,6, alltså ungefär 24 procent.

Och det är innan omtagen. 40 procent av ändringarna går tillbaka från test, vilket för dem lägger på ytterligare ett varv genom utveckling, granskningskö och testmiljökö.

### De tre största väntetiderna

1. **Releasefönstret – 11 dagar**  
   Nästan halva ledtiden, och ingen arbetar under tiden.

2. **Granskningskön – 4 dagar**  
   20 minuters arbete som väntar i fyra dagar.

3. **Testmiljön upptagen – 3 dagar**  
   En resurs som bara finns i ett exemplar.

## DORA-måtten

| Mått | Värde | Hur det räknas fram |
|---|---:|---|
| Driftsättningsfrekvens | 12 per år | Ett releasefönster i månaden |
| Tid från ändring till drift | ungefär 21 arbetsdagar | Från att pull requesten öppnas, alltså den totala ledtiden minus de 3 dagarnas utveckling: 23,6 − 3 ≈ 20,6 |
| Andel misslyckade ändringar | ungefär 25 procent | Var fjärde release kräver åtgärd dagen efter |
| Återställningstid | ett dygn eller mer | 6 timmars manuell återställning, plus att felet upptäcks först dagen efter |

## Vad man skulle ändra först

Här finns två försvarbara svar, och det viktiga är motiveringen:

### Releasefönstret

Eftersom det är den överlägset största väntetiden. Att gå från månadsvis till varje vecka skulle kapa ungefär 8 dagar av ledtiden på en gång. Det är också det svåraste att ändra, eftersom allt annat i flödet är byggt runt det.

### Granskningskön

Eftersom förhållandet mellan arbete och väntan är sämst där i hela flödet: 20 minuters arbete som väntar i fyra dagar. Det är också det billigaste att ändra, för det kräver ingen ny teknik, bara en överenskommelse om när granskningar görs.

Det som **inte** är svaret är: *"Bygget tar 45 minuter, låt oss automatisera bygget först."*

Det är den åtgärd som känns mest tekniskt tillfredsställande, och den sparar 45 minuter av 23,6 dagar. Det är precis det misstaget en värdeflödesanalys finns för att förhindra.