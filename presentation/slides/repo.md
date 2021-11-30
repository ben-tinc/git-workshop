### Ordner, Repo, Staging-Bereich

Dateien vs Repositories

Note: Die meisten werden mit Verzeichnisbäumen in Dateisystemen vertraut sein. Ordner und Dateien bilden eine Baumstruktur. Wenn ich ein Repository auf Github aufrufe, oder das, was ich dafür halte, sehe ich einen Verzeichnisbaum. Da stellt sich die Frage, was eigentlich der Unterschied ist. Wir werden sehen: was uns Github da anzeigt ist gar nicht das Repository. Aber was ist überhaupt ein Repository?


### Repositories

Note: Erstellen wir uns einmal ein Git-Repo, so wie es viele vermutlich aus
irgendwelchen Tutorials kennen. Zunächst noch im Schnelldurchlauf ohne 
Erläuterungen.


```bash
$ ls
README.md source_code.py
$ git init
$ ls
README.md source_code.py
```

Note: Wir fangen an mit einem Ordner, der einige Dateien enthält. Ist das schon ein Repo? Nee.
Wir benutzen `git init`. Hat sich nichts geändert?? Welche Dateien befinden sich in unserem Repo?
Antwort: noch überhaupt keine.


```bash
$ git add README.md source_code.py
```

Note: Jetzt aber: Welche Dateien befinden sich in unserem Repo? Antwort: immer noch keine.


```bash
$ git commit
```

Note: Puh. Ganz schön viel Aufwand. Warum tun wir uns so etwas an??
Die Grundstruktur von Git mag an dieser Stelle komplex wirken, aber wir werden sehen, dass
sie eine gigantische Funktionsvielfalt über ein recht elegantes Modell verwirklicht. 


### The Three Trees

"Git \[is\] a content manager of three trees."
Scott Chacon & Ben Straub

* **Working Directory**: Die Ordner und Dateien, an denen wir arbeiten. 
* **HEAD**: Der gerade aktuellste 'snapshot' des *Working Directory*, der `git` bekannt ist.
* **Index**: Auch *staging area* genannt; die vorgemerkten Änderungen, aus denen `git` den nächsten *HEAD* konstruieren wird.

Note: Dieser HEAD, oder snapshot, von dem da die Rede ist, wird allgemein als Commit bezeichnet. Ein Commit fasst den kompletten Zustand
eines Dateiverzeichnis zu einem bestimmten Zeitpunkt zusammen.


### Repositories

![](img/reset-workflow.png)

Note: Die allermeisten `git` Befehle lassen sich so verstehen, dass sie in irgendeiner Form jeweils zwei dieser drei Bäume miteinander
vergleichen oder synchronisieren. Schauen wir uns den obigen Prozess noch einmal an, aber diesmal detaillierter.


```bash
# Am Anfang steht ein leeres Repo,
# alle drei Bäume sind identisch.
$ git init
# Wir erstellen zwei neue Dateien.
# Das Working Directory weicht nun ab!
$ echo "# Documentation" > README.md
$ echo "print('hello')" > source_code.py
# Wir synchronisieren WD mit der Staging Area:
$ git add README.md source_code.py
# Wir synchronisieren SA mit dem HEAD:
$ git commit
# Alle drei Bäume sind nun wieder auf dem
# gleichen Stand.
```


Den aktuellen Zustand der drei Bäume liefert uns:

```bash
git status
```