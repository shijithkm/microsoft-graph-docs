# ItemReference resource type

The **ItemReference** resource provides information necessary to address a [DriveItem](driveitem.md) via the API.

## JSON representation

Here is a JSON representation of the resource

<!-- {
  "blockType": "resource",
  "optionalProperties": [ "path", "shareId", "sharepointIds" ],
  "@odata.type": "microsoft.graph.itemReference"
}-->

```json
{
  "driveId": "string",
  "id": "string",
  "name": "string",
  "path": "string",
  "shareId": "string",
  "sharepointIds": { "@odata.type": "microsoft.graph.sharepointIds" }
}
```

## Properties

| Property      | Type                              | Description                                                                                                |
| :------------ | :-------------------------------- | :--------------------------------------------------------------------------------------------------------- |
| driveId       | String                            | Unique identifier of the drive instance that contains the item. Read-only.                                 |
| id            | String                            | Unique identifier of the item in the drive. Read-only.                                                     |
| name          | String                            | The name of the item being referenced. Read-only.                                                          |
| path          | String                            | Path that can be used to navigate to the item. Read-only.                                                  |
| shareId       | String                            | A unique identifier for a shared resource that can be accessed via the [Shares](../api/shares_get.md) API. |
| sharepointIds | [sharepointIds](sharepointids.md) | Returns identifiers useful for SharePoint REST compatibility. Read-only.                                   |


## Remarks

To address a **driveItem** from an **itemReference** resource, construct a URL of the format:

```http
GET https://graph.microsoft.com/beta/drives/{driveId}/items/{id}
```

The **path** value is an API path relative to the target drive, for example: `/drive/root:/Documents/myfile.docx`.

To retrieve the human-readable path for a breadcrumb, you can safely ignore everything up to the first `:` in the path string.

<!-- uuid: 8fcb5dbc-d5aa-4681-8e31-b001d5168d79
2015-10-25 14:57:30 UTC -->
<!-- {
  "type": "#page.annotation",
  "description": "itemReference resource",
  "keywords": "",
  "section": "documentation",
  "tocPath": ""
}-->
