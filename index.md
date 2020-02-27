# Tipps

⏭ [Medien & Informatik (1. & 2. Klasse 2020)](mi)
<br>
⏭ [Ergänzungsfach Informatik (5. & 6. Klasse 2020)](efi)

## 🎹 Emoji oder andere Spezial-Zeichen einfügen:
* Windows: `Windows` `.` oder [mehr Möglichkeiten](https://support.office.com/de-de/article/Einf%C3%BCgen-von-ASCII-und-Unicode-Symbolen-oder-Zeichen-westliche-Sprachen-d13f58d3-7bcb-44a7-a4d5-972ee12e50e0)
* Mac: `⌃` `⌘` `Leertaste`
* ➡️ [unicode.org](http://unicode.org)

## 🖖 Gesten für Multi-Touch-Trackpads
* [Windows](https://support.microsoft.com/de-de/help/4027871/windows-10-touchpad-gestures)
* [Mac](https://support.apple.com/de-de/HT204895)

## `\` Backslash tippen
* Windows & Linux: `AltGr` `<` (rechts von `⇧`)
* Mac: `⌥` `⇧` `7`

## 🖥 Am eigenen Computer die Hardware Komponenten anzeigen
* Windows: Systemsteuerung > System
* Mac: Apfel (links oben) > Über diesen Mac
* Linux: Systemsteuerung > Details (mehr Details mit `sudo apt-get install hardinfo`)
* iOS: Einstellungen > Allgemein > Info
* Android: Einstellungen > Gerätewartung

## 📸 Bildschirmfoto/-aufzeichnung erstellen
* Windows:
  * [Foto](https://support.microsoft.com/de-ch/help/4488540): `PrtScn` oder `Windows` `⇧` `S`
  * Aufzeichnung: Mit der [Xbox Game Bar](https://support.xbox.com/de-ch/xbox-on-windows/social/record-game-clips-game-bar-windows-10) oder einem Programm wie z.B. [Screenpresso](https://screenpresso.com)
* [Mac](https://support.apple.com/de-ch/HT201361):
  * `⌘` `⇧` `5` (alle Optionen, inkl. Aufzeichnung)
  * `⌃` `⌘` `⇧` `3` (ganzer Bildschirm direkt in die Zwischenablage)
  * `⌃` `⌘` `⇧` `4` (Ausschnitt direkt in die Zwischenablage)
* Linux ([Gnome](https://help.gnome.org/users/gnome-help/stable/screen-shot-record.html.de)):
  * Foto: `PrtScn` oder mit «Screenshot»
  * Aufzeichnung: `Ctrl` `⇧` `Alt` `R`
* iOS:
  * [Foto (auch z.B. ganze Websites als PDF)](https://support.apple.com/de-de/HT200289): `Standby` `Home` oder `Standby` `Lauter`
  * Aufzeichnung: via [Kontrollzentrum](https://support.apple.com/de-ch/HT207935)
* Android:
  * [Foto](): `Ein/Aus` `Leiser` (einige Sekunden)
  * Aufzeichnung: Mit einer App wie z.B. [AZ Screen Recorder](https://play.google.com/store/apps/details?id=com.hecorat.screenrecorder.free)

## ✉️ Mail einrichten
* Weiterleitung einrichten: [office.com](https://www.office.com) > Outlook > ⚙️ > Weiterleitung ([Wie?](https://is.gd/mailweiterleitung))
* oder [Mobile Outlook-App](https://products.office.com/de-ch/outlook-mobile-for-android-and-ios) verwenden

## 📡 WLAN-Einstellungen für Adroid & Linux
* EAP: PEAP
* Phase 2: MSCHAPV2
* Zertifikate (CA/Benutzer): –
* Identität: Benutzername
* Anonyme Identität: –
* Passwort: Passwort

## 🚚 (Sehr) grosse Dateien übertragen
(Z.B. ein Kurzfilm, eine grosse Präsentation, etc.)
* Senden:
	* [Gymi Immensee OneDrive](https://gymnasiumimmensee-my.sharepoint.com): 15 GB (Sender_in benötigt Konto)
	* [Firefox Send](https://send.firefox.com/): 1 GB ohne Konto; 2.5 GB, falls Sender_in ein Konto hat
	* [Dropbox Transfer](https://www.dropbox.com/transfer/about)​​​​​​​: 2 GB; nur Sender_in benötigt ein Dropbox Konto
* Empfangen:
	* [Google Forms](https://www.google.com/forms/about/): 10 GB pro File; 1 TB pro Form; Sender_in und Empfänger_in benötigen ein Google Konto
	* [Dropbox File Requests](https://help.dropbox.com/files-folders/share/create-file-request): 2 GB; nur Empfänger_in benötigt ein Dropbox Konto

## 🌐 Sich mit dem Schulserver verbinden (TEACHERSTUFF)
(Benutzername: `vorname.nachname`; Kennwort: das Office365 Passwort vom blauen Blatt; Funktioniert nur im Schul-WLAN)
* Windows: `\\srvdc01.gyim.local\TEACHERSTUFF` im Explorer (≠ ~~Internet Explorer~~) eingeben: [Wie?](https://is.gd/netzlaufwerkwin)
* Mac: `⌘` `K` + [smb://srvdc01.gyim.local/TEACHERSTUFF](smb://srvdc01.gyim.local/TEACHERSTUFF): [Wie?](https://is.gd/netzlaufwerkmac)
* Linux: [smb://srvdc01.gyim.local/TEACHERSTUFF](smb://srvdc01.gyim.local/TEACHERSTUFF) bei Serveradresse eingeben.
* iOS (ab 13): App «Dateien» > «...» > «Mit Server verbinden» > [smb://srvdc01.gyim.local/TEACHERSTUFF](smb://srvdc01.gyim.local/TEACHERSTUFF): [Wie?](https://is.gd/netzlaufwerkios)
* Android: Eines [dieser Apps verwenden](https://play.google.com/store/search?q=smb&c=apps), um sich mit [smb://srvdc01.gyim.local/TEACHERSTUFF](smb://srvdc01.gyim.local/TEACHERSTUFF) zu verbinden.

## 🌐 Terminal Server Zugang via Remote Desktop
1. «Microsoft Remote Desktop» installieren: [Windows](https://www.microsoft.com/de-ch/p/microsoft-remotedesktop/9wzdncrfj3ps?activetab=pivot:overviewtab) / [Android](https://play.google.com/store/apps/details?id=com.microsoft.rdc.android&hl=de_CH) / [iOS](https://apps.apple.com/ch/app/microsoft-remotedesktop/id714464092) / [MacOS](https://apps.apple.com/ch/app/microsoft-remote-desktop-10/id1295203466)
1. `+` klicken, um Feed oder Remote Resources hinzufügen (≠ ~~Desktop~~)
1. Adresse: `schule.gymnasium-immensee.ch`
1. Benutzername: `gyim\vorname.nachname`
1. Passwort: das Office365 Passwort vom blauen Blatt

## ☁️ Teams-Dateien mit dem eigenen Computer synchronisieren
1. [«OneDrive» installieren](https://onedrive.live.com/about/de-ch/download/): [Wie?](https://is.gd/onedrivewin)
1. Im gewünschten Teams zum Reiter «Dateien» / «Files» gehen
1. «Sync» klicken
1. Gewünschte Ordner wählen: [Windows](https://support.office.com/de-de/article/synchronisieren-von-sharepoint-dateien-mit-dem-neuen-onedrive-synchronisierungsclient-6de9ede8-5b6e-4503-80b2-6190f3354a88) / [Mac](https://support.office.com/de-de/article/synchronisieren-von-dateien-mit-dem-onedrive-synchronisierungsclient-unter-mac-os-x-d11b9f29-00bb-4172-be39-997da46f913f)

📱 (iOS & Android) Auf [Sharepoint](https://gymnasiumimmensee.sharepoint.com) dem Team ⭐️folgen, bei der OneDrive-App anmelden und «Bibliotheken» (unten rechts) wählen

## 💾 Backup-Tools
* Windows: [Dateiversionsverlauf](https://support.microsoft.com/de-de/help/4027408/windows-10-backup-and-restore)
* Mac: [Time Machine](https://support.apple.com/de-de/HT201250)
* Linux: [rdiff-backup](https://rdiff-backup.net)
* [iOS](https://support.apple.com/de-de/HT203977)

## 🔐 Starke Passwörter
* Kann man mit `password strength` auf [WolframAlpha](https://www.wolframalpha.com/input/?i=password+strength) testen
* Enthalten keine Teile des ~~Kontonamens~~
* Enthalten neben Gross- und Kleinbuchstaben Ziffern und andere Zeichen (z.B. !, $, #, %)
* Sind so lange wie möglich
* Organisiert man am besten mit einem Passwortmanager, z.B. [SecureSafe](https://www.securesafe.com)

## 📽 Einstellungen für Beamer & externe Bildschirme
* Windows: `Windows` `P`
* Mac: `⌘` `«Helligkeit verringern»` oder [Systemeinstellungen > Monitore](https://support.apple.com/de-ch/HT202351) 

## 🖨 Am Gymi drucken
(Benutzername: `vorname.nachname`; Kennwort: das Office365 Passwort vom blauen Blatt; Funktioniert nur im Schul-WLAN)
* Via Browser: [papercut.gyim.local:9191](http://papercut.gyim.local:9191)
* Windows: [Installationsprogramm laden](http://papercut.com/products/ng/mobility-print/download/client/windows/): [Wie?](https://is.gd/amgymidrucken)
* Mac: `⌘` `P`
* iOS: Teilen > drucken
* Android: [Mobility Print App installieren](https://play.google.com/store/apps/details?id=com.papercut.projectbanksia): [Wie?](https://www.youtube.com/watch?v=vTgRHmURvos)

## ⌨️ Weitere Tastaturkurzbefehle
* [Windows](https://support.microsoft.com/de-ch/help/12445/windows-keyboard-shortcuts)
* [Mac](https://support.apple.com/de-ch/HT201236)
* [Linux](https://code.visualstudio.com/shortcuts/keyboard-shortcuts-linux.pdf)

## 🕹 Praktische Software

#### Zur Zusammenarbeit
* Office (Word, Excel, PowerPoint, OneNote): [office.com](https://www.office.com) > anmelden > Office installieren: [Wie?](https://is.gd/officeinstallieren)
* [Teams](https://teams.microsoft.com/downloads)
* [OneDrive](https://onedrive.live.com/about/de-ch/download/): [Wie?](https://is.gd/onedrivewin)
* [Dateien App (iOS)](https://apps.apple.com/ch/app/file/id1232058109)

#### Browser
* [Firefox](https://www.mozilla.org/de/firefox/new/)
* [Google Chrome](https://www.google.com/chrome/)
* [Opera](https://www.opera.com)
* [Edge](http://microsoft.com/edge)

#### Praktische Windows-Progamme (am einfachsten unten links danach suchen)
* Rechner
* Ausschneiden und Skizzieren
* Sprachnachricht
* Mail
* Drucker und Scanner

## 🛠 Hilfe bei Reparauren
* [ifixit](https://www.ifixit.com)

<hr>
⏫ [Nach oben](#top)