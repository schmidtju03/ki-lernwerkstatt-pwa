# KI-Lernwerkstatt

Eine kleine Progressive Web App für alle, die sich mit BWL und künstlicher Intelligenz beschäftigen. Karteikarten, ein Wirtschaftlichkeitsrechner und persönliche Notizen helfen dabei, Wissen anzuwenden und eigene Ideen festzuhalten.

**[KI-Lernwerkstatt öffnen](https://schmidtju03.github.io/ki-lernwerkstatt-pwa/)**

## Was kann die App?

- **Karteikarten:** Zehn vorbefüllte Karten zu Themen wie LLM, RAG, Memory, Prompt Injection und EU AI Act. Eigene Karten können ergänzt und als gelernt markiert werden.
- **ROI- und Tokenkostenrechner:** Annahmen für Frontier- und Mini- beziehungsweise lokale Modelle mit Reglern vergleichen. Die App schätzt monatliche Kosten, Ersparnis, Amortisationsdauer und ROI nach zwölf Monaten. Die vorgegebenen Preise sind frei gewählte Beispiele, keine aktuellen Anbieterpreise.
- **Lernstand und Notizen:** Eigene Inhalte und Einstellungen werden lokal im Browser gespeichert. Eine JSON-Sicherung kann exportiert und später wieder importiert werden. Beim Import werden die aktuellen App-Daten nach Bestätigung ersetzt.
- **Offline und installierbar:** Nach dem ersten vollständigen Laden über HTTPS ist die App auch ohne Internetverbindung nutzbar. Sie benötigt kein Konto, keine externen Bibliotheken und verwendet keine Tracker.

## Auf dem Smartphone installieren

1. Die App über den Link oben online öffnen und vollständig laden.
2. **iPhone/iPad:** In Safari auf „Teilen“ und anschließend „Zum Home-Bildschirm“ tippen.
3. **Android:** In Chrome das Menü öffnen und „App installieren“ beziehungsweise „Zum Startbildschirm hinzufügen“ wählen.

## Lokal starten

Im übergeordneten Ordner einen lokalen Webserver starten, zum Beispiel:

```sh
python3 -m http.server 8000
```

Dann `http://localhost:8000/ki-lernwerkstatt-pwa/` öffnen. Für Installation und Service Worker ist HTTPS oder localhost erforderlich; beim direkten Öffnen der HTML-Datei steht der Offline-Cache nicht zur Verfügung.

## Technik und Datenschutz

Die App besteht aus HTML, CSS und JavaScript, einem Web-App-Manifest, lokalen Icons und einem Service Worker mit versioniertem Cache. Die Daten liegen im Browser des jeweiligen Geräts und werden nicht automatisch zwischen Geräten synchronisiert. Werden Browserdaten gelöscht, können auch die Lerninhalte verloren gehen. Deshalb empfiehlt sich ein regelmäßiger JSON-Export.

Bei Änderungen an den App-Dateien die Cache-Versionsnummer in `sw.js` erhöhen. Ein neuer Service Worker wird gegebenenfalls erst aktiv, nachdem alle geöffneten App-Tabs geschlossen wurden.
