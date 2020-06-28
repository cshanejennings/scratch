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
classDiagram
Class01 <|-- AveryLongClass : Cool
Class03 *-- Class04
Class05 o-- Class06
Class07 .. Class08
Class09 --> C2 : Where am i?
Class09 --* C3
Class09 --|> Class07
Class07 : equals()
Class07 : Object[] elementData
Class01 : size()
Class01 : int chimp
Class01 : int gorilla
Class08 <--> C2: Cool label

```
