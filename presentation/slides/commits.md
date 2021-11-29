### Commits

* Momentaufname unseres Arbeitsverzeichnisses zu einem bestimmten Zeitpunkt
* Abfolgen von Commits bilden zusammen die *History* des Repos. Eine solche Abfolge wird, falls sie sich nicht verzweigt, auch "Branch" genannt

```bash
git log -3
```


### Commits 

* werden identifiziert über einen eindeutigen *Hash* Wert, z.B. "afa31d694073f0c695ab39993aa28e2a9f0349c1"
* Alternativ können Commits über ihren Abstand zum aktuellen *HEAD* Commit angegeben werden:
    * HEAD hat immer das Kürzel "@"
    * vorherige Commits werden mit `~` angesprochen: `@~` ist der vorletzte Commit, `@~2` der vor-vorletzte etc. 

```bash
git show HEAD~2
```

Note: Jedes Repo enthält immer seine vollständige History, d.h. jeden Zustand von jeder Datei, der git jemals
bekannt gemacht wurde! Außerdem ist zu bemerken, dass wir noch immer nicht über Netzwerke, Internet etc. gesprochen haben. Eine erste Ahnung davon, was mit "everything is local" gemeint sein könnte.