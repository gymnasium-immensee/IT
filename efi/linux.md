## 🐧 Linux

⏮ [Zurück zur EFI Übersicht](/efi/)

Zugriff auf die entfernte Linux-Kommandozeile (zurzeit inaktiv 💤)
➡️ Via «Eingabeaufforderung» (Windows) oder «Terminal» (Mac/Linux) auf das Ausprobier-Linux zugreifen («user» durch effektiven Benutzernamen ersetzen): `ssh user@XXX.XXX.XXX.XXX`

* 📺 Wie? [Windows](https://is.gd/sshwindows)
* 📺 Wie? [Mac](https://is.gd/sshmac) (oder man kann direkt das Terminal verwenden)
* [SSH Apps für Android](https://play.google.com/store/search?q=ssh&c=apps&hl=de) (oder man kann direkt [Termux](https://termux.com/) verwenden)
* [SSH Apps für iOS](https://www.apple.com/de/search/ssh?src=serp)

### [10 Befehle vom PCWelt-Ratgeber](https://www.pcwelt.de/ratgeber/*Die_10_wichtigsten_Linux-Befehle_fuer_Einsteiger-Kommandozeile_alias_Terminal-8858519.html)
1. Eingabefenster aufräumen: `clear`
1. Wer bin ich: `whoami`
1. Wo bin ich (print working directory): `pwd`
1. Passwort ändern: `passwd`
1. Verzeichnisinhalt anzeigen (list): `ls`
1. Verzeichnis wechseln (change directory): `cd`
1. Kopieren oder umbenennen: `cp`
1. Löschen (remove): `rm`
1. Befehl auf ganze Verzeichnisse anwenden (recursive): `befehl -r`
1. Dateiinhalt anzeigen oder leere Datei erstellen: `cat datei`
	* Datei mit Text füllen: `cat > neuedatei` + Text eingeben
	* Mehrere Textdateien zusammenfassen: `cat datei1 datei2 > neueredatei`

### Weitere Befehle

* Anleitung eines Befehls anzeigen (manual):
	* `man befehl`
	* `yelp man:Befehl`
	* [`curl cheat.sh/Befehl`](https://cheat.sh)
	* `apropos <Schlüsselwort>` 
* Ordner erstellen: `mkdir`
* Ordner löschen: `rmdir`
* Intuitiver Texteditor: `nano`
* Mächtiger Texteditor: `vim` (Tutorial: `vimtutor`)
* Überraschungen: `cmatrix` / `sl` / `xeyes`
* SQLite: `sqlite3`
* Youtube-Downloader: `youtube-dl`
* Etwas ausgeben: `echo daswasmanausgebenmöchte`
* Inhalte mit Sonderzeichen und Leerschlägen: *mit Anführungs- und Schlusszeichen einrahmen*
* Befehl beenden: Tastenkombination `ctrl``C`
* Vergangene Befehle anzeigen: `history`
* Autovervollständigen: `⇥` / `⇥⇥`
* Vergangene Befehle suchen: `Ctrl``R`
* Prozesse anzeigen: `ps``
* Prozess beenden: `kill Prozessnummer`
* Prozess beenden: `killall`
* Dateisystembelegung: `ncdu`
* Software-Verwaltung (Debian): `sudo apt`... `update` / `upgrade` / `install Paketname` / `remove Paketname` / `clean` / `search Suchbegriff` / `show Paketname`
* Konfiguration der Software-Verwaltung (Debian):
	* `/etc/apt/sources.list`
	* `/etc/apt/sources.list.d/`
* Weitere Paketmanager, etc.:
	* [RPM](https://de.wikipedia.org/wiki/RPM_Package_Manager) (Redhat, Fedora)
	* [Pacman](https://wiki.archlinux.de/title/Pacman) (Arch, Manjaro)
	* [Flatpak](https://de.wikipedia.org/wiki/Flatpak) / [Flathub](https://flathub.org/home)
	* [Snap](https://wiki.ubuntuusers.de/snap/)
	* [AppImage](https://de.wikipedia.org/wiki/AppImage)


### [GNU Emacs](https://www.gnu.org/software/emacs/)

* Noch ein mächtiger Texteditor: `emacs`
* Text adventure game: `emacs` + Tastenkombination `esc``x` + "dunnet"
* AI doctor: `emacs` + Tastenkombination `esc``x` + "doctor"
* Tetris: `emacs` + Tastenkombination `esc``x` + "tetris"
* Emacs beenden: Tastenkombination  `ctrl``x` + `ctrl``c`
* [Real Programmers use ...](https://www.xkcd.com/378/)

### Noch mehr Befehle

* Andere Shell starten: z.B. `sh` / `csh` / `ksh` / `dash` / `zsh`
* Welche Shell läuft aktuell? `echo $0`
* Welche Shells sind installiert? `cat /etc/shells`
* `more`: seitenweise Ausgabe und Suche
* `less`: wie more nur mehr
* `head`: Ausgabe der ersten Zeilen
* `tail`: Ausgabe der letzten Zeilen
* `sort`: sortieren
* `wc`: Zählen von Wörtern, Zeilen, usw.
* `grep`: filtern nach regulären Ausdrücken
* `date`: Anzeige von Datum und Uhrzeit
* Pipelining `|`: Ausgabe des ersten Befehls wird als Eingabe des zwenten verwwendet, z.B. `ls /etc/ | more` / `ls /etc/ | sort -r | more` / `last | grep root`
* `*`: Platzhalter für  beliebige Zeichenfolge
* `?`: Platzhalter für genau ein beliebiges Zeichen
* `\`: «escaped» das nachfolgende Spezialzeichen (z.B. Leerzeichen, Fragezeichen, etc.)

### Netzwerken

➡️ [DNStools.ch](http://www.dnstools.ch) <br>
➡️ [HowDNS.works](https://howdns.works) <br>
➡️ [Filius](https://lernsoftware-filius.de/Herunterladen) <br>
➡️ [Wireshark](https://www.wireshark.org) <br>

* `ip link` / `ip l`: Netzwerkschnittstellen anzeigen (lo = loopback)
* `ip neighbour` / `ip n`: ARP-Tabelle anzeigen (IP- und MAC-Adressen im Netzwerk)
* `ip address` / `ip a`: Zeigt eigene IP Adresse an
* `ping <Adresse>`: ICMP ECHO_REQUEST
* `ip route` / `ip r`: Routing-Tabelle
* `traceroute <Adresse>`: Traceroute
* `ss`: Socket statistics
* `cat /etc/hosts`: Lokale Namensauflösung
* `cat /etc/resolv.conf`: DNS
* `host <Adresse>` / `dig <Adresse>` / `nslookup <Adresse>`: Anfrage von DNS-Informationen
* `cat /etc/nsswitch.conf`: Reihenfolge der Namensauflösung
* `whois <Domain>`: Eigentümer von Domains
* Webbrowser I:
	* `telnet <Adresse> 80`
	* `GET / HTTP/1.1`
	* `Host: <Adresse>`
* Bonus: `telnet towel.blinkenlights.nl`
* Webbrowser II: `elinks`, `w3m`, `lynx`, `links``
* Downloadmanager: `wget`
* Dienste & Ports: `cat /etc/services`