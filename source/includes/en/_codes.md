#Code lists

##counterparty_type

Type of counterparty

Parameter value|Description
---------------|---------------
BANK_ACCOUNT | Bank account
PAYMENT_CARD | Payment card
ACCOUNT | GoPay account (personal/merchant)
COUPON | Coupon payment
MOBILE_PHONE | Mobile payment
GOPAY | GoPay fee


##currency
Payment currency

Parameter value|Description
------------------|-----
CZK | Czech crowns
EUR | Euros
PLN | Polish złoty
HUF | Hungarian forint
GBP | British pound
USD | US dollar
RON | Romanian Leu
HRK | Kuna
BGN | Bulgarian Lev

##scope
Parameter describing group of acquired rights

Parameter value|Description
-------|-----
payment-create|Allows only the establishment of payments
payment-all|Allows all operations
account-info| Allows to get account information (for [PSD2 AIS](#ais) purposes only)

##result
Result of operation

Parameter name|Description
---------------|---------------
ACCEPTED| Request accepted 
FINISHED| Operation finished
FAILED| Operation failed

##Payment status 
Payment can gain values following status

Parameter name|Description
-----------|---------------------
CREATED|Payment created 
PAYMENT_METHOD_CHOSEN|Payment method chosen
PAID|Payment paid
AUTHORIZED|Payment pre-authorized
CANCELED|Payment canceled
TIMEOUTED|Payment timeouted
REFUNDED|Payment refunded
PARTIALLY_REFUNDED|Payment partially refunded

##Payment substate
Payment can gain values following substates

Parameter value|Description
-----------|---------------------
_101|Payment pending. We are waiting for the online payment to be made.
_102|Payment pending. We are waiting for the offline payment to be made.
_3001|Bank payment confirmed by letter of advice.
_3002|Bank payment confirmed by statement.
_3003|Bank payment not authorised.
_5001|Approved with zero amount
_5002|Payment declined by the customer's bank authorization centre. The payment card limit had been reached.
_5003|Payment declined by the customer's bank authorization centre. There are some issues at the card issuer side.
_5004|Payment declined by the customer's bank authorization centre. Issues at the card issuer side.
_5005|Payment declined by the customer's bank authorization centre.  Payment card blocked.
_5006|Payment declined by the customer's bank authorization centre. Insufficient funds at the payment card. 
_5007|Payment declined by the customer's bank authorization centre. The payment card is expired.
_5008|Payment declined by the customer's bank authorization centre. The CVV/CVC code had been declined.
_5009, _5015, _5017, _5018, _5019, _6502, _6504|Payment declined in the 3D Secure system of the customer's bank.
_5010, _5014|Payment declined by the customer's bank authorization centre. There are some issues with the payment card. 
_5011, _5036|Payment declined by the customer's bank authorization centre. There are some issues with the payment card account.
_5012|Payment declined by the customer's bank authorization centre. There are some technical issues in the customer's bank authorization centre.
_5013|Payment declined by the customer's bank authorization centre. The customer entered an incorrect card number. 
_5016|Payment declined by the customer's bank authorization centre. The customer's card had not been authorized to make the payment.
_5020|Unknown seller
_5021|Payment declined by the customer's bank authorization centre. The card limits had been exceeded.
_5022|A technical issue occured in the customer's bank authorization centre. 
_5023, _5038|Payment not made. 
_5024|Payment not made. Customer did not enter the payment credentials in the time limit at the payment gateway.
_5025|Payment not made. The specific reason is to be reported to the customer. 
_5026|Payment not made. The total credited amounts exceeded the amount paid. 
_5027|Payment not made. The user is not authorized to undertake the operation. 
_5028|Payment not made. The amount due exceeded the amount authorized. 
_5029|Payment has not been made yet. 
_5030|Payment not made. There were several attempts to settle the payment.
_5031|A technical issue occurred in the bank while processing the payment.
_5033|SMS failed to be received. 
_5035|Card issued in a region where the card payments are not supported. 
_5037|Cardholder cancelled the payment. 
_5039|Payment declined by the customer's bank authorization centre. The payment card is blocked. 
_5040|Duplicate reversal
_5041|Duplicate transaction
_5042|Bank transfer declined. 
_5043|Payment cancelled by user.
_5044|SMS has been sent. It has not been delivered yet. 
_5045|Payment received. Payment is to be credited after it has been processed in the Bitcoin system.
_5046|A full amount of payment not made. 
_5047|Payment made after due date.


## state

State of the account

Parameter value|Description
---------------|---------------
IN_VERIFICATION | In cerification process
ACTIVATED | Activated
RESTRICTED | Functions restricted
SUSPENDED | Suspended
PASSIVE	| Passive mode
DEACTIVATED | Deactivated

## verification_level

Verification level of the account

Parameter value|Description
---------------|---------------
UNVERIFIED| Unverified profile
PARTIALLY_VERIFIED| Partially verified profile
VERIFIED| Verified profile
FULLY_VERIFIED| Fully verified profile

##current_state

State of the merchant account

Parameter value|Description
------------------|-----
BUSINESS_FINISHED| Business finished
CLOSED| Closed
DEACTIVATED| Deactivated
IN_PREPARE |  In prepare
PREPARE_FINISHED | Prepare finished
REQUESTED| Requested
SUSPENDED| Suspended
WORKER_ASSIGNED | Worker assigned

##subject_type

Subjec type

Parameter value|Description
------------------|-----
LEGAL_ENTITY| Legal entity
NATURAL_PERSON| Natural person