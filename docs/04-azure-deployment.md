# Azure deployment

## What I deployed

The plan and its tier, the web app, and the command that deployed it.
Webb app, webb service plan handlar om konstnader.

## What I saw in the log

One line from the log, and what it told me.
2026-10-20T14:42:25.5789232Z Waypoint is listening on <http://localhost:8080> - läser på en separat port sp Konfigurationen ligger utanför koden, i appinställningar (app settings). App Service ger dem till appen som miljövariabler (environment variables), som PORT. Därför kör samma kod på din dator och i Azure, med olika port.
