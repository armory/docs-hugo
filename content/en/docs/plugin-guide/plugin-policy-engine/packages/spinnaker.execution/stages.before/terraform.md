---
title: "spinnaker.execution.stages.before.terraform"
linktitle: "terraform"
description: "fill me with delicious data, Stephen!"
---

## Example Payload

<details><summary>Click to expand</summary>

```json
{
  "input": {
    "pipeline": {
      "application": "terraformer",
      "authentication": {
        "allowedAccounts": [
          "spinnaker",
          "staging",
          "staging-ecs"
        ],
        "user": "myUserName"
      },
      "buildTime": 1620923522270,
      "canceled": false,
      "canceledBy": null,
      "cancellationReason": null,
      "description": null,
      "endTime": null,
      "id": "01F5K9474WJBWAJWWDEBV923WA",
      "initialConfig": {},
      "keepWaitingPipelines": false,
      "limitConcurrent": true,
      "name": "Plan_working",
      "notifications": [],
      "origin": "api",
      "partition": null,
      "paused": null,
      "pipelineConfigId": "00819a38-0b79-4a8c-964b-6f0a61dc23cc",
      "source": null,
      "spelEvaluator": "v4",
      "stages": [
        "01F5K9476YYC6Y76VMBN61E1V8",
        {
          "context": {
            "failPipeline": true,
            "judgmentInputs": [],
            "notifications": []
          },
          "endTime": null,
          "id": "01F5K9476Y5M41EN02606JNVA9",
          "lastModified": null,
          "name": "Manual Judgment",
          "outputs": {},
          "parentStageId": null,
          "refId": "2",
          "requisiteStageRefIds": [
            "1"
          ],
          "scheduledTime": null,
          "startTime": null,
          "startTimeExpiry": null,
          "status": "NOT_STARTED",
          "syntheticStageOwner": null,
          "tasks": [],
          "type": "manualJudgment"
        },
        {
          "context": {
            "artifactContents": [
              {
                "contents": "namespace=\"terraformtestvar\"\ndeployName=\"terraformertestvar\"\nreplicas=2",
                "name": "testvariables.tfVar"
              }
            ],
            "artifacts": [
              {
                "customKind": false,
                "metadata": {},
                "name": "testvariables.tfVar",
                "reference": "bmFtZXNwYWNlPSJ0ZXJyYWZvcm10ZXN0dmFyIgpkZXBsb3lOYW1lPSJ0ZXJyYWZvcm1lcnRlc3R2YXIiCnJlcGxpY2FzPTI=",
                "type": "embedded/base64"
              }
            ],
            "expectedArtifacts": [
              {
                "defaultArtifact": {
                  "customKind": true,
                  "metadata": {
                    "id": "04b721c1-8dde-4964-96a4-b5136f6d1408"
                  }
                },
                "id": "bca795c0-b2f6-4acb-ad63-e79d0b962621",
                "matchArtifact": {
                  "artifactAccount": "embedded-artifact",
                  "customKind": true,
                  "metadata": {
                    "id": "86847605-b281-4766-9f64-d61ab608a058"
                  },
                  "name": "testvariables.tfVar",
                  "type": "embedded/base64"
                },
                "useDefaultArtifact": false,
                "usePriorArtifact": false
              }
            ],
            "resolvedExpectedArtifacts": [
              {
                "boundArtifact": {
                  "customKind": false,
                  "metadata": {},
                  "name": "testvariables.tfVar",
                  "reference": "bmFtZXNwYWNlPSJ0ZXJyYWZvcm10ZXN0dmFyIgpkZXBsb3lOYW1lPSJ0ZXJyYWZvcm1lcnRlc3R2YXIiCnJlcGxpY2FzPTI=",
                  "type": "embedded/base64"
                },
                "defaultArtifact": {
                  "customKind": true,
                  "metadata": {
                    "id": "04b721c1-8dde-4964-96a4-b5136f6d1408"
                  }
                },
                "id": "bca795c0-b2f6-4acb-ad63-e79d0b962621",
                "matchArtifact": {
                  "artifactAccount": "embedded-artifact",
                  "customKind": true,
                  "metadata": {
                    "id": "86847605-b281-4766-9f64-d61ab608a058"
                  },
                  "name": "testvariables.tfVar",
                  "type": "embedded/base64"
                },
                "useDefaultArtifact": false,
                "usePriorArtifact": false
              }
            ]
          },
          "endTime": 1620923522683,
          "id": "01F5K9476Y31CYQRDP9XN5BEHZ",
          "lastModified": null,
          "name": "Evaluate Artifacts",
          "outputs": {
            "artifacts": [
              {
                "customKind": false,
                "metadata": {},
                "name": "testvariables.tfVar",
                "reference": "bmFtZXNwYWNlPSJ0ZXJyYWZvcm10ZXN0dmFyIgpkZXBsb3lOYW1lPSJ0ZXJyYWZvcm1lcnRlc3R2YXIiCnJlcGxpY2FzPTI=",
                "type": "embedded/base64"
              }
            ],
            "resolvedExpectedArtifacts": [
              {
                "boundArtifact": {
                  "customKind": false,
                  "metadata": {},
                  "name": "testvariables.tfVar",
                  "reference": "bmFtZXNwYWNlPSJ0ZXJyYWZvcm10ZXN0dmFyIgpkZXBsb3lOYW1lPSJ0ZXJyYWZvcm1lcnRlc3R2YXIiCnJlcGxpY2FzPTI=",
                  "type": "embedded/base64"
                },
                "defaultArtifact": {
                  "customKind": true,
                  "metadata": {
                    "id": "04b721c1-8dde-4964-96a4-b5136f6d1408"
                  }
                },
                "id": "bca795c0-b2f6-4acb-ad63-e79d0b962621",
                "matchArtifact": {
                  "artifactAccount": "embedded-artifact",
                  "customKind": true,
                  "metadata": {
                    "id": "86847605-b281-4766-9f64-d61ab608a058"
                  },
                  "name": "testvariables.tfVar",
                  "type": "embedded/base64"
                },
                "useDefaultArtifact": false,
                "usePriorArtifact": false
              }
            ]
          },
          "parentStageId": null,
          "refId": "3",
          "requisiteStageRefIds": [],
          "scheduledTime": null,
          "startTime": 1620923522326,
          "startTimeExpiry": null,
          "status": "SUCCEEDED",
          "syntheticStageOwner": null,
          "tasks": [
            {
              "endTime": 1620923522515,
              "id": "1",
              "implementingClass": "io.armory.plugin.stage.artifacts.pipeline.task.EvaluateArtifactsTask",
              "loopEnd": false,
              "loopStart": false,
              "name": "evaluateArtifacts",
              "stageEnd": false,
              "stageStart": true,
              "startTime": 1620923522380,
              "status": "SUCCEEDED"
            },
            {
              "endTime": 1620923522667,
              "id": "2",
              "implementingClass": "com.netflix.spinnaker.orca.pipeline.tasks.artifacts.BindProducedArtifactsTask",
              "loopEnd": false,
              "loopStart": false,
              "name": "bindArtifacts",
              "stageEnd": true,
              "stageStart": false,
              "startTime": 1620923522528,
              "status": "SUCCEEDED"
            }
          ],
          "type": "evaluateArtifacts"
        },
        {
          "context": {
            "action": "apply",
            "artifacts": [
              {
                "id": "c16f9745-cf46-4b6a-9865-96c77a684348"
              },
              {
                "account": "",
                "id": "69159ef9-f197-44f0-9ece-731a7e299416"
              }
            ],
            "overrides": {},
            "terraformVersion": "0.14.2"
          },
          "endTime": null,
          "id": "01F5K9476Y6NR8W5RHGRMHCXYK",
          "lastModified": null,
          "name": "Terraform",
          "outputs": {},
          "parentStageId": null,
          "refId": "4",
          "requisiteStageRefIds": [
            "2"
          ],
          "scheduledTime": null,
          "startTime": null,
          "startTimeExpiry": null,
          "status": "NOT_STARTED",
          "syntheticStageOwner": null,
          "tasks": [],
          "type": "terraform"
        }
      ],
      "startTime": 1620923522314,
      "startTimeExpiry": null,
      "status": "RUNNING",
      "systemNotifications": [],
      "templateVariables": null,
      "trigger": {
        "artifacts": [
          {
            "artifactAccount": "myUserName",
            "customKind": false,
            "location": null,
            "metadata": {
              "id": "b7092f62-db55-4595-b36c-e69b75971116"
            },
            "name": "manifests/simpleTForm.tf",
            "provenance": null,
            "reference": "Https://api.github.com/repos/myUserName/hostname/contents/manifests/simpleTForm.tf",
            "type": "github/file",
            "uuid": null,
            "version": "master"
          }
        ],
        "correlationId": null,
        "isDryRun": false,
        "isRebake": false,
        "isStrategy": false,
        "notifications": [],
        "other": {
          "artifacts": [
            {
              "artifactAccount": "myUserName",
              "customKind": false,
              "metadata": {
                "id": "b7092f62-db55-4595-b36c-e69b75971116"
              },
              "name": "manifests/simpleTForm.tf",
              "reference": "Https://api.github.com/repos/myUserName/hostname/contents/manifests/simpleTForm.tf",
              "type": "github/file",
              "version": "master"
            }
          ],
          "dryRun": false,
          "enabled": false,
          "eventId": "458ef3d0-6a0d-40ff-bdb6-1ca65fa38dae",
          "executionId": "01F5K9474WJBWAJWWDEBV923WA",
          "expectedArtifacts": [
            {
              "boundArtifact": {
                "artifactAccount": "myUserName",
                "customKind": false,
                "metadata": {
                  "id": "b7092f62-db55-4595-b36c-e69b75971116"
                },
                "name": "manifests/simpleTForm.tf",
                "reference": "Https://api.github.com/repos/myUserName/hostname/contents/manifests/simpleTForm.tf",
                "type": "github/file",
                "version": "master"
              },
              "defaultArtifact": {
                "artifactAccount": "myUserName",
                "customKind": false,
                "metadata": {
                  "id": "b7092f62-db55-4595-b36c-e69b75971116"
                },
                "name": "manifests/simpleTForm.tf",
                "reference": "Https://api.github.com/repos/myUserName/hostname/contents/manifests/simpleTForm.tf",
                "type": "github/file",
                "version": "master"
              },
              "id": "c16f9745-cf46-4b6a-9865-96c77a684348",
              "matchArtifact": {
                "artifactAccount": "myUserName",
                "customKind": true,
                "metadata": {
                  "id": "3163e31c-f0bd-4708-8a64-ba947d37ed72"
                },
                "name": "manifests/simpleTForm.tf",
                "type": "github/file"
              },
              "useDefaultArtifact": true,
              "usePriorArtifact": false
            }
          ],
          "notifications": [],
          "parameters": {},
          "preferred": false,
          "rebake": false,
          "resolvedExpectedArtifacts": [
            {
              "boundArtifact": {
                "artifactAccount": "myUserName",
                "customKind": false,
                "metadata": {
                  "id": "b7092f62-db55-4595-b36c-e69b75971116"
                },
                "name": "manifests/simpleTForm.tf",
                "reference": "Https://api.github.com/repos/myUserName/hostname/contents/manifests/simpleTForm.tf",
                "type": "github/file",
                "version": "master"
              },
              "defaultArtifact": {
                "artifactAccount": "myUserName",
                "customKind": false,
                "metadata": {
                  "id": "b7092f62-db55-4595-b36c-e69b75971116"
                },
                "name": "manifests/simpleTForm.tf",
                "reference": "Https://api.github.com/repos/myUserName/hostname/contents/manifests/simpleTForm.tf",
                "type": "github/file",
                "version": "master"
              },
              "id": "c16f9745-cf46-4b6a-9865-96c77a684348",
              "matchArtifact": {
                "artifactAccount": "myUserName",
                "customKind": true,
                "metadata": {
                  "id": "3163e31c-f0bd-4708-8a64-ba947d37ed72"
                },
                "name": "manifests/simpleTForm.tf",
                "type": "github/file"
              },
              "useDefaultArtifact": true,
              "usePriorArtifact": false
            }
          ],
          "strategy": false,
          "type": "manual",
          "user": "myUserName"
        },
        "parameters": {},
        "resolvedExpectedArtifacts": [
          {
            "boundArtifact": {
              "artifactAccount": "myUserName",
              "customKind": false,
              "location": null,
              "metadata": {
                "id": "b7092f62-db55-4595-b36c-e69b75971116"
              },
              "name": "manifests/simpleTForm.tf",
              "provenance": null,
              "reference": "Https://api.github.com/repos/myUserName/hostname/contents/manifests/simpleTForm.tf",
              "type": "github/file",
              "uuid": null,
              "version": "master"
            },
            "defaultArtifact": {
              "artifactAccount": "myUserName",
              "customKind": false,
              "location": null,
              "metadata": {
                "id": "b7092f62-db55-4595-b36c-e69b75971116"
              },
              "name": "manifests/simpleTForm.tf",
              "provenance": null,
              "reference": "Https://api.github.com/repos/myUserName/hostname/contents/manifests/simpleTForm.tf",
              "type": "github/file",
              "uuid": null,
              "version": "master"
            },
            "id": "c16f9745-cf46-4b6a-9865-96c77a684348",
            "matchArtifact": {
              "artifactAccount": "myUserName",
              "customKind": true,
              "location": null,
              "metadata": {
                "id": "3163e31c-f0bd-4708-8a64-ba947d37ed72"
              },
              "name": "manifests/simpleTForm.tf",
              "provenance": null,
              "reference": null,
              "type": "github/file",
              "uuid": null,
              "version": null
            },
            "useDefaultArtifact": true,
            "usePriorArtifact": false
          }
        ],
        "type": "manual",
        "user": "myUserName"
      },
      "type": "PIPELINE"
    },
    "stage": {
      "context": {
        "action": "plan",
        "artifacts": [
          {
            "account": "",
            "id": "c16f9745-cf46-4b6a-9865-96c77a684348"
          },
          {
            "account": "",
            "id": "bca795c0-b2f6-4acb-ad63-e79d0b962621"
          }
        ],
        "expectedArtifacts": [
          {
            "defaultArtifact": {
              "customKind": true,
              "id": "265596f8-ded6-48c6-ae0d-fd66afa25d1a"
            },
            "displayName": "planfile",
            "id": "69159ef9-f197-44f0-9ece-731a7e299416",
            "matchArtifact": {
              "artifactAccount": "embedded-artifact",
              "id": "bde6a79d-8f25-4d80-b992-361259ed7499",
              "name": "planfile",
              "type": "embedded/base64"
            },
            "useDefaultArtifact": false,
            "usePriorArtifact": false
          }
        ],
        "overrides": {},
        "planForDestroy": false,
        "targets": [],
        "terraformVersion": "0.14.2"
      },
      "endTime": null,
      "id": "01F5K9476YYC6Y76VMBN61E1V8",
      "lastModified": null,
      "name": "Terraform",
      "outputs": {
        "artifacts": [],
        "status": {
          "code": 0,
          "error": "",
          "id": "e6ec9319-0c5c-4345-827a-94720acfe577",
          "outputs": {},
          "state": "WAITING"
        }
      },
      "parentStageId": null,
      "refId": "1",
      "requisiteStageRefIds": [
        "3"
      ],
      "scheduledTime": null,
      "startTime": 1620923522740,
      "startTimeExpiry": null,
      "status": "RUNNING",
      "syntheticStageOwner": null,
      "tasks": [
        {
          "endTime": 1620923523056,
          "id": "1",
          "implementingClass": "io.armory.spinnaker.orca.terraformer.tasks.RunTerraformTask",
          "loopEnd": false,
          "loopStart": false,
          "name": "runTerraform",
          "stageEnd": false,
          "stageStart": true,
          "startTime": 1620923522808,
          "status": "SUCCEEDED"
        },
        {
          "endTime": null,
          "id": "2",
          "implementingClass": "io.armory.spinnaker.orca.terraformer.tasks.MonitorRunTerraformTask",
          "loopEnd": false,
          "loopStart": false,
          "name": "monitorRunTerraform",
          "stageEnd": false,
          "stageStart": false,
          "startTime": 1620923523071,
          "status": "RUNNING"
        },
        {
          "endTime": null,
          "id": "3",
          "implementingClass": "com.netflix.spinnaker.orca.pipeline.tasks.artifacts.BindProducedArtifactsTask",
          "loopEnd": false,
          "loopStart": false,
          "name": "bindProducedArtifacts",
          "stageEnd": true,
          "stageStart": false,
          "startTime": null,
          "status": "NOT_STARTED"
        }
      ],
      "type": "terraform"
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

| Key                                               | Type      | Description                                                           |
| ------------------------------------------------- | --------- | --------------------------------------------------------------------- |
| `input.pipeline.application`                      | `string`  | The name of the Spinnaker application to which this pipeline belongs. |
| `input.pipeline.authentication.allowedAccounts[]` | `string`  |                                                                       |
| `input.pipeline.authentication.user`              | `string`  |                                                                       |
| `input.pipeline.buildTime`                        | `number`  |                                                                       |
| `input.pipeline.canceledBy`                       | ` `       |                                                                       |
| `input.pipeline.canceled`                         | `boolean` |                                                                       |
| `input.pipeline.cancellationReason`               | ` `       |                                                                       |
| `input.pipeline.description`                      | ` `       |                                                                       |
| `input.pipeline.endTime`                          | ` `       |                                                                       |
| `input.pipeline.id`                               | `string`  |                                                                       |
| `input.pipeline.keepWaitingPipelines`             | `boolean` |                                                                       |
| `input.pipeline.limitConcurrent`                  | `boolean` |                                                                       |
| `input.pipeline.name`                             | `string`  |                                                                       |
| `input.pipeline.origin`                           | `string`  |                                                                       |
| `input.pipeline.partition`                        | ` `       |                                                                       |
| `input.pipeline.paused`                           | ` `       |                                                                       |
| `input.pipeline.pipelineConfigId`                 | `string`  |                                                                       |
| `input.pipeline.source`                           | ` `       |                                                                       |
| `input.pipeline.spelEvaluator`                    | `string`  |                                                                       |
| `input.pipeline.startTimeExpiry`                  | ` `       |                                                                       |
| `input.pipeline.startTime`                        | `number`  |                                                                       |
| `input.pipeline.status`                           | `string`  |                                                                       |
| `input.pipeline.templateVariables`                | ` `       |                                                                       |
| `input.pipeline.type`                             | `string`  |                                                                       |

### input.pipeline.stages

| Key                                                           | Type      | Description                                                       |
| ------------------------------------------------------------- | --------- | ----------------------------------------------------------------- |
| `input.pipeline.stages[].context.action`                      | `string`  |                                                                   |
| `input.pipeline.stages[].context.artifactContents[].contents` | `string`  |                                                                   |
| `input.pipeline.stages[].context.artifactContents[].name`     | `string`  |                                                                   |
| `input.pipeline.stages[].context.artifacts[]`                 | `[array]` | See [artifacts]({{< ref "artifacts.md" >}}) for more information. |
| `input.pipeline.stages[].context.expectedArtifacts[]`         | `[array]` | See [artifacts]({{< ref "artifacts.md" >}}) for more information. |
| `input.pipeline.stages[].context.failPipeline`                | `boolean` |                                                                   |
| `input.pipeline.stages[].context.judgmentStatus`              | `string`  |                                                                   |
| `input.pipeline.stages[].context.lastModifiedBy`              | `string`  |                                                                   |
| `input.pipeline.stages[].context.planForDestroy`              | `boolean` |                                                                   |
| `input.pipeline.stages[].context.resolvedExpectedArtifacts[]` | `[array]` | See [artifacts]({{< ref "artifacts.md" >}}) for more information. |
| `input.pipeline.stages[].context.terraformVersion`            | `string`  |                                                                   |
| `input.pipeline.stages[].endTime`                             | ` `       |                                                                   |
| `input.pipeline.stages[].endTime`                             | `number`  |                                                                   |
| `input.pipeline.stages[].id`                                  | `string`  |                                                                   |
| `input.pipeline.stages[].lastModified.allowedAccounts[]`      | `string`  |                                                                   |
| `input.pipeline.stages[].lastModified.lastModifiedTime`       | `number`  |                                                                   |
| `input.pipeline.stages[].lastModified.user`                   | `string`  |                                                                   |
| `input.pipeline.stages[].lastModified`                        | ` `       |                                                                   |
| `input.pipeline.stages[].name`                                | `string`  |                                                                   |
| `input.pipeline.stages[].outputs.artifacts[]`                 | `[array]` | See [artifacts]({{< ref "artifacts.md" >}}) for more information. |
| `input.pipeline.stages[].outputs.resolvedExpectedArtifacts[]` | `[array]` | See [artifacts]({{< ref "artifacts.md" >}}) for more information. |
| `input.pipeline.stages[].outputs.status.code`                 | `number`  |                                                                   |
| `input.pipeline.stages[].outputs.status.error`                | `string`  |                                                                   |
| `input.pipeline.stages[].outputs.status.id`                   | `string`  |                                                                   |
| `input.pipeline.stages[].outputs.status.logs.combined`        | `string`  |                                                                   |
| `input.pipeline.stages[].outputs.status.logs.init_stderr`     | `string`  |                                                                   |
| `input.pipeline.stages[].outputs.status.logs.init_stdout`     | `string`  |                                                                   |
| `input.pipeline.stages[].outputs.status.logs.plan_stderr`     | `string`  |                                                                   |
| `input.pipeline.stages[].outputs.status.logs.plan_stdout`     | `string`  |                                                                   |
| `input.pipeline.stages[].outputs.status.outputs.artifacts[]`  | `[array]` | See [artifacts]({{< ref "artifacts.md" >}}) for more information. |
| `input.pipeline.stages[].outputs.status.state`                | `string`  |                                                                   |
| `input.pipeline.stages[].parentStageId`                       | ` `       |                                                                   |
| `input.pipeline.stages[].refId`                               | `string`  |                                                                   |
| `input.pipeline.stages[].requisiteStageRefIds[]`              | `string`  |                                                                   |
| `input.pipeline.stages[].scheduledTime`                       | ` `       |                                                                   |
| `input.pipeline.stages[].startTimeExpiry`                     | ` `       |                                                                   |
| `input.pipeline.stages[].startTime`                           | ` `       |                                                                   |
| `input.pipeline.stages[].startTime`                           | `number`  |                                                                   |
| `input.pipeline.stages[].status`                              | `string`  |                                                                   |
| `input.pipeline.stages[].syntheticStageOwner`                 | ` `       |                                                                   |
| `input.pipeline.stages[].tasks[].endTime`                     | `number`  |                                                                   |
| `input.pipeline.stages[].tasks[].id`                          | `string`  |                                                                   |
| `input.pipeline.stages[].tasks[].implementingClass`           | `string`  |                                                                   |
| `input.pipeline.stages[].tasks[].loopEnd`                     | `boolean` |                                                                   |
| `input.pipeline.stages[].tasks[].loopStart`                   | `boolean` |                                                                   |
| `input.pipeline.stages[].tasks[].name`                        | `string`  |                                                                   |
| `input.pipeline.stages[].tasks[].stageEnd`                    | `boolean` |                                                                   |
| `input.pipeline.stages[].tasks[].stageStart`                  | `boolean` |                                                                   |
| `input.pipeline.stages[].tasks[].startTime`                   | `number`  |                                                                   |
| `input.pipeline.stages[].tasks[].status`                      | `string`  |                                                                   |
| `input.pipeline.stages[].type`                                | `string`  |                                                                   |
| `input.pipeline.stages[]`                                     | `string`  |                                                                   |

### input.pipeline.trigger

See [input.pipeline.trigger]({{< ref "input.pipeline.trigger.md" >}}) for more information.

### input.stage

| Key                                              | Type      | Description                                                       |
| ------------------------------------------------ | --------- | ----------------------------------------------------------------- |
| `input.stage.context.action`                     | `string`  |                                                                   |
| `input.stage.context.artifacts[].account`        | `string`  |                                                                   |
| `input.stage.context.artifacts[].id`             | `string`  |                                                                   |
| `input.stage.context.expectedArtifacts[]`        | `array`   | See [artifacts]({{< ref "artifacts.md" >}}) for more information. |
| `input.stage.context.planForDestroy`             | `boolean` |                                                                   |
| `input.stage.context.terraformVersion`           | `string`  |                                                                   |
| `input.stage.endTime`                            | ` `       |                                                                   |
| `input.stage.id`                                 | `string`  |                                                                   |
| `input.stage.lastModified`                       | ` `       |                                                                   |
| `input.stage.name`                               | `string`  |                                                                   |
| `input.stage.outputs.artifacts[]`                | `array`   | See [artifacts]({{< ref "artifacts.md" >}}) for more information. |
| `input.stage.outputs.status.code`                | `number`  |                                                                   |
| `input.stage.outputs.status.error`               | `string`  |                                                                   |
| `input.stage.outputs.status.id`                  | `string`  |                                                                   |
| `input.stage.outputs.status.logs.apply_stderr`   | `string`  |                                                                   |
| `input.stage.outputs.status.logs.apply_stdout`   | `string`  |                                                                   |
| `input.stage.outputs.status.logs.combined`       | `string`  |                                                                   |
| `input.stage.outputs.status.logs.init_stderr`    | `string`  |                                                                   |
| `input.stage.outputs.status.logs.init_stdout`    | `string`  |                                                                   |
| `input.stage.outputs.status.logs.plan_stderr`    | `string`  |                                                                   |
| `input.stage.outputs.status.logs.plan_stdout`    | `string`  |                                                                   |
| `input.stage.outputs.status.outputs.artifacts[]` | `array`   | See [artifacts]({{< ref "artifacts.md" >}}) for more information. |
| `input.stage.outputs.status.state`               | `string`  |                                                                   |
| `input.stage.parentStageId`                      | ` `       |                                                                   |
| `input.stage.refId`                              | `string`  |                                                                   |
| `input.stage.requisiteStageRefIds[]`             | `string`  |                                                                   |
| `input.stage.scheduledTime`                      | ` `       |                                                                   |
| `input.stage.startTimeExpiry`                    | ` `       |                                                                   |
| `input.stage.startTime`                          | `number`  |                                                                   |
| `input.stage.status`                             | `string`  |                                                                   |
| `input.stage.syntheticStageOwner`                | ` `       |                                                                   |
| `input.stage.tasks[].endTime`                    | ` `       |                                                                   |
| `input.stage.tasks[].endTime`                    | `number`  |                                                                   |
| `input.stage.tasks[].id`                         | `string`  |                                                                   |
| `input.stage.tasks[].implementingClass`          | `string`  |                                                                   |
| `input.stage.tasks[].loopEnd`                    | `boolean` |                                                                   |
| `input.stage.tasks[].loopStart`                  | `boolean` |                                                                   |
| `input.stage.tasks[].name`                       | `string`  |                                                                   |
| `input.stage.tasks[].stageEnd`                   | `boolean` |                                                                   |
| `input.stage.tasks[].stageStart`                 | `boolean` |                                                                   |
| `input.stage.tasks[].startTime`                  | ` `       |                                                                   |
| `input.stage.tasks[].startTime`                  | `number`  |                                                                   |
| `input.stage.tasks[].status`                     | `string`  |                                                                   |
| `input.stage.type`                               | `string`  |                                                                   |

### input.user

This object provides information about the user performing the action. This can be used to restrict actions by role. See [input.user]({{< ref "input.user.md" >}}) for more information.