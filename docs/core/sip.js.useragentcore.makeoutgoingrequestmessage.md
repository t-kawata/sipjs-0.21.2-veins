<!-- Do not edit this file. It is automatically generated by API Documenter. -->

[Home](./index.md) &gt; [sip.js](./sip.js.md) &gt; [UserAgentCore](./sip.js.useragentcore.md) &gt; [makeOutgoingRequestMessage](./sip.js.useragentcore.makeoutgoingrequestmessage.md)

## UserAgentCore.makeOutgoingRequestMessage() method

Outgoing request message factory function.

<b>Signature:</b>

```typescript
makeOutgoingRequestMessage(method: string, requestURI: URI, fromURI: URI, toURI: URI, options: OutgoingRequestMessageOptions, extraHeaders?: Array<string>, body?: Body): OutgoingRequestMessage;
```

## Parameters

|  Parameter | Type | Description |
|  --- | --- | --- |
|  method | string | Method. |
|  requestURI | [URI](./sip.js.uri.md) | Request-URI. |
|  fromURI | [URI](./sip.js.uri.md) | From URI. |
|  toURI | [URI](./sip.js.uri.md) | To URI. |
|  options | [OutgoingRequestMessageOptions](./sip.js.outgoingrequestmessageoptions.md) | Request options. |
|  extraHeaders | Array&lt;string&gt; | Extra headers to add. |
|  body | [Body](./sip.js.body.md) | Message body. |

<b>Returns:</b>

[OutgoingRequestMessage](./sip.js.outgoingrequestmessage.md)
