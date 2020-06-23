---
title: Tag value types
summary: Understand the format of the tag values used in the Cloudmarque tagging scheme.
tags: tags, automation, meta, values
---
## Email
This value type is used for contact information, and includes both the human-readable name of the contact alongside their email address.

### Format
```
"Name" [email]
```

### Validation
Validation rules are as follows:

 * **Name**
   * Must appear in quotes
 * **Email**
   * Must appear in square brackets
   * Must validate against the regular expression: `[\w]@[\w]`

Only whitespace characters should appear outside the quoted value and email address.

### Examples
```
"Archie Baler" [a.baler@acme.com]
"IT Support" [it.support@acme.com]
```

## JArray
This value type indicates that the tag value should contain a JSON formatted array.

### Format
```
[ "val1", "val2", "val3" ]
```

### Validation
A standard JSON-formatted array. Square brackets define the array of values. Values in the array are comma separated; string values are quoted, while boolean and numerical values are represented without quotes. The following examples also represent valid JArray values:

### Examples
``` JSON
[ "Sausages", 12, true ]
[ true ]
```

## JObject
This value type indicates that the tag value should contain a JSON formatted object. Details of the object keys and values are specified as part of the relevant tag definition.

### Format
```
{ key: "value", key2: "value" }
```

### Validation
A standard JSON-formatted object. The object itself is defined between start and end braces, with keys and values making up the properties of the object. Key values can be simple types like string, numerics, and booleans; they can also be complex types like JArrays or even other JObjects.

### Examples
This example shows three properties, using simple types:
``` JSON
{ string: "Hitchhiker", numeric: 42, boolean: true }
```
This example shows a key with a value containing an array:
``` JSON
{ call: "sum.ps1", params: [ 40, 1 ] }
```
This example shows a nested JSON structure (formatted onto multiple lines for clarity):
``` JSON
{
    name: "Kevin",
    colors: [ "Mauve", "Taupe" ],
    car: { 
        wheels: 4, 
        name: "Gofast 2000",
        isDeathTrap: true
    }
}
```
