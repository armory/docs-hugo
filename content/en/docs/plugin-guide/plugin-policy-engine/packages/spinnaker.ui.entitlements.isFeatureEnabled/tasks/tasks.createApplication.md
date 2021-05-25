---
title: "spinnaker.ui.entitlements.isFeatureEnabled.tasks.type.createApplication"
linktitle: "type.createApplication"
description: "fill me with delicious data, Stephen!"
---

## Example Payload

<details><summary>Click to expand</summary>

```json
{
  "input": {
    "body": {
      "job": [
        {
          "type": "createApplication"
        }
      ]
    },
    "method": "POST",
    "path": [
      "tasks"
    ],
    "user": {
      "isAdmin": false,
      "roles": [
        {
          "name": "armory-io",
          "source": "GITHUB_TEAMS"
        },
        {
          "name": "productmanagers",
          "source": "GITHUB_TEAMS"
        }
      ],
      "username": "myUserName"
    }
  }
}
```
</details>

## Example Policy

```rego

```

## Keys

| Key                                          | Type      | Description                                              |
|----------------------------------------------|-----------|----------------------------------------------------------|
| `input.body.job[].type` | `string` |
| `input.method` | `string` |
| `input.path[]` | `string` |
| `input.user.isAdmin` | `boolean` |
| `input.user.roles[].name` | `string` |
| `input.user.roles[].source` | `string` |
| `input.user.username` | `string` |