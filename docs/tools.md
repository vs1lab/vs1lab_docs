# Tools

## Der Umgang mit Git und Repositories

Zum Umgang mit Git stellen wir ein separates Dokument zur Verfügung!
TODO


## Debuggen in Google Chrome

Chrome, als auch weitere Browser, bieten eine Vielzahl von verschiedenen
Entwicklertools an. Die Entwicklungstools werden mit ++f12++ oder über

**Einstellungen -\> Weitere Tools -\> Entwicklertools** geöffnet.

![image8](img/image8.png)

Über die Tabs können die Verschiedenen Tools aufgerufen werden. Im
rechten Bereich sind weitere Einstellungen wie die Ausrichtung der Tools
möglich.

![image9](img/image9.png)

### Elements

In Elements wird der aktuelle DOM Baum angezeigt und Chrome bietet verschiedene
Möglichkeiten um den Baum zu manipulieren.

Mit einem Rechtsklick auf ein HTML Element wird die Option angezeigt.

Hier im Bild, im rechten Teil von Elements, werden die aktuellen Styles und
weitere Einstellungen für eine Node angezeigt.

Im Styles Bereich können die vorhandenen CSS Einträge manipuliert oder es
können eigene Regeln bzw. Attribute hinzugefügt werden.

![image10.png](img/image10.png)

### Console

Gibt verschiedene Nachrichten des laufenden JS-Codes aus. Bei Fehlern im
JS-Code, werden diese in der Console mit einem Stack-Trace ausgegeben. Auch
einfache Informationen oder Warnungen werden dort ausgegeben.

Für die Console kann ein level angegeben werden, welches besagt, welche
Nachrichten angezeigt werden.

Oben rechts befinden sich noch weitere Einstellungsmöglichkeiten für die
Console

In der Console kann auch JS-Code ausgeführt werden.

Mit *console.log()* lassen sich aus dem Code Nachrichten und Werte ausgeben.
Mit *console.error()* werden diese als Fehler formatiert und mit
*console.table()* kann man sich die Werte eines Arrays formatiert ausgeben
lassen.

![image11.png](img/image11.png)

### Sources

In Sources werden alle geladenen Inhalte und die Debugging Übersicht
angezeigt.

Durch das Öffnen einer Datei können Breakpoints gesetzt werden.

Alternativ kann man im Programmcode selbst (also in der IDE oder Editor) den
Befehlsaufruf \"debugger;\" hinzufügen um einen Breakpoint zu setzen.

Auf der rechten Seite befinden sich die bekannten
Debugging-Möglichkeiten, wie zum Beispiel das Fortsetzen bis zum
nächsten Breakpoint, Funktionsaufrufe zu überspringen, hinein oder
heraus zu springen.

![image12.png](img/image12.png)

### Network

Zeichnet den Netzwerkverkehr zwischen Webseite und Server auf. Es wird
dabei der Request, Response Header und die benötigte Zeit
aufgezeichnet. Auch der Response Body wird angezeigt und formatiert in
der ab Preview angezeigt.

Es werden auch mehrere Filteroptionen angeboten, um einen Überblick
beim Netzwerkverkehr zu haben.

Wichtig kann auch die Checkbox \"Disable cache\" sein, um mögliche
Fehler beim Entwickeln durch zu strenges Caching des Browsers zu
vermeiden.

![image13.png](img/image13.png)

Weitere Informationen findet ihr hier:
[https://developer.chrome.com/docs/devtools/](https://developer.chrome.com/docs/devtools/)
