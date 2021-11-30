# Git gud!

#### Über `git`, `github`, und den Unterschied


### What is a repository?

Note: Repositories sind schon länger nicht nur für Software-Entwicklung unabdingbar. Vor allem die "VCS" `git` hat sich zur Standardlösung
entwickelt, um die man heute beinahe nicht mehr herum kommt. Für Nicht-Entwickler:innen ist der Einstieg aber nicht immer ganz einfach.
Mehrere Gründe:

* das Konzept "Versionskontrolle" ist schon sehr alt, und viele Konzepte (aber auch Abweichungen!) sind historisch begründet
* wie allgemein im SD: viele Ansätze und Best Practices lösen Probleme, die wir als Einsteiger:innen noch nie hatten
* sehr viel Jargon
* unklare Begrifflichkeiten


### What is(n't) a repository?

Was ist der Unterschied zwischen einem Repo und

* … einem Dateiverzeichnis?
* … den Dateien in einem Repo?
* … dem aktuellen Stand dieses Repos?
* … dem VCS, das dieses ermöglicht?
* … dem VCS-**Client**, mit dessen Hilfe wir mit dem Repo interagieren?

Note: Das sind alles übrigens weder rhetorische Fragen, noch Fangfragen.
Ich bin überzeugt, dass eine Reihe von Verwirrungen im Umgang mit git daher stammen,
dass Begrifflichkeiten und Konzepte im Alltag unklar verwendet werden.


**Verwirrende Außendarstellung:**

![](img/git-local.png) 


**Verwirrende Außendarstellung (cont.):**

![](img/git-distributed.png)


* **Wo** ist das Repo?
* … und wenn ja, wie viele?

Note: Die folgenden Erläuterungen werden weitgehend plattformunabhängig sein. Es wird in erster Linie um Konzepte gehen.
Beispiele nutzen die CLI Befehle der Git Shell, außer wenn es konkret um Github geht. Viele graphische Git-Clients
und Texteditoren stellen eine Untermenge dieser Funktionalität zur Verfügung, aber um diese zu verstehen brauchen wir das
nötige Vokabular, und die CLI Befehle machen das klarer. 
Außerdem ist der CLI Client von Git in den letzten Jahren sehr gut darin geworden, zu erklären, was gerade passiert und
was die Optionen sind. Diese Erklärungen erfordern ein gewisses Grundverständnis – aber das erarbeiten wir uns ja gerade.
Vielleicht ganz kurz: können wir einigermaßen CLI verstehen?