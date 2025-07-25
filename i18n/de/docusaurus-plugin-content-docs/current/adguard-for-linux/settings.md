---
title: Einstellungen und Schutzverwaltung
sidebar_position: 3
---

## Verfügbare Befehle

Um eine Liste aller verfügbaren AdGuard-Befehle zu erhalten, geben Sie ein:

```sh
adguard-cli --help-all
```

## Schutz aktivieren und deaktivieren

### Schutz aktivieren

Um den Schutz zu aktivieren, geben Sie ein:

```sh
adguard-cli start
```

Dieser Befehl versucht, eine Weiterleitung zum Proxy zu konfigurieren.

![Schutz starten \*border](https://cdn.adtidy.org/content/Kb/ad_blocker/linux/start-protection.gif)

### Schutz deaktivieren

Um den Schutz zu deaktivieren, geben Sie ein:

```sh
adguard-cli stop
```

Dieser Befehl stoppt nicht nur den Proxy, sondern auch die Weiterleitung des Datenverkehrs zu ihm.

### Schutzstatus prüfen

Um den Schutzstatus anzuzeigen, geben Sie ein:

```sh
adguard-cli status
```

![Status/Schutz stoppen \*border](https://cdn.adtidy.org/content/Kb/ad_blocker/linux/activation6.png)

## Aktualisierungen

### Auf Aktualisierungen prüfen

Um auf Aktualisierungen zu prüfen, geben Sie ein:

```sh
adguard-cli check-update
```

### AdGuard für Linux aktualisieren

Um AdGuard für Linux zu aktualisieren, geben Sie ein:

```sh
adguard-cli update
```

### Skriptausgabe aktualisieren

Um die Ausgabe des Aktualisierungsskripts anzuzeigen, geben Sie ein:

```sh
adguard-cli update -v
```

## AdGuard für Linux konfigurieren

Verwenden Sie den Befehl `config`, um AdGuard für Linux zu konfigurieren. Unterbefehle:

- `show`: Die aktuelle Konfiguration in `proxy.yaml` anzeigen

    ![Aktuelle Einrichtung \*border](https://cdn.adtidy.org/content/Kb/ad_blocker/linux/activation7.png)

- `set`: Eine Option in `proxy.yaml` konfigurieren
    - `listen_ports.http_proxy`: HTTP-Lauschport
    - `proxy_mode`: Proxy-Modus (`manual` oder `auto`)

- `get`: Den aktuellen Status der oben genannten Optionen abrufen

## Filter verwalten

Verwenden Sie den Befehl `filters`, um AdGuard für Linux zu konfigurieren. Unterbefehle:

- `list`: Liste der installierten Filter

    - `--all`: Alle Filter anzeigen

    ![Filterliste \*border](https://cdn.adtidy.org/content/Kb/ad_blocker/linux/filter-list.png)

- `install`: Einen Filter installieren. Geben Sie die URL des Filters ein, den Sie installieren möchten

- `enable`: Einen Filter aktivieren. Geben Sie den Namen oder die ID des Filters ein

    ![Filter aktivieren \*border](https://cdn.adtidy.org/content/Kb/ad_blocker/linux/built-in-filters.png)

- 'disable': Einen Filter deaktivieren. Geben Sie den Namen oder die ID des Filters ein

- 'update': Filter aktualisieren

## Lauschadresse des Proxyservers im manuellen Proxymodus ändern

Standardmäßig lauscht der Proxyserver auf `127.0.0.1` — die Adresse der Loopback-Netzwerkschnittstelle.
Es gibt zwei Möglichkeiten, den Proxyserver an einer anderen Schnittstelle lauschen zu lassen:

1. Führen Sie `adguard-cli config set listen_address <address>` aus, wobei `<address>` die Adresse ist, auf die gelauscht werden soll.
2. Konfigurationsdatei direkt bearbeiten:
    - Um den Speicherort der Konfigurationsdatei zu ermitteln, führen Sie `adguard-cli config show | grep "Config location"` aus.
    - Suchen Sie nach dem Schlüssel `listen_address` und setzen Sie dessen Wert entsprechend. Um auf allen verfügbaren Netzwerkschnittstellen zu lauschen, setzen Sie die Listen-Adresse auf `0.0.0.0` oder `::`.

Wenn die Lauschadresse auf einen anderen Wert als `127.0.0.1` eingestellt ist, ist eine Authentifizierung des Proxy-Clients erforderlich. AdGuard CLI startet nicht, wenn keine Proxy-Authentifizierung konfiguriert ist:

- Wenn Sie `adguard-cli config set listen_address <address>` ausführen, wobei `<address>` nicht `127.0.0.1` ist, wird AdGuard CLI nach einem Benutzernamen und Passwort fragen, wenn die Proxy-Authentifizierung nicht bereits konfiguriert ist.
- Wenn Sie die Konfigurationsdatei direkt bearbeiten, suchen Sie nach dem Schlüssel `listen_auth`. Setzen Sie den Unterschlüssel `enabled` auf `true` und geben Sie Werte für `username` und `password` ein.
