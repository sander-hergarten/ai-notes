Extensionalität
![[Pasted image 20230724183025.png]]
besagt, dass Mengen x und y gleich sind, falls sie dieselben Elemente enthalten. Das Extensionalitätsaximom besaht also, dass Mengen einfach Kollektionen von Mengen sein, die genau dann als gleich zu erachten sind, wenn sie dieselben Elemente enthalten. 

Aussonderungsschema
besagt, dass für jede beliebige Formel A(z) 
![[Pasted image 20230724183309.png]]
gilt, wobei x und y nicht frei in A sind. Also ist für jede Menge x und jede in der Sprache der Mengenlehre formulierbare Eigenschaft A(z) die Gesamtheit aller z ∈ x mit A(z) eine Menge. Diese ist aufgrund des Extensionalitätsaximos eindeutig bestimmt ist und wird mit dem Term 
![[Pasted image 20230724183557.png]]
bezeichnet. (Dies ist das erste Beispiel für die Konvetion, für eindeutig definierte Objekte Terme als Namen einzuführen, um das Sprechen zu erleichtern)

Man wäre vielleicht versucht das sog. Komprehensionschema zu postulieren: 
![[Pasted image 20230724183725.png]]
wobei x in A(y) nicht frei vorkommt. Allerdings würde durch die Hinzunahme dieses so harmlos erscheinenden Komprehensionsschames ein Widerspruch herleitbar. Sei: 
![[Pasted image 20230724183832.png]], dann gilt offensichtlich  ![[Pasted image 20230724183908.png]], was offensichtlich aus rein logischen Gründen unmöglich ist. 

Man beachte, das Russels Argument nichts anderes als der prädikatenlogische Beweis von ![[Pasted image 20230724184115.png]] 
ist wobei 
![[Pasted image 20230724184153.png]]
gesetzt wurde. Die Widersprüchlichkeit des Komprehensionsschemas ergibt sich nun daraus, dass es zu beweisen gestattet, dass ![[Pasted image 20230724184241.png]] , was im Widerspruch zu ![[Pasted image 20230724184115.png]] steht. Das Problem ist allerdings nicht, dass es für eine Menge x die Menge aller y ∈ x mit A(y) existiert, wie es das Separations- bzw. Aussonderungsschema fordert, sondern die Annahme einer Menge V aller Mengen. Wenn diese nämlich existierte, so gäbe es aufgrund des Seperationsschemas die Menge ![[Pasted image 20230724185641.png]] was, wie Russel gezeigt hat, zu dem Widerspruch ![[Pasted image 20230724185719.png]] führt, da ja R ∈ V. Wir haben also bewiesen, dass ![[Pasted image 20230724185811.png]].  

Dies erscheint auf den ersten Blick verwirrend, da man sich ja Gesamtheiten (von Mengen) wie V oder R durchaus vorstellen kann und sie per se gar nicht als widersprüchlich erscheinen. Sind sie auch nicht: widersprüchlich ist bloß die Annahme, dass solche Gesamtheiten auch immer Mengen sind. Die Gesamtheiten V und R können auch nicht in einer Menge als Teilmenge enthalten sein, da ja sonst aufgrund des Separationsschemas V bzw. R als Mengen existieren würden. Solche großen Kollektionen von Mengen werden üblicherweise als (eigentliche) Klassen bezeichnet, haben jedoch in der Mengenlehre á la Zermelo-Freankel keinen ontologischen Status, was ja auch ganz unnötig ist, da sie durch Prädikate in der Sprache der Mengenlehre ausgedrückt werden können. Es gibt jedoch eine zur Zermelo-Fraenkelschen Mengenlehre ZF equikonsistene auf Gödel, Bernays und von Neumann zurückgehende Klassentheorien GBN, auf die wir hier nicht näher eingehen, in der Klassen einen ontologischen Status haben (d.g. als existierend angenommen werden) und Mengen als diejenigen Klassen definiert werden, die selbst in einer Klasse als Elemente enthalten sind. Selbstverständlich wäre es widersprüchlich, die Existenz einer Klasse aller Klassen anzunehmen, was aber in GBN nicht geschieht. Man beachte, dass das Separationsschema die Existenz der leeren Mengen gewährleistet. Man kann ja beweisen, dass ![[Pasted image 20230724190528.png]]
als auch ![[Pasted image 20230724190616.png]]
aufgrund der Gleichheitsaxiome immer falsch ist. Die Behauptung ![[Pasted image 20230724190644.png]] folgt daraus rein logisch ![[Pasted image 20230724190713.png]]

Dieses y ist eindeutig bestimmt und wird (wie üblich) mit ∅ bezeichnet. 
Bemerkung: Exentsionalität und Separation gestatten und noch nicht außer der leeren Menge irgendwelche anderen Mengen als existent nachzuweisen. Dies sieht man daran, dass in der Struktur M mit ![[Pasted image 20230724190847.png]]
das Extensionalitätsschema und das Separationsschema gelten. 

Paarmengenaxiom 
Das Paarmengenaxiom ![[Pasted image 20230724190946.png]]
besagt, dass es für beliebige Mengen x und y eine Menge z gibt, die gerade x und y als Elemente enthält. Diese aufgrund des Extensionalitätsaxioms eindeutig bestimmte Menge wird (wie üblich) mit
 { x , y }
bezeichnet. Wenn x = y , dann schreiben wir { x } (anstatt { x , x }) für die Singletonmenge, die x als einziges Element enthält. Für { x } gilt offenbar 
![[Pasted image 20230724191222.png]]
Man kann nun für die Paarmengenbildung iterieren und aus x und y die Menge 
< x , y > := {{ x } , { x , y }} 
bilden, die als geordnetes Paar von x und y bezeichnet wird. Es lässt sich leicht zeigen, dass ![[Pasted image 20230724191358.png]], was den Namen "geordnetes Paar" rechtfertigt. Diese auf K. Kuratowski zurückgehende Codierung geordneter Paare entbehrt nicht einer gewissen Willkürlichkeit, weil man ja 
< x , y > genau so gut als {{x,y},{y}} hätte definieren können oder als {{{{x}}}, {{{x}}, y}} 
d.h. als <<x , x > , y> wobei < – , – > wie ursprünglich definiert ist). Es sei bemerkt, dass wir n-Tupel induktiv wie folgt definieren können: 
![[Pasted image 20230724192420.png]]
wobei allerdings < x, y > eine von der ursprünglichen leicht verschiedene Bedeutungen erhält. Es wäre jedoch übertrieben, dies notationell zu unterscheiden!

Vereinigungsaxiom 
Das Vereinigungsaxiom 
![[Pasted image 20230724192534.png]]
besagt, dass es für jede Menge x eine Menge y gibt, die genau diejenigen Mengen z als Elemente enthält, die in irgendeiner Menge u ∈ x als Element enthalten sind. Diese des Extensionalitätsaxioms eindeutig bestimmte Menge y wird wie üblich mit
![[Pasted image 20230724192729.png]] 
bezeichnet. Wenn wir für Mengen x und y die Menge
![[Pasted image 20230724192809.png]] 
definieren  als 
![[Pasted image 20230724192829.png]] 
dann können wir leicht nachweisen, dass ![[Pasted image 20230724193045.png]]
es hier bemerkt, dass wir bereits ohne Paarmengen- und Vereinigungsaxiom Durchschnitt und Differenz von Mengen folgendermaßen definieren können als ![[Pasted image 20230724193138.png]]
Also bilden die Teilmengen einer Menge x einen booleschen Verband bzgl. der Mengeninklusion

![[Pasted image 20230724193311.png]] 
Offensichtlich gilt aufgrund des Extensionalitätsaxiom, dass ![[Pasted image 20230724193456.png]]
Es sei bemerkt, dass wir mithilfe von Pairing und Union beliebige endliche Mengen definieren können, nämlich als ![[Pasted image 20230724193547.png]]
vermittels (externer) Induktion. 
Notation wir schreiben oft abkürzend 
![[Pasted image 20230724193622.png]]
Mithilfe dieser Notation kann das Unionsaxiom folgderndermaßen mulieren: für jede Menge x ist die Klasse 
![[Pasted image 20230724195039.png]]
selbst wieder eine Menge. 
Bemerkung 
Folgendes Modell zeigt, dass Union nicht aus Extensionality, Separation und Pairings folgt sei ![[Pasted image 20230724195207.png]]
eine Bijektion. ![[Pasted image 20230724195242.png]] ![[Pasted image 20230724195255.png]] die Gleichheit auf N und ![[Pasted image 20230724195336.png]]. Man zeigt leicht, dass M Extensionality, Separation und Pairing erfüllt. Da aber in M die Menge ![[Pasted image 20230724195424.png]] nicht existiert, erfüllt M das Axiom Union nicht. 


Potenzmengenaxiom (Power Set)
![[Pasted image 20230724195527.png]]
Besagt, dass die Klasse
![[Pasted image 20230724195544.png]]  
aller Teilmengen einer vorgegebenen Menge x selbst wieder eine Menge ist, die wir (wie üblich) mit P(x) bezeichnen und Potenzmengen von x nennen. Im Falle einer unendlichen Menge x ist die Potenzmenge P(x) etwas unbestimmter Natur, da etwas unklar ist, was eine beliebige Teilmenge von x sein soll. Vermittels des Separationsschemas wird ja bloß die Existenz definierbarer Teilmengen von x sichergestellt. Es hängt vom (implizit) zugrundegelegten Modell ab, welche Teilmengen von x darüber hinaus im Modell auch existieren. Der etwas vage Charakter von p(x) wird inbesondere deswegen problematisch (vom philosophisch-grundlagentheoretischen Gesichtspunkt!) erachtet, weil Teilmengen von x durch Quantifikation über P(x) definiert werden können, ohne dass man genau weiß, welche Elemente über P(x) definiert werden können, ogne das man genau weiß, welche Elemente P(x) denn nun enthält. Dieses Phänomen wird als Imprädikativität bezeichnet. 

Als erste Anwendung des Potenzmengenaxioms zeigen wir, dass für Mengen u,v die Klasse ![[Pasted image 20230724200411.png]]
tatsächlich auch eine Menge ist. Zu diesem Zweck beobachten wir, dass für x ∈ u und 
y ∈ u das Paar
![[Pasted image 20230724200559.png]] 
und somit 
![[Pasted image 20230724200629.png]].  Also ist
![[Pasted image 20230724200654.png]]
aufgrund des Separationsschemas eine Menge. Natürlich können wir für n > 1 auch n-fache Produkte folgendermaßen definieren: 
![[Pasted image 20230724200740.png]]
Offensichtlich gilt: 
![[Pasted image 20230724200755.png]]
Die Elemente von
![[Pasted image 20230724200823.png]]. 
heißen n-stellige Relationen zwischen den Mengen A1,..., An. Offensichtlich ist es in der Sprache der Mengenlehre ausdrückbar, dass eine Menge z ein Paar ist, nämlich durch 
![[Pasted image 20230724201219.png]]. 
Eine Menge R heißt 2-stellige Relation genau dann, wenn 
![[Pasted image 20230724201248.png]]
Für 2-stellige Relationen R sei ihr Definitions- und Wertebereich definiert als 
![[Pasted image 20230724201323.png]]
welche beiden Mengen sind dann dom(R) und rng(R) beide Teilmengen von 
![[Pasted image 20230724201347.png]]
sind. Eine zweistellige Relation f heißt Funktion genau dann, wenn 
![[Pasted image 20230724201859.png]]
Wie üblich schreiben wir meist y = f(x) anstatt ⟨x, y⟩ ∈ f . Wenn f eine Funktion und X eine Menge ist, so sind 
![[Pasted image 20230724202420.png]]
beides Mengen da 
![[Pasted image 20230724202433.png]]
und heißen Bild bzw. Urbild von X unter f. Es sei bemerkt, dass diese Begriffe auch für Klassen Sinn machen. In diesem Fall reden wir von Klassenfunktionen bzw. 2-Stelligen "Klassenrelationen"
![[Pasted image 20230724202529.png]]
![[Pasted image 20230724202549.png]]
selbst eine Menge. Mehrstellige Funktionen werden wie üblich dadurch erfasst, dass man X von der Gestalt X = X1 x ... x Xn wählt. 
Die bisherigen Axiome stellen sicher, dass Mengen unter den üblichen Operationen wie 
![[Pasted image 20230724202701.png]]
abgeschlossen sind. Jedoch können wir mit den bisherigen Axiomen noch nicht die Existenz unendlicher Mengen sicherstellen. Und das mit gutem Grund, da man die Mengen der natürlichen Zahlen irgendwie "erschaffen" muss. Es sei darauf hingewiesen, dass man die Existenz der einzelnen natürlichen Zahlen ![[Pasted image 20230724202919.png]]
durchaus mithilfe der Axiome nachweisen kann, nicht jedoch die Existenz einer Menge, die alle natürlichen Zahlen umfasst. Diese "erschaffen" wir nicht, sondern postulieren sie mithilfe des Unedlichkeitsaxioms. 


Unendlichkeitsaxiom 
Das Unendlichkeitsaxiom postuliert also die Existenz einer induktiven Menge. Es lässt sich zeigen, dass induktive Mengen unter beliebigen nichtleeren Durchschnitten abgeschlossen sind. Somit existiert eine kleinste induktive Menge, die sog. Menge der natürlichen Zahlen, die wir wie üblich mit N oder w bezeichnen.(5) Da N die kleinste induktive Menge ist, gilt für
![[Pasted image 20230724203213.png]]
genau dann, wenn P induktiv ist, d.h. 
![[Pasted image 20230724203237.png]]
![[Pasted image 20230724203301.png]]

worin wir das wohlvertraute Induktionsaxiom für die natürlichen Zahlen (wieder)erkennen, das wir allerdings hergeleitet haben und zwar nicht ziemlich unmittelbar aus der Definition von N . Wir weisen nun noch zwei weitere Eigenschaften von N nach: 
![[Pasted image 20230724203521.png]]
![[Pasted image 20230724203913.png]]


Lemma 1.1 Die Menge N ist transitiv 
![[Pasted image 20230724203941.png]]

Lemma 1.3 Alle Elemente von $\mathbb{N}$ sind transitiv. 
![[Pasted image 20230724204941.png]]

Lemma 1.3 Es gilt $x\notin x$ für alle $x \in \mathbb{N}$. 
![[Pasted image 20230724205402.png]]
Lemma 1.4 $x,y \in \mathbb{N}$ und Sc($x$) = Sc($y$), dann $x=y$ . 
![[Pasted image 20230724205759.png]]


Ersetzungsschema 
Das Ersetzungsschema  besagt das 
![[Pasted image 20230724210549.png]]
wobei A eine beliebige Formel in der Sprache der Mengenlehre ist. Informell heißt dies, dass das Bild einer Menge $u$ unter einer Relation $A(x,y)$, die in der Sprache der Mengenlehre (mithilfe von Parametern) definierbar ist, selbst wieder eine Menge ist sofern $A$ eingeschränkt auf $u$ total und rechtseindeutig ist. Insbesondere dann 
![[Pasted image 20230724210744.png]]
eine Funktion im mengentheoretischen Sinn. 
Man zeigt leicht, dass aus dem Ersetzungsschema folgt, dass 
![[Pasted image 20230724210821.png]]
Aus diesem Schema folgt unmittelbar das Aussonderungsschema, indem man $A(x,y)$ durch $A(x)$ $\land$ $x = y$ instantiiert. Jedoch lässt sich das Aussonderungsschema schon direkt aus dem Ersetzungsschema beweisen. Außerdem lässt sich das Paarmengenaxiom aus dem Ersetzungsschema herleiten. 

Regularitätsaxiom 
![[Pasted image 20230725091739.png]]
d.h. jede nicht leere Menge x besitzt ein " $\in$ - minimales" Element $y$ , das $y \in x$ und $\forall z \in y . z \notin x$ . Weite Teile der Mengenlehre, insbesondere die für die "normale" Mathematik relevanten solchen, lass sich ohne Regularitätsaxiom entwickeln. Jedoch ist das Regularitätsaxiom in der axiomatischen Mengenlehre selbst von großem Nutzen, da es folgendes Prinzip der $\in$ -Induktion für beliebige in der Sprache der Mengenlehre ausdrückbare Prädikate $A(x)$ bereitstellt. 
![[Pasted image 20230725092749.png]]
Andererseits erlaubt das Schema der $\in$ - Induktion, das Regularitätsaxiom herzuleiten und ist somit zu ihm äquivalent. 
Um das Schema der $\in$-Induktion herzuleiten, brauchen wir folgenden Hilfssatz, dessen Beweise eine interessante (und typische) Anwendung des Ersetzungsschemas beinhaltet. 

Lemma 1.5 Für jede Menge x gibt es kleinste transitive Menge  TC(x), die x als Teilmenge enthält

Beweis: Sei 
F$(y,z)$ $\equiv$ $\exists f$ ($f$ ist Funktion) $\land$ $f(y)$ = $z \land$ $f(\emptyset)$ = $x$ $\land$ 
				$\forall u, v ((Sc(u), v)$ $\in f$ $\rightarrow$  $\exists w ((u,w)\in f \land v \cup w)))$ 

Durch Induktion über $\mathbb{N}$ zeigt man leicht, dass
(1) $\forall n \in \mathbb{N}. \exists !z F(n,z)$ 
(2) $F( \emptyset ,x)$ 
(3) $\forall n \in \mathbb{N}. \forall u,v (F(n,u) \land F(Sc(n),v)\rightarrow v = \bigcup u)$ 

Aufgrund des Ersetzungsschemas existiert nun
$M = F(n) \mid n \in \mathbb{N}$ 

als Menge und aufgrund des Vereinigungsaxioms existiert die Menge
$TC(x)=\bigcup M = \bigcup\limits_{n\in \mathbb{N}}F(n)$ 
Offensichtlich ist $TC(x)$ transitiv: wenn $y \in TC(x)$ , dann $y \in F(n)$ für ein $n \in \mathbb{N}$; wenn nun $z \in y \in F(n)$, dann $z \in \bigcup F(n)= F(Sc(n))$ , also $z \in TC(x)$. Sei $u$ eine transitive Menge mit $u \supseteq x$. Dann zeigt man leicht mit Induktion, dass $F(n) \subseteq u$ für alle $n \in \mathbb{N}$, also $TC(x)= \bigcup\limits_{n\in \mathbb{N}}F(n) \subseteq u$.  Somit ist $TC(x)$, die kleinste transitive Menge, die $x$ als Teilmenge enthält (da ja auch gilt, dass $x = F(\emptyset) \subseteq TC(x)$). 

Satz 1.1 Sei $A(x)$ ein in der Sprache der Mengenlehre definierbares Prädikat. 
Dann gilt 
$\forall x ((\forall y \in x. A(y))\rightarrow A(x))\rightarrow \forall x A(x)$ 

Beweis: Angenommen, es gelte
$\forall x ((\forall y \in x. A(y))\rightarrow A(x))$ 

und es gebe eine Menge $x$ mit $\neg A(x)$. Dann gibt es ein $y\in x$ mit $\neg A(y)$ wegen (der Kontraposition von) (3). Sei $M :=$ {$y \in TC(x)\mid \neg A(y)$}. Da $M$ nichtleer ist, gibt es wegen des Regularitätsaxioms ein $y \in M$ mit $y \cap M =\emptyset$, d.h. $\forall y \in y. z \notin M$. Aufgrund der Transivität von $TC(x)$ und $y \in TC(x)$ gilt $\forall z \in y. z\in TC(x)$ und somit $\forall z \in y. A(z)$, woraus mit (3) folgt, dass $A(y)$ im Widerspruch zu $y \in M$. Also haben wir bewiesen, dass $\forall x A(x)$. 
Umgekehrt folgt aus dem Schema der $\in$-Induktion das Regularitätsaxiom, indem man für beliebige Mengen $a$ in dem $\in$-Induktionsschema das Prädikat $A(x)$ durch $x\notin a$ instaniiert. Mit Kontraposition ergibt sich
$$(\exists x.x \in a)\rightarrow \exists x((\forall y \in x. y\notin a)\land x\in a)$$
also das Regularitätsaxiom.

Auswahlaxiom
Das Auswahlaxiom besagt dass
$$\forall x (\emptyset \notin x \rightarrow \exists f (f:x\rightarrow \bigcup x \land \forall y\in x. f(y)\in y))$$
d.h. für jede Menge $x$ nichtleerer Mengen gibt es eine Funktion $f$ mit Definitionsbereich $x$, die aus jeder Menge $y \in x$ ein Element $f(y)\in y$ auswählt. Das Auswahlaxiom hat in der Mathematik einen umstrittenen Status, da es außer seinen vielen nützlichen Konsequenzen auch viele nicht-intuitive Konsequenten nach sich zieht. Das Auswahlaxiom ist allerdings oft äquivalent zu seinen nützlichen Konsequenzen, z.B. dass jeder Vektorraum eine Basis hat. Somit muss man die nicht-intuitiven Konsequenzen hinnehmen, sofern man sich seiner nützlichen äquivalenten Konsequenzen bedienen will. 


Nichtfundierte Mengenlehre 
1.1 Jeder fundierter, azyklisch gerichteter Graph (apg) ist ein Bild einer einzigartigen Menge. 
Welche Mengen haben Bilder? 

1.2. Alle Mengen haben ein Bild. 
Um dies zu sehen, werden wir jeder Menge a ihr KANONISCHES BILD zuordnen. Bilden Sie den Graphen, der als Knoten die Mengen enthält, die in den Folgen $a_{0},a_{1},a_{2}...$ vorkommen, so dass

$$...\in a_{2} \in a_{1}\in a_{0}=a$$

und als Kanten die Knotenpaare (x, y), für die gilt, dass $y \in x$ ist. Wenn a als Punkt gewählt wird, erhalten wir eine apg. Diese apg ist eindeutig ein Bild von a, dessen Dekoration aus der Zuordnung der Menge x zu jedem Knoten x besteht. Man beachte, dass diese Konstruktion nicht voraussetzt, dass die Menge a well founded ist.

Jedes Bild einer Menge kann in ein Baumbild derselben Menge entfaltet werden. Bei einer apg können wir den Baum bilden, dessen Knoten die endlichen Pfade der apg sind, die vom Punkt der apg ausgehen, und dessen Kanten Paare von Pfaden der Form

$$(a_{0}\rightarrow ... \rightarrow a, a_{0}\rightarrow... a\rightarrow a')$$

Unsere bisherige Diskussion diente dazu, das folgende Axiom zu begründen:

Das Anti-Fundierungs Axiom (AFA):
Jeder Graph hat eine einzigartige Dekoration
Bemerkung: 
- Jeder apg ist ein Bild einer einzigartigen Menge
- Nichtfundierte Mengen existieren 
Tatsächlich wird jedweder nichtfundierter apg ein bild sein einer nichtfundierten Menge

Beispiele für nichtfundierte Mengen 
In dem Rest dieses Abschnittes untersuchen wir Bilder von nichtfundierten Mengen unter Annahme des neuen Axioms. Selbstverständlich müssen das Fundierungsaxiom aufgeben, aber es stellt sich heraus, keines der Anderen. 

Beispiel: Erwägen Sie diesen apg
![[Pasted image 20230725133609.png]]
Dies ist ein Bild einer einzigartigen Menge $\Omega$ so dass
$\Omega =$ {$\Omega$} 

Das ist unser erstes Beispiel einer nichtfundierten Menge. Wenn dieser apg entfalten wird, erhalten wir den unendlichen Baum.
![[Pasted image 20230725134032.png]] 

Eine Analogie zum Entfalten der Gleichung würde so aussehen:
Omega = {{{...}}}, wenn der rechte Ausdruck doch nur eine Bedeutung hätte! 
Der obige unendliche Baum und der damit unendlich assoziiert Ausdruck suggerieren das auf eine Art $\Omega$ ein unendliches Objekt ist. Aber ein kurzer Gedanke sollte den Leser davon überzeugen, dass es ein so endliches Objekt ist, wie man es sich nur wünschen kann. Schließlich hat es ein endliches Bild.  Wir können Mengen, die endliche Bilder haben, als HEREDITÄR ENDLICHE Mengen bezeichnen. $\Omega$  hat viele Bilder. 
In der Tat haben wir die folgende Charakterisierung.

1.4. Proposition: Ein apg ist ein Bild von $\Omega$ wenn und nur wenn jeder Knoten der apg ein Kind hat.

Beweis: Angenommen gegeben ist ein Bild $\Omega$ mit einer Wurzel $a$. Lassen Sie $d$ eine Dekoration sein, so dass $da=\Omega$ ist. Jetzt, wenn $b$ ist ein Knoten des Bilds ist, dann muss es einen Pfad von $a=a_0\rightarrow...a_n=b$ , sodass $db= da_{n}\in ... \in da_{0} =da =\Omega$ . Seit $\Omega$ das einzige Element von $\Omega$ ist folgt daraus $db=\Omega$. Seit $\Omega$ ein Element hat folgt, dass $b$ ein Kind haben muss. Daher muss jeder Knoten den Bilds auch ein Kind haben. 
Umgekehrt, angenommen, ein apg mit der Eigenschaft, das jeder Knoten ein Kind hat. Dann ist die Zuordnung von $\Omega$  zu jedem Knoten der apg leicht als eine Dekoration der apg zu erkennen, so dass die apg ein Bild von $\Omega$ ist.

1.5. Beispiel: der apg 
![[Pasted image 20230725140758.png]]
das ist ein Bild der einzigartigen Menge $0^*$ sodass
$$0^{*}= {0,0^*}$$
Wenn entfaltet: 
$$0^*={0,{0,{0,...}}}$$
1.6 Beispiel: Wir haben gesehen, dass jede Menge ein Bild hat. Lassen Sie dies ein Bild der Menge $a$ sein
![[Pasted image 20230725141050.png]] 
Dann ist dies das Bild der einzigartigen Menge $a^*$ , sodass
$$a^*={a,a^*}$$
Wenn $a=0$ ist, bekommen wir den besonderen Fall in Beispiel 1.5.. Nochmal, die obige Gleichung kann entfaltet werden über de offensichtlichen Weg. 

Nehmen wir jetzt diesen besonderen Fall an, dass $a=\Omega$ ist. $\Omega^*$ ist die einzigartige Menge sodass $\Omega^*={\Omega, \Omega^*}$ . Aber $\Omega$ = {$\Omega$} = {$\Omega$,$\Omega$}. Daraus müssen wir schließen, dass $\Omega^*=\Omega$ ist. Selbstverständlich wird das auch klar von den Charakterisierungen der Bilder $\Omega$ vorher. 

1.7. Beispiel: Die geordneten Paare von zwei Mengen sind üblicherweise so repräsentiert: 
$$(a,b)={{a},{a,b}$$ Also die Gleichung 
$$x= (0,x)$$
wird zu:
$$x ={{0},{0,x}$$
Diese Gleichung in einer Variablen $x$ ist in einem offensichtlichen Sinn äquivalent zu dem folgenden System von vier Gleichungen in den vier Variablen $x, y, z, w$.
$x={y,z}$
$y={w}$
$z={w,x}$
$w=0$

Diese Gleichung besteht hält genau dann, wenn folgendes Diagramm der korrekt dekorierte apg ist. 
![[Pasted image 20230725142259.png]]
Daraus folgt, unter AFA des obigen System von vier Gleichungen hat eine einzigartige Lösung und daher hat folgende Gleichung 
$$x={0,x}$$
das folgende eindeutige Bild 
![[Pasted image 20230725142437.png]]
Durch entfalten der Gleichung bekommen wir
$$x=(0,(0,(0,...)))$$


1.8. Beispiel: Wie in Beispiel 1.6. kann das vorherige Beispiel vereinfacht werden,  um zu zeigen, dass die Gleichung $x = (a, x)$ für jede beliebige Menge a
eine eindeutige Lösung $x$ hat
Noch allgemeiner: Für eine beliebige unendliche Folge von Mengen $a_0,a_1,a_2,...$  können wir das folgende unendliche Gleichungssystem betrachten
![[Pasted image 20230725143316.png]]
Es sollte für den Leser eine einfache Übung sein, zu zeigen, dass dieses Gleichungssystem eine eindeutige Lösung hat. Unendliche Ausdrücke für diese eindeutige Lösung können durch "Entfaltung" des Gleichungssystems erhalten werden, um Folgendes zu erhalten
![[Pasted image 20230725143358.png]]
Dieses und andere Beispiele können mit der folgenden Verstärkung der AFA noch einfacher behandelt werden. Ein GELABELTER GRAPH ist ein Graph mit einer Zuordnung einer Menge $a_1$ von LABELN zu jedem Knoten $a\downarrow$.
Eine LABELLED DEKORATION eines gelabelten Graphen ist eine Zuordnung $d$ einer Menge da zu jedem Knoten $a$, so dass 
$$da=(db\mid a\rightarrow b)\cup a \downarrow$$


Das gelabelte AFA 
Jeder gelabelte Graph hat seinen einzigartige Beschriftung. 
Das gewöhnliche Antifundierungsaxiom kann als Sonderfall betrachtet werden, indem man gewöhnliche Graphen als beschriftete Graphen mit einer leeren Menge von Beschriftungen für jeden Knoten betrachtet. Umgekehrt werden wir sehen, dass das gelabelte AFA eine Folge des gewöhnlichen Axioms ist.

Angenommen die gegebene Menge $a_0,a_1,a_2,...$  können wir die Mengen $x_n$ so erhalten, dass $x_n= (a_n,x_n+1)$ for $n= 0,1,...$ auf folgende Weise. 
Betrachten wir den beschrifteten Graphen mit natürlichen Zahlen als Knoten, einer Kante $n\rightarrow n + 1$  für jedes $n$ und Mengen von Beschriftungen, die gegeben sind durch:
$(2n)\downarrow = {{a_n}}, (2n+1)\downarrow= {a_n}.$

Benutzt man jetzt die gelabelten AFA und lässt $d$ die einzigartige gelabelte Dekoration des gelabelten Graphen sein. 

Dann ist für $n=0,1,...$ 
$d(2n)=(d(2n+1))\cup((a_n))$
$d(2n+1=(d(2n+2))\cup(a_n)$

Daraus ergibt sich, wenn $x_n=d(2n)$, dann 
![[Pasted image 20230725152005.png]]
Für jedes $n$. 
Wir haben also die gewünschten Mengen $x_n$ erhalten. Ihre Eindeutigkeit folgt leicht aus der Eindeutigkeit von $d$.
Es gibt eine noch leistungsfähigere Technik, mit der man dieses und andere Beispiele behandeln kann. Diese Technik beinhaltet die Formulierung eines Ergebnisses, das besagt, dass jedes Gleichungssystem eines bestimmten Typs eine eindeutige Lösung hat. Wir können dieses Ergebnis dann einfach direkt auf jedes Beispiel anwenden, ohne dass eine Kodierung erforderlich ist. 

In Anlehnung an die Terminologie von Barwise und Etchemendy wird das Ergebnis im Folgenden als Lösungslemma bezeichnet. Um das Lemma intuitiv ansprechend zu formulieren, müssen wir eine Erweiterung des Universums der reinen Mengen betrachten, die wir bisher betrachtet haben. 
Reine Mengen können nur Mengen als Elemente haben, und diese Mengen sind ebenfalls rein. Die Erweiterung des Universums beinhaltet die Hinzufügung von Atomen und Mengen, die aus ihnen bestehen. 

Atome sind Objekte, die keine Mengen sind und in keiner Weise aus Mengen bestehen, so dass sie keine mengentheoretische Struktur haben. Sie können jedoch bei der Bildung von Mengen verwendet werden. Siehe (Barwise 1975) für eine Diskussion über die Formalisierung der Mengenlehre mit Atomen. In diesem Buch werden Atome als Urelemente bezeichnet. Die Konstruktion eines erweiterten Universums durch Anfügen von Atomen an ein Universum von Mengen und Hinzufügen aller Mengen, die diese Atome in ihren Aufbau einbeziehen können ist analog zur Konstruktion eines Polynomrings aus einem Ring durch Anfügen von Unbestimmtheiten und Hinzufügen aller Polynome in diesen Unbestimmtheiten mit Koeffizienten aus dem Ring. 

Es ist zweckmäßig, davon auszugehen, dass wir über einen reichlichen Vorrat an Atomen verfügen. 
Wir nehmen also an, dass es für jede reine Menge $i$ ein Atom $x_i$ gibt, wobei $x_i≠x_j$ für verschiedene reine Mengen $i, j$. 

Wenn $X$ eine Klasse von Atomen ist, dann nennen wir Mengen, die Atome aus der Klasse $X$ in ihren Aufbau einbeziehen können, $X-SETS$. Das Lösungslemma gilt für ein System von Gleichungen der Form
$x =a_{x}$ ($x \in X$)

wobei $a_x$ eine X-Menge ist für jedes $x \in X$. zum Beispiel ergibt sich bei reiner Menge $a_0,a_1,...$ das Gleichungssystem 

$$x_n(a_n,x_{n+1})  (n=0,1,...)$$
hat die obige Form, wenn wir $X=(x_0,x_1,...)$ und für jedes $n$ nehmen wir an $a_xn$ , dass es $(a_n,x_{n+1})$;  d.h. die X-Menge$((a_n),(a_n,x_n+1))$. In diesem Beispiel ist die Lösung der Gleichung klar. Es muss ein Familie von reinen Mengen $b_0,b_1,...$, eins für jedes Atom in $X$ sein, sodass 
$$b_n=(a_n,b_{n+1})for n=0,1,...$$

Man beachte, dass die rechten Seiten dieser Gleichungen aus den rechten Seiten des ursprünglichen Gleichungssystems gewonnen werden, indem man $b_n$ für jedes Atom $x_n$ einsetzt. Dies legt nahe, wie eine Lösung des allgemeinen Gleichungssystems aussehen sollte. Es sollte eine Familie $\pi=(b_X)_{x\in X}$ von reinen Mengen $b_x$ sein, eine für jedes $x \in X$, so dass für jedes $x \in X$
$$b_x = \hat\pi a_x$$

Hier ist für jede X-Menge $a$, die Menge $\hat\pi a$ diejenige reine Menge, die man aus $a$ erhält, indem man $b_x$ für jedes Vorkommen eines Atoms X in der Zusammensetzung von $a$ ersetzt. $\hat\pi a$ ist also die Substitutionsoperation, die durch das folgende Ergebnis gekennzeichnet ist. 

Substitutionslemma 
Für jede Familie von reinen Mengen $\pi =(b_x)_{x\in X}$ gibt es eine einzigartige $\hat\pi$ Menge a zu jeder X-Menge a so dass 
$$\hat\pi a= (\hat\pi b\mid b-is-an-X-Set, sodass b\in a)\cup(\pi x\mid x \in a \cap X)$$
Wir können nun das angestrebte Ergebnis erreichen. 


Lösungslemma: 
Wenn $a_x$ eine X-Menge für jedes Atom $x$ in der Klasse X der Atome ist, dann ist das Gleichungssystem
$$x=ax (x\in X)$$
eine eindeutige Lösung, d.h. eine eindeutige Familie von reinen Mengen $\pi=(b_x)_{x\in X}$ , so dass für jedes $x \in X$
$$b_x=\hat\pi a_{x}$$
Die obige informelle Diskussion über das Lösungslemma scheint alles zu sein, was man braucht. Eine Ausformulierung wird an das Ende des Kapitels gestellt. 

Systeme
Wir müssen den Begriff des Graphen so erweitern, dass es eine eigene Klasse von Knoten geben kann. Ein SYSTEM ist eine Klasse M von Knoten zusammen mit einer Klasse von KANTEN, die aus geordneten Knotenpaaren besteht. Wir sollten einfach M verwenden, um auf das System zu verweisen, und schreiben, dass $a\rightarrow b$ in M oder einfach $a\rightarrow b$ if $(a,b)$ eine Kante von M ist. 
Ein System M muss die Bedingung erfüllen, dass für jeden Knoten $a$ die Klasse $a_M(b\in M \mid a\rightarrow b)$ der Kindern von a eine Menge ist.

Beachten Sie, dass ein Graph einfach ein kleines System ist. Ein Beispiel für
ein großes System ist das Universum V mit $a\rightarrow b$, wenn $b \in a$. 
Der Begriff der Dekoration eines Graphen erweitert sich auf Systeme in die offensichtliche Weise. Wir erhalten die folgende Verstärkung von AFA.


1.9. Theorem (unter Annahme von AFA)
Jedes System hat eine einzigartige Dekoration. 

Beweis: Lasse M ein System sein. Für jedes $a \in M$ können wir zu $M a$ ein apg zuordnen, das wie folgt aufgebaut ist: 

- Die Knoten und Kanten von $Ma$ sind jene Knoten und Ecken von $M$, die auf den Pfaden von M liegen startend von den Knoten $a$,  und die Punkte von $Ma$ sind die Knoten selbst. 

Dass die Knoten von $Ma$ eine Menge formen, zeigt Folgendes. Lasse $X_0=(a)$ und für jede natürliche Zahl $n$ lass 
$$X_{n+1}=\bigcup(x_{M}\mid x \in X_n)$$
Da $x_M$ eine Menge für alle $x\in M$ ist, ist jedes $X_n$ eine Menge derjenigen Knoten von M, die in M Pfade der Länge n beenden, die vom Knoten a ausgehen. Daher formen die Knoten von $Ma$ die Menge $\bigcup_{n}X_n$ . Durch AFA hat jedes apg $Ma$ eine einzigartige Dekoration $d_a$ so dass $Ma$ ein Bild der Menge $d_{a}a$ ist. Für jedes $x\in M$ sei $da=d_{a}a$. Wir werden zeigen, dass d die einzigartige Dekoration von M ist. Als erstes beobachtet man, dass $a \rightarrow x$ in M dann wird jeder Knoten von Mx auch ein Knoten von Ma sein und die $Ma$ und die Restriktion von $d_a$ auf Mx ist eine Dekoration von Mx und damit gleich dx, die einzige Dekoration von Mx. Wenn also $a \rightarrow x$ in M, dann $d_{a}x=d_{x}x=dx$ 
So ist für jedes $a\in M$, 
$da = d_{a}a$
$=(d_{a}x\mid a \rightarrow in Ma)$
$= (dx \mid a \rightarrow x in M)$
Daher ist d eine Dekoration von M. Um die Einzigartigkeit dieser Dekoration zu sehen, genügt die Feststellung, dass jede Dekoration von M eine Dekoration von jedem Ma sein muss, wenn sie eingeschränkt wird, und daher jedes $d_a$ erweitern muss, so dass es $d$ selbst sein muss. 

GELABELTE SYSTEME und ihre gelabelten Dekorationen werden auf die offensichtliche Weise definiert. Wenn $a \in M$ ist, dann bezeichnet $a \downarrow M$ die Menge der Etiketten bei a im etikettierten System M. Als nächstes verallgemeinern wir das vorige Ergebnis auf etikettierte Systeme. 


1.10. Theorem (angenommen AFA)
Sei M ein gelabeltes System. Sei M' das System das als Knoten alle geordneten Paare (i,a) hat, sodass entweder $i=1$ und $a\in M$ or $i=2$ and $a \in V$ und als Kanten: 
- $(1,a)\rightarrow (1,b) whenever$ $a$ $\rightarrow b$  $\text{in}{} M,$
- $(1,a)\rightarrow(2,b)whenever$ $a$ $\in M$ and $b \in a\downarrow M$, 
- $(2,a)\rightarrow(2,b)$ $whenever$ $b \in a$.
Bei AFA M' hat eine eindeutige Dekoration $\pi$. Also für jedes $a\in M$ 
$$\pi(1,a) = (\pi(1,b)\mid a \rightarrow b in M)\cup (\pi(2,b)\mid b \in a \downarrow M)$$
und für jedes $a\in V$
$$\pi(2,a) = (\pi(2,b)\mid b \in a)$$
Beachte dass die Zuschreibung der Menge $\pi(2,a)$ für jedes $a \in V$ ist eine Dekoration in dem System V so dass bei AFA $\pi(2,a)=a$ für alle $a \in V$. Daher lassen wir $\tau a = \pi(1,a) für a \in M$ dann, für $a\in M$, 
$$\tau a=(\tau b\mid a \rightarrow b in M) \cup a \downarrow M,$$
so dass $\tau$ eine gelabelte Dekoration des gelabelten Systems M ist. 
Für die Einzigartigkeit von $\tau$ suppose that $\tau '$ ein gelalbte Dekoration des gelabelten System M ist. Dann ist $\tau '$ eine Dekoration des System M' wobei

$\pi '(1,a) = \tau ' a$ für $a\in M$,
$\pi (2,a)= a$ für $a \in V$

Es folgt AFA, dass $\pi '=\pi$ sodass für $a\in M$
$$\tau 'a= \pi '(1,a) = \pi (1,a) = \tau a,$$
und daraus
$$\tau'=\tau$$
Als Nächstes geben wir ein allgemeines Ergebnis an, das dann zum Beweis des
die Substitutions- und Lösungslemmata zu beweisen.


1.11. Theorem: 
Sei M ein gelabeltes System, dessen Labelmengen Teilmengen der Klasse X sind. 
(1) Wenn $\pi:X\rightarrow V$ , dann gibt es eine einzigartige Karte $\hat\pi:M\rightarrow V$ sodass für jedes 
$a\in M$
$$\hat\pi a=(\hat\pi b \mid a \rightarrow b in M )\cup(\pi x\mid x \in a\downarrow M).$$
(2) Gegeben $a_{x}\in M$ for $x\in M$ existiert eine einzigartige Karte $\pi:X\rightarrow V$ so dass 
für alle $x\in X$
$$\pi x = \hat\pi a_{x}.$$
Beweis: 
(1) Für jedes $\pi: X \rightarrow V$ sei $M_\pi$ das man aus M erhält, indem man die Mengen der Etiketten so umdefiniert, dass für jeden Knoten a
$$a\downarrow M_{\pi}= (\pi\mid x \in a \downarrow M).$$
Dann ist die erforderte einzigartige Karte $\hat\pi$ , die einzigartig gelabelte Dekoration von $M_\pi$ 

(2) Sei M' das System  mit den gleichen Knoten wie M, und allen Kanten M und den Kanten $a\rightarrow a_x$ immer, wenn $a\in M$ und $x\in a\downarrow M$. Bei Theorem 1.9 hat M' eine einzigartige Dekoration $\varphi$ . Also für jedes $a\in M$
$$\varphi a = (\varphi b \mid a \rightarrow b in M)\cup (\varphi a_{x}\mid x \in a \downarrow M).$$
Sei $\pi x = \varphi a_x$ für $x\in X$. Dann ist $\varphi$ eine gelabelte Dekoration des gelabelten System $M_\pi$ , sodass $\varphi =\hat\pi$ and hence $\pi x = \varphi a_x$ für $x\in X$. Für die Einzigartigkeit von $\pi$ let $\pi ': X \rightarrow V$ sodass $\pi 'x= \hat\pi 'a_{x}$ für $x \in X$. Then observe that $\hat\pi '$ is a decoration of M' , sodass $\hat\pi '=\varphi$ and hence $\pi'=\varphi$ and hence $\pi'x=\hat\pi'a_{x}=\varphi a_{x}=\pi x$
for $x \in X.$ Also $\pi'=\pi$.


Beweis für die Substitution und Lösungslemma 
Die informelle Darstellung des Substitutions- und Lösungslemmas, die wir gegeben haben, kann auf der Grundlage des Axiomensystems für die Mengenlehre, mit dem wir implizit gearbeitet haben, nicht auf direktem Wege rigoros gemacht werden. Anstatt dieses Axiomensystem so zu modifizieren, dass es für das erweiterte Universum mit Atomen geeignet ist, werden wir ein Modell des erweiterten Universums innerhalb des Universums der reinen Mengen geben. Wir werden die reinen Mengen $x_i=(1,i)$ als die Atome in dem Modell verwenden und sie *-Atome nennen. Die Mengen des Modells werden *-Mengen genannt und sind bestimmte reine Mengen der Form (2, u). Wenn $a = (2, u)$ ist, dann sei $a^* = u$. Die Elemente von $a^*$ werden die *-Elemente von a genannt. Die Klasse der *-Mengen ist definiert als die größte Klasse von Mengen der Form (2, u), so dass jedes *-Element einer *-Menge entweder ein *-Atom oder eine *-Menge ist. Wir werden hier nicht aufhören, die Existenz einer solchen größten Klasse zu zeigen, sondern verweisen den Leser auf Theorem 6.5. Bei einer Klasse X von *-Atomen definieren wir auch die Klasse der X-Mengen als die größte Klasse von *-Mengen, so dass jedes *-Atom in einer X-Menge in X enthalten ist. Die X-Mengen bilden nun die Klasse der Knoten eines beschrifteten Systems M, wobei für jeden Knoten a

$a_{M}= M \cap a^*$,
$a \downarrow M = X \cap a^*$.

We may apply the two parts of theorem 1.11 to this labelled system to obtain proofs of the substitution and solution lemmas, except that in the right hand side of the characterising equation for $\hat\pi a$ in the substitution lemma, the set $a$ must be replaced by the set $a^*$. This slight revision of the substitution lemma is needed as we are not really expanding the universe but only using a model of an expanded universe.




2| The Axiom in more Detail 
- $AFA_1$ Every graph has at least one decoration
- $AFA_2$ Every graph has at most one decoration


Bisimulations
What sort of relation is $\equiv$ ? Um diese Frage zu beantworten brauchen wir folgende fundamentale notion. Eine binäre Relation $R$ auf dem System $M$ ist eine BISIMULATION auf $M$, wenn $R \subseteq R^{+} , \text{where for},  a,b \in M$
$$aR^{+}b \Leftrightarrow \forall x \in a_{M}\exists y\in b_{M}xRy - \text{and}- \forall y \in b_{M}\exists x \in a_{M}xRy.$$

Beachte, dass wenn $R_{0}\subseteq R$ dann ist $R^{+}_{0} \subseteq R^+$  ; i.e. die operation ()^+ ist monoton. 


2.4 Theorem: Es gibt eine eindeutige maximale Bisimulation $\equiv _M$ auf jedem System $M$; i.e. 
(1)$\equiv _M$ is eine Bisimulation auf $M$,
(2) Wenn $R$ eine Bisimulation auf $M$ dann  für alle $a,b\in M$ 
$$aRb\Rightarrow a\equiv _Mb.$$
Tatsächlich: 
$$ a\equiv _Mb \Leftrightarrow aRb   \text{     for some small bisimulation R on M.}  $$

Die Relation $\equiv _M$ wird auch manchmal schwache bzw. größte Bisimulation genannt auf $M.$


Beweis: Sei $\equiv _M$ definiert wie oben. Wir beweisen (1) und (2). Für (1), lassen wir $a\equiv _{M}b$ sein. Dann $aRb$ für eine kleine Bisimulation $R$ auf $M$. 
Beachte, dass trivial: 

$$xRy \Rightarrow x \equiv _{M}y  \text{ for all } x,y \in M.$$

sodass bei monotonicity of ()$^+$

$$xR^{+}y \Longrightarrow x \equiv_{M}y \text{ für alle } x,y \in M $$

Als $aRb$ und $R \subseteq R^+$ folgt, dass $a \equiv _{M}^{+}b.$ Für (2) sei $R$ eine Bisimulation auf $M$ and $aRb.$ Verweis auf Theorem 1.9., dass für jedes $x \in M$ $Mx$ ein apg mit dem Punkt $x$ ist sodass für $u,v \in Mx$
$$u \rightarrow v \text{ in }Mx \Leftrightarrow u\rightarrow v \text{ in } M. $$
Das ist einfach zu überprüfen, wenn
$$R_{0}= R \cap((Ma)\times(Mb))$$
dann ist $R_0$ eine Bisimulation auf A sodass $aR_{0}b.$ Weiter, seit $Ma$ und $Mb$ klein sind, ist die Bisimulation $R_0$ klein. Also $\equiv_{M}b.$

2.5 Proposition Für alle Mengen $a,b$
$$a\equiv b \Leftrightarrow a\equiv _{V}b.$$

Beweis: Weil $\equiv$ eine Bisimulation auf $V$ und $\equiv_V$ ist  maximale Bisimulation auf $V$ is, folgt die Implikation, dass von links nach rechts richtig ist. Für die umgekehrte Implikation reicht es zu zeigen, dass wenn $R$ eine Bisimulation auf $V$ ist dann für alle Mengen $a,b$
$$aRb \Longrightarrow a \equiv b.$$
So sei $R$ eine Bisimulation auf $V$. Definiere das System $M_0$ wie folgt. Die Knoten von $M_0$ sind die Elemente von R; i.e. sind die geordneten Paare (a,b) sodass $aRb$. Die Kanten von $M_0$ sind definiert als 
$$(a,b)\rightarrow (x,y)\text{ in }M_{0}\Longleftrightarrow x \in a \text{ |-and-| } y \in b.$$

Jetzt beobachte, dass $d_1$ und $d_2$ beides Dekorationen von $M_0$ sind, wo für $(a,b) \in M_0$
$d_1(a,b)=a,$
$d_2(a,b)=b$.

Also, wenn $aRb$ ist dann ist der apg $M_0(a,b)$ ein Bild von beiden $a$ and $b$, der die Restriktionen von $d_1$ und $d_2$ zu dem apg nutzt. Daher, wenn $aRb$ dann $a\equiv b$. 
Die Fakten der folgenden Aufgabe werden nützlich sein beim zeigen, das die maximale Bisimulation Relation auf ein System ist eine Äquivalenz Relation. 

Zeige das, wenn $M$ ein System ist, dass
wenn $R_{1},R_{2}\subseteq M \times M$ dann 
$R_{1}^{+}\mid R_{1}^{+2}\subseteq (R_{1}\mid R_{2})^+$ 


Beweis:

1. Also, $(a, b)$ ist ein Element von $R_1^+ \mid R_2^+$. DAs bedeutet, dass es Paare in $M$ gibt, aus $a$  und  $b$ , und alle aufeinanderfolgenden Paare sind in $R_1$ oder $R_2$.
    
2. Da die Union $R_1 \mid R_2$  alle Elemente von $R_1$ und alle Elemente von $R_2$ enthält, ist das dann auch in der transitiven Hülle von $R_1 \mid R_2$.
    
3. Daher ist $(a, b)$ auch ein Element von $(R_1 \mid R_2)^+$.
    

Da dies für jedes Element in $R_1^+ \mid R_2^+$ so ist, kommt raus $R_1^+ \mid R_2^+ \subseteq (R_1 \mid R_2)^+$.


2.7 Proposition 
Für jedes System $M$ ist die Relation $\equiv_{M}$ eine Äquivalenzrelation auf $M$ sodass für alle $a,b\in M$ gilt
$$a\equiv_{M}^{+}b \Leftrightarrow a \equiv_{M}b.$$
Beweis:
Das $\equiv _{M}$ eine Äquivalenzrelation ist, ist eine einfache Anwendung der letzten Aufgabe. Seit $\equiv_{M}$ eine Bisimulation ist, haben wir die Implikation von rechts nach links. Seit dem die Operation $\text{()}^+$ monoton ist, folgt dass $\equiv_{M}^{+}$ auch eine Bisimulation ist. Seit $\equiv_M$ die maximale Bisimulation ist erhalten wir die Implikation von links nach rechts. 


2.8 Aufgabe 
Wenn $M$ ein System ist, zeige, dass für all $a,b \in M$

(i) $a_{M}= b_{M} \Rightarrow a\equiv_{M}b,$ 
(ii) $M_{a}\cong M_{b}\Rightarrow a\equiv_{M}b.$

In (ii) $M_a$ ist die der apg, der in 1.9. aus $M$ and $b$ bewiesen wurde, $\cong$ ist die Ismorphismusrelation zwischen den apg. 

Ein System $M$ ist EXTENSIONAL, wenn für alle $a,b \in M$
gilt: $$a_{M}= b_{M}\Longrightarrow a=b.$$
und es ist STARK EXTENSIONAL, wenn für alle $a,b \in M$
gilt:$$a \equiv_{M}b \Longrightarrow a=b$$
2.9 Aufgabe 
Zeige: 
$$ AFA_{2} \Longleftrightarrow AFA_{2}^{ext},$$
wo $AFA_{2}^{ext}$ ist: 
Jeder exetensional Graph höchstens eine Dekoration hat 
Beachte, dass bei 2.8(i) jedes stark extensional System extensional ist. Beachte, dass bei dem Extensional Axiom das System $V$ extensional ist. Für das nächste Ergebnis drückt $AFA_{2}^{ext}$ eine Stärkung des Extensional Axiom aus. 


2.10 Proposition $AFA_{2}\Leftrightarrow V$ ist stark extensional. 

Beweis: Zunächst nehmen wir an, dass $AFA_2$ und lassen $a\equiv_{V}b$. Wegen der Aufgabe 2.5   $a\equiv b$  sodass der Graph $G_n$ und Dekorationen $d_1$ und $d_2$ von $G$ entsteht, sodass $d_{1}n = a$ und $d_{2}n=b$. Bei $AFA_{2}$ $d_{1}=d_2$ so dass $a=b$. Daher ist $V$ stark extensional. 
Umgekehrt sei $V$ stark extensional sein und lass $d_1$ und $d_2$ Dekorationen von $G$ sein.
Wenn $x \in G$ dann ist $d_{1}x \equiv d_2{x}$ , seit $Gx$ ein Bild von $d_{1}x$ und $d_{2}x$ ist. Daher bei Aufgabe 2.5.    $d_{1}x \equiv_{V}d_{2}x$   , sodass $d_{1}x = d_{2}x$ ist, so ist $V$ stark extensional. Daraus $d_{1}=d_2$ ,  somit ist $AFA_2$ bewiesen. 

Sytem Karten 
A SYSTEM MAP from the system $M$ to the System $M'$ is a map $\pi : M \rightarrow M'$ such that for $a\in M$
$$(\pi a)_{M'}= {\pi b \mid b\in a_{M} }.$$
If $\pi$ is a bijection then the it is a SYSTEM ISOMORPHISM. 
