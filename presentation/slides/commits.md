### Commits

* Momentaufname unseres Arbeitsverzeichnisses zu einem bestimmten Zeitpunkt
* Abfolgen von Commits bilden zusammen die *History* des Repos. Eine solche Abfolge wird, falls sie sich nicht verzweigt, auch "Branch" genannt
* wenn nichts anderes konfiguriert wurde, ist der anfängliche Branch unter dem Namen `master` identifizierbar.

```bash
# Zeige Zusammenfassung der 3 letzten Commits
git log -3
# Zeige alle Commits, die README.md modifiziert haben
git log --follow README.md
```


### Commits 

* werden identifiziert über einen eindeutigen *Hash* Wert, z.B. "afa31d694073f0c695ab39993aa28e2a9f0349c1"
* Alternativ können Commits über ihren Abstand zum aktuellen *HEAD* Commit angegeben werden:
    * HEAD hat immer das Kürzel "@"
    * vorherige Commits werden mit `~` angesprochen: `@~` ist der vorletzte Commit, `@~2` der vor-vorletzte etc. 

```bash
# Zeige History ab einem bestimmten Commit
git log afa31d6   # unvollständig, OK!
# Zeige die Änderungen, die der vor-vorletzte
# Commit vorgenommen hat.
git show HEAD~2
```

Note: Jedes Repo enthält immer seine vollständige History, d.h. jeden Zustand von jeder Datei, der git jemals
bekannt gemacht wurde! Außerdem ist zu bemerken, dass wir noch immer nicht über Netzwerke, Internet etc. gesprochen haben. Ich habe Github noch nicht einmal erwähnt! Eine erste Ahnung davon, was mit "everything is local" gemeint sein könnte.


### Checkouts

`git checkout` gleicht unser Arbeitsverzeichnis an den Zustand eines Commits (oder den HEAD eines Branches) an.

```bash
# Synchronisiere Arbeitsverzeichnis mit dem
# vorletzten Commit
git checkout @~
# zurück zum letzten Zustand des master branchs
git checkout master
```

Note: Auch hier greift wieder unser mentales Modell mit den drei Bäumen.