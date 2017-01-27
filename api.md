# Cardinal API

## API Objects


## Users

|User Object|||
|---|---|---|
|Field|Type|Description|
|id|`string`|the id of the user|
|display_name|`string`|the display name of the user|

### Example User Object

```json
{
    "id" : "ccfc13b8-e22a-4c8a-a4c1-8faf9fef556f",
    "display_name" : "John Appleseed"
}
```

## Meetings

|Meeting Object Structure|||
|---|---|---|
|Field|Type|Description|
|id|`string`|the id of the meeting|
|name|`string`|the name of the meeting|
|created_time|`datetime`|the time the meeting was created|

### Example Meeting Object

```json
{
    "id" : "ccfc13b8-e22a-4c8a-a4c1-8faf9fef556f",
    "name" : "Super Important Meeting"
}
```

## Meeting Time

|Meeting Time Object|||
|---|---|---|
|Field|Type|Description|
|start_time|`datetime`|the starting time of the meeting|
|end_time|`datetime`|the ending time of the meeting|

### Example Meeting Time Object

```json
{
    "start_time" : "",
    "end_time" : ""
}
```

## Messages

|Message Object|||
|---|---|---|
|Field|Type|Description|
|id|`string`|the id of the message|
|meeting_id|`string`|the id of the meeting this message belongs to|
|author|`user`|the user who posted the message|
|content|`string`|the content of the message|
|created_time|`datetime`|the time the message was created|

### Example Message Object

```json
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
```

## Get a Meeting

```http
GET /meetings/{meeting.id}
```

Get a meeting by id. Returns a meeting object.


## Create a Meeting

```http
POST /meetings/
```

Creates a new meeting. Returns a meeting object representing the newly created meeting.

|JSON Body Params|||
|---|---|---|
|Field|Type|Description|
|name|`string`|the name of the meeting|

## Get Suggested Meeting Times

```
GET /meetings/{meeting.id}/suggested-times
```

Gets a list of suggested meeting times for a meeting.

## Get Meeting messages

```
GET /meetings/{meeting.id}/messages
```

Returns a list of messages for a meeting.

## Create Message

```
POST /meetings/{meeting.id}/messages
```

Posts a message to a meeting. Returns a message object representing the new message.

|JSON Body Params|||
|---|---|---|
|Field|Type|Description|
|content|`string`|the content of the message|

## Join a Meeting

```
POST /meeting/{meeting.id}/join
```

Adds the user to an existing meeting.