Gruppen Mitglieder: Petra Bernroitner, Lisa Hintermaier, Sarah Krottenhammer
Fach: ITSE5- Übungen
Datum: 09.11.2026, 16.11.2026


## Darstellung der Idee: 
Wir wollen einen Rubber Ducky erstellen, der an die Schul PCs angeschlossen wird und von bestimmten Schülern die     
Benutzerdaten: Benutzername und Passwort abfängt.        
Es soll nach der Anmeldung ein Spiel gestartet werden, dass dann für 5 Minuten läuft und der Schüler kommt dann      
nicht mehr aus des Speil raus.

### Angriffsart: 

### Zielgruppe: 
Unsere Zielgruppe sind die Schüler und Schülerinnen der 4 AHITS, die in dem Raum Infotech an dem PCs arbeiten. 

### Bezug zu realen Angriffen:

## Umsetzung: 
### Architektur des Systems: 
  
``` ssh 
# Einfaches Zahlenraten-Spiel – 1 Minute
$timeoutSeconds = 60
$startTime = Get-Date
$secret = Get-Random -Minimum 1 -Maximum 101
$versuche = 0
$gewonnen = $false

Clear-Host
Write-Host "=== Zahlenraten (1-100) ===" -ForegroundColor Cyan
Write-Host "Du hast maximal 1 Minute. Viel Erfolg!" -ForegroundColor Yellow
Write-Host ""

while (((Get-Date) - $startTime).TotalSeconds -lt $timeoutSeconds) {
    $rest = [math]::Round($timeoutSeconds - ((Get-Date) - $startTime).TotalSeconds)
    Write-Host "Verbleibende Zeit: $rest Sekunden" -ForegroundColor DarkGray

    $eingabe = Read-Host "Dein Tipp"
    
    if ([string]::IsNullOrWhiteSpace($eingabe)) { continue }
    
    if ($eingabe -match '^\d+$') {
        $zahl = [int]$eingabe
        $versuche++
        
        if ($zahl -eq $secret) {
            Write-Host ""
            Write-Host "Richtig! Die Zahl war $secret." -ForegroundColor Green
            Write-Host "Du hast $versuche Versuch(e) gebraucht." -ForegroundColor Green
            $gewonnen = $true
            break
        }
        elseif ($zahl -lt $secret) {
            Write-Host "Zu niedrig!" -ForegroundColor Yellow
        }
        else {
            Write-Host "Zu hoch!" -ForegroundColor Yellow
        }
    }
    else {
        Write-Host "Bitte nur eine Zahl eingeben." -ForegroundColor Red
    }
}

# Ende
Clear-Host
if ($gewonnen) {
    Write-Host "Spiel beendet – du hast gewonnen!" -ForegroundColor Green
} else {
    Write-Host "Zeit abgelaufen! Die gesuchte Zahl war $secret." -ForegroundColor Red
}

Write-Host ""
Write-Host "Druecke eine Taste zum Beenden..."
$null = $Host.UI.RawUI.ReadKey("NoEcho,IncludeKeyDown")
```


### Aufgabenverteilung:
Petra Bernroitner: 
Lisa Hintermaier:
Sarah Krottenhammer: 
