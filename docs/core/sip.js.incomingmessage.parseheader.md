<!-- Do not edit this file. It is automatically generated by API Documenter. -->

[Home](./index.md) &gt; [sip.js](./sip.js.md) &gt; [IncomingMessage](./sip.js.incomingmessage.md) &gt; [parseHeader](./sip.js.incomingmessage.parseheader.md)

## IncomingMessage.parseHeader() method

Parse the given header on the given index.

<b>Signature:</b>

```typescript
parseHeader(name: string, idx?: number): any | undefined;
```

## Parameters

|  Parameter | Type | Description |
|  --- | --- | --- |
|  name | string | header name |
|  idx | number | header index |

<b>Returns:</b>

any \| undefined

Parsed header object, undefined if the header is not present or in case of a parsing error.
