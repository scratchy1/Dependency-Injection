# Dependency-Injection
Die konsequente Verwendung von Interfaces in Variablen- und Methodendeklarationen erlaubt
es, die Anzahl der Referenzierungen anderer Klassen und damit die Abhängigkeit von
diesen (bzw. die damit verbundene Kopplung) zu verringern. Es bleibt jedoch die Abhän-gigkeit von einer Klasse, die durch den Aufruf des Konstruktors zum Zwecke der Erzeugung einer Instanz dieser Klasse entsteht. Diese lässt sich durch die sog. Dependency injection eliminieren.
Sehr häufig findet man in Klassen, die sich Instanzen einer anderen Klasse als Server halten, Code der Art 
Server server = new Server();
Dabei nützt es dann nichts, wenn man den Typ der Variable in ein geeignetes Client/Server-Interface, also etwa wie in
IServer server = new Server();
abändert, denn dann wird ja immer noch die Klasse direkt referenziert. Es ist auch der Kon-struktoraufruf zu entfernen.
Die Lösung der Dependency injection besteht nun darin, die benötigte Instanz nicht von dem abhängigen Objekt
(im obigen Beispiel das, das die Variable server besitzt) selbst, per Konstruktoraufruf, erzeugen zu lassen, sondern sie von außen in dieses hineinzubrin-gen,
eben zu injizieren. Mit dem Konstruktor verschwindet dann auch die Abhängigkeit von einer bestimmten Klasse (die mit der Dependency injection somit eliminiert wird);
die Ab-hängigkeit von einem anderen Objekt besteht jedoch weiter.
In Abhängigkeit davon, wie das Objekt injiziert wird, unterscheidet man verschiedene Arten von Dependency injection.
Die gebräuchlichsten nennen sich Constructor injection, Setter injection und Interface injection
