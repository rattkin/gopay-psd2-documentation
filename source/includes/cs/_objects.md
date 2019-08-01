#Objekty
Popis jednotlivých objektů použitých při komunikaci s platební bránou

##accounts
Údaje účtu elektronických peněz

```json
{
    "id": 100001660,
    "balance": 0,
    "currency": "EUR"
}
```

Název parametru|Popis parametru|Datový typ
---------------|---------------|----------
id| ID účtu
balance| Zůstatek účtu
[currency](#currency)| Měna, formát měny odpovídá [ISO 4217](http://www.iso.org/iso/home/standards/currency_codes.htm)

##address
Adresa/sídlo

```json
{
  "street": "Planá 67",
  "postal_code": "37001",
  "city": "Planá",
  "country": "cz"
}
```
Název parametru|Popis parametru|Datový typ
---------------|---------------|----------
street| Ulice | string
postal_code| Poštovní směrovací číslo | string
city| Město | string
country| Kód státu| string [ISO 3166-2](https://en.wikipedia.org/wiki/ISO_3166-2)

##payer
Definice plátce platby

```json
 {
   "allowed_payment_instruments":["PAYMENT_CARD", "BANK_ACCOUNT"],
   "default_payment_instrument":"BANK_ACCOUNT",
   "default_swift":"GIBACZPX",
   "allowed_swifts":["FIOBCZPP","BREXCZPP"],
   "bank_account":{},
   "contact": {}
 }
```

Název parametru|Popis parametru|Datový typ
---------------|---------------|----------
[allowed_payment_instruments](#payment-instrument)|Pole povolených platebních metod|string, nabývající hodnot viz [payment_instrument](#payment-instrument)
[default_payment_instrument](#payment-instrument)|Preferovaná platební metoda|string, nabývající hodnot viz [payment_instrument](#payment-instrument)
[default_swift](#swift)|Preferová banka pokud je default_payment_instrument nastaveno na BANK_ACCOUNT, nastaveno pomocí SWIFT kódu banky|string, nabývající hodnot viz [SWIFT](#swift)
[allowed_swifts](#swift)|Pole povolených kódů bank| string, nabývající hodnot viz [SWIFT](#swift)
[bank_account](#bank-account)|Údaje o bankovním účtu plátce|Objekt
[payment_card](#payment-card)|Údaje o použité platební kartě|Objekt
[contact](#contact)|Údaje o zákaníkovi|Objekt
verify_pin|PIN pro účely [identifikační platby](#identifikacni-platba)|String, 4 číslice
allowed_card_token|Token pro účely [identifikační platby](#identifikacni-platba)|String

##contact
Zákaznické informace

```json
{
   "first_name":"Zbynek",
   "last_name":"Zak",
   "email":"test@test.cz",
   "phone_number":"+420777456123",
   "city":"C.Budejovice",
   "street":"Plana 67",
   "postal_code":"373 01",
   "country_code":"CZE"
}
```

Název parametru|Popis parametru|Datový typ
---------------|---------------|-------
first_name|Jméno zákazníka|string, 256 znaků
last_name|Příjmení zákazníka|string, 256 znaků
email|Validní e-mail zákazníka|string, 128 znaků
phone_number|Telefonní číslo zákazníka s předvolbou|string, 128 znaků
city|Město zákazníka|string, 128 znaků
street|Ulice zákazníka|string, 128 znaků
postal_code|Poštovní směrovací číslo zákazníka|string, 16 znaků
country_code|Kód státu zákazníka| string [ISO 3166-1 alpha-3](http://en.wikipedia.org/wiki/ISO_3166-1_alpha-3)

##target
Identifikace příjemce platby

```json
{
  "type":"ACCOUNT",
  "goid":"8123456789"
}
```

Název parametru|Popis parametru|Datový typ
---------------|---------------|-------
type|Popis příjemce platby|string, nastaveno na ACCOUNT
goid|Jedinečný identifikátor eshopu v systému platební brány|long
email|E-mail