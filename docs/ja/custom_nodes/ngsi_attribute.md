# NGSI attribute

このカスタム・ノードは、NGSIv2 エンティティの属性の読み取り、更新、または削除ができるノードです。

![](https://raw.githubusercontent.com/lets-fiware/node-red-contrib-letsfiware-NGSI/gh-pages/images/attribute/attribute-01.png)

## コンテンツ

<details>
<summary><strong>詳細</strong></summary>

-   [属性の読み取り](#read-an-attribute)
-   [属性の更新](#update-an-attribute)
-   [属性の削除](#delete-an-attribute)
-   [Payload 内の actionType の値を使用](#use-value-of-actionType-in-payload)

</details>

<a name="read-an-attribute"></a>

## 属性の読み取り

NGSIv2 エンティティの属性を読み取ることができます。

### プロパティ

![](https://raw.githubusercontent.com/lets-fiware/node-red-contrib-letsfiware-NGSI/gh-pages/images/attribute/attribute-02.png)

-   `name`: ノード・インスタンスの名前
-   `Context Broker`: Context Broker のエンドポイント
-   `ServicePath`: FIWARE Service Path
-   `Action type`: `read`
-   `Entity id`: 読み取る属性のエンティティ id
-   `Entity type`: 読み取る属性のエンティティ・タイプ
-   `Attribute name`: 読み取る属性の名前
-   `Metadata`: 属性を読み取る属性名
-   `Skip forwarding`: Context Broker は Context Provider への転送をスキップします

### 例

#### 入力

Payload *JSON Object*

`msg.payload` には、読み取る属性に関連する情報が含まれている必要があります。

```
{}
```

```
{
  "attrName": "relativeHumidity"
}
```

```
{
  "id": "E",
  "type": "T",
  "attrName": "relativeHumidity"
}
```

#### 出力

Payload *JSON Object*

`msg.payload` には、属性を表すオブジェクトが含まれています。

```
{
  "type":"Number",
  "value":45,
  "metadata":{}
}
```

<a name="update-an-attribute"></a>

## 属性の更新

NGSIv2 エンティティの属性を更新できます。

### プロパティ

![](https://raw.githubusercontent.com/lets-fiware/node-red-contrib-letsfiware-NGSI/gh-pages/images/attribute/attribute-03.png)

-   `name`: ノード・インスタンスの名前
-   `Context Broker`: Context Broker のエンドポイント
-   `ServicePath`: FIWARE Service Path
-   `Action type`: `update`
-   `Entity id`: 更新する属性のエンティティ id
-   `Entity type`: 更新する属性のエンティティ・タイプ
-   `Attribute name`: 更新する属性の名前
-   `Override metadata`: true の場合、既存のメタデータを置き換えます
-   `Forced update`: true の場合、一致するサブスクリプションをトリガーします
-   `Flow control`: true の場合、フロー制御メカニズムが有効になります

### 例

#### 入力

Payload  *JSON Object*

`msg.payload` には、更新する属性を表すオブジェクトが含まれている必要があります。

```
{
  "type": "Number",
  "value": 1234.5
}
```

#### 出力

Payload *Number* または *null*

`msg.payload` にはステータス・コードが含まれています。

```
204
```

```
null
```

<a name="delete-an-attribute"></a>

## 属性の削除

NGSIv2 エンティティの属性を削除できます。

### プロパティ

![](https://raw.githubusercontent.com/lets-fiware/node-red-contrib-letsfiware-NGSI/gh-pages/images/attribute/attribute-04.png)

-   `name`: ノード・インスタンスの名前
-   `Context Broker`: Context Broker のエンドポイント
-   `ServicePath`: FIWARE Service Path
-   `Action type`: `delete`
-   `Entity id`: 削除する属性のエンティティ id
-   `Entity type`: 削除する属性のエンティティ・タイプ
-   `Attribute name`: 削除する属性の名前

### 例

#### 入力

Payload  *JSON Object*

`msg.payload` には、削除する属性に関連する情報が含まれている必要があります。

```
{}
```

```
{
  "attrName": "relativeHumidity"
}
```

```
{
  "id": "E",
  "type": "T",
  "attrName": "relativeHumidity"
}
```


#### 出力

Payload *null* または *string*

`msg.payload` にはステータス・コードが含まれています。

```
204
```

```
null
```

<a name="use-value-of-actionType-in-payload"></a>

## Payload 内の actionType の値を使用

NGSIv2 エンティティの属性の読み取り、更新、または削除が可能です。

### プロパティ

![](https://raw.githubusercontent.com/lets-fiware/node-red-contrib-letsfiware-NGSI/gh-pages/images/attribute/attribute-05.png)

-   `name`: ノード・インスタンスの名前
-   `Context Broker`: Context Broker のエンドポイント
-   `ServicePath`: FIWARE Service Path
-   `Action type`: `value of actionType in payload`
-   `Entity id`: 読み取り、更新、または削除を行う属性のエンティティ id
-   `Entity type`: 読み取り、更新、または削除を行う属性のエンティティ・タイプ
-   `Attribute name`: 読み取り、更新、または削除を行う属性の名前
-   `Metadata`: メタデータ名のリスト
-   `Skip forwarding`: Context Broker は Context Provider への転送をスキップします
-   `Override metadata`: true の場合、既存のメタデータを置き換えます
-   `Forced update`: true の場合、一致するサブスクリプションをトリガーします
-   `Flow control`: true の場合、フロー制御メカニズムが有効になります

### 例

属性を読み取る場合、`msg.payload` には、読み取る属性に関連する情報を含む JSON オブジェクトが含まれている必要があります。

#### 入力 1

Payload  *JSON Object*

```
{
  "actionType": "read",
  "attrName": "relativeHumidity"
}
```

#### 出力 1

Payload *JSON Object*

`msg.payload` には、属性を表すオブジェクトが含まれています。

```
{
  "type":"Number",
  "value":45,
  "metadata":{}
}
```

属性を更新する場合、 `msg.payload` には、更新する属性の関連情報を含む JSON オブジェクトが含まれている必要があります。

#### 入力 2

Payload  *JSON Object*

```
{
  "actionType": "update",
  "attribute": {
    "type": "Number",
    "value": 1234.5
  }
}
```

#### 出力 2

Payload *Number* または *null*

`msg.payload` にはステータス・コードが含まれています。

```
204
```

```
null
```

属性を削除する場合、`msg.payload` には、削除する属性に関連する情報を含む JSON オブジェクトが含まれている必要があります。

#### 入力 3

Payload  *JSON Object*

```
{
  "actionType": "delete",
  "attrName": "relativeHumidity"
}
```

#### 出力 3

Payload *Number* または *null*

`msg.payload` にはステータス・コードが含まれています。

```
204
```

```
null
```
