---
title: Tips och tekniker för att bemästra 3D-ljus i CGI
description: Lär dig mer om 3D-ljus och hur du skapar olika ljusförhållanden som helt kan förändra en datorgenererad scen och hur objekt ser ut i den
role: User
level: Beginner, Intermediate
keywords: 3D-belysning, 600 Global MSV
exl-id: 05eb729e-35b8-46e2-9c56-590250097d0b
source-git-commit: 01d80f9b296bc7d13b5e931cf0ca22d1335271dc
workflow-type: tm+mt
source-wordcount: '2739'
ht-degree: 0%

---

# Tips och tekniker för att bemästra 3D-ljus i CGI

Lär dig mer om 3D-ljus och hur du skapar olika ljusförhållanden som helt kan förändra en datorgenererad scen och hur objekt ser ut i den.

Vi uppfattar världen omkring oss med våra sinnen: Vi hör, vi känner, vi luktar, vi ser. Vi kan se eftersom våra ögon fångar upp information som kommer till oss från elementära partiklar som kallas fotoner. Denna information bearbetas av vår hjärna för att skapa en bild. Det vi tolkar som objektfärg, glansighet, genomskinlighet eller metalliska egenskaper är alla produkter av samspelet mellan fotonerna och objektets yta.

Ljusmekaniken i en datorgenererad 3D-scen följer samma naturliga princip om fotonspridning, genom en process som kallas [strålföljning](https://en.wikipedia.org/wiki/Ray_tracing_(graphics)). Strålar studsar mot former och interagerar med deras material, vilket effektivt definierar hur objekt visas i den slutliga bilden. Ljus visar dimensionerna för allt som finns i en 3D-scen.

Vissa material är mer känsliga för ljusförhållanden än andra. Ta till exempel metaller: Ett kromobjekt reflekterar i princip allt runt det. Om ett ljus flyttas, blir ljusare eller större, är all denna information synlig direkt på kromytan i nästan spegelliknande detalj, så att den kan se helt annorlunda ut från ett ljusförhållande till det andra.

![En 3D CGI-scen av en bil på en parkeringsplats med en neonskylt på väggen. Belysningen skiftar från dagsljus till en neonlampa som strålar från skylten](assets/Mastering3dlighting_1.gif)

## Arbeta med 3D-ljus för att skapa effektiva 3D-renderingar

Processen för att skapa en 3D-rendering är aldrig riktigt densamma, men detta är de vanligaste stegen:

1. Skapa eller förvärva objekt
1. Scensammanställning
1. Bildruta scenen
1. **Ljus**
1. Skapa eller tilldela material
1. Återgivning

När du kommer till belysningsfasen är det idealiskt att ställa in dina lampor innan du arbetar på materialen. Det gör du genom att tilldela hela scenen ett neutralt grått, matt material. På så sätt kommer du att kunna se och förstå tydligare hur ljusen påverkar objektets silhuetter på scenen. När materialen är klara kan belysningen behöva ytterligare förbättringar.

![CGI vardagsrum rendera jämförelse med neutralt grå matt material till vänster jämfört med färdiga material till höger](assets/Mastering3dlighting_2.jpg)

Det är bäst att arbeta med ljuset en i taget. Det aktiva ljuset ska vara det enda som syns på scenen, medan alla andra ljus tillfälligt ska vara släckta. På så sätt kan du se hur ett specifikt ljus påverkar motivet och ändra det genom att arbeta på dess egenskaper, till exempel position, riktning, intensitet osv.

![Exempel på 3 ljus som lyser upp en 3D-bilmodell individuellt och alla 3 av dem arbetar tillsammans](assets/Mastering3dlighting_3.gif)

Ett annat användbart trick är att skapa en sfär med ett glänsande metallmaterial (en krom eller en spegel). Denna &quot;spegelboll&quot; speglar effektivt hela scenen runt den, så att du enkelt kan bestämma ljusets position, riktning eller storlek. När det gäller miljön ljus, kommer du att kunna se dess reflektion i spegelkulan, vilket hjälper till att ställa in dess orientering i rymden.

![Använda en spegelkula (sfär med metallisk textur) för att se och orientera miljöljuset i en 3D-scen](assets/Mastering3dlighting_4.gif)

## Typer av ljus i Adobe [!DNL Dimension]

### Miljöbelysning

Miljöljus är ekvirektangulära (sfäriska) bilder som är lindade runt hela scenen. Som namnet antyder, fungerar dessa ljus för att emulera hela miljön, inklusive ljuskällorna, som lagras i dem.

![Exempel på miljöljussättning gjord av foton, en 3D-studioscen och en abstrakt 3D-scen](assets/Mastering3dlighting_5.jpg)

När du skapar en ny scen i [[!DNL Dimension]](https://www.adobe.com/products/dimension.html), en standardmiljöljussättning skapas åt dig. Det är därför du omedelbart kan se något i scenen. Adobe [!DNL Dimension] Startmediefiler innehåller ett visst antal miljöljusfunktioner, som du kan prova direkt. Dessutom [Adobe [!DNL Stock]](https://stock.adobe.com/search?filters[content_type:3d]=1&amp;filters[3d_type_id][0]=2&amp;load_type=3d+lp) erbjuder ett stort, välstrukturerat urval av miljöljussättning.

Miljöljus ger mycket realistiska resultat och kan spara mycket tid. För att uppnå något liknande manuellt, måste du faktiskt skapa hela miljön i 3D (inklusive olika ljuskällor), vilket är en betydande mängd arbete.

![Exempel på en scen där hela uppsättningen (inklusive ljusen) har monterats i 3D för att uppnå studioliknande resultat](assets/Mastering3dlighting_6.jpg)

Det finns många sätt att skapa miljöljussättning, bland annat genom att hämta från en 3D-scen, från ett foto och använda parametriska system. Om miljöljuset är gjort av en 3D-scen är processen enkel. Utdatabilden måste vara 32 bitar, vilket fångar upp ljusinformationen från allt ljus i scenen. 3D-kameran måste använda den ekvirektangulära projektionen (för att få en sfärisk bild).

![Exempel på en scen belyst av ett 3D-studiomiljöljus](assets/Mastering3dlighting_7.jpg)

![En 3D-studiomiljusbild skapas genom att en 3D-scen från en studio renderas till en ekvirektangulär 32-bitarsbild](assets/Mastering3dlighting_8.png)

Du kan också skapa miljöljussättning genom att ta foton av verkligheten. För det här arbetsflödet behövs en 360-kamera (t.ex. [Ricoh Theta Z1](https://theta360.com/en/about/theta/z1.html)). Kameran används sedan för exponeringsgaffling, eller för att ta flera bilder av samma miljö, tagna med en rad olika exponeringsvärden (från underexponerad till överexponerad). Dessa bilder används sedan för att skapa 32-bitars bilder, som ofta kallas HDR (förkortning för High Dynamic Range). Ett sätt att montera en sådan bild är med funktionen Lägg samman till HDR i Photoshop. Det inbäddade exponeringsintervallet blir intensitetsegenskapen.

![Exempel på en 3D-scen belyst av en ljusmiljö i fotografisk miljö](assets/Mastering3dlighting_9.jpg)

![Fotografimiljöljuset skapas med hjälp av exponeringsgaffling och Lägg samman till HDR Pro i Photoshop](assets/Mastering3dlighting_10.jpg)

I båda fallen &quot;bakas&quot; ljuskällorna (och deras intensitet) in i dessa bilder och kommer att avge ljuset när de används i [!DNL Dimension].

Med de här metoderna har du fångat allt ljus, alla reflektioner och alla detaljer du behöver, men med 3D-programmen kan du fortsätta redigera dem i 3D-rymden så att du kan justera ljusrotationen samt ändra den övergripande intensiteten och färgen.

![Ändra intensiteten och orienteringen för ett miljöljus i en 3D-scen](assets/Mastering3dlighting_11.gif)

### Riktat ljus

Förutom miljöbelysning, som avger ljus från 360 grader, finns det också riktningsljus, som avger ljus från endast en riktning. De används för att emulera ficklampor och andra typer av ljus som kommer från en väldefinierad emitter, och de kan formas som en cirkel eller en kvadrat.

Användning av riktningsljus ger full kontroll över ljusinställningen. Att belysa scenen med dessa ljus görs på samma sätt som i traditionell fotografering, där varje ljus kan styras oberoende, så att du kan bygga din egen virtuella fotografiska belysning. En av de vanligaste ljusinställningarna är 3-punktsljussystemet.

[!DNL Dimension] har en praktisk funktion, Sikta ljus vid punkt, som du kan använda för att styra rotation och höjd genom att helt enkelt klicka och dra över ett 3D-objekt. På så sätt kan du dynamiskt rikta ljusstrålarna. Dessa parametrar kan också justeras manuellt.

Du kan ändra färg och intensitet på riktningsljusen samt justera formen på ljuskällan - göra den cirkulär eller rektangulär, sträcka den, eller göra den större. Slutligen kan du göra ljuskällans kanter mjukare.

![Ändra formen på ett riktat ljus i Adobe [!DNL Dimension]](assets/Mastering3dlighting_12.gif)

Om du gör ljuskällan mindre än objektet blir skuggorna skarpare, med en skarpare kontur, eftersom strålarna inte kan ta sig förbi det belysta objektet. Större ljuskällor ger mjukare skuggor, eftersom strålarna i det här fallet kommer från alla sidor av objektet (markerat med rött i bilden nedan) och skapar en array med skuggor. Dessa skuggor mjukas upp av strålar som kommer från motsatt riktning.

![Diagram som illustrerar den effekt som ljusintensitet, riktning och storlek har på det sätt som ett 3D-objekt belyses och skuggan den kastar](assets/Mastering3dlighting_13.jpg)

![Exempel på hur storleken på ett 3D-ljus påverkar skuggans mjukhet från en CGI-bilmodell](assets/Mastering3dlighting_14.gif)

### Sol och himmel

Solljus är en särskild typ av riktat ljus. Processen för att ställa in den är mycket lik en vanlig riktad ljus, men detta ljus kommer automatiskt att ändra färgen med höjd; När den är nära horisonten (låg höjd vinkelvärden), kommer det gradvis att bli varmare för att simulera solnedgången. Färgen kan också ändras med hjälp av förinställningar. Under tiden kommer grumlighet att påverka skuggans mjukhet.

![Ändra ljusegenskaper för solljus på en 3D-bilmodell i Adobe [!DNL Dimension]](assets/Mastering3dlighting_15.gif)

![En 3D-scen på månen där den enda ljuskällan är solljus](assets/Mastering3dlighting_16.jpg)

Vi kan emulera himlen med hjälp av miljöbelysning, och all belysning i miljön som har himlen kan användas. Nu måste vi anpassa solljuset (gjord i [!DNL Dimension]) med solen, fångad i omgivningen ljus. Ett snabbt sätt att göra detta är att skapa en sfär och tilldela ett metallmaterial till den; Detta kommer att ge oss reflexioner av miljön i realtid, så att vi kan använda Sikta ljus vid punkten för att anpassa solljuset till solen.

Om miljöljuset har en mulen himmel kan egenskapen cloudiness användas för att matcha dessa villkor närmare.

![Ändra molnighetsegenskaper för himmelsmiljöbelysning på en 3D-bilmodell i Adobe [!DNL Dimension]](assets/Mastering3dlighting_17.gif)

När solljuset och himmelsmiljöljuset har parats ihop kan du rotera dem tillsammans med egenskapen Global rotation.

### Objektbaserade ljus

Objekt kan omvandlas till ljuskällor genom att egenskapen Glöd aktiveras för deras material. På så sätt är det möjligt att skapa objekt som glödlampor, neonljus, softboxar och alla typer av skärmar och displayer.

Den största fördelen med att använda denna typ av belysning är intensitetsutfallet, som ger mycket naturliga resultat. Detta är ganska användbart för produktvisualisering eller andra studiobaserade scener.

![Ljuskälla med utfall (glödande platta) VS. en oändlig ljuskälla (riktat ljus)](assets/Mastering3dlighting_18.png)

Du kan kontrollera skuggornas mjukhet genom att skala det glödande objektet uppåt eller nedåt med omformningsverktyget. Om du gör den större ökar också ljusintensiteten.

![Om du ändrar storleken på objektljuset ökar ljusmängden och skuggorna mjukas upp](assets/Mastering3dlighting_19.gif)

Till skillnad från de tidigare ljustyperna vi har täckt kan dessa ljus också utnyttja texturer, förutom vanliga färger. Texturerna kan fästas vid basfärgen på deras material, och ljusintensiteten styrs med ett glödreglage.

![Använda en textur på ett objektljus som belyser en 3D-bilmodell](assets/Mastering3dlighting_20.gif)

## Exempel på effektiv 3D-belysning

### Produktbelysning

![Exempel på 3 ljus (nyckel, fyllning och fälg) som belyser en 3D-hörlursmodell individuellt och alla tre arbetar tillsammans](assets/Mastering3dlighting_21.gif)

Det finns många fotografiska tekniker för att ställa in ljuset för en produktbild. Vi kommer att använda en av de vanligaste inställningarna, som är 3-punktsljussystemet.

Installationen består av tre ljuskällor:

1. **Nyckelbelysning:** används som primär källa, lyser detta ungefär från kamerans riktning

   ![Exempel på en knappbelysning som belyser en 3D-hörlursmodell](assets/Mastering3dlighting_22.jpg)

1. **Fälgljus:** orienterad på motsatt sida från nyckeln, används detta för att visa silhuetten av motivet.

   ![Exempel på en fälglampa som belyser en 3D-hörlursmodell](assets/Mastering3dlighting_23.jpg)

1. **Fyllnadsljus:** mindre intensivt och tjänar till att fylla i mörkare områden, används detta för områden som de tidigare två ljusen inte når.

   ![Exempel på en fyllnadsljus som belyser en 3D-hörlursmodell](assets/Mastering3dlighting_24.jpg)

Det finns två sätt att skapa 3-punktsbelysning i [!DNL Dimension] - använda riktat ljus (lägg till dem individuellt i motivet eller använd en förinställning med 3 punkter) eller via glödande objekt.

![Exempel på en ljusinställning med 3 punkter i en 3D-scen](assets/Mastering3dlighting_25.jpg)

![En softbox från en 3D-ljusinställning dekonstrueras till en ram, lampor och skärm](assets/Mastering3dlighting_26.jpg)

### Kreativ belysning

![3D-konstverk av Vladimir Petkovic](assets/Mastering3dlighting_27.jpg)

Kreativ belysning används där fysisk noggrannhet inte är det primära målet. Detta omfattar abstrakta och surrealistiska scener av alla slag, så det finns inga verkliga gränser där vår fantasi kan ta oss.

I exemplet ovan var tanken att skildra en drömlik miljö: godis, pastellfärger och släta ytor. Belysningssystemet är uppbyggt av tre glödande plattor (två på sidan och den viktigaste lyser nedifrån). Alla glödande plåtar är orealistiskt stora, vilket skapar mycket mjuka skuggor och högdagrar. Ljuskällorna är färgade och den färgen överförs till det material som tilldelats objekten på scenen.

Motivet för scenen (rör) är helt omgivet av väggens geometri. Detta kommer att få ljusstrålar att studsa fram och tillbaka och blanda ihop på intressanta sätt. Att leka med svala VS varma toner skapar ofta fin kontrast (den här tekniken används ibland i porträttfotografering).

![En illustration som visar 3D-belysningen för Vladimir Petkovics Pipe Dreams](assets/Mastering3dlighting_28.jpg)

### Invändig visualisering

![En 3D-inredning i ett vardagsrum](assets/Mastering3dlighting_29.jpg)

Att skapa en visualisering av en 3D-interiör följer en viss uppsättning regler, som nästan alltid garanterar bra resultat. För denna användning fall, vi kommer att överväga endast naturligt ljus (inga artificiella källor, som lampor).

Först och främst måste en scen som denna vara i en sluten miljö. Precis som i verkliga livet, inredningen kommer att behöva väggar, golv, tak och fönster. Detta säkerställer att ljuset kommer genom fönstren och sedan studsar runt (via en process som kallas strålföljning). Detta beteende ger mycket naturlig belysning (de slutna områdena, liksom hörn, blir till exempel mörkare).

Eftersom scenen nästan helt omges av arkitektonisk geometri kommer vi att se mycket lite belysning och nästan inga reflektioner från miljöljuset. Men i det här fallet bygger vi faktiskt upp vår egen miljö, som är själva interiören. Så ljuset kommer att reagera med objekten i scenen genom att studsa av dem och de omgivande väggarna. Objekten reflekterar bara varandra och väggarna runt dem. Det är dock en bra idé att lägga till en miljö ljus, med himlen. Då läggs en diffus blå fyllning till.

Det enklaste sättet att ställa in ljuset är att använda plan med glödande material. I detta fall har vi tre plan, som täcker alla öppningar i insidan.

![En illustration som visar hur ljus för nyckel och fyllning är placerade i ett 3D-vardagsrum inuti för att belysa scenen](assets/Mastering3dlighting_30.jpg)

Ljusets intensitet styrs av glödegenskapen på planens material. Du kan lägga till en färg eller till och med en textur, som kan användas för att kasta intressanta skuggor. Användning av glöd material kommer också att ge ljusintensitetsutfall, vilket är ganska viktigt för inre belysning.

![Exempel på miljöbelysning, miljö och nyckelljus och miljö, nyckel- och fyllnadsljus som lyser upp en 3D-scen i vardagsrummet](assets/Mastering3dlighting_31.gif)

### Utomhusbelysning

![En scen med en trädstubbe på skogsgolvet, sammanflätad med CGI-trådar och band upplysta med 3D-utomhusbelysning](assets/Mastering3dlighting_32.jpg)

Att skapa utomhusbelysning är ganska enkelt och det handlar om att använda ett sol- och himmelssystem (se ovan). Det är viktigt att solskenet matchas korrekt med det himmelsbaserade omgivningsljuset - med uppmärksamhet på både orientering och molnighet.

Själva scenen spelar en stor roll i detta. Om du vill skapa övertygande resultat kan du använda objekt i motivet som katalysatorer som interagerar med ljuset. I skogrenderingen ovan placeras föremålen (olika växter, stockar och träd) nära varandra.

![Objekt i en 3D-skogsscen visar hur ljuset interagerar med miljön](assets/Mastering3dlighting_33.png)

Detta innebär att det kommer att finnas en hel del komplex ray tracing interaktion, som ljuset studsar mellan objekten. Skuggade fläckar blir mörka (som förväntat), medan exponerade områden förblir ljusa.

![Använda Global rotation i Adobe [!DNL Dimension] för att omorientera sol- och himmelssystemet i en 3D-scen](assets/Mastering3dlighting_34.gif)

Jag hoppas att den här översikten visar hur viktigt det är att behärska 3D-ljus i olika situationer. Du bör vara redo att börja producera mer övertygande resultat.

Glad belysning! Hämta [senaste versionen](https://creativecloud.adobe.com/apps/download/Dimension) av Dimension idag.
