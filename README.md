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
class User{
  +id: String
}

```
