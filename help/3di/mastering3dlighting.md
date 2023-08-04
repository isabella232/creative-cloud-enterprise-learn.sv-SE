---
title: Tips och tekniker för att bemästra 3D-ljus i CGI
description: Lär dig mer om 3D-belysning och hur du skapar olika ljusförhållanden som kan förändra en datorgenererad scen och hur objekt ser ut i den
feature: 3D
role: User
level: Beginner, Intermediate
keywords: 3D-belysning, 600 globala MSV
exl-id: 05eb729e-35b8-46e2-9c56-590250097d0b
source-git-commit: e39efe0f7afc4e3e970ea7f2df57b51bf17123a6
workflow-type: tm+mt
source-wordcount: '2733'
ht-degree: 0%

---

# Tips och tekniker för att bemästra 3D-ljus i CGI

Lär dig mer om 3D-belysning och hur du skapar olika ljusförhållanden som kan förändra en datorgenererad scen och hur objekt ser ut i den.

Vi uppfattar världen omkring oss med hjälp av våra sinnen: vi hör, vi känner, vi luktar, vi ser. Vi kan se det eftersom våra ögon fångar upp information som kommer till oss från elementära partiklar som kallas fotoner. Den här informationen bearbetas av vår hjärna för att skapa en bild. Vad vi tolkar som objektfärg, glansighet, genomskinlighet eller metallegenskaper är alla produkter av interaktionen mellan fotonerna och objektets yta.

Ljusmekaniken i en datorgenererad 3D-scen följer samma naturliga princip för fotonspridning, genom en process som kallas strålföljning. Strålar studsar mot former och interagerar med sina material, vilket effektivt definierar hur objekt visas i den slutliga bilden. Ljus exponerar dimensionaliteten för allt som finns i en 3D-scen.

Vissa material är mer känsliga för ljusförhållanden än andra. Ta metaller till exempel: ett kromobjekt reflekterar i princip allt runt det. Om ett ljus flyttas, blir ljusare eller större, är all den informationen synlig direkt på kromytan i nästan spegelliknande detaljer, så att den kan se helt annorlunda ut från det ena ljustillståndet till det andra.

![En 3D CGI scen av en bil på en parkeringsplats med en neonskylt på väggen. Belysningen skiftar från dagsljus till en neonlampa som strålar ut från skylten](assets/Mastering3dlighting_1.gif)

## Arbeta med 3D-ljus för att skapa effektiva 3D-renderingar

Processen med att skapa en 3D-rendering är aldrig riktigt densamma, men det här är de vanligaste stegen:

1. Skapa eller förvärva objekt
1. Scensammansättning
1. Inrama scenen
1. **Belysning**
1. Skapa eller tilldela material
1. Rendering

När du kommer till belysningsfasen är det idealiskt att ställa in dina lampor innan du arbetar med materialen. För att göra det kan du tilldela hela motivet ett neutralt grått, matt material. På så sätt kan du se och förstå tydligare hur ljuset påverkar objektets silhuetter i motivet. När materialen är klara kan belysningen behöva finjusteras ytterligare.

![CGI vardagsrum gör jämförelse med neutralt grått matt material till vänster jämfört med färdiga material till höger](assets/Mastering3dlighting_2.jpg)

Det är bäst att arbeta med belysningen en i taget. Det aktiva ljuset bör vara det enda som syns på motivet, medan alla andra ljus tillfälligt bör vara avstängda. På så sätt kan du se hur ett specifikt ljus påverkar motivet och ändra det genom att arbeta med dess egenskaper, till exempel position, riktning, intensitet osv.

![Exempel på 3 lampor som belyser en 3D-bilmodell individuellt och alla tre fungerar tillsammans](assets/Mastering3dlighting_3.gif)

Ett annat användbart trick är att skapa en sfär med ett glänsande metallmaterial (en krom eller en spegel). Den här &quot;spegelkulan&quot; speglar effektivt hela motivet runt omkring, så att du enkelt kan bestämma ljusets position, riktning eller storlek. Om omgivningsljusen lyser kommer du att kunna se dess reflektion i spegelkulan, vilket hjälper till att ställa in dess orientering i rymden.

![Använda en spegelkula (sfär med metallisk textur) för att se och rikta miljöljuset i en 3D-scen](assets/Mastering3dlighting_4.gif)

## Typer av ljus i Adobe [!DNL Dimension]

### Miljöbelysning

Miljöbelysning är ekvirektangulära (sfäriska) bilder som är lindade runt hela motivet. Som namnet antyder, fungerar dessa lampor för att efterlikna hela miljön, inklusive ljuskällorna, som lagras i dem.

![Exempel på miljöbelysning gjord av foton, en 3D-studioscen och en abstrakt 3D-scen](assets/Mastering3dlighting_5.jpg)

När du skapar en ny scen i [[!DNL Dimension]](https://www.adobe.com/products/dimension.html), skapas en standardmiljöljussättning åt dig. Det är därför du omedelbart kan se något i scenen. Adobe [!DNL Dimension] I startresurserna finns ett antal ljuskällor i miljön, som du kan prova direkt. Dessutom [Adobe [!DNL Stock]](https://stock.adobe.com/search?filters[content_type:3d]=1&amp;filters[3d_type_id][0]=2&amp;load_type=3d+lp) erbjuder ett stort, utvalt urval av miljöljussättning.

Miljöbelysning ger mycket realistiska resultat och kan spara mycket tid. För att uppnå något liknande manuellt, skulle du behöva faktiskt skapa hela miljön i 3D (inklusive olika ljuskällor), vilket är en betydande mängd arbete.

![Exempel på en scen där hela uppsättningen (inklusive lamporna) har monterats i 3D för att uppnå studioliknande resultat](assets/Mastering3dlighting_6.jpg)

Det finns många sätt att skapa miljöljussättning, inklusive att ta bilder från en 3D-scen, från ett foto och använda parametriska system. Om omgivningsljuset består av en 3D-scen är processen okomplicerad. Utdatabilden måste vara 32 bitar, vilket fångar ljusinformationen från alla ljus i motivet. 3D-kameran måste använda den ekvirektangulära projektionen (för att få ut en sfärisk bild).

![Exempel på en scen som lyses upp av ett ljus i 3D-studiomiljö](assets/Mastering3dlighting_7.jpg)

![En ljus för 3D-studiomiljö skapas genom att en 3D-scen i en studio renderas till en 32-bitars liksidig rektangel](assets/Mastering3dlighting_8.png)

Du kan också skapa miljöljussättning genom att ta fotografier av verkliga världen. För detta arbetsflöde behövs en 360-kamera (t.ex. [Ricoh Theta Z1](https://theta360.com/en/about/theta/z1.html)). Kameran används sedan för exponeringsgaffling eller för att ta flera bilder av samma miljö, tagna med ett intervall av olika exponeringsvärden (från underexponerade till överexponerade). Dessa bilder används sedan för att skapa 32-bitars bilder, ofta kallade HDR-bilder (kort för High Dynamic Range). Ett sätt att montera en sådan bild är med funktionen Lägg samman till HDR i Photoshop. Det inbäddade exponeringsintervallet blir intensitetsegenskapen.

![Exempel på en 3D-scen som belyses av en ljus från en fotografisk miljö](assets/Mastering3dlighting_9.jpg)

![Ljuset för fotografisk miljö skapas med exponeringsgaffling och Slå samman till HDR Pro i Photoshop](assets/Mastering3dlighting_10.jpg)

I båda fallen &quot;bakas&quot; ljuskällorna (och deras intensitet) in i dessa bilder och avger ljuset när de har använts i [!DNL Dimension].

Med de här metoderna har du fångat all belysning, alla reflektioner och detaljer du behöver, men med 3D-programmen kan du fortsätta redigera dem i 3D-rymden, så att du kan justera ljusrotationen samt ändra den övergripande intensiteten och färgen.

![Ändra intensiteten och orienteringen för ett miljöljus i en 3D-scen](assets/Mastering3dlighting_11.gif)

### Riktade lampor

Förutom miljöbelysning, som avger ljus från 360 grader, finns det också riktningsljus, som avger ljus från endast en riktning. De används för att emulera ficklampor och andra typer av ljus som kommer från en väldefinierad emitter, och de kan formas som en cirkel eller en kvadrat.

Med riktad belysning får du full kontroll över ljussättningen. Belysning av scenen med dessa ljus görs på samma sätt som i traditionell fotografering, där varje ljus kan styras oberoende, så att du kan bygga din egen virtuella fotografiska belysning. En av de vanligaste ljusinställningarna är 3-punktsljussystemet.

[!DNL Dimension] har en bekväm åtgärd, rikta ljus vid punkt, som låter dig styra rotation och höjd genom att helt enkelt klicka och dra över ett 3D-objekt. På så sätt kan du dynamiskt rikta ljusstrålarna. Dessa parametrar kan också justeras manuellt.

Du kan ändra färg och intensitet på riktningsljusen samt justera formen på ljuskällan - göra den cirkulär eller rektangulär, sträcka den, eller göra den större. Slutligen kan du mjuka upp ljuskällans kanter.

![Ändra formen på ett riktat ljus i Adobe [!DNL Dimension]](assets/Mastering3dlighting_12.gif)

Om du gör ljuskällan mindre än objektet kommer skuggorna att bli skarpare, med en skarpare kontur, eftersom strålarna inte kan ta sig förbi det upplysta objektet. Större ljuskällor ger mjukare skuggor, eftersom strålarna i det här fallet kommer från alla sidor av objektet (markerat med rött i bilden nedan), vilket skapar en array med skuggor. Skuggorna mjukas upp av strålarna från motsatt riktning.

![Diagram som visar effekten av ljusintensitet, riktning och storlek på hur ett 3D-objekt lyses upp och skuggan kastar](assets/Mastering3dlighting_13.jpg)

![Exempel på hur storleken på ett 3D-ljus påverkar skuggans mjukhet som avges av en CGI-bilmodell](assets/Mastering3dlighting_14.gif)

### Sol och himmel

Solljus är en särskild typ av riktat ljus. Processen för att ställa in den är mycket lik ett vanligt riktat ljus, men detta ljus kommer automatiskt att ändra färgen med höjd; när det är nära horisonten (låg höjd vinkelvärden), kommer det gradvis att bli varmare för att simulera solnedgången. Färgen kan också ändras med hjälp av förinställningar. Under tiden påverkar grumlighet skuggans mjukhet.

![Ändra ljusegenskaper för solljus på en 3D-bilmodell i Adobe [!DNL Dimension]](assets/Mastering3dlighting_15.gif)

![En 3D-scen på månen där den enda ljuskällan är solljus](assets/Mastering3dlighting_16.jpg)

Vi kan emulera himlen med hjälp av miljöbelysning, och allt miljöljus som finns på himlen kan användas. Nu måste vi justera solljuset (gjord i [!DNL Dimension]) med solen, fångad i omgivningen ljus. Ett snabbt sätt att göra detta är att skapa en sfär och tilldela den ett metallmaterial. Detta kommer att ge oss reflektioner av miljön i realtid, så att vi kan använda Riktat ljus vid punkten för att justera solljuset mot solen.

Om omgivningsljuset har en mulen himmel kan egenskapen grumlighet användas för att matcha villkoren bättre.

![Ändra grumlighetsegenskaper för himmelsmiljöbelysning på en 3D-bilmodell i Adobe [!DNL Dimension]](assets/Mastering3dlighting_17.gif)

När solljuset och ljuset från himmelsmiljön har parats ihop kan du rotera dem tillsammans med hjälp av egenskapen Global rotation.

### Objektbaserade ljus

Objekt kan göras om till ljuskällor genom att aktivera egenskapen Glöd för deras material. På så sätt är det möjligt att skapa objekt som glödlampor, neonljus, softboxar och alla typer av skärmar och displayer.

Den största fördelen med att använda den här typen av belysning är intensitetsutfallet, som ger mycket naturliga resultat. Detta är ganska användbart för produktvisualisering eller andra studiobaserade scener.

![Ljuskälla som har ett utfall (en glödande platta) VS en oändlig ljuskälla (ett riktat ljus)](assets/Mastering3dlighting_18.png)

Du kan styra skuggornas mjukhet genom att skala det glödande objektet uppåt eller nedåt med omformningsverktyget. Om du gör den större ökar även ljusintensiteten.

![Om du ändrar storleken på objektljuset ökas ljusmängden och skuggorna blir mjukare](assets/Mastering3dlighting_19.gif)

Till skillnad från de tidigare typerna av ljus som vi har täckt, dessa ljus kan också utnyttja texturer, förutom enkla färger. Texturerna kan fästas till basfärgen på materialet och ljusintensiteten styrs med ett glödreglage.

![Använda en textur på ett objektljus som belyser en 3D-bilmodell](assets/Mastering3dlighting_20.gif)

## Exempel på effektiv 3D-belysning

### Produktbelysning

![Exempel på tre ljuskällor (nyckel, fyllning och kant) som belyser en 3D-hörlursmodell individuellt och alla tre fungerar tillsammans](assets/Mastering3dlighting_21.gif)

Det finns många fotografiska tekniker för att ställa in ljuset för en produktbild. Vi kommer att använda en av de vanligaste inställningarna, som är 3-punkters ljussystem.

Denna konfiguration består av tre lampor:

1. **Nyckelbelysning:** som används som primär källa, lyser detta ungefär från kamerariktningen

   ![Exempel på nyckelljus som lyser upp en 3D-hörlursmodell](assets/Mastering3dlighting_22.jpg)

1. **Ljus för fälg:** Orienterat på motsatt sida från nyckeln, används detta för att exponera silhuetten av motivet.

   ![Exempel på en fälglampa som belyser en 3D-hörlursmodell](assets/Mastering3dlighting_23.jpg)

1. **Fyllnadsljus:** mindre intensiva och som tjänar till att fylla i mörkare områden, används detta för områden som de två föregående ljusen inte når.

   ![Exempel på en fyllnadsljus som belyser en 3D-hörlursmodell](assets/Mastering3dlighting_24.jpg)

Det finns två sätt att skapa 3-punktsbelysning i [!DNL Dimension] - använda riktat ljus (var för sig genom att lägga till dem i motivet eller använda en 3-punkters ljusförinställning) eller via glödande objekt.

![Exempel på en ljussättning med tre punkter i en 3D-scen](assets/Mastering3dlighting_25.jpg)

![En softbox från en 3D-ljussättning dekonstrueras till en ram, lampor och skärm](assets/Mastering3dlighting_26.jpg)

### Kreativt ljus

![3D-bild benämnd av Pipe Dreams av Vladimir Petkovic](assets/Mastering3dlighting_27.jpg)

Kreativ belysning används där fysisk noggrannhet inte är det primära målet. Detta inkluderar abstrakta och surrealistiska scener av alla slag, så det finns inga verkliga gränser där vår fantasi kan ta oss.

I exemplet ovan var tanken att porträttera en drömlik miljö: godis, pastellfärger och släta ytor. Belysningssystemet består av tre lysande plattor (två på sidan, och den viktigaste lyser nedifrån). Alla glödande plattor är orealistiskt stora, vilket skapar mycket mjuka skuggor och högdagrar. Ljuskällorna är färgade och den färgen överförs till det material som tilldelats objekten i motivet.

Motivet i scenen (rören) är helt omgivet av väggens geometri. Detta gör att ljusstrålar studsar fram och tillbaka och blandas på intressanta sätt. Experiment med svala VS-varma toner ger ofta fin kontrast (den här tekniken används ibland inom porträttfotografering).

![En illustration som visar 3D-ljussättningen för Vladimir Petkovics Pipe Dreams](assets/Mastering3dlighting_28.jpg)

### Invändig visualisering

![En 3D-interiör av ett vardagsrum](assets/Mastering3dlighting_29.jpg)

Att skapa en visualisering av en 3D-interiör följer en viss uppsättning regler, som nästan alltid garanterar bra resultat. För detta användningsfall kommer vi endast att överväga naturligt ljus (inga artificiella källor, som lampor).

Först och främst måste en scen som denna vara i en sluten miljö. Precis som i verkliga livet, interiören kommer att behöva väggar, golv, tak, och fönster. På så sätt ser du till att ljuset kommer genom fönstren och sedan studsar runt (via en process som kallas strålföljning). Detta beteende ger mycket naturlig belysning (de täckta områdena, som hörn, blir till exempel mörkare).

Eftersom motivet nästan helt omges av arkitektonisk geometri kommer vi att se mycket lite belysning och nästan inga reflektioner från miljöljuset. Men i det här fallet bygger vi faktiskt vår egen miljö, som är själva interiören. Ljuset kommer då att reagera med objekt i motivet genom att studsa mot dem och de omgivande väggarna. Objekten reflekterar endast varandra och väggarna runt dem. Men det är ändå en bra idé att lägga till ett miljöljus som lyser upp himlen. Detta ger en diffus blå fyllning.

Det enklaste sättet att ställa in ljuset är att använda plan med glödande material. I detta användningsfall har vi tre plan, som täcker alla öppningar i det inre.

![En illustration som visar hur nyckel- och fyllnadsljus placeras i ett 3D-vardagsrum inomhus för att belysa motivet](assets/Mastering3dlighting_30.jpg)

Ljusets intensitet styrs av glödegenskapen på planens material. Du kan lägga till en färg eller till och med en textur, som kan användas för att kasta intressanta skuggor. Användning av glödmaterial kommer också att ge ljusintensitetsutfall, vilket är ganska viktigt för interiör belysning.

![Exempel på miljöbelysning, miljö och nyckelljus samt miljö-, nyckel- och fyllnadsljus som lyser upp ett 3D-vardagsrumsmotiv](assets/Mastering3dlighting_31.gif)

### Utomhusbelysning

![En scen med en trädstubbe på ett skogsgolv, sammanflätad med CGI-trådar och band upplysta med 3D-utomhusbelysning](assets/Mastering3dlighting_32.jpg)

Att skapa utomhusbelysning är ganska enkelt och det handlar om att använda ett sol- och himmelssystem (se ovan). Det är viktigt att solljuset matchas korrekt med det himmelsbaserade omgivningsljuset - med uppmärksamhet på både orienteringen och molnigheten.

Själva scenen spelar en stor roll i detta. Om du vill skapa intressanta resultat kan du använda objekt i motivet som katalysatorer som samverkar med ljuset. I skogrenderingen som visas ovan placeras föremålen (olika växter, stockar och träd) nära varandra.

![Objekt i en 3D-skogsscen visar hur ljuset samverkar med miljön](assets/Mastering3dlighting_33.png)

Det innebär att det kommer att finnas en massa komplexa strålföljningsinteraktioner, när ljuset studsar mellan objekten. Skuggade fläckar kommer att se mörka ut (som förväntat), medan exponerade områden förblir ljusa.

![Använda Global rotation i Adobe [!DNL Dimension] för att justera sol- och himmelssystemet i en 3D-scen](assets/Mastering3dlighting_34.gif)

Jag hoppas att den här översikten visar hur viktigt det är att bemästra 3D-ljus i olika situationer. Du bör vara redo att börja producera mer övertygande resultat.

Glad belysning! Hämta [senaste utgåvan](https://creativecloud.adobe.com/apps/download/Dimension) av Dimension idag.
