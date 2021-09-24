Git ist ein Versionierungssystem für Dateien und Ordner in einem
Projekt. Die Gesamtheit des versionierten Projektes wird als Repository
bezeichnet. Über Webseiten wie GitHub (<https://github.com>) oder GitLab
(<https://gitlab.com>) ist es möglich, Repositories gemeinsam und
gleichzeitig mit anderen Personen zu bearbeiten.

Das Repository für Verteilte Systeme 1 finden Sie auf GitHub:
<https://github.com/zirpins/vs1lab>

Im Folgenden sind Schritte beschrieben, die Sie zur Nutzung von Git und
GitHub für Verteilte Systeme 1 nutzen können. **Wichtig:** Es besteht
keine Verpflichtung zur Nutzung von Git für die Bearbeitung der
Aufgaben. Wir empfehlen aber dennoch die Verwaltung via Git, da
Kollaboration und Versionierung dadurch erheblich erleichtert werden.

Git kann auch lokal zur Versionierung genutzt werden. Hierzu ist kein
Account notwendig.

Installation von Git

Eine Übersicht zur Installation von Git erhalten Sie hier:

<https://git-scm.com/book/en/v2/Getting-Started-Installing-Git>

Falls Sie direkt zu den Downloads springen möchten, finden Sie diese
hier:

<https://git-scm.com/download>

Git nutzt zur Identifizierung eines Nutzers dessen Namen sowie
Email-Adresse. Nach erfolgreicher Installation können Sie in der
Kommandozeile Ihres Computers folgende Befehle ausführen, um Git zu
konfigurieren:

git config \--global user.name \"John Doe\"\
git config \--global user.email johndoe\@example.org

Verifizieren Sie die Korrektheit der Eingabe im Folgenden durch prüfen
der korrekten Werte:

git config user.name

git config user.email

sollte den von Ihnen gewählten Namen ausgeben.

Das Repository forken

Grundsätzlich haben Sie viele verschiedene Möglichkeiten, mit Git an
einem Projekt zu arbeiten. Wir werden im Folgenden auf die für unseren
Fall am besten geeignete Methode eingehen: Das sogenannte „Forken" des
vs1lab-Repositories.

Beim Forken wird das Repository quasi in ein neues Repository kopiert,
welches dem eigenen Nutzer gehört. In diesem Repository können dann, im
Gegensatz zum Original-Repository von Herrn Dr. Zirpins, auch ohne
Probleme Änderungen vorgenommen werden, ohne das originale Repository zu
verändern.

Melden Sie sich bei GitHub an und navigieren Sie zum Repository „vs1lab"
(Link siehe oben).

Klicken Sie dann auf den Knopf „Fork":

![A screenshot of a computer Description automatically generated with
medium confidence](img/git/image1.png)

Nach dem erfolgreichen „Forken" finden Sie eine Kopie des Repositories
unter Ihrem eigenen Nutzer (Klick auf Profilbild rechts oben, dann „Your
repositories"):

![A screenshot of a computer Description automatically
generated](img/git/image2.png)

Nun muss das Repository noch lokal verfügbar gemacht werden. Hierfür
kann der Befehl

git clone \<URL>

verwendet werden. Öffnen Sie eine lokale Kommandozeile und navigieren
Sie in den Ordner, in dem Sie das Repository lokal ablegen möchten.
Führen Sie dann den Befehl mit der URL zu Ihrem Fork aus:

git clone https://github.com/\<username>/vs1lab

Falls Ihr Fork privat ist, fragt die Git-Anwendung nach Zugangsdaten zu
GitHub.com.

Nach dem erfolgreichen Klonen des Repositories auf den lokalen Rechner
kann nun problemlos (auch mit mehreren Teammitgliedern) parallel am
Projekt gearbeitet werden.

Gemeinsam an Aufgaben arbeiten

Damit mehrere Mitglieder Zugriff auf ein GitHub-Repository haben, muss
dieser zuerst konfiguriert werden. Gehen Sie hierzu in GitHub auf den
Tab „Settings" Ihres Repositories und laden Sie unter dem Punkt „Manage
access" Ihre Teammitglieder ein:

![A screenshot of a computer Description automatically generated with
medium confidence](img/git/image3.png)

Ihre Teammitglieder befolgen dann dieselben Schritte wie aus Abschnitt
2, um das Repository auf ihren lokalen Rechner zu klonen.

Um parallel an Code zu arbeiten, ohne sich gegenseitig zu stören, stellt
Git eine Funktion namens „Branches" bereit. Ein Branch ist vereinfacht
gesagt ein Abbild des Codes zu dem Zeitpunkt, an dem der Branch erstellt
wurde. Änderungen werden dann auf diesem Branch gespeichert und
irgendwann wieder in den Ausgangsbranch zurückgeführt.

Der Hauptbranch bei Git heißt meist „master" (in neueren Repositories
auch „main"). Die Branches selbst können frei benannt werden.

Ein Beispiel: Alice und Bob wollen nach erfolgreichem Klonen des
Repositories auf Ihre lokalen Rechner gemeinsam an der Bearbeitung der
Aufgaben arbeiten. Dazu erstellen beide einen eigenen Branch:

git checkout -b \<branch-name>

(Der Befehl "checkout" wird zum Wechseln von Branches verwendet. Das
Argument „-b" erzeugt dann einen neuen Branch.)

Alice erstellt beispielsweise den Branch „html-und-css", während Bob den
Branch „javascript" erstellt. Beide können nun unabhängig voneinander
Ihre Aufgaben bearbeiten. Doch wie werden Änderungen zwischen Alice und
Bob synchronisiert?

Wenn Alice Änderungen an Ihrem Branch vorgenommen hat, dann muss Sie
diese Änderungen speichern. Git nennt diesen Prozess einen Commit: Es
können bestimmte Änderungen gewählt und gespeichert werden. Hierfür
werden zuerst die Dateien zum sogenannten Index (einer Art
Zwischenspeicher) hinzugefügt, die am Ende im Commit landen sollen. Nach
dem Commit (Der Commit speichert die Änderungen aus dem Index mit
zusammen mit einer Nachricht ab) muss Alice Ihre gespeicherten
Änderungen an GitHub senden. Dieser Prozess nennt sich „Push".

git add \--all

git commit -m \"Beschreibung der Änderung\"

git push

(Möglicherweise beschwert sich Git, dass kein Upstream-Branch existiert.
In diesem Fall müssen Sie explizit angeben, auf welchen Branch der Push
ausgeführt werden werden soll. Für unsere Fälle gibt es keinen Grund,
nicht einfach denselben Branch zu verwenden. Der Push-Command lautet
dann:

git push \--set-upstream origin \<branch-name>

)

Anstelle des Parameters „\--all" können auch einzelne Dateien angegeben
werden. Nach Erfolgreichem Ausführen des Pushes sind die Änderungen auf
GitHub sichtbar. Wenn Bob nun die Änderungen von Alice herunterladen
möchte, so muss er sich zuerst die Änderungen holen, und sie dann in
seinen eigenen Branch integrieren:

git pull

git merge \<alice's-branch-name>

Um sich im Repository zurechtzufinden, gibt es noch einige weitere
Befehle, die zwischendurch nützlich sein können:

git status

> zeigt den Zustand des Repositories, inklusive aller geänderten Dateien
> und Dateien, die zum aktuellen Commit hinzugefügt worden sind

git branch

zeigt den aktuell ausgewählten Branch, sowie weitere verfügbare
Branches.

git log \--oneline \--all

zeigt eine Historie aller vorangehenden Commits.

Sind Alice und Bob mit Ihren Änderungen fertig, so kann der jeweilige
Branch wieder in den Hauptbranch zurückgeführt werden. Hierzu wechselt
man auf den Hauptbranch und integriert dann den jeweils anderen Branch:

git checkout master

git merge \<alice's-branch-name>

Änderungen des Original-Repositories nachladen

Im Laufe der Vorlesung wird das Original-Repository erweitert. In diesem
Fall müssen die Änderungen des originalen Repositories in den Fork
übernommen werden. Hierzu kann eine Referenz auf das originale
Repository hinzugefügt werden, dessen Branches dann nach demselben
Prinzip in den Fork integriert werden können wie oben bereits gesehen.

Das standardmäßige Remote-Repository trägt den Namen „origin" und ist
bereits vorhanden, es referenziert den Fork. Um das vs1lab als neues
Remote-Repository hinzuzufügen, führen Sie den folgenden Befehl aus:

git remote add upstream https://github.com/zirpins/vs1lab.git

Überprüfen Sie danach die Existenz beider Remote-Repositories, indem Sie

git remote -v

ausführen:

![Graphical user interface, text Description automatically
generated](img/git/image4.png)

Danach laden Sie die Änderungen des vs1lab und integrieren Sie in Ihren
eigenen „master"-Branch:

git fetch upstream

git checkout master

git merge upstream/master

Der Master-Branch Ihres lokalen Repositories ist nun aktuell. Wie weiter
oben beschrieben können Sie die Änderungen nun in Ihre eigenen Branches
integrieren. Denken Sie auch daran, git push auszuführen, um den
Teammitgliedern die Änderungen am „master"-Branch zur Verfügung zu
stellen.

Hier ein Beispielablauf:

![Text Description automatically
generated](img/git/image5.png)

Ein Wort zum Tooling

Neben der Kommandozeile, die wir hier kennengelernt haben, gibt es auch
viele grafische Benutzeroberflächen, mit denen dieselben Abläufe
erreicht werden können. WebStorm und VSCode beispielsweise binden direkt
eine Git-Integration ein. Auch GitHub selbst bietet eine grafische
Benutzeroberfläche für das Verwalten von Git-Repositories an. Die Wahl
des Werkzeuges bleibt letztendlich Ihnen überlassen.

Hilfreiche Links

Der einfache Einstieg in Git:
<https://rogerdudler.github.io/git-guide/index.de.html>

Kostenfreier Kurs:
<https://www.udacity.com/course/version-control-with-git--ud123>

Git Dokumentation: <https://git-scm.com/doc>

Fork synchronisieren im Detail:
<https://docs.github.com/en/github/collaborating-with-issues-and-pull-requests/syncing-a-fork>
