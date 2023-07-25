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



