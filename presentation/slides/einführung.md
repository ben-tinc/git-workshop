### (Sehr kurze) Einführung

* `git` wurde TODO von Linus Torvalds entwickelt
* Motivation: existierende Lösungen unbefriedigend für Linux Projekt
    * Geschwindigkeit
    * \> 1000 Entwickler:innen
    * verteilte Entwicklung
* Tool "by developers for developers"
* Idee: "everything is local"

Note: Historisch war es so, dass VCS ein zentrales Repository bereitstellten, mit dem sich alle Nutzer:innen verbinden mussten, um ihre eigenen Änderungen einzuspielen. Dies war langsam, und das einzelne Repo war ein single-point-of-failure. Mit Git haben stattdessen alle Beteiligten ein eigenes, autonomes Repo. Diese lassen sich differenziert miteinander synchronisieren, ansonsten funktionieren sie aber unabhängig voneinander.