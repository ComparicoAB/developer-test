# Arbetsprov för Comparico

## Instruktioner

Detta arbetsprov tillämpas för att se ditt tankesätt och din förmåga att skriva kod. Det är inte meningen att det ska vara perfekt, så lägg inte ner mer tid än du anser är behövligt för att visa upp din förmåga. Vi tänker oss 2-3 timmar. Viktigt att du skriver ner varför du tagit den väg du tagit i antingen en readme eller i kommenterar på koden om då det säger mer än koden själv.

Arbetsprovet går ut på att du ska skapa kod som hanterar tre olika json filer (de tre som ligger i detta repo) och presenterar dom i en tabell, denna tabell ska sedan kunna sorteras och filtreras på minst tre attribut (t.ex. namn, operatör och pris). 

## JSON

JSON datat finns här nedan och är skapad efter den här mallen:

```javascript
[
    /*
    * Type: Object
    * Description: ID of Object concatenated of Mobile->id and Contract->id
    * Contains: 
    *   String id
    *   Object mobile
    *   Object contract
    *   String serviceProvider
    *   DateTime createdAt
    */
    "F51648-10465":{ 
        /*
        * Type: String
        * Value: String concatenated of Mobile->id and Contract->id
        */
        "id": "Mobile->id - Contract->id", 
        /*
        * Type: Object
        * Description: Object containing information of a single mobile.
        * Contains: 
        *   String id
        *   String name
        *   String color
        *   Integer|Null storage
        *   String condition
        *   String|Null url
        *   String|Null imageUrl
        *   Integer|Null subscriptionDuration
        *   Integer monthlyPrice
        *   Integer startPrice
        *   Integer|Null campaignPrice
        *   Integer|Null campaignDuration
        */
        "mobile":{ 
            /*
            * Type: String
            * Value: Unique string for this mobile.
            */
            "id": "F51648",
            /*
            * Type: String
            * Value: The name of the mobile.
            */ 
            "name": "iPhone 6S - 32 GB", 
            /*
            * Type: String
            * Value: The color of the mobile.
            */ 
            "color": "Rymdgrå",
            /*
            * Type: Integer|Null
            * Default: Null
            * Value: Size of storage on the mobile in GB. 
            * Can be Null if no data is found.
            */ 
            "storage": 32,
            /*
            * Type: String
            * Default: "new"
            * Value: Condition type of the mobile. Enum: new, used.
            */ 
            "condition": "new",
            /*
            * Type: String|Null
            * Default: Null
            * Value: Absolut URL to the mobile. 
            * Can be Null if no url is found.
            */ 
            "url":"https:\/\/www.hallon.se\/mobiler\/iphone-6s-32-gb",
            /*
            * Type: String|Null
            * Default: Null
            * Value: Absolut URL to the image of the mobile. 
            * Can be Null if no url is found.
            */ 
            "imageUrl":"https:\/\/www.hallon.se\/mobiler\/iphone-6s-32-gb",
            /*
            * Type: Integer|Null
            * Default: Null
            * Value: Amount of months the partpayment is set for. 
            * Can be Null if no subscription duration is set.
            */ 
            "subscriptionDuration":24,
            /*
            * Type: Integer
            * Value: The monthly price in SEK. 
            */ 
            "monthlyPrice":150,
            /*
            * Type: Integer
            * Value: Start fee in SEK. 
            */ 
            "startPrice":0,
            /*
            * Type: Integer|Null
            * Default: Null
            * Value: Temporary price for the current campaign. 
            * Can be Null if no campaign is available.
            */ 
            "campaignPrice": null,
            /*
            * Type: Integer|Null
            * Default: Null
            * Value: Amount of months the campaignPrice is valid. 
            * Can be Null if no campaign is available.
            */ 
            "campaignDuration": null,
        },
        /*
        * Type: Object
        * Description: Object containing information of a single contract.
        * Contains: 
        *   String id
        *   String hashId
        *   String name
        *   String|Null description
        *   Integer|Null data
        *   Integer|Null subscriptionDuration
        *   Integer monthlyPrice
        *   Integer startPrice
        *   Integer|Null campaignPrice
        *   Integer|Null campaignDuration
        *   Boolean isStudentContract
        *   Boolean isUnder18Contract
        *   Boolean isPlus55Contract
        *   Boolean isYouthContract
        *   String|Null extraInfo
        */
        "contract":{ 
            /*
            * Type: String
            * Value: Unique string for this contract.
            */
            "id":"10465", 
            /*
            * Type: String
            * Value: MD5 Unique hashId based on data, subscriptionDuration and demographics.
            * Formula: md5($subscription->serviceProvider . $contract->data .
            *    $contract->isStudentContract . $contract->isUnder18Contract . $contract->isPlus55Contract)
            */
            "hashId": "71EE77FB5180EEE4D589D66A0DD1B5AD", 
            /*
            * Type: String
            * Value: The name of the contract.
            */ 
            "name":"Mobilabonnemang 100 GB", 
            /*
            * Type: String|Null
            * Default: Null
            * Value: Description of the contract.
            */ 
            "description":"174 kr per mån i 3 mån, därefter 349 kr\/mån",
            /*
            * Type: Integer|Null
            * Default: Null
            * Value: Amount of monthly data usage available in GB.
            */
            "data":100, 
            /*
            * Type: Integer|Null
            * Default: Null
            * Value: Amount of months the subscription is set for. 
            * Can be Null if no subscription duration is set.
            */ 
            "subscriptionDuration":0, 
            /*
            * Type: Integer
            * Value: The monthly price in SEK. 
            */ 
            "monthlyPrice":349, 
            /*
            * Type: Integer
            * Value: Start fee in SEK. 
            */ 
            "startPrice":0, 
            /*
            * Type: Integer|Null
            * Default: Null
            * Value: Temporary price for the current campaign. 
            * Can be Null if no campaign is available.
            */ 
            "campaignPrice":174, 
            /*
            * Type: Integer|Null
            * Default: Null
            * Value: Amount of months the campaignPrice is valid. 
            * Can be Null if no campaign is available.
            */ 
            "campaignDuration":3, 
            /*
            * Type: Boolean
            * Default: False
            * Value: True if the contract is only available for Students.
            */ 
            "isStudentContract":false,
            /*
            * Type: Boolean
            * Default: False
            * Value: True if the contract is only available for people 
            *   under the age of 18.
            */ 
            "isUnder18Contract":false,
            /*
            * Type: Boolean
            * Default: False
            * Value: True if the contract is only available for people 
            *   over the age of 55.
            */
            "isPlus55Contract":false,
            /*
            * Type: Boolean
            * Default: False
            * Value: True if the contract is only available for people 
            *   between 18-27.
            */
            "isYouthContract":false,
            /*
            * Type: String|Null
            * Default: Null
            * Value: If there are any extra info on the page its appended to *  this parameter
            */
            "extraInfo":"Prissänkt\nPassa på att handla Galaxy S10 till superpris.\nKampanjen gäller endast så långt lagret räcker eller t.o.m. 30 september 2019\n\n50% mer surf i 1 år\n50% mer surf i 12 mån med alla abonnemang, när du binder dig 24 mån – t o m 27 oktober 2019."
        },
        /*
        * Type: String
        * Value: The name of the service provider in slug-format.
        */
        "serviceProvider":"hallon",
        /*
        * Type: DateTime
        * Value: The time the file was created. Formatted to ISO8601.
        */
        "createdAt":"2019-09-13T11:19:21+02:00"
    }
]
```


## Krav

- JSON-filerna måste parsas i PHP. Koden bör ha en lättare felhantering också, om det är fält som fattas eller är felaktiga t.ex. Telias namn
- Den parseade datat måste hämtas med Javascript (Ajax, HttpRequest osv. Du väljer själv.)
- Tabellen som presenterar datat måste ha en "action"-knapp som tar en vidare till respektive telefons hemsida. Designa tabellen hur du vill, men den måste kunna ses i sin fulla prakt i mobil likväl som desktop. Ta eget beslut på vilken data du anser ska visas för användaren.

## Inlämning

Lämna in filerna i en ZIP till Peter på mailen eller lägg upp det som ett repo på github. 

