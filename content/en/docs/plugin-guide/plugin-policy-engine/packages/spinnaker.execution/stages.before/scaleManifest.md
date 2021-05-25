---
title: "spinnaker.execution.stages.before.scaleManifest"
linktitle: "scaleManifest"
description: "fill me with delicious data, Stephen!"
---

The full package name sent to OPA is `spinnaker.execution.stages.before.scaleManifest`. The keys below are children of this path.

## Example Payload

<details><summary>Click to expand</summary>

```json
{
  "input": {
    "pipeline": {
      "application": "hostname",
      "authentication": {
        "allowedAccounts": [
          "spinnaker",
          "staging",
          "staging-ecs"
        ],
        "user": "myUserName"
      },
      "buildTime": 1620752545407,
      "canceled": false,
      "canceledBy": null,
      "cancellationReason": null,
      "description": "Scale manifest",
      "endTime": null,
      "id": "01F5E62DKZH06TP0V627RBP4M2",
      "initialConfig": {},
      "keepWaitingPipelines": false,
      "limitConcurrent": false,
      "name": null,
      "notifications": [],
      "origin": "unknown",
      "partition": null,
      "paused": null,
      "pipelineConfigId": null,
      "source": null,
      "spelEvaluator": null,
      "stages": [
        "01F5E62DKZ1YANDNTZ9ZJY0QGE"
      ],
      "startTime": 1620752545426,
      "startTimeExpiry": null,
      "status": "RUNNING",
      "systemNotifications": [],
      "templateVariables": null,
      "trigger": {
        "artifacts": [],
        "correlationId": null,
        "isDryRun": false,
        "isRebake": false,
        "isStrategy": false,
        "notifications": [],
        "other": {
          "artifacts": [],
          "dryRun": false,
          "expectedArtifacts": [],
          "notifications": [],
          "parameters": {},
          "rebake": false,
          "resolvedExpectedArtifacts": [],
          "strategy": false,
          "type": "manual",
          "user": "myUserName"
        },
        "parameters": {},
        "resolvedExpectedArtifacts": [],
        "type": "manual",
        "user": "myUserName"
      },
      "type": "ORCHESTRATION"
    },
    "stage": {
      "context": {
        "account": "spinnaker",
        "cloudProvider": "kubernetes",
        "deploy.server.groups": {},
        "kato.last.task.id": {
          "id": "552a47bb-59ea-4f5b-aa58-9f28851a6bc6"
        },
        "kato.result.expected": false,
        "kato.task.firstNotFoundRetry": -1,
        "kato.task.lastStatus": "SUCCEEDED",
        "kato.task.notFoundRetryCount": 0,
        "kato.task.terminalRetryCount": 0,
        "kato.tasks": [
          {
            "history": [
              {
                "phase": "ORCHESTRATION",
                "status": "Initializing Orchestration Task"
              },
              {
                "phase": "ORCHESTRATION",
                "status": "Processing op: KubernetesScaleManifestOperation"
              },
              {
                "phase": "SCALE_KUBERNETES_MANIFEST",
                "status": "Starting scale operation..."
              },
              {
                "phase": "SCALE_KUBERNETES_MANIFEST",
                "status": "Looking up resource properties..."
              },
              {
                "phase": "SCALE_KUBERNETES_MANIFEST",
                "status": "Calling scale operation..."
              },
              {
                "phase": "ORCHESTRATION",
                "status": "Orchestration completed."
              }
            ],
            "id": "552a47bb-59ea-4f5b-aa58-9f28851a6bc6",
            "resultObjects": [],
            "status": {
              "completed": true,
              "failed": false,
              "retryable": false
            }
          }
        ],
        "location": "staging",
        "manifest.account.name": "spinnaker",
        "manifest.location": "staging",
        "manifest.name": "deployment hostname",
        "manifestName": "deployment hostname",
        "outputs.manifestNamesByNamespace": {
          "staging": [
            "deployment hostname"
          ]
        },
        "replicas": "5",
        "user": "myUserName"
      },
      "endTime": null,
      "id": "01F5E62DKZ1YANDNTZ9ZJY0QGE",
      "lastModified": null,
      "name": "scaleManifest",
      "outputs": {},
      "parentStageId": null,
      "refId": "0",
      "requisiteStageRefIds": [],
      "scheduledTime": null,
      "startTime": 1620752545489,
      "startTimeExpiry": null,
      "status": "RUNNING",
      "syntheticStageOwner": null,
      "tasks": [
        {
          "endTime": 1620752545644,
          "id": "1",
          "implementingClass": "com.netflix.spinnaker.orca.clouddriver.tasks.manifest.ResolveTargetManifestTask",
          "loopEnd": false,
          "loopStart": false,
          "name": "resolveTargetManifest",
          "stageEnd": false,
          "stageStart": true,
          "startTime": 1620752545521,
          "status": "SUCCEEDED"
        },
        {
          "endTime": 1620752545916,
          "id": "2",
          "implementingClass": "com.netflix.spinnaker.orca.clouddriver.tasks.manifest.ScaleManifestTask",
          "loopEnd": false,
          "loopStart": false,
          "name": "scaleManifest",
          "stageEnd": false,
          "stageStart": false,
          "startTime": 1620752545659,
          "status": "SUCCEEDED"
        },
        {
          "endTime": 1620752551162,
          "id": "3",
          "implementingClass": "com.netflix.spinnaker.orca.clouddriver.tasks.MonitorKatoTask",
          "loopEnd": false,
          "loopStart": false,
          "name": "monitorScale",
          "stageEnd": false,
          "stageStart": false,
          "startTime": 1620752545933,
          "status": "SUCCEEDED"
        },
        {
          "endTime": null,
          "id": "4",
          "implementingClass": "com.netflix.spinnaker.orca.clouddriver.tasks.manifest.WaitForManifestStableTask",
          "loopEnd": false,
          "loopStart": false,
          "name": "waitForManifestToStabilize",
          "stageEnd": true,
          "stageStart": false,
          "startTime": 1620752551183,
          "status": "RUNNING"
        }
      ],
      "type": "scaleManifest"
    },
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

### input.pipeline

| Key                                                               | Type      | Description                                                                 |
| ----------------------------------------------------------------- | --------- | --------------------------------------------------------------------------- |
| `input.pipeline.application`                                      | `string`  | The name of the Spinnaker application to which this pipeline belongs.       |
| `input.pipeline.authentication.allowedAccounts.[]`                | `string`  |                                                                             |
| `input.pipeline.authentication.user`                              | `string`  | The Spinnaker user initiating the change.                                   |
| `input.pipeline.buildTime`                                        | `number`  |                                                                             |
| `input.pipeline.canceled`                                         | `boolean` |                                                                             |
| `input.pipeline.canceledBy`                                       | ``        |                                                                             |
| `input.pipeline.cancellationReason`                               | ``        |                                                                             |
| `input.pipeline.description`                                      | `string`  |                                                                             |
| `input.pipeline.endTime`                                          | ``        |                                                                             |
| `input.pipeline.id`                                               | `string`  |                                                                             |
| `input.pipeline.keepWaitingPipelines`                             | `boolean` |                                                                             |
| `input.pipeline.limitConcurrent`                                  | `boolean` |                                                                             |
| `input.pipeline.name`                                             | ``        |                                                                             |
| `input.pipeline.origin`                                           | `string`  |                                                                             |
| `input.pipeline.partition`                                        | ``        |                                                                             |
| `input.pipeline.paused`                                           | ``        |                                                                             |
| `input.pipeline.pipelineConfigId`                                 | ``        |                                                                             |
| `input.pipeline.source`                                           | ``        |                                                                             |
| `input.pipeline.spelEvaluator`                                    | ``        | Which version of spring expression language is being used to evaluate SpEL. |
| `input.pipeline.stages.[]`                                        | `string`  |                                                                             |
| `input.pipeline.startTime`                                        | `number`  |                                                                             |
| `input.pipeline.startTimeExpiry`                                  | ``        |                                                                             |
| `input.pipeline.status`                                           | `string`  |                                                                             |
| `input.pipeline.templateVariables`                                | ``        |                                                                             |
| `input.pipeline.type`                                             | `string`  |                                                                             |

### input.pipeline.trigger

See [input.pipeline.trigger]({{< ref "input.pipeline.trigger.md" >}}) for more information.

### input.stage

| Key                                                               | Type      | Description                                                                 |
| ----------------------------------------------------------------- | --------- | --------------------------------------------------------------------------- |
| `input.stage.context.account`                                     | `string`  |                                                                             |
| `input.stage.context.cloudProvider`                               | `string`  |                                                                             |
| `input.stage.context.kato.last.task.id.id`                        | `string`  |                                                                             |
| `input.stage.context.kato.result.expected`                        | `boolean` |                                                                             |
| `input.stage.context.kato.task.firstNotFoundRetry`                | `number`  |                                                                             |
| `input.stage.context.kato.task.lastStatus`                        | `string`  |                                                                             |
| `input.stage.context.kato.task.notFoundRetryCount`                | `number`  |                                                                             |
| `input.stage.context.kato.task.terminalRetryCount`                | `number`  |                                                                             |
| `input.stage.context.kato.tasks.[].history.[].phase`              | `string`  |                                                                             |
| `input.stage.context.kato.tasks.[].history.[].status`             | `string`  |                                                                             |
| `input.stage.context.kato.tasks.[].id`                            | `string`  |                                                                             |
| `input.stage.context.kato.tasks.[].status.completed`              | `boolean` |                                                                             |
| `input.stage.context.kato.tasks.[].status.failed`                 | `boolean` |                                                                             |
| `input.stage.context.kato.tasks.[].status.retryable`              | `boolean` |                                                                             |
| `input.stage.context.location`                                    | `string`  |                                                                             |
| `input.stage.context.manifest.account.name`                       | `string`  |                                                                             |
| `input.stage.context.manifest.location`                           | `string`  |                                                                             |
| `input.stage.context.manifest.name`                               | `string`  |                                                                             |
| `input.stage.context.manifestName`                                | `string`  |                                                                             |
| `input.stage.context.outputs.manifestNamesByNamespace.staging.[]` | `string`  |                                                                             |
| `input.stage.context.replicas`                                    | `string`  |                                                                             |
| `input.stage.context.user`                                        | `string`  |                                                                             |
| `input.stage.endTime`                                             | ``        |                                                                             |
| `input.stage.id`                                                  | `string`  |                                                                             |
| `input.stage.lastModified`                                        | ``        |                                                                             |
| `input.stage.name`                                                | `string`  |                                                                             |
| `input.stage.parentStageId`                                       | ``        |                                                                             |
| `input.stage.refId`                                               | `string`  |                                                                             |
| `input.stage.scheduledTime`                                       | ``        |                                                                             |
| `input.stage.startTime`                                           | `number`  |                                                                             |
| `input.stage.startTimeExpiry`                                     | ``        |                                                                             |
| `input.stage.status`                                              | `string`  |                                                                             |
| `input.stage.syntheticStageOwner`                                 | ``        |                                                                             |
| `input.stage.tasks.[].endTime`                                    | `number`  |                                                                             |
| `input.stage.tasks.[].endTime`                                    | ``        |                                                                             |
| `input.stage.tasks.[].id`                                         | `string`  |                                                                             |
| `input.stage.tasks.[].implementingClass`                          | `string`  |                                                                             |
| `input.stage.tasks.[].loopEnd`                                    | `boolean` |                                                                             |
| `input.stage.tasks.[].loopStart`                                  | `boolean` |                                                                             |
| `input.stage.tasks.[].name`                                       | `string`  |                                                                             |
| `input.stage.tasks.[].stageEnd`                                   | `boolean` |                                                                             |
| `input.stage.tasks.[].stageStart`                                 | `boolean` |                                                                             |
| `input.stage.tasks.[].startTime`                                  | `number`  |                                                                             |
| `input.stage.tasks.[].status`                                     | `string`  |                                                                             |
| `input.stage.type`                                                | `string`  | The current state of activity of the stage.                                 |

### input.user

This object provides information about the user performing the action. This can be used to restrict actions by role. See [input.user]({{< ref "input.user.md" >}}) for more information.