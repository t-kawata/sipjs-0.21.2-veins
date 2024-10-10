<!-- Do not edit this file. It is automatically generated by API Documenter. -->

[Home](./index.md) &gt; [sip.js](./sip.js.md) &gt; [Transport](./sip.js.transport.md)

## Transport interface

Transport layer interface expected by the `UserAgent`<!-- -->.

<b>Signature:</b>

```typescript
export interface Transport extends CoreTransport 
```
<b>Extends:</b> [CoreTransport](./sip.js.transport.md)

## Remarks

The transport behaves in a deterministic manner according to the the state defined in [TransportState](./sip.js.transportstate.md)<!-- -->.

The "Connecting" state is ONLY entered in response to the user calling `connect()`<!-- -->. The "Disconnecting" state is ONLY entered in response to the user calling `disconnect()`<!-- -->. The `onConnect` callback is ALWAYS called upon transitioning to the "Connected" state. The `onDisconnect` callback is ALWAYS called upon transitioning from the "Connected" state.

Adherence to the state machine by the transport implementation is critical as the UserAgent depends on this behavior. Furthermore it is critical that the transport transition to the "Disconnected" state in all instances where network connectivity is lost as the UserAgent, API, and application layer more generally depend on knowing network was lost. For example, from a practical standpoint registrations and subscriptions are invalidated when network is lost - particularly in the case of connection oriented transport protocols such as a secure WebSocket transport.

Proper handling the application level protocol recovery must be left to the application layer, thus the transport MUST NOT attempt to "auto-recover" from or otherwise hide loss of network. Note that callbacks and emitters such as `onConnect` and `onDisconnect` MUST NOT call methods `connect()` and `direct()` synchronously (state change handlers must not loop back). They may however do so asynchronously using a Promise resolution, `setTimeout`<!-- -->, or some other method. For example...

```ts
transport.onDisconnect = () => {
  Promise.resolve().then(() => transport.connect());
}
```

## Properties

|  Property | Modifiers | Type | Description |
|  --- | --- | --- | --- |
|  [onConnect](./sip.js.transport.onconnect.md) |  | (() =&gt; void) \| undefined | Callback on state transition to "Connected". |
|  [onDisconnect](./sip.js.transport.ondisconnect.md) |  | ((error?: Error) =&gt; void) \| undefined | Callback on state transition from "Connected". |
|  [onMessage](./sip.js.transport.onmessage.md) |  | ((message: string) =&gt; void) \| undefined | Callback on receipt of a message. |
|  [state](./sip.js.transport.state.md) |  | [TransportState](./sip.js.transportstate.md) | Transport state. |
|  [stateChange](./sip.js.transport.statechange.md) |  | [Emitter](./sip.js.emitter.md)<!-- -->&lt;[TransportState](./sip.js.transportstate.md)<!-- -->&gt; | Transport state change emitter. |

## Methods

|  Method | Description |
|  --- | --- |
|  [connect()](./sip.js.transport.connect.md) | Connect to network. |
|  [disconnect()](./sip.js.transport.disconnect.md) | Disconnect from network. |
|  [dispose()](./sip.js.transport.dispose.md) | Dispose. |
|  [isConnected()](./sip.js.transport.isconnected.md) | Returns true if the <code>state</code> equals "Connected". |
|  [send(message)](./sip.js.transport.send.md) | Send a message. |
