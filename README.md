# Roll20 Parser

*Work in Progress*

Generate a JSON document containing the character information scraped from a Roll20 Character sheet.

* Requires downloading the rendered sheet HTML from Roll20.
* Currently accomplished by setting the sheet to pop-out into a separate window and using the browser's dev tools to grab the rendered sheet. 

JSON Schema
```json
{
  "$schema": "http://json-schema.org/draft-04/schema#",
  "type": "object",
  "properties": {
    "name": {
      "type": "string"
    },
    "feats": {
      "type": "array",
      "items": [
        {
          "type": "object",
          "properties": {
            "name": {
              "type": "string"
            },
            "desc": {
              "type": "string"
            },
            "sourceName": {
              "type": "string"
            },
            "sourceType": {
              "type": "string"
            }
          },
          "required": [
            "name",
            "desc",
            "sourceName",
            "sourceType"
          ]
        }
      ]
    },
    "spells": {
      "type": "array",
      "items": [
        {
          "type": "object",
          "properties": {
            "name": {
              "type": "string"
            },
            "spellLevel": {
              "type": "string"
            },
            "spellSchool": {
              "type": "string"
            },
            "castingTime": {
              "type": "string"
            },
            "range": {
              "type": "string"
            },
            "target": {
              "type": "string"
            },
            "components": {
              "type": "string"
            },
            "desc": {
              "type": "string"
            },
            "higherLevels": {
              "type": "string"
            }
          },
          "required": [
            "name",
            "spellLevel",
            "spellSchool",
            "castingTime",
            "range",
            "target",
            "components",
            "desc",
            "higherLevels"
          ]
        }
      ]
    }
  },
  "required": [
    "name",
    "feats",
    "spells"
  ]
}
```