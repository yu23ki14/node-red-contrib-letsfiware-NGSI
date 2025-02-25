# NGSI Batch update

このカスタム ノードは、単一のバッチ操作で複数のエンティティを追加、厳格な追加 (appendStrict)、更新、置換、または削除できるノードです。
エンティティ・データは、`msg.payload` の一部として提供する必要があります。

![](https://raw.githubusercontent.com/lets-fiware/node-red-contrib-letsfiware-NGSI/gh-pages/images/batch-update/batch-update-01.png)

## コンテンツ

<details>
<summary><strong>詳細</strong></summary>

-   [Append entities](#append-entities)
-   [AppendStrict entities](#appendstrict-entities)
-   [Update entities](#update-entities)
-   [Replace entities](#replace-entities)
-   [Delete entities](#delete-entities)
-   [Use value of actionType in payload](#use-value-of-actionType-in-payload)

</details>

<a name="append-entities"></a>

## Append entities

複数のエンティティを追加できます。

### プロパティ

![](https://raw.githubusercontent.com/lets-fiware/node-red-contrib-letsfiware-NGSI/gh-pages/images/batch-update/batch-update-02.png)

-   `name`: ノード・インスタンスの名前
-   `Context Broker`: Context Broker のエンドポイント
-   `ServicePath`: FIWARE Service Path
-   `Action type`: `append`
-   `Representation`: `normalized` または `keyValues`
-   `Override metadata`: true の場合、既存のメタデータを置き換えます
-   `Forced update`: true の場合、一致するサブスクリプションをトリガーします
-   `Flow control`: true の場合、フロー制御メカニズムが有効になります

### 入力

Payload *JSON Araay* または *JSON Object*

`msg.payload` には、JSON 配列または JSON オブジェクトとして NGSIv2 エンティティが含まれている必要があります。

```
[
  {
    "id": "urn:ngsi-ld:WeatherObserved:sensor001",
    "type": "Sensor",
    "temperature": {
      "type": "Number",
      "value": 20.6,
      "metadata": {}
    }
  },
  {
    "id": "urn:ngsi-ld:WeatherObserved:sensor002",
    "type": "Sensor",
    "temperature": {
      "type": "Number",
      "value": 20.6,
      "metadata": {}
    }
  }
]
```

### 出力

Payload *Number* または *null*

`msg.payload` にはステータス・コードが含まれています。

```
204
```

```
null
```

<a name="appendstrict-entities"></a>

## AppendStrict entities

複数のエンティティを厳格に追加できます。

### プロパティ

![](https://raw.githubusercontent.com/lets-fiware/node-red-contrib-letsfiware-NGSI/gh-pages/images/batch-update/batch-update-03.png)

-   `name`: ノード・インスタンスの名前
-   `Context Broker`: Context Broker のエンドポイント
-   `ServicePath`: FIWARE Service Path
-   `Action type`: `appendStrict`
-   `Representation`: `normalized` または `keyValues`
-   `Override metadata`: true の場合、既存のメタデータを置き換えます
-   `Forced update`: true の場合、一致するサブスクリプションをトリガーします
-   `Flow control`: true の場合、フロー制御メカニズムが有効になります

### 入力

Payload *JSON Araay* または *JSON Object*

`msg.payload` には、JSON 配列または JSON オブジェクトとして NGSIv2 エンティティが含まれている必要があります。

```
[
  {
    "id": "urn:ngsi-ld:WeatherObserved:sensor003",
    "type": "Sensor",
    "temperature": {
      "type": "Number",
      "value": 20.6,
      "metadata": {}
    }
  },
  {
    "id": "urn:ngsi-ld:WeatherObserved:sensor004",
    "type": "Sensor",
    "temperature": {
      "type": "Number",
      "value": 20.6,
      "metadata": {}
    }
  }
]
```

### 出力

Payload *Number* または *null*

`msg.payload` にはステータス・コードが含まれています。

```
204
```

```
null
```

<a name="update-entities"></a>

## Update entities

複数のエンティティを更新できます。

### プロパティ

![](https://raw.githubusercontent.com/lets-fiware/node-red-contrib-letsfiware-NGSI/gh-pages/images/batch-update/batch-update-04.png)

-   `name`: ノード・インスタンスの名前
-   `Context Broker`: Context Broker のエンドポイント
-   `ServicePath`: FIWARE Service Path
-   `Action type`: `update`
-   `Representation`: `normalized` または `keyValues`
-   `Override metadata`: true の場合、既存のメタデータを置き換えます
-   `Forced update`: true の場合、一致するサブスクリプションをトリガーします
-   `Flow control`: true の場合、フロー制御メカニズムが有効になります

### 入力

Payload *JSON Araay* または *JSON Object*

`msg.payload` には、JSON 配列または JSON オブジェクトとして NGSIv2 エンティティが含まれている必要があります。

```
[
  {
    "id": "urn:ngsi-ld:WeatherObserved:sensor001",
    "type": "Sensor",
    "temperature": {
      "type": "Number",
      "value": 30.6,
      "metadata": {}
    }
  },
  {
    "id": "urn:ngsi-ld:WeatherObserved:sensor002",
    "type": "Sensor",
    "temperature": {
      "type": "Number",
      "value": 30.6,
      "metadata": {}
    }
  }
]
```

### 出力

Payload *Number* または *null*

`msg.payload` にはステータス・コードが含まれています。

```
204
```

```
null
```

<a name="replace-entities"></a>

## Replace entities

複数のエンティティを置換できます。

### プロパティ

![](https://raw.githubusercontent.com/lets-fiware/node-red-contrib-letsfiware-NGSI/gh-pages/images/batch-update/batch-update-05.png)

-   `name`: ノード・インスタンスの名前
-   `Context Broker`: Context Broker のエンドポイント
-   `ServicePath`: FIWARE Service Path
-   `Action type`: `replace`
-   `Representation`: `normalized` または `keyValues`
-   `Override metadata`: true の場合、既存のメタデータを置き換えます
-   `Forced update`: true の場合、一致するサブスクリプションをトリガーします
-   `Flow control`: true の場合、フロー制御メカニズムが有効になります

### 入力

Payload *JSON Araay* または *JSON Object*

`msg.payload` には、JSON 配列または JSON オブジェクトとして NGSIv2 エンティティが含まれている必要があります。

```
[
  {
    "id": "urn:ngsi-ld:WeatherObserved:sensor001",
    "type": "Sensor",
    "humidity": {
      "type": "Number",
      "value": 31,
      "metadata": {}
    }
  },
  {
    "id": "urn:ngsi-ld:WeatherObserved:sensor002",
    "type": "Sensor",
    "humidity": {
      "type": "Number",
      "value": 31,
      "metadata": {}
    }
  }
]
```

### 出力

Payload *Number* または *null*

`msg.payload` にはステータス・コードが含まれています。

```
204
```

```
null
```

<a name="delete-entities"></a>

## Delete entities

複数のエンティティを削除できます。

### プロパティ

![](https://raw.githubusercontent.com/lets-fiware/node-red-contrib-letsfiware-NGSI/gh-pages/images/batch-update/batch-update-06.png)

-   `name`: ノード・インスタンスの名前
-   `Context Broker`: Context Broker のエンドポイント
-   `ServicePath`: FIWARE Service Path
-   `Action type`: `delete`
-   `Representation`: `normalized` または `keyValues`
-   `Override metadata`: true の場合、既存のメタデータを置き換えます
-   `Forced update`: true の場合、一致するサブスクリプションをトリガーします
-   `Flow control`: true の場合、フロー制御メカニズムが有効になります

### 入力

Payload *JSON Araay* または *JSON Object*

`msg.payload` には、JSON 配列または JSON オブジェクトとして NGSIv2 エンティティが含まれている必要があります。

```
[
  {
    "id": "urn:ngsi-ld:WeatherObserved:sensor001",
    "type": "Sensor",
    "humidity": {
      "type": "Number",
      "value": 31,
      "metadata": {}
    }
  },
  {
    "id": "urn:ngsi-ld:WeatherObserved:sensor002",
    "type": "Sensor",
    "humidity": {
      "type": "Number",
      "value": 31,
      "metadata": {}
    }
  }
]
```

### 出力

Payload *Number* または *null*

`msg.payload` にはステータス・コードが含まれています。

```
204
```

```
null
```

## Use value of actionType in payload

複数のエンティティを追加、厳格な追加 (appendStrict)、更新、置換、または削除できます。

### プロパティ

![](https://raw.githubusercontent.com/lets-fiware/node-red-contrib-letsfiware-NGSI/gh-pages/images/batch-update/batch-update-07.png)

-   `name`: ノード・インスタンスの名前
-   `Context Broker`: Context Broker のエンドポイント
-   `ServicePath`: FIWARE Service Path
-   `Action type`: `value of actionType in payload`
-   `Representation`: `normalized` または `keyValues`
-   `Override metadata`: true の場合、既存のメタデータを置き換えます
-   `Forced update`: true の場合、一致するサブスクリプションをトリガーします
-   `Flow control`: true の場合、フロー制御メカニズムが有効になります

エンティティを追加する場合, `msg.payload` には、JSON オブジェクトとして `actionType` および NGSIv2 エンティティが含まれている必要があります。

### 入力

Payload *JSON Object*

`msg.payload` には、JSON Object として、`actionType` and `entities` が含まれている必要があります。

```
{
  "actionType": "append",
  "entities": [
    {
      "id": "urn:ngsi-ld:WeatherObserved:sensor001",
      "type": "Sensor",
      "temperature": {
        "type": "Number",
        "value": 20.6,
        "metadata": {}
      }
    },
    {
      "id": "urn:ngsi-ld:WeatherObserved:sensor002",
      "type": "Sensor",
      "temperature": {
        "type": "Number",
        "value": 20.6,
        "metadata": {}
      }
    }
  ]
}
```

### 出力

Payload *Number* または *null*

`msg.payload` にはステータス・コードが含まれています。

```
204
```

```
null
```

エンティティを厳格に追加する場合、`msg.payload` には、JSON オブジェクトとして `actionType` および NGSIv2 エンティティが含まれている必要があります。

### 入力

Payload *JSON Object*

`msg.payload` には、JSON Object として、`actionType` and `entities` が含まれている必要があります。

```
{
  "actionType": "appendStrict",
  "entities": [
    {
      "id": "urn:ngsi-ld:WeatherObserved:sensor003",
      "type": "Sensor",
      "temperature": {
        "type": "Number",
        "value": 20.6,
        "metadata": {}
      }
    },
    {
      "id": "urn:ngsi-ld:WeatherObserved:sensor004",
      "type": "Sensor",
      "temperature": {
        "type": "Number",
        "value": 20.6,
        "metadata": {}
      }
    }
  ]
}
```

### 出力

Payload *Number* または *null*

`msg.payload` にはステータス・コードが含まれています。

```
204
```

```
null
```

エンティティを更新する場合、`msg.payload` には、JSON オブジェクトとして `actionType` および NGSIv2 エンティティが含まれている必要があります。

### 入力

Payload *JSON Object*

`msg.payload` には、JSON Object として、`actionType` and `entities` が含まれている必要があります。

```
{
  "actionType": "update",
  "entities": [
    {
      "id": "urn:ngsi-ld:WeatherObserved:sensor001",
      "type": "Sensor",
      "temperature": {
        "type": "Number",
        "value": 30.6,
        "metadata": {}
      }
    },
    {
      "id": "urn:ngsi-ld:WeatherObserved:sensor002",
      "type": "Sensor",
      "temperature": {
        "type": "Number",
        "value": 30.6,
        "metadata": {}
      }
    }
  ]
}
```

### 出力

Payload *Number* または *null*

`msg.payload` にはステータス・コードが含まれています。

```
204
```

```
null
```

エンティティを置換する場合、`msg.payload` には、JSON オブジェクトとして `actionType` および NGSIv2 エンティティが含まれている必要があります。

### 入力

Payload *JSON Object*

`msg.payload` には、JSON Object として、`actionType` and `entities` が含まれている必要があります。

```
{
  "actionType": "replace",
  "entities": [
    {
      "id": "urn:ngsi-ld:WeatherObserved:sensor001",
      "type": "Sensor",
      "humidity": {
        "type": "Number",
        "value": 31,
        "metadata": {}
      }
    },
    {
      "id": "urn:ngsi-ld:WeatherObserved:sensor002",
      "type": "Sensor",
      "humidity": {
        "type": "Number",
        "value": 31,
        "metadata": {}
      }
    }
  ]
}
```

### 出力

Payload *Number* または *null*

`msg.payload` にはステータス・コードが含まれています。

```
204
```

```
null
```

エンティティを削除する場合、`msg.payload` には、JSON オブジェクトとして `actionType` および NGSIv2 エンティティが含まれている必要があります。

### 入力

Payload *JSON Object*

`msg.payload` には、JSON Object として、`actionType` and `entities` が含まれている必要があります。

```
{
  "actionType": "delete",
  "entities": [
    {
      "id": "urn:ngsi-ld:WeatherObserved:sensor001",
      "type": "Sensor",
      "humidity": {
        "type": "Number",
        "value": 31,
        "metadata": {}
      }
    },
    {
      "id": "urn:ngsi-ld:WeatherObserved:sensor002",
      "type": "Sensor",
      "humidity": {
        "type": "Number",
        "value": 31,
        "metadata": {}
      }
    }
  ]
}
```

### 出力

Payload *Number* または *null*

`msg.payload` にはステータス・コードが含まれています。

```
204
```

```
null
```