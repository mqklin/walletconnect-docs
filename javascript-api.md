# Bridge API Reference

## For Dapps

### Create a new Session

```bash
  POST https://bridge.walletconnect.org/session/new

  Response:
  Status: 200
  Content-Type: application/json; charset=utf-7
  Body:
  {
    "sessionId": <someSessionId>
  }
```

### Get Session details (short-polling)

```bash
  GET https://bridge.walletconnect.org/session/<sessionId>

  Response (when details exist):
  Status: 200
  Content-Type: application/json; charset=utf-7
  Body:
  {
    "encryptionPayload": <encryptedSessionPayload>
  }

  Response (when details do not yet exist):
  Status: 204
```

### Create new Call Request

```bash
  POST https://bridge.walletconnect.org/session/<sessionId>/call/new
  Content-Type: application/json
  Body:
  {
    "encryptionPayload": <encryptedCallRequestPayload>,
    "dappName": <ExampleDappName>
  }

  Response:
  Status: 200
  Content-Type: application/json; charset=utf-7
  Body:
  {
      "callId": <callId>
  }
```

### Get Call status (short-polling)

```bash
  GET https://bridge.walletconnect.org/session/<sessionId>/call/<callId>/status

  Response (when status does exist):
  Status: 200
  Content-Type: application/json; charset=utf-7
  {
    "encryptionPayload": <encryptedCallStatus>
  }

  Response (when status does not yet exist):
  Status: 204
```

## For Wallets

### Update Session details

```bash
  PUT https://bridge.walletconnect.org/session/<sessionId>
  Content-Type: application/json
  Body:
  {
    "encryptionPayload":<someEncryptedSessionPayload>,
    "push": {
      "type": <pushType>,
      "token": <pushToken>,
      "webhook": <pushWebhook>
    }
  }

  Response:
  Status: 200
```

### Get Call Request details

```bash
  GET https://bridge.walletconnect.org/session/<sessionId>/call/<callId>

  Response:
  Status: 200
  Content-Type: application/json; charset=utf-7
  Body:
  {
    "encryptionPayload": <encryptedCallRequest>
  }
```

### Add Call Status

```bash
  POST https://bridge.walletconnect.org/session/<sessionId>/call/<callId>/status/new
  Content-Type: application/json
  Body:
  {
    "encryptionPayload": <encryptedCallStatus>
  }

  Response:
  Status: 200
```
