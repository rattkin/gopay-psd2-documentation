#Objects
Description of each object used within the communication with the payment gateway. 

##accounts
Information about electronic money account

```json
{
    "id": 100001660,
    "balance": 0,
    "currency": "EUR"
}
```

Parameter name|Description| Type
---------------|---------------|----------
id| ID of account
balance| Balance of account
[currency](#currency)|Currency of payment, format corresponds to [ISO 4217](http://www.iso.org/iso/home/standards/currency_codes.htm)

##address
Address

```json
{
  "street": "Planá 67",
  "postal_code": "37001",
  "city": "Planá",
  "country": "cz"
}
```
Parameter name|Description| Type
---------------|---------------|----------
street| Street | string
postal_code| Postal code | string
city| City | string
country| Country code| string [ISO 3166-2](https://en.wikipedia.org/wiki/ISO_3166-2)

##payer
Definition of the payer or the payment

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

Parameter name|Description| Type
---------------|---------------|----------
[allowed_payment_instruments](#payment-instrument)|Array of allowed payment methods|string, can gain values of [payment_instrument](#payment-instrument)
[default_payment_instrument](#payment-instrument)|Preferred payment method|string, can gain values of [payment_instrument](#payment-instrument)
[default_swift](#swift)|Preferred bank if default_payment_instrument is set to BANK_ACCOUNT, set by SWIFT code|string, can gain values of [SWIFT](#swift)
[allowed_swifts](#swift)|Array of allowed bank codes| string, can gain values of [SWIFT](#swift)
[bank_account](#bank-account)|Bank account information|Object
[payment_card](#payment-card)|Payment card information|Object
[contact](#contact)|Customer data|Object
verify_pin|PIN for [identification payment](#identification-payment) purposes|String, 4 digits
allowed_card_token|Token for [identification payment](#identification-payment) purposes|String

##contact
Customer information

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

Parameter name|Description| Type
---------------|---------------|-------
first_name|First name|string, 256 characters
last_name|Last name|string, 256 characters
email|E-mail|string, 128 characters
phone_number|Phone number with country code|string 128 characters
city|City|string, 128 characters
street|Street|string, 128 characters
postal_code|Postal code|string 16 characters
country_code|Country code| string [ISO 3166-1 alpha-3](http://en.wikipedia.org/wiki/ISO_3166-1_alpha-3)

##counterparty

Type of counterparty


```json
{
  "type": "ACCOUNT",
  "value": "goshop.com"
}
```

Parameter name|Description|Type
---------------|---------------|-------
[type](#counterparty-type)|Type of counterparty|string
value|Counterparty'S description| string

##target
Identification of the payee

```json
{
  "type":"ACCOUNT",
  "goid":"8123456789"
}
```

Parameter name|Description| Type
---------------|---------------|-------
type|Description of payee|string
goid|Unique identifier of an e-shop in the payment gateway system|long
email|E-mail|string