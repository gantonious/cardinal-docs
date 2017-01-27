# Cardinal Events

## Event Structure

|Event Object|||
|---|---|---|
|Field|Type|Description|
|type|`string`|the type of the event|
|payload|`any`|the event payload|

### Example Event Object

```json
{
    "type" : "MESSAGE_CREATED",
    "payload" : 
    {
        "id" : "a397d22a-b9b3-4ff7-9bd6-cfa746f92833",
        "meeting_id" : "ccfc13b8-e22a-4c8a-a4c1-8faf9fef556f",
        "content" : "I'm actually busy Monday evening.",
        "author" : 
        {
            "id" : "ccfc13b8-e22a-4c8a-a4c1-8faf9fef556f",
            "display_name" : "John Appleseed"
        }
    }
}
```

## Events

### Meeting Times Updated

Sent when the times for a meeting are updated.

### Message Created

Sent when a message is created. The payload contains a `message` object.