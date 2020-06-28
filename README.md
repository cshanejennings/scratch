## Incoming message diagram
can be viewed with the [GitHub + Mermaid Chrome Extension](https://chrome.google.com/webstore/detail/github-%2B-mermaid/goiiopgdnkogdbjmncgedmgpoajilohe/related?hl=en)

```mermaid
sequenceDiagram
Note right of SMS: After Authentication
SMS ->> User: Id by "To" phone number
SMS-->>Message: Search for last "From" number
Note right of Thread: Thread created if<br> it doesn't exist
Message-->> Thread: Get last thread_id
Note right of Thread: Thread updated_at<br> adjusted
Thread-->> Message: New Message Created
Message-->> User: Update user session

```

## Related Classes
```mermaid
classDiagram
User <|-- Thread
Thread<|-- Message

class User{
  #first_name: String
  #last_name: String
  #email: String
  #sms_number: String
  #sms_name: String
  #company_name: String
  -password: String
}

class Thread{
  - id: int
  - user_id: int
  - due: ts
  - created_at: ts
  - updated_at: ts
  - deleted_at: ts
  + messages(): HasMany
}

class Message{
- id: int
- thread_id: int
- from: phone
- to: phone
- msg: string
- created_at: ts
- deleted_at: ts
}

class TwilioSMS{
+AccountSid: String
+SmsStatus: String
+To: String
+From: String
+Body: String
+SmsMessageSid: String
+NumMedia: String
+NumSegments: String
+MessageSid: String
+ApiVersion: String
+MediaUrlX: String
}

```
