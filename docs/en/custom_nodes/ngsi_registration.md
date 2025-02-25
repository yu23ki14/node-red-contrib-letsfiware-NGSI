# NGSI Registration

This custom node is a simple node that allows to create or delete an NGSIv2 registration.

![](https://raw.githubusercontent.com/lets-fiware/node-red-contrib-letsfiware-NGSI/gh-pages/images/registration/registration-01.png)

<details>
<summary><strong>Details</strong></summary>

-   [Create a registration](#create-a-registration)
-   [Delete a registration](#delete-a-registration)
-   [Use value of actionType in payload](#use-value-of-actiontype-in-payload)

</details>

## Create a registration

This operation allows to create a new registration.

### Properties

![](https://raw.githubusercontent.com/lets-fiware/node-red-contrib-letsfiware-NGSI/gh-pages/images/registration/registration-02.png)

-   `name`: A name for a node instance
-   `Context Broker`: An endpoint of a context broker
-   `ServicePath`: FIWARE Service Path
-   `Action type`: `create`

### Examples

#### Input

Payload *JSON Object*

A `msg.payload` contains a NGSIv2 registration data.

```json
{
  "description": "Relative Humidity Context Source",
  "dataProvided": {
    "entities": [
      {
        "id": "room",
        "type": "Room"
      }
    ],
    "attrs": [
      "relativeHumidity"
    ]
  },
  "provider": {
    "http": {
      "url": "http://orion:1026"
    }
  }
}
```

#### Output

Payload  *string*

A `msg.payload` contains a registration id.

```text
63ed51173bdeaadaf909c57b
```

## Delete a registration

This operation allows to delete a existing registration.

### Properties

![](https://raw.githubusercontent.com/lets-fiware/node-red-contrib-letsfiware-NGSI/gh-pages/images/registration/registration-03.png)

-   `name`: A name for a node instance
-   `Context Broker`: An endpoint of a context broker
-   `ServicePath`: FIWARE Service Path
-   `Action type`: `delete`

### Example

#### Input

Payload *string*

A `msg.payload` contains a registration id.

```
63ed51173bdeaadaf909c57b
```

#### Output

Payload *Number* or *null*

A `msg.payload` contains a status code.

```
204
```

```
null
```

## Use value of actionType in payload

This operation allows to create or delete a registration.

### Properties

![](https://raw.githubusercontent.com/lets-fiware/node-red-contrib-letsfiware-NGSI/gh-pages/images/registration/registration-04.png)

-   `name`: A name for a node instance
-   `Context Broker`: An endpoint of a context broker
-   `ServicePath`: FIWARE Service Path
-   `Action type`: `value of actionType in payload`

### Example

When creating a new registration, A `msg.payload` should contain a JSON Object with actionType and registration data.

#### Input

```json
{
  "actionType": "delete",
  "id": "63ed53123bdeaadaf909c57d"
}
```

#### Output

Payload  *string*

A `msg.payload` contains a registration id.

```text
63ed51173bdeaadaf909c57b
```

When deleting a existing registration, A `msg.payload` should contain a JSON Object with actionType and registration id.

#### Input

```json
{
  "actionType": "delete",
  "id": "63ea11e4a0cec98fc6017aae"
}
```

#### Output

Payload *Number* or *null*

A `msg.payload` contains a status code.

```
204
```

```
null
```
