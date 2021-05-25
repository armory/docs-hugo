---
title: "Task Type: scaleManifest"
linktitle: "scaleManifest"
description: "fill me with delicious data, Stephen!"
---

- **Path:** tasks
- **Method:** Post
- **Package:** `spinnaker.http.authz`

## Example Payload

<details><summary>Click to expand</summary>

```json
{
  "input": {
    "body": {
      "application": "hostname",
      "description": "Scale manifest",
      "job": [
        {
          "account": "spinnaker",
          "cloudProvider": "kubernetes",
          "location": "staging",
          "manifestName": "deployment hostname",
          "reason": null,
          "replicas": "5",
          "type": "scaleManifest",
          "user": "myUserName"
        }
      ]
    },
    "method": "POST",
    "path": [
      "tasks"
    ],
    "user": {
      "isAdmin": false,
      "roles": [],
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

| Key                              | Type      | Description |
| -------------------------------- | --------- | ----------- |
| `input.body.application`         | `string`  |             |
| `input.body.description`         | `string`  |             |
| `input.body.job[].account`       | `string`  |             |
| `input.body.job[].cloudProvider` | `string`  |             |
| `input.body.job[].location`      | `string`  |             |
| `input.body.job[].manifestName`  | `string`  |             |
| `input.body.job[].reason`        | ` `       |             |
| `input.body.job[].replicas`      | `string`  |             |
| `input.body.job[].type`          | `string`  |             |
| `input.body.job[].user`          | `string`  |             |
| `input.method`                   | `string`  |             |
| `input.path[]`                   | `string`  |             |
| `input.user.isAdmin`             | `boolean` |             |
| `input.user.username`            | `string`  |             |