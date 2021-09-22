---
title: Om förfallodatum för serienummer för Creative Cloud for enterprise och Acrobat
description: Så här fungerar serienummerutgångar för Creative Cloud for enterprise och Acrobat
role: User
level: Beginner, Intermediate
exl-id: bc457be0-86dc-4e8a-b6b2-34bc76af2d21
source-git-commit: 6b819aef801e003e5a160d24ba69522cf6a7e715
workflow-type: tm+mt
source-wordcount: '848'
ht-degree: 3%

---

# Om förfallodatum för serienummer för Creative Cloud for enterprise och Acrobat

Historiskt sett har Adobe utfärdat serienummer med våra appar (dvs. Creative Suite, Creative Cloud for enterprise, Acrobat XI, Acrobat DC) till kunder med Enterprise Term License Agreements (ETLA). Dessa serienummer har ett förfallodatum. När utgångsdatumet har passerat kommer produkten inte längre att fungera, så det är viktigt att planera migreringen innan serienumren går ut. På den här sidan beskrivs de steg som krävs för att se till att slutanvändarna har fortsatt tillgång till sina appar och tjänster på Adobe.

## Kontrollera serienumren för deras utgångsdatum

### Hitta dina serienummer

De serienummerlicenser som är kopplade till ditt ETLA-avtal finns på [Adobe Licensing Website](https://licensing.adobe.com/) (LWS). Följ de här anvisningarna för att visa och hämta:

1. Logga in på [Adobe licenswebbplats](https://licensing.adobe.com/) (LWS) med din Adobe ID och ditt lösenord.
1. Välj **Licenser > Hämta serienummer**.
1. Ange ditt **slutanvändar-ID** eller **Distribuera till ID**.
1. (Valfritt) Välj en **produktnamn**, **produktversion** eller **Plattform** om du vill filtrera resultaten.
1. Klicka på Search (Sök). 
1. Produktens namn och serienummer visas.
1. (Valfritt) Välj EXPORTERA TILL CSV för att hämta listan med serienummer.

![Hitta dina serienummer](assets/retrieveserialnumbers.png)

### Kontrollera utgångsdatum

[AdobeExpiryCheck](https://helpx.adobe.com/enterprise/kb/volume-license-expiration-check.html) är ett kommandoradsverktyg som IT-administratörer kan använda för att kontrollera om Adobe-produkter på en dator använder serienummer som har upphört att gälla eller som upphör att gälla. Verktyget visar information som LEID (product licensing identifier), det krypterade serienumret och sista giltighetsdatum. Den här [sidan](https://helpx.adobe.com/enterprise/kb/volume-license-expiration-check.html) innehåller anvisningar om hur du hämtar och använder verktyget på Mac- eller Windows-datorer.

## Förstå slutanvändarens upplevelse innan och efter att serienumret förfaller

Både Acrobat och Creative Cloud for enterprise-appar börjar visa meddelanden (i programmen) med början 60 dagar innan de förfaller. När serienumret har gått ut slutar produkterna att fungera och användaren uppmanas att vidta åtgärder.

### Creative Cloud för företagsupplevelser

Följande information beskriver slutanvändarens upplevelse. Det finns en kort video nedan som följs av en genomgång av användarupplevelsen.

>[!VIDEO](https://video.tv.adobe.com/v/331746?hidetitle=true)

**Före förfallodatum**

Från och med 60 dagar innan serienumret upphör att gälla visar alla Creative Cloud for enterprise-appar en dialogruta i produkten för slutanvändaren. Det här meddelandet visas varje vecka, fram till 30 dagar innan det upphör att gälla, och visas sedan dagligen fram till det utgångsdatum som anges som *Licensen upphör att gälla. Adobe använder en licens som löper ut den 29 november 2020. Kontakta din administratör för att säkerställa fortsatt åtkomst*.

![CCE före förfallodatum](assets/cceexpiring.png)

**Efter utgångsdatum**

När serienumret har gått ut har användarna inte längre tillgång till Creative Cloud för företagsappar. Första gången du startar programmet efter att det gått ut visas en dialogruta med namnet *Serienumret du angav har gått ut. Det går inte att licensiera den här produkten. Kontakta kundsupport*.

![CCE efter förfallomeddelande](assets/cceafterexpire.png)

För alla efterföljande försök att starta programmen uppmanas slutanvändaren att **logga in nu** följt av alternativet att skapa sin egen Adobe ID och gå till testversionsläge. Alla nya Adobe ID-licenser som skapas av slutanvändaren kommer dock inte att kopplas till organisationens licenser och kommer att skapa ytterligare förvirring för användarna. För att undvika störningar i verksamheten och/eller onödig förvirring bör du migrera dina användare till personliga licenser innan serienumret eller serienumren går ut.

![CCE Inloggningsdialogruta 1](assets/ccesignin1.png)

![CCE Inloggningsdialogruta 2](assets/ccesignin2.png)

### Acrobat upplevelse

Följande information beskriver slutanvändarens upplevelse. Det finns en kort video nedan som följs av en genomgång av användarupplevelsen.

>[!VIDEO](https://video.tv.adobe.com/v/331749?hidetitle=true)


**Före förfallodatum**

Från och med 60 dagar innan serienumret upphör visas ett popup-meddelande i produkten för slutanvändaren i Acrobat. Detta kommer att uppträda en gång i veckan till 7 dagar innan det upphör att gälla. Den kommer sedan att visas dagligen med *Din Adobe Acrobat-licens upphör att gälla den 30/11/2020. Kontakta administratören om du vill fortsätta använda Acrobat utan avbrott.*

![Acrobat förfallomeddelande](assets/acrobatexpiring.png)

**Efter utgångsdatum**

När serienumret har gått ut har användarna inte längre tillgång till Acrobat. Första gången du startar programmet efter att det gått ut visas en dialogruta med namnet *Serienumret du angav har gått ut. Det går inte att licensiera den här produkten. Kontakta kundsupport.*

![Acrobat efter förfallodatum](assets/acrobatafterexpire.png)

För alla efterföljande försök att starta Acrobat uppmanas slutanvändaren att **logga in nu** följt av alternativet att skapa en egen Adobe ID och gå till testläge. Alla nya Adobe ID-licenser som skapas av slutanvändaren kommer dock inte att kopplas till organisationens licenser och kommer att skapa ytterligare förvirring för användarna.

![Acrobat Sign in dialog 1](assets/acrobatsignin1.png)

![Acrobat Sign in dialog 2](assets/acrobatsignin2.png)

## Kontakta oss om du behöver hjälp

Om du har några frågor om hur du använder verktyget [AdobeExpiryCheck](https://helpx.adobe.com/enterprise/kb/volume-license-expiration-check.html) eller behöver hjälp med att migrera från serienummerdistribution till namngivna användare har du några alternativ:
* Skicka ett e-postmeddelande till Adobe Enterprise Onboarding-team - **entonb@adobe.com**
* Öppna en supportanmälan i [Admin Console](https://adminconsole.adobe.com/support)
* Kontakta din kontoansvarige eller Customer Success Manager på Adobe
