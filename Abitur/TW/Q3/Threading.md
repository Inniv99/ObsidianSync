#Q3 #TW Erstellt am 11.12.2024 um 19:03 Uhr

---
### Prinzip
- Threads ermöglichen die gleichzeitige Ausführung von mehreren Programmpfaden innerhalb des Adressraumes eines [[Prozesse]]s
- Sie ändern den sequentiellen Ablauf eines [[Prozesse]]s in einen Parallelen, indem ein Prozess, mehrere Threads enthält, welcher jeweils einen eigenen **program counter**, Registersatz und Stack besitzt
- Alle Threads greifen auf den selben Adressraum zu, weshalb alle die selben globalen Variablen besitzen

![[Pasted image 20241213181210.png]]

#### Gründe für Threading
Sie wurden erfunden um Blockierungen von Prozessen, welche gewisse Dienstleistungen zur Verfügung stellen, zu verhindern

#### Vermeidung von Blockaden
Um Blockaden zu vermeiden, benutzt man **Dispatcher** (Zuteiler)
Diese erstellen bei jeder Anforderung einen neuen Thread, wodurch der Server nur kurz, bei der Erzeugung des Threads blockiert wird. Zusätzlich muss danach jener Thread wieder terminiert werden.
Eine weiterer Methode, um sogar die kurzweilige Blockade zu umgehen, wäre, dass zu Beginn eine Mehrzahl an Threads erzeugt wird und diese bei Nichtbenutzung "schlafen gelegt" werden. Sobald man sie benötigt kann der Dispatcher den Thread wieder ansteuern und es müssen nicht ständig neue Threads erstellt werden. (Word Datei könnte relevant sein)
In C# gibt es sogar eine Klasse ThreadPool dafür

Dabei unterscheidet man in [[Mutex]] oder [[Semaphore]]


#### Unterschied zu [[Prozesse]]#
Threads und Prozesse unterscheiden sich also darin, dass Threads innerhalb eines Prozesses zusammen arbeiten, und die selben globalen Variablen benutzen können. Während ein Prozess nur einen program counter, Stack, etc besitzt, hat jeder Thread innerhalb eines Prozesses seine eigenen.
Threads können parallel ablaufen, während zwei Prozesse nur sequentiell laufen.  Außerdem teilen sich Threads einen Adressraum.
