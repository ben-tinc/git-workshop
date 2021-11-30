### Branches

* eines der wesentlichen *design goals* von git: höchst effizientes und simples Arbeiten mit (falls gewünscht) Unmengen an branches.
* branches sind einfach Abfolgen von Commits, zusammen mit einem Namen (z.B. 'main')
* wir benutzen schon die ganze Zeit branches (bzw. genau einen: per default 'master')


### Abzweigen

```bash
# Liste existierende branches auf
$ git branch
# Erstelle neuen branch, identisch zum aktuellen
$ git branch mybranchname
# Synchronisiere Arbeitsverzeichnis und branch
$ git checkout mybranchname
# Neue commits werden nun an den neuen branch angehängt
#  ...
# Wenn wir zurück zum alten branch wechseln hat sich
# dort nichts geändert
$ git checkout master
```


### Wieder zusammenführen


![](img/01-forked-history.svg)

Quelle: [https://www.atlassian.com/git/tutorials/merging-vs-rebasing](https://www.atlassian.com/git/tutorials/merging-vs-rebasing)


Was sind unsere Optionen, diese branches wieder zusammen zu führen?

Note: Denken wir da kurz drüber nach, ohne Rücksicht darauf, wie eine Software wie git das bewerkstelligen würde. Wir können

* Änderungen einfach verwerfen
* Nicht im Bild, aber möglich: einfach vorspulen
* eine neue Änderung erstellen, die genau aus den Differenzen von Br 1 und Br 2 besteht
* wir können einen branch komplett neu aufbauen, auf Basis des vollständigen aktuellen zweiten branches


**Änderungen verwerfen**

```bash
git branch -d mybranchname
```


![](img/02-merge-commit.svg)

Note: Diese Option erstellt einen völlig neuen Commit, der vorher weder Teil von Main, noch von Feature war. Dieser enthält die nötigen Anpassungen, um die Änderungen zusammen zu führen. Das erscheint unästhetisch, aber es ist non-destruktiv!


![](img/03-rebasing.svg)

Note: Hier gibt es keinen separaten Merge-Commit. Stattdessen müssen *alle* (!) Commits von Feature neu erstellt werden, sodass sie die Änderungen auf Grundlage des aktualisierten Main, statt auf Grundlage des alten Main, enthalten.
Auf den ersten Blick scheint das nur Vorteile zu bieten. Aber es lauern auch Gefahren, weil wir effektiv die *History* von Feature umschreiben!! Wir verlieren Kontext, und möglicherweise haben sich andere bereits auf die History verlassen... 


### "The Golden Rule of Rebasing"

**Never** rebase public branches!

![](img/05-rebase-catastrophe.svg)

Note: The rebase moves all of the commits in main onto the tip of feature. The problem is that this only happened in your repository. All of the other developers are still working with the original main. Since rebasing results in brand new commits, Git will think that your main branch’s history has diverged from everybody else’s.

The only way to synchronize the two main branches is to merge them back together, resulting in an extra merge commit and two sets of commits that contain the same changes (the original ones, and the ones from your rebased branch). Needless to say, this is a very confusing situation.

Aber: rebase kann sehr schön sein, um rein lokale branches "aufzuräumen". Das führt aber für heute etwas zu weit.