---
layout: default
title: Send Messages
nav_order: 3
has_children: false
parent : API Integration
---
# Sending Messages
Message API calls are sent to the **/api/v1/message/send** endpoint regardless of message type, but the content of the JSON message body differs for each type of message (text, image, etc.). See the [Full Documentation](/server-contak/public2/index.html?shell#sendCustomerNoteUsingPOST): for information regarding the type of messages you want to send:

### OTP Message
#### Sample Request : 
##### POST : /entoc/send
```javascript
{
  "phone": "9199887766",
  "template": {
    "code": "LOGIN_OTP_TEMPLATE", // Name of your template
    "model": {
      "prefix": "", // Optional
      "value": "432765",
      "data": {
        // Additonal Date as per template
      }
    }
  },
  "validity": 60 //Message validty in seconds
}
```

### Transactional Message
#### Sample Request : 
##### POST : /entoc/send
```javascript
{
  "phone": "9199887766",
  "template": {
    "code": "DEBIT_ALERT_TEMPLATE", // Name of your template
    "model": {
      "template"
      "prefix": "Rs", // Optional
      "value": "50,000", // Value in Focus
      "data": {
        // Additonal Date as per template
      }
    }
  },
  "validity": 60 //Message validty in seconds
}
```
