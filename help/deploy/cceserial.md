---
title: Om serienummer för Creative Cloud for enterprise och Acrobat upphör att gälla
description: Om hur serienummer upphör att gälla för Creative Cloud for enterprise och Acrobat
role: Admin
level: Beginner, Intermediate
feature: Deploy
exl-id: bc457be0-86dc-4e8a-b6b2-34bc76af2d21
source-git-commit: c57212d39b2e613964bc15d2967a1958dc0c8c8e
workflow-type: tm+mt
source-wordcount: '844'
ht-degree: 3%

---

# Om serienummer för Creative Cloud for enterprise och Acrobat upphör att gälla

Historiskt sett har Adobe utfärdat serienummer med våra appar (dvs. Creative Suite, Creative Cloud for enterprise, Acrobat XI, Acrobat DC) till kunder som har ett Enterprise Term License Agreements (ETLA). Serienumren har ett utgångsdatum. När utgångsdatumet har passerats kommer produkten inte längre att fungera, så det är viktigt att planera migreringen innan serienumren löper ut. På den här sidan beskrivs de steg som krävs för att se till att slutanvändarna har fortsatt åtkomst till sina Adobe-program och -tjänster.

## Kontrollerar serienumren efter utgångsdatumet

### Hitta dina serienummer

Serienummerlicenserna som är kopplade till ditt ETLA-avtal är tillgängliga via [Adobe licensieringswebbplats](https://licensing.adobe.com/) (LWS) Följ dessa anvisningar när du vill visa och hämta:

1. Logga in på [Adobe licensieringswebbplats](https://licensing.adobe.com/) (LWS) med ditt Adobe ID och lösenord.
1. Välj **Licenser > Hämta serienummer**.
1. Ange ditt **Slutanvändar-ID** eller **Distributions-ID**.
1. (Valfritt) Välj en **Produktnamn**, **Produktversion**, eller **Plattform** för att filtrera resultat.
1. Klicka på Search (Sök). 
1. Produktens namn och serienummer visas.
1. (Valfritt) Välj &quot;EXPORTERA TILL CSV&quot; för att hämta listan med serienummer.

![Hitta dina serienummer](assets/retrieveserialnumbers.png)

### Kontrollera förfallodatum

Inställningen [AdobeExpiryCheck](https://helpx.adobe.com/enterprise/kb/volume-license-expiration-check.html) är ett kommandotolksverktyg som IT-administratörer kan använda för att kontrollera om Adobe-produkter på en dator har serienummer som har löpt ut eller snart löper ut. Verktyget visar information som produktlicensidentifierare (LEID), det krypterade serienumret och utgångsdatumet. Detta [sida](https://helpx.adobe.com/enterprise/kb/volume-license-expiration-check.html) innehåller instruktioner om hur du hämtar och använder verktyget på antingen Mac- eller Windows-datorer.

## Att förstå slutanvändarens upplevelse före och efter att serienumret har upphört att gälla

Både Acrobat- och Creative Cloud for enterprise-programmen börjar visa meddelanden (i programmen) 60 dagar före förfallodatum. När serienumret har gått ut slutar produkterna att fungera och användaren uppmanas att vidta åtgärder.

### Creative Cloud för företag

Följande information beskriver slutanvändarupplevelsen. Det finns en kort video nedan följt av en genomgång av slutanvändarupplevelsen.

>[!VIDEO](https://video.tv.adobe.com/v/331746?hidetitle=true)

**Före förfallodatum**

Från och med 60 dagar innan serienumret löper ut visas dialogrutan I produkten för slutanvändaren i alla Creative Cloud for enterprise-program. Det här meddelandet visas varje vecka, fram till 30 dagar före förfallodatum, och visas sedan dagligen fram till det förfallodatum som anges *Din licens går snart ut. Den här Adobe-produkten använder en licens som upphör att gälla 29 november 2020. Kontakta administratören för att säkerställa fortsatt åtkomst*.

![CCE före förfallomeddelande](assets/cceexpiring.png)

**Efter förfallodatum**

När serienumret har gått ut har användarna inte längre tillgång till företagsapparnas Creative Cloud. Vid den första starten efter utgångsdatumet visas en dialogruta med information om *Serienumret du har angett har upphört att gälla. Produkten kan inte licensieras. Kontakta kundsupporten*.

![CCE efter förfallomeddelande](assets/cceafterexpire.png)

Vid alla efterföljande försök att starta programmen uppmanas slutanvändaren att **Logga in nu** följt av möjligheten att skapa ett eget Adobe ID och gå in i testversionsläge. Nya Adobe ID som skapas av slutanvändaren kopplas dock inte till organisationens licenser och kommer att orsaka ytterligare förvirring hos användarna. Migrera dina användare till namngiven användare-licensiering innan dina serienummer löper ut för att undvika störningar i verksamheten och/eller onödig förvirring.

![CCE-inloggningsdialogruta 1](assets/ccesignin1.png)

![CCE-inloggningsdialogruta 2](assets/ccesignin2.png)

### Acrobat-upplevelse

Följande information beskriver slutanvändarupplevelsen. Det finns en kort video nedan följt av en genomgång av slutanvändarupplevelsen.

>[!VIDEO](https://video.tv.adobe.com/v/331749?hidetitle=true)


**Före förfallodatum**

Från och med 60 dagar innan serienumret löper ut visas ett popup-meddelande i Acrobat till slutanvändaren. Detta visas en gång i veckan fram till 7 dagar före utgångsdatum. Det kommer då att börja visas dagligen anger *Din Adobe Acrobat-licens upphör att gälla 2020-30-11. Kontakta administratören för att fortsätta använda Acrobat utan avbrott.*

![Acrobat - meddelande löper ut](assets/acrobatexpiring.png)

**Efter förfallodatum**

När serienumret har gått ut har användarna inte längre tillgång till Acrobat. Vid den första starten efter utgångsdatumet visas en dialogruta med information om *Serienumret du har angett har upphört att gälla. Produkten kan inte licensieras. Kontakta kundsupporten.*

![Acrobat efter utgångsmeddelande](assets/acrobatafterexpire.png)

Vid alla efterföljande försök att starta Acrobat uppmanas slutanvändaren att **Logga in nu** följt av möjligheten att skapa ett eget Adobe ID och gå in i testversionsläge. Nya Adobe ID som skapas av slutanvändaren kopplas dock inte till organisationens licenser och kommer att orsaka ytterligare förvirring hos användarna.

![Acrobat Sign i dialog 1](assets/acrobatsignin1.png)

![Acrobat Sign i dialog 2](assets/acrobatsignin2.png)

## Kontakta oss om du behöver hjälp

Om du har några frågor om hur du använder [AdobeExpiryCheck](https://helpx.adobe.com/enterprise/kb/volume-license-expiration-check.html) eller behöver hjälp med att migrera från serienummerdistribution till namngiven användare, har du några alternativ:
* Skicka ett e-postmeddelande till introduktionsteamet för Adobe Enterprise - **entonb@adobe.com**
* Öppna ett supportärende i [Admin Console](https://adminconsole.adobe.com/support)
* Kontakta ditt Adobe-kontoteam
