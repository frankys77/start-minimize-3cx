<header>
</header>

# Windows verweigert die Ausführung des PowerShell Scripts

Beim Versuch, ein PowerShell-Skript zu starten, heißt es: 

_"Die Datei kann nicht geladen werden, da die Ausführung von Skripts auf diesem System deaktiviert ist"_.

Das ist auch richtig! Windows führt standardmäßig keine PowerShell-Skripts aus.
Die Fehlermeldung teilt dem Anwender mit, dass die PowerShell-Skriptdatei nicht ausgeführt werden darf und verweist auf einen Microsoft-Artikel. Unter Windows 10 und 11 das Ausführen von PowerShell-Skripts beschränkt. 

Im PowerShell-Konsolenfenster lassen sich zwar einzelne Befehle ausführen, aber sobald der Anwender eine **.ps1-Datei** mit mehreren Befehlen ausführen möchte, erscheint die oben besagte Fehlermeldung.

**Lösung:** 

Klicken Sie auf Start, tippen Sie PowerShell ein und benutzen Sie beim gefundenen PowerShell den Befehl _Als Administrator ausführen_. Die PowerShell erscheint mit Admin-Rechten. 
Tippen Sie **Get-ExecutionPolicy** ein und drücken Sie Enter. 

Standardmäßig erscheint _Restricted_.

Grundsätzlich wäre es viel zu gefährlich alle Scripte einfach zuzulassen, aber es gibt eine Einstellung, mit der nur die lokal erzeugten _. ps1-Scripte_ auf diesem PC ausgeführt werden können:
Tippen Sie hierfür den Befehl in die PowerShell und drücken Sie Enter: <br />
**ps:>Set-ExecutionPolicy RemoteSigned**

Überprüfen Sie es jetzt noch einmal mit dem Befehl:<br />
**ps:>Get-ExecutionPolicy**<br />

jetzt sollte der Rückgabewert _**RemoteSigned**_ angezeigt werden.

Möchten Sie irgendwann diese Einstellung wieder rückgängig machen, dann hilft der Befehl in der Admin-PowerShell:<br />
**ps:>Get-ExecutionPolicy Default**
