## Cards [/cards]
Cards endspoint allows you to manage card Details. Request and Response format will be only in JSON format.

### Cards 
Cards resource represents following details

| Property | Type | As request | As response | Description |
| :-------------------- | :---------- | :-------------------- | :-------------------- | ------------------------------------------------------------ |
| id | String | Not required | Returned always | Its helps to identify Card resource. It is a randomly generated for each resource .|
| holderName|String | Optional | Returned always | Its helps to identify the name of the card holder.|
|cardType|String  | Optional | Returned always| It contains the type of card like Visa,Maestro.|
|cardNumber|String | Optional | Returned always| It contains the card number of the Payment card.|
|expiryMonth|Integer | Optional | Returned always| It contains the Expiry month of the payment card.|
|expiryYear|Integer | Optional | Returned always| It contains the Expiry year of the payment card.|
|saveCardID|String | Optional | Returned always| It contains the unique id for each card.|
|cvv|Integer| Optional | Returned always| It contains the cvv number of the card|
|priorityCard|String| Optional | Returned always| It contains the priority flag of that particular customer. Value may be 'Y' or 'N'|

### Use cases

### Retrieve cards [GET/cards]
+ Request

    + Headers
    
                Authorization: Bearer {accesstoken}
                cid: 05e230bf-a9cf-4b31-bc54-d3a995f62526

+ Response 200 (application/json)

            {
                "status": "SUCCESS",
                "data": {
                    "cards": [{
                        "id": "987654321",
                        "holderName": "Anburaja",
                        "cardType": "visa",
                        "cardNumber": "5eeBZ++aHquYp2pmYseO9W3r+1zginDfYs8KsFfHVBk=",
                        "expiryMonth": "05",
                        "expiryYear": "2020",
                        "saveCardID": "00505683065B1EE78EF34A3F0BD0AF4C",
                        "cvv": "123",
                        "priorityCard": "Y"
                    }]
                },
                "errors": {}
            }
            
+ Request 'No Cards available'

    + Headers

            Authorization: Bearer {accesstoken}
            cid: 05e230bf-a9cf-4b31-bc54-d3a995f62526

+ Response 200 (application/json)

            {
                "status": "SUCCESS",
                "data": {
                    "cards": []
                },
                "errors": {}
            }

### Retrieve specific card details [GET /cards/{id}]

+ Parameters

    + id: 00505683065B1EE78EF34A3F0BD0AF4C (string) - SaveCardId

+ Request

    + Headers

            Authorization: Bearer {accesstoken}
            cid: 05e230bf-a9cf-4b31-bc54-d3a995f62526

+ Response 200 (application/json)

        {
            "status": "SUCCESS",
            "data": {
                "card": {
                    "id": "987654321",
                    "holderName": "Anburaja",
                    "cardType": "visa",
                    "cardNumber": "5eeBZ++aHquYp2pmYseO9W3r+1zginDfYs8KsFfHVBk=",
                    "expiryMonth": "05",
                    "expiryYear": "2020",
                    "saveCardID": "00505683065B1EE78EF34A3F0BD0AF4C",
                    "cvv": "123",
                    "priorityCard": "Y"
                }
            },
            "errors": {}
        }

### Save card Detail [POST/cards]

+ Request 'Success'

    + Headers

            Authorization: Bearer {accesstoken}
            cid: 05e230bf-a9cf-4b31-bc54-d3a995f62526
    + Body

            {
                "card": {
                    "holderName": "Anburaja",
                    "cardType": "visa",
                    "cardNumber": "5eeBZ++aHquYp2pmYseO9W3r+1zginDfYs8KsFfHVBk=",
                    "expiryMonth": "05",
                    "expiryYear": "2020",
                    "cvv": "123",
                    "priorityCard": "Y"
                },
                "meta": {}
            }

+ Response 200 (application/json)
            
            {
                "status": "SUCCESS",
                "data": {
                    "card": {
                        "id": "00505683065B1EE78EF34A3F0BD0AF4C",
                        "holderName": "Anburaja",
                        "cardType": "visa",
                        "cardNumber": "5eeBZ++aHquYp2pmYseO9W3r+1zginDfYs8KsFfHVBk=",
                        "expiryMonth": "05",
                        "expiryYear": "2020",
                        "cvv": "123",
                        "priorityCard": "Y"
                    }
                },
                "errors": {}
            }

+ Request 'Card already available'
    
    + Headers
    
            cid: 05e230bf-a9cf-4b31-bc54-d3a995f62526
    
    + Body

            {
            "card": {
                "holderName": "Anburaja",
                "cardType": "visa",
                "cardNumber": "5eeBZ++aHquYp2pmYseO9W3r+1zginDfYs8KsFfHVBk=",
                "expiryMonth": "05",
                "expiryYear": "2020",
                "cvv": "123",
                "priorityCard": "Y"
            },
            "meta": {}
            }
    
+ Response 400 (application/json)

        {
            "status": "FAIL",
            "data": {},
            "errors": [{
                "code": "card",
                "message": "error.card.already.available"
            }],
            "meta": {}
        }
        
+ Request 'Service unavailable to save card Detail'
    
        + Headers
            cid: 05e230bf-a9cf-4b31-bc54-d3a995f62526
    
    + Body

            {
            "card": {
                "holderName": "Anburaja",
                "cardType": "visa",
                "cardNumber": "5eeBZ++aHquYp2pmYseO9W3r+1zginDfYs8KsFfHVBk=",
                "expiryMonth": "05",
                "expiryYear": "2020",
                "cvv": "123",
                "priorityCard": "Y"
            },
            "meta": {}
            }

+ Response 500 (application/json)

        {
            "status": "FAIL",
            "data": {},
            "errors": [{
                "code": "Service unavailable",
                "message": "error.sap.pi.operation.failure"
            }],
            "meta": {}
        }

### Edit card Detail [PUT /cards/{id}]

+ Parameters

    + id: 00505683065B1EE78EF34A3F0BD0AF4C (string) - SaveCardId

+ Request
    
        + Headers
            cid: 05e230bf-a9cf-4b31-bc54-d3a995f62526
    
    + Body

            {
            "card": {
                "holderName": "Anburaja",
                "cardType": "visa",
                "cardNumber": "5eeBZ++aHquYp2pmYseO9W3r+1zginDfYs8KsFfHVBk=",
                "expiryMonth": "05",
                "expiryYear": "2025",
                "cvv": "123",
                "priorityCard": "Y"
            },
            "meta": {}
            }

+ Response 200 (application/json)

        {
            "status": "SUCCESS",
            "data": {
                "card": {
                    "id": "00505683065B1EE78EF34A3F0BD0AF4C",
                    "holderName": "Anburaja",
                    "cardType": "visa",
                    "cardNumber": "5eeBZ++aHquYp2pmYseO9W3r+1zginDfYs8KsFfHVBk=",
                    "expiryMonth": "05",
                    "expiryYear": "2025",
                    "cvv": "123",
                    "priorityCard": "Y"
                }
            },
            "errors": {}
        }

### Delete card Detail [DELETE /cards/{id}]

+ Parameters

    + id: 00505683065B1EE78EF34A3F0BD0AF4C (string) - Id

+ Request

      + Headers
            cid: 05e230bf-a9cf-4b31-bc54-d3a995f62526

+ Response 204

+ Request 'Error from SAP'

        + Headers
            cid: 05e230bf-a9cf-4b31-bc54-d3a995f62526

+ Response 500 (application/json)

        {
            "status": "ERROR",
            "data": {},
            "errors": [{
              "code": "system",
              "message": "error.system.unexpected.error"
            }],
            "meta": {}
        }

+ Request 'Card number is blank'
        
        + Headers
            cid: 05e230bf-a9cf-4b31-bc54-d3a995f62526

+ Response 400 (application/json)

        {
            "status": "FAIL",
            "data": {},
            "errors": [{
                "code": "cardNumber",
                "message": "error.client.cardNumber.blank"
            }],
            "meta": {}
        }

+ Request 'Invalid card number'
    
        + Headers
            cid: 05e230bf-a9cf-4b31-bc54-d3a995f62526

+ Response 400 (application/json)

        {
            "status": "FAIL",
            "data": {},
            "errors": [{
                "code": "cardNumber",
                "message": "error.client.cardNumber.invalid"
            }],
            "meta": {}
        }
