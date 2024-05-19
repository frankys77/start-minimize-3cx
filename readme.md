<header>

<!--
  <<< Author notes: Frank Grzbielok >>>
  Include a 1280×640 image, course title in sentence case, and a concise description in emphasis.
  In your repository settings: enable template repository, add your 1280×640 social image, auto delete head branches.
  
-->

# 3cx Client in Windows minimieren

_Beispiel-Code für ein PowerShell Script._
</header>


_Welcome to "minimimize-3cx"! :wave:_

**Was macht dieses Script?** Dieses Powershell Script dient dazu den 3CX Software Client auf einem Windows PC nach dem Start zu minimieren, sofern der 3CX-Softclient installiert ist. Sollte der Client nicht gestartet sein, 
dann führt das Script die Startdatei aus um diese anschließend zu minimieren. Das Script prüft dann einmal pro Sekunde ob der Client gestartet wurde.

### Einrichtung

**Step 1: Script erstellen**

1. Erstelle ein Powershell-Script mit einem beliebigen Namen. In meinem Beispiel habe ich es einfach **minimize-3cx.ps1** benannt
2. Kopieren den Code (minimize-script) in das Script und speichere dieses unter C:\Windows\system32
oder in einen beliebigen anderen Pfad z.B. C:\Scripts o.ä. dann muss allerdings die **Ausführungs Policy** für das Ausführen von nicht signierten ps-Scripten noch angepasst werden.
3. Erstelle eine geplante Aufgabe und führe das Script beim Start des Comuputers aus.

### Aufgabe anlegen

**Step 2: Script automatisch starten**
1. Öffne die Computerverwaltung
2. Wähle den Abschnitt **Aufgabenplanung** und dort die Aufgabenbibliothek
3. Erstelle eine _einfache Aufgabe_ und vergib einen Namen wie "3CX mininmieren" öder ähnliches und setzt eine kurze Beschreibung ein
4. Wähle unter **Trigger** die Option _Beim Start des Cumputers_ aus
5. Wähle unter **Aktion** die Option _Programm starten_ aus
6. Füge den Pfad für das gespeicherte PS-Script hinzu (z.B. C:\Scripts\minimize-3cx.ps1)
7. Starte den PC neu um den Erfolg zu überprüfen
