# Regler för Schack 2
Detta dokument utgör regelverket för Schack 2, en modifierad uppföljare till det urgamla brädspelet schack. 
## 000. Ändring av regler
001\. Ändringar till detta dokument i `main` kräver godkännande från samtliga styrelsemedlemmar. För att föreslå ändringar, skapa en personlig branch.

002\. För nuvarande är styrelsemedlemmar David Cedermark (@david01000011), Axel Gustavsson (ANVÄNDARNAMN) och Ludvig Ahnlund Groiss (ANVÄNDARNAMN).

003\. Spelets regler utgår från Schack 1. Se dess regler hos FIDE. Skillnader finns dock.
## 100. Grundläggande spelkoncept
101\. Spelet spelas av två spelare, där den ena innan spelet börjar bestäms vara vit och den andra svart. Denna bestämning kan ske på något sätt som båda spelarna är överens om. Tre resultat är möjliga när spelet tar slut: Att endera spelare vinner och den andra förlorar, eller att spelet är oavgjort. Spelet är slut när något av detta händer, och om en spelare vinner, så förlorar den andra. Om en spelare förlorar, så vinner den andra.

102\. En spelare kan när som helst ge upp spelet genom att säga "Jag ger upp", avsiktligt välta sin kung, eller på annat sätt otvetydigt kommunicera avsikt att ge upp. När en spelare ger upp tar spelet omedelbart slut och den spelaren som gav upp först förlorar.

103\. Spelet innehåller följande objekt:

103a. Ett bräde. Brädet har 64 rutor i ett kvadratiskt mönster. 32 är vita och 32 är svarta. Rutorna är numrerade 1 till 8 i vågräta rader (vinkelräta mot en linje mellan spelarna) och a till h i lodräta kolumner (parallella med en linje mellan spelarna). Sett från rad 1 är a-kolumnen till vänster. a1 är en vit ruta, och alla rutor är motsatt färg till direkt intilliggande rutor (ett vågrätt eller lodrätt steg ifrån).

103b. Pjäser. Pjäser har flera egenskaper, se regel 201.

103c. Rutor. Rutor är en del av brädet. Varje ruta är antingen blockerad, halvblockerad, fri eller otillgänglig för en pjäs. En pjäs kan inte göra ett drag till en ruta om rutan är blockerad eller otillgänglig för den pjäsen. Blockerade eller halvblockerade rutor påverkar också linjerörelse, se regel TBA. Om inte en annan regel ändrar på detta så är en ruta utan pjäser fri för alla pjäser, och en ruta med en pjäs på är blockerad för pjäser med samma färg och halvblockerad för pjäser med motsatt färg. Om flera pjäser av olika färg är på samma ruta så är en av dem huvudpjäs (bestämt av regeln som orsakade detta) och tillgängligheten på rutan är densamma som om enbart huvudpjäsen stod där. Varje ruta har en position som också är en benämning på rutan. 1 är den lägsta raden och a är den lägsta kolumnen. En ruta kan också ha vissa tillstånd om en regel ger dem det. Tillgänglighet är inte ett tillstånd.

104\. Innan spelet börjar ställs pjäserna upp på brädet enligt rådande startposition och spelarnas färg utses (kan ske i endera ordning, men vit bör sitta vid sidan närmast rad 1 och svart närmast rad 8. När spelet börjar är det vits tur. Om klocka används är det alltid den spelare vars tur det är vars tid ska räknas. När det är en spelares tur kan den spelaren göra ett drag, vartefter den spelarens tur är över och det blir motspelarens tur. Om ett drag görs "som deldrag" så är det endast en del i utförandet av ett annat drag, och instruktionerna för draget utförs utan att det räknas som ett drag i sig eller avslutar spelarens tur. Ett drag som instruerar ett eller flera deldrag räknas fortfarande som ett drag.
## 200. Pjäserna
201\. Aspekter av en pjäs

201a. En pjäs har följande egenskaper:

201b. En ruta på brädet som är pjäsens position. Att förflytta en pjäs är detsamma som att ändra dess position.

201c. Upp till en färg som motsvarar vilken spelare som styr pjäsen och kan göra drag med den.

201d. En pjästyp. Se regel TBA för pjästyper och regler som gäller dem

201e. Ett variabelt antal tillstånd som gäller pjäsen. Vissa regler påverkar pjäser olika beroende på deras tillstånd, och vissa regler kan ändra pjäsers tillstånd. En pjäs har inga tillstånd om ingen regel säger att den har eller får ett. Om en pjäs byter pjästyp så behåller den alla tillstånd om inget annat anges, men de kan sluta ha betydelse.

201f. Ett variabelt antal definierade objekt, val eller värden från andra regler. Dessa lagras separat för varje objekt, val eller värde som en regel efterfrågar. (Exempel: En drake vet vilken pjäs den bär på)

202\. Pjästyper

202.1. Det finns ett definierat antal pjästyper. Pjästyper har följande information:

202.1a. Ett namn. Varje pjästyp har ett unikt namn

202.1b. Ett värde. Pjäser med högre värde brukar vara mer användbara eller skyddsvärda. Ett värde är oftast antingen ett heltal är "Kunglig". Om något försöker räkna på "Kunglig" adderat eller subtraherat med något blir resultatet "Kunglig". Om det divideras eller multipliceras med ett nollskilt tal blir resultatet "Kunglig" om talet är positivt, eller "Antikunglig" om talet är negativt. Om "Kunglig" och "Antikunglig" adderas blir resultatet 0. Detta sker innan andra additioner och subtraktioner som utförs samtidigt. "Antikunglig" följer samma regel, med undantaget att det blir "Antikunglig" av operationer som "Kunglig" blir "Kunglig" av, och vice versa. Det största värdet i en mängd som innehåller "Kunglig" är "Kunglig", och det minsta värdet i en mängd som innehåller "Antikunglig" är "Antikunglig". "Kunglig" är endast det minsta värdet i en mängd om alla värden är "Kunglig", och "Antikunglig" är endast det största värdet i en mängd om alla värden är "Antikunglig".

202.1c. En variabel mängd passiva regler. Dessa regler anger själva när och i vilken utsträckning de gäller, men de har bara effekt när minst en pjäs av den typen existerar. Oftast består de av att modifiera en handling som en spelare gör, eller att utföra en handling vid en viss tidpunkt.

202.1d. Ett eller flera drag. Ett drag består av en serie instruktioner, som kan innebära förflyttning eller tagning av pjäser, vinnande eller förlorande av spelet, ändring av pjäsers tillstånd eller värden, eller ändring av rutors tillstånd. Om en pjäs har flera drag måste ett av dem väljas för att göra ett drag med den pjäsen. Ett drag kan ha krav för att det ska kunna utföras; som regel kan ett drag inte utföras om det kräver ett val av något som inte går att välja (t.ex. en ledig ruta som uppfyller vissa krav). Ett drag som inte kan utföras kallas för ett illegalt drag.
