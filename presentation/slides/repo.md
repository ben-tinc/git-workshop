### Ordner, Repo, Staging-Bereich

Dateien vs Repositories

Note: Die meisten werden mit Verzeichnisbäumen in Dateisystemen vertraut sein. Ordner und Dateien bilden eine Baumstruktur. Wenn ich ein Repository auf Github aufrufe, oder das, was ich dafür halte, sehe ich einen Verzeichnisbaum. Da stellt sich die Frage, was eigentlich der Unterschied ist. Wir werden sehen: was uns Github da anzeigt ist gar nicht das Repository. Aber was ist überhaupt ein Repository?


### Repositories

![](img/screenshot-git-init.png)

![](img/screenshot-git-init-after.png)

Note: Wir fangen an mit einem Ordner, der einige Dateien enthält. Ist das schon ein Repo? Nee.
Wir benutzen `git init`. Hat sich nichts geändert?? Doch! Es wurde der Ordner `.git/` erstellt.
Er enthält weitere Ordner und Dateien – das ist das eigentliche Repository.


```bash
$ ls
README.md source_code.py
$ git init
$ ls
README.md source_code.py
$ ls -A
.git/ README.md source_code.py
$ ls .git/
branches  config  description  HEAD  hooks  info 
 objects  refs
```

Note: Fangfrage: Welche Dateien befinden sich in unserem Repo? Antwort: noch überhaupt keine.
Dateiverzeichnis und Repo sind unabhängig voneinander. Derzeit werden noch keine Dateien getracked.


```bash
$ git add README.md source_code.py
```

Note: Befinden sich die Dateien jetzt in unserem Repo? Naja, eigentlich immer noch nicht.
Wir haben sie nur vorgemerkt zum nächsten "Commit". Derzeit befinden sie sich in der Staging
Area.


```bash
$ git commit
```

Note: Das, was zuvor in der Staging Area war, bildet nun den ersten Commit. Ein Commit beschreibt den
Unterschied zwischen dem was vorher war, und was nun ist. Alle Commits eines Repos bilden zusammen
seine History, und damit auch den letztendlichen Zustand der Dateien im Repo. Ein Commit wird identifiziert
entweder über den Abstand zum Status Quo (HEAD), oder durch einen eindeutigen Hash-Wert.


### The Three Trees

"Git \[is\] a content manager of three trees."
Scott Chacon & Ben Straub

* HEAD: the latest commit
* Index: staging area, soon to be the next commit
* Working Directory: sandbox; whatever I have done since my latest commit


### Repositories

![](img/reset-workflow.png)