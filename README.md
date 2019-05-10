HAWK 4411 AWS Cloud9
------

## Anmeldung nach vorheriger Einladung

Melde dich bei der AWS Console an:

`https://signin.aws.amazon.com/console`

## Cloud9-Umgebung einrichten

Lasse einen Webserver durch Klicken auf „Create Environment” erstellen. Benutzte dabei die folgenden Parameter:

| Einstellung | Wert |
|:--|:--|
| Environment type | EC2 |
| Instance type | t2.micro |
| Platform | Amazon Linux |
| Cost-saving setting | 30 Minutes |

### Einrichtung der Entwicklungsumgebung

Öffne die Konsole (View > Console) und installiere folgende Pakete:

```sh
$ sudo yum -y update
$ npm install -g node-sass
```

### Build-System erstellen

Damit aus SCSS-Dateien CSS-Dateien generiert werden können, klicke im Menü auf `Run` > `Build System` > New Build System`. Trage dort bitte folgendes nach und speichere die Datei.

```
{
  "cmd" : ["node-sass", "$file", "$file_path/assets/$file_base_name.css"],
  "env" : {},
  "info" : "Building $project_path/$project_name/$file_name",
  "selector": "source.scss"
}
```

Datei speichern durch CMD + S (Mac) bzw. STRG + S (PC) und als Dateiname `node-sass.build` nennen.

### Einstellungen vornehmen

Klicke bitte oben rechts auf das Zahnrad-Icon für die Einstellungen.

### User Settings / Preview

Einstellung | Wert
|:---|:---|
Soft Tabs | 2

### User Settings / Preview

Einstellung | Wert
|:---|:---|
Preview Running Apps | yes
Default previwer | Browser
When Saving Reload Preview | Always

### Themes

Unter Themes kannst du ein dunkles Theme verwenden. Ich verwende gern `Flat blue` und `Jett`.
 
## Testen

Nun kannst du loslegen. Lege bitte folgenden Verzeichnisse und Dateien an:

```
index.html
styles.scss
assets/normalize.css
assets/scripts.js
assets/images/
```

Öffne jetzt die Datei `styles.scss` und wähle im Menu `Run` > `Automatically Build Supported Files`, sowie `Run` > `Build System` > `Node-sass´.

Öffne jetzt die Datei `ìndex.html` und klicke dann im Menü auf `Run` > `Run with` > `PHP (build-in)`. 

Nun klicke im Menü auf den Button `Preview` > `Preview Running Application`.

Speichere jeweils deine Änderungen mit CMD + S (Mac) bzw. STRG + S (Windows). Die Änderungen im Preview kannst du durch drücken von CMD + Enter (Mac) bzw. STRG + Enter sichtbar machen.