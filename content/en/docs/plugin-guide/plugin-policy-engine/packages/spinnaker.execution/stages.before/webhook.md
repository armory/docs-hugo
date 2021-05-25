---
title: "spinnaker.execution.stages.before.webhook"
linktitle: "webhook"
description: "fill me with delicious data, Stephen!"
---

## Example Payload

<details><summary>Click to expand</summary>

```json
{
  "input": {
    "pipeline": {
      "application": "test",
      "authentication": {
        "allowedAccounts": [
          "spinnaker",
          "staging",
          "staging-ecs"
        ],
        "user": "myUserName"
      },
      "buildTime": 1620926703486,
      "canceled": false,
      "canceledBy": null,
      "cancellationReason": null,
      "description": null,
      "endTime": 1620926705283,
      "id": "01F5KC59TRGWKCP31C4N51CDSB",
      "initialConfig": {},
      "keepWaitingPipelines": false,
      "limitConcurrent": true,
      "name": "test",
      "notifications": [],
      "origin": "api",
      "partition": null,
      "paused": null,
      "pipelineConfigId": "6a4cff2e-8265-4584-8993-2da2eb6254f5",
      "source": null,
      "spelEvaluator": "v4",
      "stages": [
        {
          "context": {
            "expectedArtifacts": [
              {
                "defaultArtifact": {
                  "customKind": true,
                  "id": "f9275bbf-fef7-4339-88f4-b2a18ec7b0ab"
                },
                "displayName": "pink-dog-80",
                "id": "eb9e5a6c-e9d1-489b-9f3b-4d414ba33b73",
                "matchArtifact": {
                  "artifactAccount": "embedded-artifact",
                  "customKind": false,
                  "id": "301e50f0-2bc6-4d3e-894b-31dbf0b67bf0",
                  "name": "test",
                  "type": "embedded/base64"
                },
                "useDefaultArtifact": false,
                "usePriorArtifact": false
              }
            ],
            "inputArtifacts": [
              {
                "account": "",
                "id": "05ad020e-73a6-49f2-9988-2073831219e9"
              }
            ],
            "namespace": "testns",
            "outputName": "test",
            "overrides": {},
            "templateRenderer": "HELM2"
          },
          "endTime": null,
          "id": "01F5KC59VXSVC287E96M310EF5",
          "lastModified": null,
          "name": "Bake (Manifest)",
          "outputs": {},
          "parentStageId": null,
          "refId": "10",
          "requisiteStageRefIds": [],
          "scheduledTime": null,
          "startTime": 1620926703574,
          "startTimeExpiry": null,
          "status": "RUNNING",
          "syntheticStageOwner": null,
          "tasks": [
            {
              "endTime": null,
              "id": "1",
              "implementingClass": "com.netflix.spinnaker.orca.bakery.tasks.manifests.CreateBakeManifestTask",
              "loopEnd": false,
              "loopStart": false,
              "name": "createBake",
              "stageEnd": false,
              "stageStart": true,
              "startTime": 1620926703700,
              "status": "RUNNING"
            },
            {
              "endTime": null,
              "id": "2",
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
          "type": "bakeManifest"
        },
        {
          "context": {
            "analysisType": "realTimeAutomatic",
            "beforeStagePlanningFailed": true,
            "canaryConfig": {
              "metricsAccountName": "prometheus",
              "scopes": [
                {
                  "extendedScopeParams": {},
                  "scopeName": "default"
                }
              ],
              "scoreThresholds": {},
              "storageAccountName": "s3"
            },
            "exception": {
              "details": {
                "error": "Unexpected Task Failure",
                "errors": [
                  "Canary stage configuration must include either `endTime` or `lifetimeDuration`."
                ],
                "stackTrace": "java.lang.IllegalArgumentException: Canary stage configuration must include either `endTime` or `lifetimeDuration`.\n\tat com.netflix.spinnaker.orca.kayenta.pipeline.KayentaCanaryStage.beforeStages(KayentaCanaryStage.kt:56)\n\tat com.netflix.spinnaker.orca.q.StageDefinitionBuildersKt.buildBeforeStages(StageDefinitionBuilders.kt:103)\n\tat com.netflix.spinnaker.orca.q.handler.StartStageHandler.plan(StartStageHandler.kt:174)\n\tat com.netflix.spinnaker.orca.q.handler.StartStageHandler.access$plan(StartStageHandler.kt:61)\n\tat com.netflix.spinnaker.orca.q.handler.StartStageHandler$handle$1$1.invoke(StartStageHandler.kt:99)\n\tat com.netflix.spinnaker.orca.q.handler.StartStageHandler$handle$1$1.invoke(StartStageHandler.kt:61)\n\tat com.netflix.spinnaker.orca.q.handler.AuthenticationAware$sam$java_util_concurrent_Callable$0.call(AuthenticationAware.kt)\n\tat com.netflix.spinnaker.security.AuthenticatedRequest.lambda$wrapCallableForPrincipal$0(AuthenticatedRequest.java:272)\n\tat com.netflix.spinnaker.orca.q.handler.AuthenticationAware$DefaultImpls.withAuth(AuthenticationAware.kt:51)\n\tat com.netflix.spinnaker.orca.q.handler.StartStageHandler.withAuth(StartStageHandler.kt:61)\n\tat com.netflix.spinnaker.orca.q.handler.StartStageHandler$handle$1.invoke(StartStageHandler.kt:81)\n\tat com.netflix.spinnaker.orca.q.handler.StartStageHandler$handle$1.invoke(StartStageHandler.kt:61)\n\tat com.netflix.spinnaker.orca.q.handler.OrcaMessageHandler$withStage$1.invoke(OrcaMessageHandler.kt:85)\n\tat com.netflix.spinnaker.orca.q.handler.OrcaMessageHandler$withStage$1.invoke(OrcaMessageHandler.kt:46)\n\tat com.netflix.spinnaker.orca.q.handler.OrcaMessageHandler$DefaultImpls.withExecution(OrcaMessageHandler.kt:95)\n\tat com.netflix.spinnaker.orca.q.handler.StartStageHandler.withExecution(StartStageHandler.kt:61)\n\tat com.netflix.spinnaker.orca.q.handler.OrcaMessageHandler$DefaultImpls.withStage(OrcaMessageHandler.kt:74)\n\tat com.netflix.spinnaker.orca.q.handler.StartStageHandler.withStage(StartStageHandler.kt:61)\n\tat com.netflix.spinnaker.orca.q.handler.StartStageHandler.handle(StartStageHandler.kt:79)\n\tat com.netflix.spinnaker.orca.q.handler.StartStageHandler.handle(StartStageHandler.kt:61)\n\tat com.netflix.spinnaker.q.MessageHandler$DefaultImpls.invoke(MessageHandler.kt:36)\n\tat com.netflix.spinnaker.orca.q.handler.OrcaMessageHandler$DefaultImpls.invoke(OrcaMessageHandler.kt)\n\tat com.netflix.spinnaker.orca.q.handler.StartStageHandler.invoke(StartStageHandler.kt:61)\n\tat com.netflix.spinnaker.orca.q.audit.ExecutionTrackingMessageHandlerPostProcessor$ExecutionTrackingMessageHandlerProxy.invoke(ExecutionTrackingMessageHandlerPostProcessor.kt:72)\n\tat com.netflix.spinnaker.q.QueueProcessor$callback$1$1.run(QueueProcessor.kt:90)\n\tat java.base/java.util.concurrent.ThreadPoolExecutor.runWorker(ThreadPoolExecutor.java:1128)\n\tat java.base/java.util.concurrent.ThreadPoolExecutor$Worker.run(ThreadPoolExecutor.java:628)\n\tat java.base/java.lang.Thread.run(Thread.java:834)\n"
              },
              "exceptionType": "IllegalArgumentException",
              "operation": "Canary Analysis",
              "shouldRetry": false,
              "timestamp": 1620926704026
            }
          },
          "endTime": 1620926704342,
          "id": "01F5KC59VXZA70H3SN0GQWE1DT",
          "lastModified": null,
          "name": "Canary Analysis",
          "outputs": {},
          "parentStageId": null,
          "refId": "11",
          "requisiteStageRefIds": [],
          "scheduledTime": null,
          "startTime": 1620926703576,
          "startTimeExpiry": null,
          "status": "TERMINAL",
          "syntheticStageOwner": null,
          "tasks": [
            {
              "endTime": null,
              "id": "1",
              "implementingClass": "com.netflix.spinnaker.orca.kayenta.tasks.AggregateCanaryResultsTask",
              "loopEnd": false,
              "loopStart": false,
              "name": "aggregateCanaryResults",
              "stageEnd": true,
              "stageStart": true,
              "startTime": null,
              "status": "NOT_STARTED"
            }
          ],
          "type": "kayentaCanary"
        },
        {
          "context": {
            "application": "test",
            "attempt": 2,
            "cloudProvider": "aws",
            "cloudProviderType": "aws",
            "consecutiveNotFound": 0,
            "copySourceCustomBlockDeviceMappings": false,
            "credentials": "staging",
            "freeFormDetails": "",
            "lastException": "Unable to locate current_asg_dynamic in staging/us-east-2/test\ncom.netflix.spinnaker.orca.clouddriver.pipeline.servergroup.support.TargetServerGroup$NotFoundException: Unable to locate current_asg_dynamic in staging/us-east-2/test\n\tat java.base/jdk.internal.reflect.NativeConstructorAccessorImpl.newInstance0(Native Method)\n\tat java.base/jdk.internal.reflect.NativeConstructorAccessorImpl.newInstance(NativeConstructorAccessorImpl.java:62)\n\tat java.base/jdk.internal.reflect.DelegatingConstructorAccessorImpl.newInstance(DelegatingConstructorAccessorImpl.java:45)\n\tat java.base/java.lang.reflect.Constructor.newInstance(Constructor.java:490)\n\tat org.codehaus.groovy.reflection.CachedConstructor.invoke(CachedConstructor.java:80)\n\tat org.codehaus.groovy.reflection.CachedConstructor.doConstructorInvoke(CachedConstructor.java:74)\n\tat org.codehaus.groovy.runtime.callsite.ConstructorSite$ConstructorSiteNoUnwrap.callConstructor(ConstructorSite.java:84)\n\tat org.codehaus.groovy.runtime.callsite.CallSiteArray.defaultCallConstructor(CallSiteArray.java:59)\n\tat org.codehaus.groovy.runtime.callsite.AbstractCallSite.callConstructor(AbstractCallSite.java:237)\n\tat org.codehaus.groovy.runtime.callsite.AbstractCallSite.callConstructor(AbstractCallSite.java:249)\n\tat com.netflix.spinnaker.orca.clouddriver.pipeline.servergroup.support.TargetServerGroupResolver.resolveByTarget(TargetServerGroupResolver.groovy:75)\n\tat java.base/jdk.internal.reflect.NativeMethodAccessorImpl.invoke0(Native Method)\n\tat java.base/jdk.internal.reflect.NativeMethodAccessorImpl.invoke(NativeMethodAccessorImpl.java:62)\n\tat java.base/jdk.internal.reflect.DelegatingMethodAccessorImpl.invoke(DelegatingMethodAccessorImpl.java:43)\n\tat java.base/java.lang.reflect.Method.invoke(Method.java:566)\n\tat org.codehaus.groovy.reflection.CachedMethod.invoke(CachedMethod.java:101)\n\tat groovy.lang.MetaMethod.doMethodInvoke(MetaMethod.java:323)\n\tat org.codehaus.groovy.runtime.metaclass.ClosureMetaClass.invokeMethod(ClosureMetaClass.java:351)\n\tat org.codehaus.groovy.runtime.callsite.PogoMetaClassSite.callCurrent(PogoMetaClassSite.java:64)\n\tat org.codehaus.groovy.runtime.callsite.CallSiteArray.defaultCallCurrent(CallSiteArray.java:51)\n\tat org.codehaus.groovy.runtime.callsite.AbstractCallSite.callCurrent(AbstractCallSite.java:156)\n\tat org.codehaus.groovy.runtime.callsite.AbstractCallSite.callCurrent(AbstractCallSite.java:176)\n\tat com.netflix.spinnaker.orca.clouddriver.pipeline.servergroup.support.TargetServerGroupResolver$_resolveByParams_closure1.doCall(TargetServerGroupResolver.groovy:56)\n\tat java.base/jdk.internal.reflect.NativeMethodAccessorImpl.invoke0(Native Method)\n\tat java.base/jdk.internal.reflect.NativeMethodAccessorImpl.invoke(NativeMethodAccessorImpl.java:62)\n\tat java.base/jdk.internal.reflect.DelegatingMethodAccessorImpl.invoke(DelegatingMethodAccessorImpl.java:43)\n\tat java.base/java.lang.reflect.Method.invoke(Method.java:566)\n\tat org.codehaus.groovy.reflection.CachedMethod.invoke(CachedMethod.java:101)\n\tat groovy.lang.MetaMethod.doMethodInvoke(MetaMethod.java:323)\n\tat org.codehaus.groovy.runtime.metaclass.ClosureMetaClass.invokeMethod(ClosureMetaClass.java:263)\n\tat groovy.lang.MetaClassImpl.invokeMethod(MetaClassImpl.java:1041)\n\tat groovy.lang.Closure.call(Closure.java:405)\n\tat groovy.lang.Closure.call(Closure.java:421)\n\tat org.codehaus.groovy.runtime.DefaultGroovyMethods.collect(DefaultGroovyMethods.java:3574)\n\tat org.codehaus.groovy.runtime.DefaultGroovyMethods.collect(DefaultGroovyMethods.java:3559)\n\tat org.codehaus.groovy.runtime.DefaultGroovyMethods.collect(DefaultGroovyMethods.java:3659)\n\tat org.codehaus.groovy.runtime.dgm$87.invoke(Unknown Source)\n\tat org.codehaus.groovy.runtime.callsite.PojoMetaMethodSite$PojoMetaMethodSiteNoUnwrapNoCoerce.invoke(PojoMetaMethodSite.java:244)\n\tat org.codehaus.groovy.runtime.callsite.PojoMetaMethodSite.call(PojoMetaMethodSite.java:53)\n\tat org.codehaus.groovy.runtime.callsite.CallSiteArray.defaultCall(CallSiteArray.java:47)\n\tat org.codehaus.groovy.runtime.callsite.AbstractCallSite.call(AbstractCallSite.java:115)\n\tat org.codehaus.groovy.runtime.callsite.AbstractCallSite.call(AbstractCallSite.java:127)\n\tat com.netflix.spinnaker.orca.clouddriver.pipeline.servergroup.support.TargetServerGroupResolver.resolveByParams(TargetServerGroupResolver.groovy:54)\n\tat com.netflix.spinnaker.orca.kato.pipeline.support.SourceResolver.getSource(SourceResolver.groovy:79)\n\tat com.netflix.spinnaker.orca.kato.pipeline.support.SourceResolver$getSource.call(Unknown Source)\n\tat org.codehaus.groovy.runtime.callsite.CallSiteArray.defaultCall(CallSiteArray.java:47)\n\tat org.codehaus.groovy.runtime.callsite.AbstractCallSite.call(AbstractCallSite.java:115)\n\tat org.codehaus.groovy.runtime.callsite.AbstractCallSite.call(AbstractCallSite.java:127)\n\tat com.netflix.spinnaker.orca.kato.pipeline.strategy.DetermineSourceServerGroupTask.execute(DetermineSourceServerGroupTask.groovy:59)\n\tat com.netflix.spinnaker.orca.q.handler.RunTaskHandler$handle$1$1$1.invoke(RunTaskHandler.kt:144)\n\tat com.netflix.spinnaker.orca.q.handler.RunTaskHandler$handle$1$1$1.invoke(RunTaskHandler.kt:75)\n\tat com.netflix.spinnaker.orca.q.handler.RunTaskHandler.withLoggingContext(RunTaskHandler.kt:419)\n\tat com.netflix.spinnaker.orca.q.handler.RunTaskHandler.access$withLoggingContext(RunTaskHandler.kt:75)\n\tat com.netflix.spinnaker.orca.q.handler.RunTaskHandler$handle$1$1.invoke(RunTaskHandler.kt:105)\n\tat com.netflix.spinnaker.orca.q.handler.RunTaskHandler$handle$1$1.invoke(RunTaskHandler.kt:75)\n\tat com.netflix.spinnaker.orca.q.handler.AuthenticationAware$sam$java_util_concurrent_Callable$0.call(AuthenticationAware.kt)\n\tat com.netflix.spinnaker.security.AuthenticatedRequest.lambda$wrapCallableForPrincipal$0(AuthenticatedRequest.java:272)\n\tat com.netflix.spinnaker.orca.q.handler.AuthenticationAware$DefaultImpls.withAuth(AuthenticationAware.kt:51)\n\tat com.netflix.spinnaker.orca.q.handler.RunTaskHandler.withAuth(RunTaskHandler.kt:75)\n\tat com.netflix.spinnaker.orca.q.handler.RunTaskHandler$handle$1.invoke(RunTaskHandler.kt:104)\n\tat com.netflix.spinnaker.orca.q.handler.RunTaskHandler$handle$1.invoke(RunTaskHandler.kt:75)\n\tat com.netflix.spinnaker.orca.q.handler.RunTaskHandler$withTask$1.invoke(RunTaskHandler.kt:247)\n\tat com.netflix.spinnaker.orca.q.handler.RunTaskHandler$withTask$1.invoke(RunTaskHandler.kt:75)\n\tat com.netflix.spinnaker.orca.q.handler.OrcaMessageHandler$withTask$1.invoke(OrcaMessageHandler.kt:68)\n\tat com.netflix.spinnaker.orca.q.handler.OrcaMessageHandler$withTask$1.invoke(OrcaMessageHandler.kt:46)\n\tat com.netflix.spinnaker.orca.q.handler.OrcaMessageHandler$withStage$1.invoke(OrcaMessageHandler.kt:85)\n\tat com.netflix.spinnaker.orca.q.handler.OrcaMessageHandler$withStage$1.invoke(OrcaMessageHandler.kt:46)\n\tat com.netflix.spinnaker.orca.q.handler.OrcaMessageHandler$DefaultImpls.withExecution(OrcaMessageHandler.kt:95)\n\tat com.netflix.spinnaker.orca.q.handler.RunTaskHandler.withExecution(RunTaskHandler.kt:75)\n\tat com.netflix.spinnaker.orca.q.handler.OrcaMessageHandler$DefaultImpls.withStage(OrcaMessageHandler.kt:74)\n\tat com.netflix.spinnaker.orca.q.handler.RunTaskHandler.withStage(RunTaskHandler.kt:75)\n\tat com.netflix.spinnaker.orca.q.handler.OrcaMessageHandler$DefaultImpls.withTask(OrcaMessageHandler.kt:60)\n\tat com.netflix.spinnaker.orca.q.handler.RunTaskHandler.withTask(RunTaskHandler.kt:75)\n\tat com.netflix.spinnaker.orca.q.handler.RunTaskHandler.withTask(RunTaskHandler.kt:236)\n\tat com.netflix.spinnaker.orca.q.handler.RunTaskHandler.handle(RunTaskHandler.kt:101)\n\tat com.netflix.spinnaker.orca.q.handler.RunTaskHandler.handle(RunTaskHandler.kt:75)\n\tat com.netflix.spinnaker.q.MessageHandler$DefaultImpls.invoke(MessageHandler.kt:36)\n\tat com.netflix.spinnaker.orca.q.handler.OrcaMessageHandler$DefaultImpls.invoke(OrcaMessageHandler.kt)\n\tat com.netflix.spinnaker.orca.q.handler.RunTaskHandler.invoke(RunTaskHandler.kt:75)\n\tat com.netflix.spinnaker.orca.q.audit.ExecutionTrackingMessageHandlerPostProcessor$ExecutionTrackingMessageHandlerProxy.invoke(ExecutionTrackingMessageHandlerPostProcessor.kt:72)\n\tat com.netflix.spinnaker.q.QueueProcessor$callback$1$1.run(QueueProcessor.kt:90)\n\tat java.base/java.util.concurrent.ThreadPoolExecutor.runWorker(ThreadPoolExecutor.java:1128)\n\tat java.base/java.util.concurrent.ThreadPoolExecutor$Worker.run(ThreadPoolExecutor.java:628)\n\tat java.base/java.lang.Thread.run(Thread.java:834)\n",
            "region": "us-east-2",
            "stack": "",
            "target": "current_asg_dynamic",
            "targetCluster": "test",
            "useAmiBlockDeviceMappings": false,
            "useSourceCapacity": true
          },
          "endTime": null,
          "id": "01F5KC59VXW75H7Q7Z2C87CXET",
          "lastModified": null,
          "name": "Clone Server Group",
          "outputs": {},
          "parentStageId": null,
          "refId": "12",
          "requisiteStageRefIds": [],
          "scheduledTime": null,
          "startTime": 1620926703580,
          "startTimeExpiry": null,
          "status": "RUNNING",
          "syntheticStageOwner": null,
          "tasks": [
            {
              "endTime": null,
              "id": "1",
              "implementingClass": "com.netflix.spinnaker.orca.kato.pipeline.strategy.DetermineSourceServerGroupTask",
              "loopEnd": false,
              "loopStart": false,
              "name": "determineSourceServerGroup",
              "stageEnd": false,
              "stageStart": true,
              "startTime": 1620926703830,
              "status": "RUNNING"
            },
            {
              "endTime": null,
              "id": "2",
              "implementingClass": "com.netflix.spinnaker.orca.clouddriver.tasks.DetermineHealthProvidersTask",
              "loopEnd": false,
              "loopStart": false,
              "name": "determineHealthProviders",
              "stageEnd": false,
              "stageStart": false,
              "startTime": null,
              "status": "NOT_STARTED"
            },
            {
              "endTime": null,
              "id": "3",
              "implementingClass": "com.netflix.spinnaker.orca.clouddriver.pipeline.providers.aws.CaptureSourceServerGroupCapacityTask",
              "loopEnd": false,
              "loopStart": false,
              "name": "snapshotSourceServerGroup",
              "stageEnd": false,
              "stageStart": false,
              "startTime": null,
              "status": "NOT_STARTED"
            },
            {
              "endTime": null,
              "id": "4",
              "implementingClass": "com.netflix.spinnaker.orca.clouddriver.tasks.servergroup.CloneServerGroupTask",
              "loopEnd": false,
              "loopStart": false,
              "name": "cloneServerGroup",
              "stageEnd": false,
              "stageStart": false,
              "startTime": null,
              "status": "NOT_STARTED"
            },
            {
              "endTime": null,
              "id": "5",
              "implementingClass": "com.netflix.spinnaker.orca.clouddriver.tasks.MonitorKatoTask",
              "loopEnd": false,
              "loopStart": false,
              "name": "monitorDeploy",
              "stageEnd": false,
              "stageStart": false,
              "startTime": null,
              "status": "NOT_STARTED"
            },
            {
              "endTime": null,
              "id": "6",
              "implementingClass": "com.netflix.spinnaker.orca.clouddriver.tasks.servergroup.ServerGroupCacheForceRefreshTask",
              "loopEnd": false,
              "loopStart": false,
              "name": "forceCacheRefresh",
              "stageEnd": false,
              "stageStart": false,
              "startTime": null,
              "status": "NOT_STARTED"
            },
            {
              "endTime": null,
              "id": "7",
              "implementingClass": "com.netflix.spinnaker.orca.clouddriver.tasks.instance.WaitForUpInstancesTask",
              "loopEnd": false,
              "loopStart": false,
              "name": "waitForUpInstances",
              "stageEnd": false,
              "stageStart": false,
              "startTime": null,
              "status": "NOT_STARTED"
            },
            {
              "endTime": null,
              "id": "8",
              "implementingClass": "com.netflix.spinnaker.orca.clouddriver.tasks.servergroup.ServerGroupCacheForceRefreshTask",
              "loopEnd": false,
              "loopStart": false,
              "name": "forceCacheRefresh",
              "stageEnd": false,
              "stageStart": false,
              "startTime": null,
              "status": "NOT_STARTED"
            },
            {
              "endTime": null,
              "id": "9",
              "implementingClass": "com.netflix.spinnaker.orca.igor.tasks.GetCommitsTask",
              "loopEnd": false,
              "loopStart": false,
              "name": "getCommits",
              "stageEnd": true,
              "stageStart": false,
              "startTime": null,
              "status": "NOT_STARTED"
            }
          ],
          "type": "cloneServerGroup"
        },
        {
          "context": {
            "failOnFailedExpressions": true
          },
          "endTime": null,
          "id": "01F5KC59VX419V14RWY4JCWEHK",
          "lastModified": null,
          "name": "Concourse",
          "outputs": {},
          "parentStageId": null,
          "refId": "13",
          "requisiteStageRefIds": [],
          "scheduledTime": null,
          "startTime": 1620926703586,
          "startTimeExpiry": null,
          "status": "RUNNING",
          "syntheticStageOwner": null,
          "tasks": [
            {
              "endTime": null,
              "id": "1",
              "implementingClass": "com.netflix.spinnaker.orca.igor.tasks.WaitForConcourseJobStartTask",
              "loopEnd": false,
              "loopStart": false,
              "name": "waitForConcourseJobStartTask",
              "stageEnd": false,
              "stageStart": true,
              "startTime": 1620926703684,
              "status": "RUNNING"
            },
            {
              "endTime": null,
              "id": "2",
              "implementingClass": "com.netflix.spinnaker.orca.igor.tasks.WaitForConcourseJobCompletionTask",
              "loopEnd": false,
              "loopStart": false,
              "name": "waitForConcourseJobCompletionTask",
              "stageEnd": true,
              "stageStart": false,
              "startTime": null,
              "status": "NOT_STARTED"
            }
          ],
          "type": "concourse"
        },
        {
          "context": {
            "kato.last.task.id": {
              "id": "f377bbb1-d404-4ff7-8444-b25e5b3ccf10"
            },
            "kato.result.expected": true,
            "loadBalancers": [],
            "notification.type": "upsertloadbalancer",
            "targets": []
          },
          "endTime": null,
          "id": "01F5KC59VX3VNVYJ5PTGDJQ4PK",
          "lastModified": null,
          "name": "Create Load Balancers",
          "outputs": {},
          "parentStageId": null,
          "refId": "14",
          "requisiteStageRefIds": [],
          "scheduledTime": null,
          "startTime": 1620926703592,
          "startTimeExpiry": null,
          "status": "RUNNING",
          "syntheticStageOwner": null,
          "tasks": [
            {
              "endTime": 1620926704382,
              "id": "1",
              "implementingClass": "com.netflix.spinnaker.orca.clouddriver.tasks.loadbalancer.UpsertLoadBalancersTask",
              "loopEnd": false,
              "loopStart": false,
              "name": "upsertLoadBalancers",
              "stageEnd": false,
              "stageStart": true,
              "startTime": 1620926703674,
              "status": "SUCCEEDED"
            },
            {
              "endTime": null,
              "id": "2",
              "implementingClass": "com.netflix.spinnaker.orca.clouddriver.tasks.MonitorKatoTask",
              "loopEnd": false,
              "loopStart": false,
              "name": "monitorUpsert",
              "stageEnd": false,
              "stageStart": false,
              "startTime": 1620926705108,
              "status": "RUNNING"
            },
            {
              "endTime": null,
              "id": "3",
              "implementingClass": "com.netflix.spinnaker.orca.clouddriver.tasks.loadbalancer.UpsertLoadBalancerResultObjectExtrapolationTask",
              "loopEnd": false,
              "loopStart": false,
              "name": "extrapolateUpsertResult",
              "stageEnd": false,
              "stageStart": false,
              "startTime": null,
              "status": "NOT_STARTED"
            },
            {
              "endTime": null,
              "id": "4",
              "implementingClass": "com.netflix.spinnaker.orca.clouddriver.tasks.loadbalancer.UpsertLoadBalancerForceRefreshTask",
              "loopEnd": false,
              "loopStart": false,
              "name": "forceCacheRefresh",
              "stageEnd": true,
              "stageStart": false,
              "startTime": null,
              "status": "NOT_STARTED"
            }
          ],
          "type": "upsertLoadBalancers"
        },
        {
          "context": {
            "account": "staging",
            "application": "test",
            "availabilityZones": {
              "us-east-2": [
                "us-east-2a",
                "us-east-2b",
                "us-east-2c"
              ]
            },
            "capacity": {
              "desired": 1,
              "max": 1,
              "min": 1
            },
            "cloudProvider": "aws",
            "cooldown": 10,
            "copySourceCustomBlockDeviceMappings": false,
            "ebsOptimized": false,
            "enabledMetrics": [],
            "freeFormDetails": "",
            "healthCheckGracePeriod": 600,
            "healthCheckType": "EC2",
            "iamRole": "BaseIAMRole",
            "instanceMonitoring": false,
            "instanceType": "t3.nano",
            "keyPair": "Demo",
            "loadBalancers": [],
            "name": "Deploy in us-east-2",
            "provider": "aws",
            "reason": "sad",
            "securityGroups": [],
            "source": {},
            "spotPrice": "",
            "stack": "",
            "strategy": "",
            "subnetType": "",
            "suspendedProcesses": [],
            "tags": {},
            "targetGroups": [],
            "targetHealthyDeployPercentage": 100,
            "terminationPolicies": [
              "Default"
            ],
            "type": "createServerGroup",
            "useAmiBlockDeviceMappings": false
          },
          "endTime": null,
          "id": "01F5KC59ZVHCFYZPQ9851X0D3X",
          "lastModified": null,
          "name": "Deploy in us-east-2",
          "outputs": {},
          "parentStageId": "01F5KC59VX6DZFTP10F521J3G2",
          "refId": "15<1",
          "requisiteStageRefIds": [],
          "scheduledTime": null,
          "startTime": 1620926703698,
          "startTimeExpiry": null,
          "status": "RUNNING",
          "syntheticStageOwner": "STAGE_BEFORE",
          "tasks": [
            {
              "endTime": null,
              "id": "1",
              "implementingClass": "com.netflix.spinnaker.orca.kato.pipeline.strategy.DetermineSourceServerGroupTask",
              "loopEnd": false,
              "loopStart": false,
              "name": "determineSourceServerGroup",
              "stageEnd": false,
              "stageStart": true,
              "startTime": 1620926703970,
              "status": "RUNNING"
            },
            {
              "endTime": null,
              "id": "2",
              "implementingClass": "com.netflix.spinnaker.orca.clouddriver.tasks.DetermineHealthProvidersTask",
              "loopEnd": false,
              "loopStart": false,
              "name": "determineHealthProviders",
              "stageEnd": false,
              "stageStart": false,
              "startTime": null,
              "status": "NOT_STARTED"
            },
            {
              "endTime": null,
              "id": "3",
              "implementingClass": "com.netflix.spinnaker.orca.clouddriver.pipeline.providers.aws.CaptureSourceServerGroupCapacityTask",
              "loopEnd": false,
              "loopStart": false,
              "name": "snapshotSourceServerGroup",
              "stageEnd": false,
              "stageStart": false,
              "startTime": null,
              "status": "NOT_STARTED"
            },
            {
              "endTime": null,
              "id": "4",
              "implementingClass": "com.netflix.spinnaker.orca.clouddriver.tasks.servergroup.CreateServerGroupTask",
              "loopEnd": false,
              "loopStart": false,
              "name": "createServerGroup",
              "stageEnd": false,
              "stageStart": false,
              "startTime": null,
              "status": "NOT_STARTED"
            },
            {
              "endTime": null,
              "id": "5",
              "implementingClass": "com.netflix.spinnaker.orca.clouddriver.tasks.MonitorKatoTask",
              "loopEnd": false,
              "loopStart": false,
              "name": "monitorDeploy",
              "stageEnd": false,
              "stageStart": false,
              "startTime": null,
              "status": "NOT_STARTED"
            },
            {
              "endTime": null,
              "id": "6",
              "implementingClass": "com.netflix.spinnaker.orca.clouddriver.tasks.servergroup.ServerGroupCacheForceRefreshTask",
              "loopEnd": false,
              "loopStart": false,
              "name": "forceCacheRefresh",
              "stageEnd": false,
              "stageStart": false,
              "startTime": null,
              "status": "NOT_STARTED"
            },
            {
              "endTime": null,
              "id": "7",
              "implementingClass": "com.netflix.spinnaker.orca.clouddriver.tasks.instance.WaitForUpInstancesTask",
              "loopEnd": false,
              "loopStart": false,
              "name": "waitForUpInstances",
              "stageEnd": false,
              "stageStart": false,
              "startTime": null,
              "status": "NOT_STARTED"
            },
            {
              "endTime": null,
              "id": "8",
              "implementingClass": "com.netflix.spinnaker.orca.clouddriver.tasks.servergroup.ServerGroupCacheForceRefreshTask",
              "loopEnd": false,
              "loopStart": false,
              "name": "forceCacheRefresh",
              "stageEnd": false,
              "stageStart": false,
              "startTime": null,
              "status": "NOT_STARTED"
            },
            {
              "endTime": null,
              "id": "9",
              "implementingClass": "com.netflix.spinnaker.orca.igor.tasks.GetCommitsTask",
              "loopEnd": false,
              "loopStart": false,
              "name": "getCommits",
              "stageEnd": true,
              "stageStart": false,
              "startTime": null,
              "status": "NOT_STARTED"
            }
          ],
          "type": "createServerGroup"
        },
        {
          "context": {
            "clusters": [
              {
                "account": "staging",
                "application": "test",
                "availabilityZones": {
                  "us-east-2": [
                    "us-east-2a",
                    "us-east-2b",
                    "us-east-2c"
                  ]
                },
                "capacity": {
                  "desired": 1,
                  "max": 1,
                  "min": 1
                },
                "cloudProvider": "aws",
                "cooldown": 10,
                "copySourceCustomBlockDeviceMappings": false,
                "ebsOptimized": false,
                "enabledMetrics": [],
                "freeFormDetails": "",
                "healthCheckGracePeriod": 600,
                "healthCheckType": "EC2",
                "iamRole": "BaseIAMRole",
                "instanceMonitoring": false,
                "instanceType": "t3.nano",
                "keyPair": "Demo",
                "loadBalancers": [],
                "provider": "aws",
                "reason": "sad",
                "securityGroups": [],
                "spotPrice": "",
                "stack": "",
                "strategy": "",
                "subnetType": "",
                "suspendedProcesses": [],
                "tags": {},
                "targetGroups": [],
                "targetHealthyDeployPercentage": 100,
                "terminationPolicies": [
                  "Default"
                ],
                "useAmiBlockDeviceMappings": false
              }
            ]
          },
          "endTime": null,
          "id": "01F5KC59VX6DZFTP10F521J3G2",
          "lastModified": null,
          "name": "Deploy",
          "outputs": {},
          "parentStageId": null,
          "refId": "15",
          "requisiteStageRefIds": [],
          "scheduledTime": null,
          "startTime": 1620926703597,
          "startTimeExpiry": null,
          "status": "RUNNING",
          "syntheticStageOwner": null,
          "tasks": [
            {
              "endTime": null,
              "id": "1",
              "implementingClass": "com.netflix.spinnaker.orca.kato.pipeline.ParallelDeployStage.CompleteParallelDeployTask",
              "loopEnd": false,
              "loopStart": false,
              "name": "completeParallelDeploy",
              "stageEnd": true,
              "stageStart": true,
              "startTime": null,
              "status": "NOT_STARTED"
            }
          ],
          "type": "deploy"
        },
        {
          "context": {
            "cloudProvider": "aws",
            "cloudProviderType": "aws",
            "credentials": "staging",
            "regions": [
              "us-east-2"
            ],
            "target": "current_asg_dynamic"
          },
          "endTime": null,
          "id": "01F5KC5AFSDSNE2QQEBV91VKF1",
          "lastModified": null,
          "name": "determineTargetServerGroup",
          "outputs": {},
          "parentStageId": "01F5KC59VXHAQ7P03S2RD1MHKP",
          "refId": "16<1",
          "requisiteStageRefIds": [],
          "scheduledTime": null,
          "startTime": 1620926704525,
          "startTimeExpiry": null,
          "status": "RUNNING",
          "syntheticStageOwner": "STAGE_BEFORE",
          "tasks": [
            {
              "endTime": null,
              "id": "1",
              "implementingClass": "com.netflix.spinnaker.orca.clouddriver.tasks.servergroup.support.DetermineTargetServerGroupTask",
              "loopEnd": false,
              "loopStart": false,
              "name": "determineTargetServerGroup",
              "stageEnd": true,
              "stageStart": true,
              "startTime": 1620926705590,
              "status": "RUNNING"
            }
          ],
          "type": "determineTargetServerGroup"
        },
        {
          "context": {
            "cloudProvider": "aws",
            "cloudProviderType": "aws",
            "credentials": "staging",
            "region": "us-east-2",
            "target": "current_asg_dynamic",
            "targetLocation": {
              "type": "REGION",
              "value": "us-east-2"
            }
          },
          "endTime": null,
          "id": "01F5KC5AGTMK1EHY3RN5X25F9H",
          "lastModified": null,
          "name": "destroyServerGroup",
          "outputs": {},
          "parentStageId": "01F5KC59VXHAQ7P03S2RD1MHKP",
          "refId": "16<2",
          "requisiteStageRefIds": [
            "16<1"
          ],
          "scheduledTime": null,
          "startTime": null,
          "startTimeExpiry": null,
          "status": "NOT_STARTED",
          "syntheticStageOwner": "STAGE_BEFORE",
          "tasks": [],
          "type": "destroyServerGroup"
        },
        {
          "context": {
            "cloudProvider": "aws",
            "cloudProviderType": "aws",
            "credentials": "staging",
            "target": "current_asg_dynamic"
          },
          "endTime": null,
          "id": "01F5KC59VXHAQ7P03S2RD1MHKP",
          "lastModified": null,
          "name": "Destroy Server Group",
          "outputs": {},
          "parentStageId": null,
          "refId": "16",
          "requisiteStageRefIds": [],
          "scheduledTime": null,
          "startTime": 1620926703600,
          "startTimeExpiry": null,
          "status": "RUNNING",
          "syntheticStageOwner": null,
          "tasks": [],
          "type": "destroyServerGroup"
        },
        {
          "context": {
            "credentials": "staging",
            "exception": {
              "details": {
                "error": "Unexpected Task Failure",
                "errors": [
                  "No regions selected. At least one region must be chosen."
                ],
                "stackTrace": "java.lang.IllegalArgumentException: No regions selected. At least one region must be chosen.\n\tat com.netflix.spinnaker.orca.clouddriver.tasks.providers.aws.cloudformation.DeployCloudFormationTask.lambda$execute$2(DeployCloudFormationTask.java:146)\n\tat java.base/java.util.Optional.orElseThrow(Optional.java:408)\n\tat com.netflix.spinnaker.orca.clouddriver.tasks.providers.aws.cloudformation.DeployCloudFormationTask.execute(DeployCloudFormationTask.java:144)\n\tat com.netflix.spinnaker.orca.q.handler.RunTaskHandler$handle$1$1$1.invoke(RunTaskHandler.kt:144)\n\tat com.netflix.spinnaker.orca.q.handler.RunTaskHandler$handle$1$1$1.invoke(RunTaskHandler.kt:75)\n\tat com.netflix.spinnaker.orca.q.handler.RunTaskHandler.withLoggingContext(RunTaskHandler.kt:419)\n\tat com.netflix.spinnaker.orca.q.handler.RunTaskHandler.access$withLoggingContext(RunTaskHandler.kt:75)\n\tat com.netflix.spinnaker.orca.q.handler.RunTaskHandler$handle$1$1.invoke(RunTaskHandler.kt:105)\n\tat com.netflix.spinnaker.orca.q.handler.RunTaskHandler$handle$1$1.invoke(RunTaskHandler.kt:75)\n\tat com.netflix.spinnaker.orca.q.handler.AuthenticationAware$sam$java_util_concurrent_Callable$0.call(AuthenticationAware.kt)\n\tat com.netflix.spinnaker.security.AuthenticatedRequest.lambda$wrapCallableForPrincipal$0(AuthenticatedRequest.java:272)\n\tat com.netflix.spinnaker.orca.q.handler.AuthenticationAware$DefaultImpls.withAuth(AuthenticationAware.kt:51)\n\tat com.netflix.spinnaker.orca.q.handler.RunTaskHandler.withAuth(RunTaskHandler.kt:75)\n\tat com.netflix.spinnaker.orca.q.handler.RunTaskHandler$handle$1.invoke(RunTaskHandler.kt:104)\n\tat com.netflix.spinnaker.orca.q.handler.RunTaskHandler$handle$1.invoke(RunTaskHandler.kt:75)\n\tat com.netflix.spinnaker.orca.q.handler.RunTaskHandler$withTask$1.invoke(RunTaskHandler.kt:247)\n\tat com.netflix.spinnaker.orca.q.handler.RunTaskHandler$withTask$1.invoke(RunTaskHandler.kt:75)\n\tat com.netflix.spinnaker.orca.q.handler.OrcaMessageHandler$withTask$1.invoke(OrcaMessageHandler.kt:68)\n\tat com.netflix.spinnaker.orca.q.handler.OrcaMessageHandler$withTask$1.invoke(OrcaMessageHandler.kt:46)\n\tat com.netflix.spinnaker.orca.q.handler.OrcaMessageHandler$withStage$1.invoke(OrcaMessageHandler.kt:85)\n\tat com.netflix.spinnaker.orca.q.handler.OrcaMessageHandler$withStage$1.invoke(OrcaMessageHandler.kt:46)\n\tat com.netflix.spinnaker.orca.q.handler.OrcaMessageHandler$DefaultImpls.withExecution(OrcaMessageHandler.kt:95)\n\tat com.netflix.spinnaker.orca.q.handler.RunTaskHandler.withExecution(RunTaskHandler.kt:75)\n\tat com.netflix.spinnaker.orca.q.handler.OrcaMessageHandler$DefaultImpls.withStage(OrcaMessageHandler.kt:74)\n\tat com.netflix.spinnaker.orca.q.handler.RunTaskHandler.withStage(RunTaskHandler.kt:75)\n\tat com.netflix.spinnaker.orca.q.handler.OrcaMessageHandler$DefaultImpls.withTask(OrcaMessageHandler.kt:60)\n\tat com.netflix.spinnaker.orca.q.handler.RunTaskHandler.withTask(RunTaskHandler.kt:75)\n\tat com.netflix.spinnaker.orca.q.handler.RunTaskHandler.withTask(RunTaskHandler.kt:236)\n\tat com.netflix.spinnaker.orca.q.handler.RunTaskHandler.handle(RunTaskHandler.kt:101)\n\tat com.netflix.spinnaker.orca.q.handler.RunTaskHandler.handle(RunTaskHandler.kt:75)\n\tat com.netflix.spinnaker.q.MessageHandler$DefaultImpls.invoke(MessageHandler.kt:36)\n\tat com.netflix.spinnaker.orca.q.handler.OrcaMessageHandler$DefaultImpls.invoke(OrcaMessageHandler.kt)\n\tat com.netflix.spinnaker.orca.q.handler.RunTaskHandler.invoke(RunTaskHandler.kt:75)\n\tat com.netflix.spinnaker.orca.q.audit.ExecutionTrackingMessageHandlerPostProcessor$ExecutionTrackingMessageHandlerProxy.invoke(ExecutionTrackingMessageHandlerPostProcessor.kt:72)\n\tat com.netflix.spinnaker.q.QueueProcessor$callback$1$1.run(QueueProcessor.kt:90)\n\tat java.base/java.util.concurrent.ThreadPoolExecutor.runWorker(ThreadPoolExecutor.java:1128)\n\tat java.base/java.util.concurrent.ThreadPoolExecutor$Worker.run(ThreadPoolExecutor.java:628)\n\tat java.base/java.lang.Thread.run(Thread.java:834)\n"
              },
              "exceptionType": "IllegalArgumentException",
              "operation": "deployCloudFormation",
              "shouldRetry": false,
              "timestamp": 1620926704546
            },
            "parameters": {},
            "regions": [],
            "source": "artifact",
            "stackArtifactAccount": "myUserName",
            "stackArtifactId": "05ad020e-73a6-49f2-9988-2073831219e9",
            "stackName": "satest",
            "tags": {}
          },
          "endTime": null,
          "id": "01F5KC59VXV45WRT9VBRT4HSQC",
          "lastModified": null,
          "name": "Deploy (CloudFormation Stack)",
          "outputs": {},
          "parentStageId": null,
          "refId": "17",
          "requisiteStageRefIds": [],
          "scheduledTime": null,
          "startTime": 1620926703613,
          "startTimeExpiry": null,
          "status": "RUNNING",
          "syntheticStageOwner": null,
          "tasks": [
            {
              "endTime": 1620926705629,
              "id": "1",
              "implementingClass": "com.netflix.spinnaker.orca.clouddriver.tasks.providers.aws.cloudformation.DeployCloudFormationTask",
              "loopEnd": false,
              "loopStart": false,
              "name": "deployCloudFormation",
              "stageEnd": false,
              "stageStart": true,
              "startTime": 1620926703699,
              "status": "TERMINAL"
            },
            {
              "endTime": null,
              "id": "2",
              "implementingClass": "com.netflix.spinnaker.orca.clouddriver.tasks.MonitorKatoTask",
              "loopEnd": false,
              "loopStart": false,
              "name": "monitorCloudFormation",
              "stageEnd": false,
              "stageStart": false,
              "startTime": null,
              "status": "NOT_STARTED"
            },
            {
              "endTime": null,
              "id": "3",
              "implementingClass": "com.netflix.spinnaker.orca.clouddriver.tasks.providers.aws.cloudformation.CloudFormationForceCacheRefreshTask",
              "loopEnd": false,
              "loopStart": false,
              "name": "forceRefreshCache",
              "stageEnd": false,
              "stageStart": false,
              "startTime": null,
              "status": "NOT_STARTED"
            },
            {
              "endTime": null,
              "id": "4",
              "implementingClass": "com.netflix.spinnaker.orca.clouddriver.tasks.providers.aws.cloudformation.WaitForCloudFormationCompletionTask",
              "loopEnd": false,
              "loopStart": false,
              "name": "waitForCloudFormationCompletion",
              "stageEnd": true,
              "stageStart": false,
              "startTime": null,
              "status": "NOT_STARTED"
            }
          ],
          "type": "deployCloudFormation"
        },
        {
          "context": {
            "cloudProvider": "aws",
            "cloudProviderType": "aws",
            "cluster": "test",
            "credentials": "staging",
            "interestingHealthProviderNames": [
              "Amazon"
            ],
            "preferLargerOverNewer": "false",
            "regions": [],
            "remainingEnabledServerGroups": 1
          },
          "endTime": null,
          "id": "01F5KC59VX9BYMY7CCXAG75NXT",
          "lastModified": null,
          "name": "Disable Cluster",
          "outputs": {},
          "parentStageId": null,
          "refId": "18",
          "requisiteStageRefIds": [],
          "scheduledTime": null,
          "startTime": 1620926703616,
          "startTimeExpiry": null,
          "status": "RUNNING",
          "syntheticStageOwner": null,
          "tasks": [
            {
              "endTime": 1620926704950,
              "id": "1",
              "implementingClass": "com.netflix.spinnaker.orca.clouddriver.tasks.DetermineHealthProvidersTask",
              "loopEnd": false,
              "loopStart": false,
              "name": "determineHealthProviders",
              "stageEnd": false,
              "stageStart": true,
              "startTime": 1620926703761,
              "status": "SUCCEEDED"
            },
            {
              "endTime": null,
              "id": "2",
              "implementingClass": "com.netflix.spinnaker.orca.clouddriver.tasks.cluster.DisableClusterTask",
              "loopEnd": false,
              "loopStart": false,
              "name": "disableCluster",
              "stageEnd": false,
              "stageStart": false,
              "startTime": null,
              "status": "NOT_STARTED"
            },
            {
              "endTime": null,
              "id": "3",
              "implementingClass": "com.netflix.spinnaker.orca.clouddriver.tasks.MonitorKatoTask",
              "loopEnd": false,
              "loopStart": false,
              "name": "monitorDisableCluster",
              "stageEnd": false,
              "stageStart": false,
              "startTime": null,
              "status": "NOT_STARTED"
            },
            {
              "endTime": null,
              "id": "4",
              "implementingClass": "com.netflix.spinnaker.orca.clouddriver.tasks.servergroup.ServerGroupCacheForceRefreshTask",
              "loopEnd": false,
              "loopStart": false,
              "name": "forceCacheRefresh",
              "stageEnd": false,
              "stageStart": false,
              "startTime": null,
              "status": "NOT_STARTED"
            },
            {
              "endTime": null,
              "id": "5",
              "implementingClass": "com.netflix.spinnaker.orca.clouddriver.tasks.cluster.WaitForClusterDisableTask",
              "loopEnd": false,
              "loopStart": false,
              "name": "waitForClusterDisable",
              "stageEnd": false,
              "stageStart": false,
              "startTime": null,
              "status": "NOT_STARTED"
            },
            {
              "endTime": null,
              "id": "6",
              "implementingClass": "com.netflix.spinnaker.orca.clouddriver.tasks.servergroup.ServerGroupCacheForceRefreshTask",
              "loopEnd": false,
              "loopStart": false,
              "name": "forceCacheRefresh",
              "stageEnd": true,
              "stageStart": false,
              "startTime": null,
              "status": "NOT_STARTED"
            }
          ],
          "type": "disableCluster"
        },
        {
          "context": {
            "beforeStagePlanningFailed": true,
            "cloudProvider": "aws",
            "cloudProviderType": "aws",
            "cluster": "test",
            "credentials": "staging",
            "exception": {
              "details": {
                "error": "Unexpected Task Failure",
                "errors": [
                  "Cannot invoke method singularType() on null object"
                ],
                "stackTrace": "java.lang.NullPointerException: Cannot invoke method singularType() on null object\n\tat org.codehaus.groovy.runtime.NullObject.invokeMethod(NullObject.java:91)\n\tat org.codehaus.groovy.runtime.callsite.PogoMetaClassSite.call(PogoMetaClassSite.java:43)\n\tat org.codehaus.groovy.runtime.callsite.CallSiteArray.defaultCall(CallSiteArray.java:47)\n\tat org.codehaus.groovy.runtime.callsite.NullCallSite.call(NullCallSite.java:34)\n\tat org.codehaus.groovy.runtime.callsite.CallSiteArray.defaultCall(CallSiteArray.java:47)\n\tat org.codehaus.groovy.runtime.callsite.AbstractCallSite.call(AbstractCallSite.java:115)\n\tat org.codehaus.groovy.runtime.callsite.AbstractCallSite.call(AbstractCallSite.java:119)\n\tat com.netflix.spinnaker.orca.clouddriver.pipeline.servergroup.support.TargetServerGroupLinearStageSupport.composeDynamicTargets(TargetServerGroupLinearStageSupport.groovy:176)\n\tat java.base/jdk.internal.reflect.NativeMethodAccessorImpl.invoke0(Native Method)\n\tat java.base/jdk.internal.reflect.NativeMethodAccessorImpl.invoke(NativeMethodAccessorImpl.java:62)\n\tat java.base/jdk.internal.reflect.DelegatingMethodAccessorImpl.invoke(DelegatingMethodAccessorImpl.java:43)\n\tat java.base/java.lang.reflect.Method.invoke(Method.java:566)\n\tat org.codehaus.groovy.runtime.callsite.PlainObjectMetaMethodSite.doInvoke(PlainObjectMetaMethodSite.java:43)\n\tat org.codehaus.groovy.runtime.callsite.PogoMetaMethodSite$PogoCachedMethodSiteNoUnwrapNoCoerce.invoke(PogoMetaMethodSite.java:190)\n\tat org.codehaus.groovy.runtime.callsite.PogoMetaMethodSite.callCurrent(PogoMetaMethodSite.java:58)\n\tat org.codehaus.groovy.runtime.callsite.CallSiteArray.defaultCallCurrent(CallSiteArray.java:51)\n\tat org.codehaus.groovy.runtime.callsite.AbstractCallSite.callCurrent(AbstractCallSite.java:156)\n\tat org.codehaus.groovy.runtime.callsite.AbstractCallSite.callCurrent(AbstractCallSite.java:184)\n\tat com.netflix.spinnaker.orca.clouddriver.pipeline.servergroup.support.TargetServerGroupLinearStageSupport.composeTargets(TargetServerGroupLinearStageSupport.groovy:144)\n\tat com.netflix.spinnaker.orca.clouddriver.pipeline.servergroup.support.TargetServerGroupLinearStageSupport$composeTargets.callCurrent(Unknown Source)\n\tat org.codehaus.groovy.runtime.callsite.CallSiteArray.defaultCallCurrent(CallSiteArray.java:51)\n\tat com.netflix.spinnaker.orca.clouddriver.pipeline.servergroup.support.TargetServerGroupLinearStageSupport$composeTargets.callCurrent(Unknown Source)\n\tat com.netflix.spinnaker.orca.clouddriver.pipeline.servergroup.support.TargetServerGroupLinearStageSupport.beforeStages(TargetServerGroupLinearStageSupport.groovy:110)\n\tat com.netflix.spinnaker.orca.q.StageDefinitionBuildersKt.buildBeforeStages(StageDefinitionBuilders.kt:103)\n\tat com.netflix.spinnaker.orca.q.handler.StartStageHandler.plan(StartStageHandler.kt:174)\n\tat com.netflix.spinnaker.orca.q.handler.StartStageHandler.access$plan(StartStageHandler.kt:61)\n\tat com.netflix.spinnaker.orca.q.handler.StartStageHandler$handle$1$1.invoke(StartStageHandler.kt:99)\n\tat com.netflix.spinnaker.orca.q.handler.StartStageHandler$handle$1$1.invoke(StartStageHandler.kt:61)\n\tat com.netflix.spinnaker.orca.q.handler.AuthenticationAware$sam$java_util_concurrent_Callable$0.call(AuthenticationAware.kt)\n\tat com.netflix.spinnaker.security.AuthenticatedRequest.lambda$wrapCallableForPrincipal$0(AuthenticatedRequest.java:272)\n\tat com.netflix.spinnaker.orca.q.handler.AuthenticationAware$DefaultImpls.withAuth(AuthenticationAware.kt:51)\n\tat com.netflix.spinnaker.orca.q.handler.StartStageHandler.withAuth(StartStageHandler.kt:61)\n\tat com.netflix.spinnaker.orca.q.handler.StartStageHandler$handle$1.invoke(StartStageHandler.kt:81)\n\tat com.netflix.spinnaker.orca.q.handler.StartStageHandler$handle$1.invoke(StartStageHandler.kt:61)\n\tat com.netflix.spinnaker.orca.q.handler.OrcaMessageHandler$withStage$1.invoke(OrcaMessageHandler.kt:85)\n\tat com.netflix.spinnaker.orca.q.handler.OrcaMessageHandler$withStage$1.invoke(OrcaMessageHandler.kt:46)\n\tat com.netflix.spinnaker.orca.q.handler.OrcaMessageHandler$DefaultImpls.withExecution(OrcaMessageHandler.kt:95)\n\tat com.netflix.spinnaker.orca.q.handler.StartStageHandler.withExecution(StartStageHandler.kt:61)\n\tat com.netflix.spinnaker.orca.q.handler.OrcaMessageHandler$DefaultImpls.withStage(OrcaMessageHandler.kt:74)\n\tat com.netflix.spinnaker.orca.q.handler.StartStageHandler.withStage(StartStageHandler.kt:61)\n\tat com.netflix.spinnaker.orca.q.handler.StartStageHandler.handle(StartStageHandler.kt:79)\n\tat com.netflix.spinnaker.orca.q.handler.StartStageHandler.handle(StartStageHandler.kt:61)\n\tat com.netflix.spinnaker.q.MessageHandler$DefaultImpls.invoke(MessageHandler.kt:36)\n\tat com.netflix.spinnaker.orca.q.handler.OrcaMessageHandler$DefaultImpls.invoke(OrcaMessageHandler.kt)\n\tat com.netflix.spinnaker.orca.q.handler.StartStageHandler.invoke(StartStageHandler.kt:61)\n\tat com.netflix.spinnaker.orca.q.audit.ExecutionTrackingMessageHandlerPostProcessor$ExecutionTrackingMessageHandlerProxy.invoke(ExecutionTrackingMessageHandlerPostProcessor.kt:72)\n\tat com.netflix.spinnaker.q.QueueProcessor$callback$1$1.run(QueueProcessor.kt:90)\n\tat java.base/java.util.concurrent.ThreadPoolExecutor.runWorker(ThreadPoolExecutor.java:1128)\n\tat java.base/java.util.concurrent.ThreadPoolExecutor$Worker.run(ThreadPoolExecutor.java:628)\n\tat java.base/java.lang.Thread.run(Thread.java:834)\n"
              },
              "exceptionType": "NullPointerException",
              "operation": "Enable Server Group",
              "shouldRetry": false,
              "timestamp": 1620926704111
            },
            "target": "current_asg_dynamic"
          },
          "endTime": 1620926704409,
          "id": "01F5KC59VXD2VE54883ZMJHEX3",
          "lastModified": null,
          "name": "Enable Server Group",
          "outputs": {},
          "parentStageId": null,
          "refId": "19",
          "requisiteStageRefIds": [],
          "scheduledTime": null,
          "startTime": 1620926703624,
          "startTimeExpiry": null,
          "status": "TERMINAL",
          "syntheticStageOwner": null,
          "tasks": [],
          "type": "enableServerGroup"
        },
        {
          "context": {
            "entityRef": {
              "entityId": "test",
              "entityType": "application"
            },
            "tags": [
              {
                "name": "test",
                "namespace": "testns",
                "value": "test"
              }
            ]
          },
          "endTime": null,
          "id": "01F5KC59VX8MSHMTMHBY1YR8Y0",
          "lastModified": null,
          "name": "Entity Tags",
          "outputs": {},
          "parentStageId": null,
          "refId": "20",
          "requisiteStageRefIds": [],
          "scheduledTime": null,
          "startTime": 1620926703665,
          "startTimeExpiry": null,
          "status": "RUNNING",
          "syntheticStageOwner": null,
          "tasks": [
            {
              "endTime": null,
              "id": "1",
              "implementingClass": "com.netflix.spinnaker.orca.clouddriver.tasks.entitytags.UpsertEntityTagsTask",
              "loopEnd": false,
              "loopStart": false,
              "name": "upsertEntityTags",
              "stageEnd": false,
              "stageStart": true,
              "startTime": 1620926703784,
              "status": "RUNNING"
            },
            {
              "endTime": null,
              "id": "2",
              "implementingClass": "com.netflix.spinnaker.orca.clouddriver.tasks.MonitorKatoTask",
              "loopEnd": false,
              "loopStart": false,
              "name": "monitorUpsert",
              "stageEnd": true,
              "stageStart": false,
              "startTime": null,
              "status": "NOT_STARTED"
            }
          ],
          "type": "upsertEntityTags"
        },
        {
          "context": {
            "expressionEvaluationSummary": {
              "trigger.buildInfo.number": [
                {
                  "description": "Failed to evaluate [var] EL1007E: Property or field 'number' cannot be found on null",
                  "exceptionType": "org.springframework.expression.spel.SpelEvaluationException",
                  "level": "ERROR",
                  "timestamp": 1620926704357
                }
              ]
            },
            "failOnFailedExpressions": true,
            "variables": [
              {
                "key": "test",
                "sourceValue": "{trigger.buildInfo.number}",
                "value": "${trigger.buildInfo.number}"
              }
            ]
          },
          "endTime": null,
          "id": "01F5KC59VXH51C7G7KH5CA8JDZ",
          "lastModified": null,
          "name": "Evaluate Variables",
          "outputs": {},
          "parentStageId": null,
          "refId": "21",
          "requisiteStageRefIds": [],
          "scheduledTime": null,
          "startTime": 1620926704036,
          "startTimeExpiry": null,
          "status": "RUNNING",
          "syntheticStageOwner": null,
          "tasks": [
            {
              "endTime": null,
              "id": "1",
              "implementingClass": "com.netflix.spinnaker.orca.pipeline.tasks.EvaluateVariablesTask",
              "loopEnd": false,
              "loopStart": false,
              "name": "evaluateVariables",
              "stageEnd": true,
              "stageStart": true,
              "startTime": 1620926704354,
              "status": "RUNNING"
            }
          ],
          "type": "evaluateVariables"
        },
        {
          "context": {
            "application": "hostname",
            "artifacts": [
              {
                "customKind": false,
                "location": "staging",
                "metadata": {
                  "account": "spinnaker"
                },
                "name": "hostname-metrics",
                "reference": "hostname-metrics",
                "type": "kubernetes/service",
                "version": ""
              }
            ],
            "executionOptions": {
              "successful": true
            },
            "expectedArtifacts": [
              {
                "defaultArtifact": {
                  "customKind": true,
                  "id": "df96edee-9d90-486c-b269-ef110f469499"
                },
                "displayName": "light-panther-92",
                "id": "4d764059-d642-4870-ae63-476e59af708c",
                "matchArtifact": {
                  "customKind": true,
                  "id": "7bd826db-a9c8-4052-ad15-5029baba0067"
                },
                "useDefaultArtifact": false,
                "usePriorArtifact": false
              }
            ],
            "pipeline": "7db1e350-dedb-4dc1-9976-e71f97b5f132",
            "resolvedExpectedArtifacts": [
              {
                "boundArtifact": {
                  "customKind": false,
                  "location": "staging",
                  "metadata": {
                    "account": "spinnaker"
                  },
                  "name": "hostname-metrics",
                  "reference": "hostname-metrics",
                  "type": "kubernetes/service",
                  "version": ""
                },
                "defaultArtifact": {
                  "customKind": true,
                  "metadata": {
                    "id": "df96edee-9d90-486c-b269-ef110f469499"
                  }
                },
                "id": "4d764059-d642-4870-ae63-476e59af708c",
                "matchArtifact": {
                  "customKind": true,
                  "metadata": {
                    "id": "7bd826db-a9c8-4052-ad15-5029baba0067"
                  }
                },
                "useDefaultArtifact": false,
                "usePriorArtifact": false
              }
            ]
          },
          "endTime": null,
          "id": "01F5KC59VXDDF9TBZTVM242YHT",
          "lastModified": null,
          "name": "Find Artifacts From Execution",
          "outputs": {
            "artifacts": [
              {
                "customKind": false,
                "location": "staging",
                "metadata": {
                  "account": "spinnaker"
                },
                "name": "hostname-metrics",
                "reference": "hostname-metrics",
                "type": "kubernetes/service",
                "version": ""
              }
            ],
            "resolvedExpectedArtifacts": [
              {
                "boundArtifact": {
                  "customKind": false,
                  "location": "staging",
                  "metadata": {
                    "account": "spinnaker"
                  },
                  "name": "hostname-metrics",
                  "reference": "hostname-metrics",
                  "type": "kubernetes/service",
                  "version": ""
                },
                "defaultArtifact": {
                  "customKind": true,
                  "metadata": {
                    "id": "df96edee-9d90-486c-b269-ef110f469499"
                  }
                },
                "id": "4d764059-d642-4870-ae63-476e59af708c",
                "matchArtifact": {
                  "customKind": true,
                  "metadata": {
                    "id": "7bd826db-a9c8-4052-ad15-5029baba0067"
                  }
                },
                "useDefaultArtifact": false,
                "usePriorArtifact": false
              }
            ]
          },
          "parentStageId": null,
          "refId": "22",
          "requisiteStageRefIds": [],
          "scheduledTime": null,
          "startTime": 1620926703681,
          "startTimeExpiry": null,
          "status": "RUNNING",
          "syntheticStageOwner": null,
          "tasks": [
            {
              "endTime": null,
              "id": "1",
              "implementingClass": "com.netflix.spinnaker.orca.clouddriver.tasks.artifacts.FindArtifactFromExecutionTask",
              "loopEnd": false,
              "loopStart": false,
              "name": "findArtifactFromExecution",
              "stageEnd": true,
              "stageStart": true,
              "startTime": 1620926703882,
              "status": "RUNNING"
            }
          ],
          "type": "findArtifactFromExecution"
        },
        {
          "context": {
            "account": "spinnaker",
            "app": "test",
            "cloudProvider": "kubernetes",
            "location": "spinnaker",
            "manifestName": "deployment spin-gate",
            "mode": "static"
          },
          "endTime": null,
          "id": "01F5KC59VXS0PN55TX4ARCFFCS",
          "lastModified": null,
          "name": "Find Artifacts From Resource (Manifest)",
          "outputs": {},
          "parentStageId": null,
          "refId": "23",
          "requisiteStageRefIds": [],
          "scheduledTime": null,
          "startTime": 1620926703707,
          "startTimeExpiry": null,
          "status": "RUNNING",
          "syntheticStageOwner": null,
          "tasks": [
            {
              "endTime": 1620926705606,
              "id": "1",
              "implementingClass": "com.netflix.spinnaker.orca.clouddriver.tasks.manifest.ResolveTargetManifestTask",
              "loopEnd": false,
              "loopStart": false,
              "name": "resolveTargetManifest",
              "stageEnd": false,
              "stageStart": true,
              "startTime": 1620926703827,
              "status": "SUCCEEDED"
            },
            {
              "endTime": null,
              "id": "2",
              "implementingClass": "com.netflix.spinnaker.orca.clouddriver.tasks.artifacts.FindArtifactsFromResourceTask",
              "loopEnd": false,
              "loopStart": false,
              "name": "findArtifactsFromResource",
              "stageEnd": false,
              "stageStart": false,
              "startTime": null,
              "status": "NOT_STARTED"
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
          "type": "findArtifactsFromResource"
        },
        {
          "context": {
            "cloudProvider": "aws",
            "cloudProviderType": "aws",
            "cluster": "test",
            "credentials": "staging",
            "exception": {
              "details": {
                "error": "Unexpected Task Failure",
                "errors": [
                  "Could not find cluster 'test' for 'staging' in 'us-east-2'."
                ],
                "stackTrace": "java.lang.IllegalStateException: Could not find cluster 'test' for 'staging' in 'us-east-2'.\n\tat java.base/jdk.internal.reflect.NativeConstructorAccessorImpl.newInstance0(Native Method)\n\tat java.base/jdk.internal.reflect.NativeConstructorAccessorImpl.newInstance(NativeConstructorAccessorImpl.java:62)\n\tat java.base/jdk.internal.reflect.DelegatingConstructorAccessorImpl.newInstance(DelegatingConstructorAccessorImpl.java:45)\n\tat java.base/java.lang.reflect.Constructor.newInstance(Constructor.java:490)\n\tat org.codehaus.groovy.reflection.CachedConstructor.invoke(CachedConstructor.java:80)\n\tat org.codehaus.groovy.reflection.CachedConstructor.doConstructorInvoke(CachedConstructor.java:74)\n\tat org.codehaus.groovy.runtime.callsite.ConstructorSite$ConstructorSiteNoUnwrap.callConstructor(ConstructorSite.java:84)\n\tat org.codehaus.groovy.runtime.callsite.CallSiteArray.defaultCallConstructor(CallSiteArray.java:59)\n\tat org.codehaus.groovy.runtime.callsite.AbstractCallSite.callConstructor(AbstractCallSite.java:237)\n\tat org.codehaus.groovy.runtime.callsite.AbstractCallSite.callConstructor(AbstractCallSite.java:249)\n\tat com.netflix.spinnaker.orca.clouddriver.tasks.cluster.FindImageFromClusterTask$_execute_closure2.doCall(FindImageFromClusterTask.groovy:178)\n\tat java.base/jdk.internal.reflect.NativeMethodAccessorImpl.invoke0(Native Method)\n\tat java.base/jdk.internal.reflect.NativeMethodAccessorImpl.invoke(NativeMethodAccessorImpl.java:62)\n\tat java.base/jdk.internal.reflect.DelegatingMethodAccessorImpl.invoke(DelegatingMethodAccessorImpl.java:43)\n\tat java.base/java.lang.reflect.Method.invoke(Method.java:566)\n\tat org.codehaus.groovy.reflection.CachedMethod.invoke(CachedMethod.java:101)\n\tat groovy.lang.MetaMethod.doMethodInvoke(MetaMethod.java:323)\n\tat org.codehaus.groovy.runtime.metaclass.ClosureMetaClass.invokeMethod(ClosureMetaClass.java:263)\n\tat groovy.lang.MetaClassImpl.invokeMethod(MetaClassImpl.java:1041)\n\tat groovy.lang.Closure.call(Closure.java:405)\n\tat groovy.lang.Closure.call(Closure.java:421)\n\tat org.codehaus.groovy.runtime.DefaultGroovyMethods.collectEntries(DefaultGroovyMethods.java:4137)\n\tat org.codehaus.groovy.runtime.DefaultGroovyMethods.collectEntries(DefaultGroovyMethods.java:4044)\n\tat org.codehaus.groovy.runtime.DefaultGroovyMethods.collectEntries(DefaultGroovyMethods.java:4069)\n\tat org.codehaus.groovy.runtime.dgm$96.invoke(Unknown Source)\n\tat org.codehaus.groovy.runtime.callsite.PojoMetaMethodSite$PojoMetaMethodSiteNoUnwrapNoCoerce.invoke(PojoMetaMethodSite.java:244)\n\tat org.codehaus.groovy.runtime.callsite.PojoMetaMethodSite.call(PojoMetaMethodSite.java:53)\n\tat org.codehaus.groovy.runtime.callsite.CallSiteArray.defaultCall(CallSiteArray.java:47)\n\tat org.codehaus.groovy.runtime.callsite.AbstractCallSite.call(AbstractCallSite.java:115)\n\tat org.codehaus.groovy.runtime.callsite.AbstractCallSite.call(AbstractCallSite.java:127)\n\tat com.netflix.spinnaker.orca.clouddriver.tasks.cluster.FindImageFromClusterTask.execute(FindImageFromClusterTask.groovy:141)\n\tat com.netflix.spinnaker.orca.q.handler.RunTaskHandler$handle$1$1$1.invoke(RunTaskHandler.kt:144)\n\tat com.netflix.spinnaker.orca.q.handler.RunTaskHandler$handle$1$1$1.invoke(RunTaskHandler.kt:75)\n\tat com.netflix.spinnaker.orca.q.handler.RunTaskHandler.withLoggingContext(RunTaskHandler.kt:419)\n\tat com.netflix.spinnaker.orca.q.handler.RunTaskHandler.access$withLoggingContext(RunTaskHandler.kt:75)\n\tat com.netflix.spinnaker.orca.q.handler.RunTaskHandler$handle$1$1.invoke(RunTaskHandler.kt:105)\n\tat com.netflix.spinnaker.orca.q.handler.RunTaskHandler$handle$1$1.invoke(RunTaskHandler.kt:75)\n\tat com.netflix.spinnaker.orca.q.handler.AuthenticationAware$sam$java_util_concurrent_Callable$0.call(AuthenticationAware.kt)\n\tat com.netflix.spinnaker.security.AuthenticatedRequest.lambda$wrapCallableForPrincipal$0(AuthenticatedRequest.java:272)\n\tat com.netflix.spinnaker.orca.q.handler.AuthenticationAware$DefaultImpls.withAuth(AuthenticationAware.kt:51)\n\tat com.netflix.spinnaker.orca.q.handler.RunTaskHandler.withAuth(RunTaskHandler.kt:75)\n\tat com.netflix.spinnaker.orca.q.handler.RunTaskHandler$handle$1.invoke(RunTaskHandler.kt:104)\n\tat com.netflix.spinnaker.orca.q.handler.RunTaskHandler$handle$1.invoke(RunTaskHandler.kt:75)\n\tat com.netflix.spinnaker.orca.q.handler.RunTaskHandler$withTask$1.invoke(RunTaskHandler.kt:247)\n\tat com.netflix.spinnaker.orca.q.handler.RunTaskHandler$withTask$1.invoke(RunTaskHandler.kt:75)\n\tat com.netflix.spinnaker.orca.q.handler.OrcaMessageHandler$withTask$1.invoke(OrcaMessageHandler.kt:68)\n\tat com.netflix.spinnaker.orca.q.handler.OrcaMessageHandler$withTask$1.invoke(OrcaMessageHandler.kt:46)\n\tat com.netflix.spinnaker.orca.q.handler.OrcaMessageHandler$withStage$1.invoke(OrcaMessageHandler.kt:85)\n\tat com.netflix.spinnaker.orca.q.handler.OrcaMessageHandler$withStage$1.invoke(OrcaMessageHandler.kt:46)\n\tat com.netflix.spinnaker.orca.q.handler.OrcaMessageHandler$DefaultImpls.withExecution(OrcaMessageHandler.kt:95)\n\tat com.netflix.spinnaker.orca.q.handler.RunTaskHandler.withExecution(RunTaskHandler.kt:75)\n\tat com.netflix.spinnaker.orca.q.handler.OrcaMessageHandler$DefaultImpls.withStage(OrcaMessageHandler.kt:74)\n\tat com.netflix.spinnaker.orca.q.handler.RunTaskHandler.withStage(RunTaskHandler.kt:75)\n\tat com.netflix.spinnaker.orca.q.handler.OrcaMessageHandler$DefaultImpls.withTask(OrcaMessageHandler.kt:60)\n\tat com.netflix.spinnaker.orca.q.handler.RunTaskHandler.withTask(RunTaskHandler.kt:75)\n\tat com.netflix.spinnaker.orca.q.handler.RunTaskHandler.withTask(RunTaskHandler.kt:236)\n\tat com.netflix.spinnaker.orca.q.handler.RunTaskHandler.handle(RunTaskHandler.kt:101)\n\tat com.netflix.spinnaker.orca.q.handler.RunTaskHandler.handle(RunTaskHandler.kt:75)\n\tat com.netflix.spinnaker.q.MessageHandler$DefaultImpls.invoke(MessageHandler.kt:36)\n\tat com.netflix.spinnaker.orca.q.handler.OrcaMessageHandler$DefaultImpls.invoke(OrcaMessageHandler.kt)\n\tat com.netflix.spinnaker.orca.q.handler.RunTaskHandler.invoke(RunTaskHandler.kt:75)\n\tat com.netflix.spinnaker.orca.q.audit.ExecutionTrackingMessageHandlerPostProcessor$ExecutionTrackingMessageHandlerProxy.invoke(ExecutionTrackingMessageHandlerPostProcessor.kt:72)\n\tat com.netflix.spinnaker.q.QueueProcessor$callback$1$1.run(QueueProcessor.kt:90)\n\tat java.base/java.util.concurrent.ThreadPoolExecutor.runWorker(ThreadPoolExecutor.java:1128)\n\tat java.base/java.util.concurrent.ThreadPoolExecutor$Worker.run(ThreadPoolExecutor.java:628)\n\tat java.base/java.lang.Thread.run(Thread.java:834)\n"
              },
              "exceptionType": "IllegalStateException",
              "operation": "findImage",
              "shouldRetry": false,
              "timestamp": 1620926705232
            },
            "onlyEnabled": true,
            "regions": [
              "us-east-2"
            ],
            "selectionStrategy": "LARGEST"
          },
          "endTime": null,
          "id": "01F5KC59VXR6HM4ZDGQS533X3Z",
          "lastModified": null,
          "name": "Find Image from Cluster",
          "outputs": {},
          "parentStageId": null,
          "refId": "24",
          "requisiteStageRefIds": [],
          "scheduledTime": null,
          "startTime": 1620926703771,
          "startTimeExpiry": null,
          "status": "RUNNING",
          "syntheticStageOwner": null,
          "tasks": [
            {
              "endTime": null,
              "id": "1",
              "implementingClass": "com.netflix.spinnaker.orca.clouddriver.tasks.cluster.FindImageFromClusterTask",
              "loopEnd": false,
              "loopStart": false,
              "name": "findImage",
              "stageEnd": true,
              "stageStart": true,
              "startTime": 1620926704082,
              "status": "RUNNING"
            }
          ],
          "type": "findImage"
        },
        {
          "context": {
            "cloudProvider": "aws",
            "cloudProviderType": "aws",
            "exception": {
              "details": {
                "error": "Bad Request",
                "errors": [
                  "Minimum of 3 characters required to filter namedImages"
                ],
                "kind": "HTTP",
                "responseBody": "{\"error\":\"Bad Request\",\"message\":\"Minimum of 3 characters required to filter namedImages\",\"status\":400,\"timestamp\":1620926705030}",
                "status": 400,
                "url": "http://spin-clouddriver.spinnaker:7002/aws/images/find?tag:test=test"
              },
              "exceptionType": "RetrofitError",
              "operation": "findImage",
              "shouldRetry": false,
              "timestamp": 1620926705048
            },
            "regions": [
              "us-east-2"
            ],
            "tags": {
              "test": "test"
            }
          },
          "endTime": null,
          "id": "01F5KC59VXVYM16F67ZF4DKPDP",
          "lastModified": null,
          "name": "Find Image from Tags",
          "outputs": {},
          "parentStageId": null,
          "refId": "25",
          "requisiteStageRefIds": [],
          "scheduledTime": null,
          "startTime": 1620926703765,
          "startTimeExpiry": null,
          "status": "RUNNING",
          "syntheticStageOwner": null,
          "tasks": [
            {
              "endTime": null,
              "id": "1",
              "implementingClass": "com.netflix.spinnaker.orca.clouddriver.tasks.image.FindImageFromTagsTask",
              "loopEnd": false,
              "loopStart": false,
              "name": "findImage",
              "stageEnd": true,
              "stageStart": true,
              "startTime": 1620926704147,
              "status": "RUNNING"
            }
          ],
          "type": "findImageFromTags"
        },
        {
          "context": {
            "exception": {
              "details": {
                "error": "Path parameter \"account\" value must not be null.",
                "errors": [],
                "kind": "UNEXPECTED"
              },
              "exceptionType": "RetrofitError",
              "operation": "startGoogleCloudBuildTask",
              "shouldRetry": false,
              "timestamp": 1620926705364
            }
          },
          "endTime": null,
          "id": "01F5KC59VXFCE23E6ZZVWS5E34",
          "lastModified": null,
          "name": "Google Cloud Build",
          "outputs": {},
          "parentStageId": null,
          "refId": "26",
          "requisiteStageRefIds": [],
          "scheduledTime": null,
          "startTime": 1620926703770,
          "startTimeExpiry": null,
          "status": "RUNNING",
          "syntheticStageOwner": null,
          "tasks": [
            {
              "endTime": null,
              "id": "1",
              "implementingClass": "com.netflix.spinnaker.orca.igor.tasks.StartGoogleCloudBuildTask",
              "loopEnd": false,
              "loopStart": false,
              "name": "startGoogleCloudBuildTask",
              "stageEnd": false,
              "stageStart": true,
              "startTime": 1620926704336,
              "status": "RUNNING"
            },
            {
              "endTime": null,
              "id": "2",
              "implementingClass": "com.netflix.spinnaker.orca.igor.tasks.MonitorGoogleCloudBuildTask",
              "loopEnd": false,
              "loopStart": false,
              "name": "monitorGoogleCloudBuildTask",
              "stageEnd": false,
              "stageStart": false,
              "startTime": null,
              "status": "NOT_STARTED"
            },
            {
              "endTime": null,
              "id": "3",
              "implementingClass": "com.netflix.spinnaker.orca.igor.tasks.GetGoogleCloudBuildArtifactsTask",
              "loopEnd": false,
              "loopStart": false,
              "name": "getGoogleCloudBuildArtifactsTask",
              "stageEnd": false,
              "stageStart": false,
              "startTime": null,
              "status": "NOT_STARTED"
            },
            {
              "endTime": null,
              "id": "4",
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
          "type": "googleCloudBuild"
        },
        {
          "context": {
            "exception": {
              "details": {
                "error": "Unexpected Task Failure",
                "errors": [
                  "No API Key provided"
                ],
                "stackTrace": "java.lang.RuntimeException: No API Key provided\n\tat com.netflix.spinnaker.orca.gremlin.pipeline.GremlinStage.getApiKey(GremlinStage.java:58)\n\tat com.netflix.spinnaker.orca.gremlin.tasks.LaunchGremlinAttackTask.execute(LaunchGremlinAttackTask.java:31)\n\tat com.netflix.spinnaker.orca.q.handler.RunTaskHandler$handle$1$1$1.invoke(RunTaskHandler.kt:144)\n\tat com.netflix.spinnaker.orca.q.handler.RunTaskHandler$handle$1$1$1.invoke(RunTaskHandler.kt:75)\n\tat com.netflix.spinnaker.orca.q.handler.RunTaskHandler.withLoggingContext(RunTaskHandler.kt:419)\n\tat com.netflix.spinnaker.orca.q.handler.RunTaskHandler.access$withLoggingContext(RunTaskHandler.kt:75)\n\tat com.netflix.spinnaker.orca.q.handler.RunTaskHandler$handle$1$1.invoke(RunTaskHandler.kt:105)\n\tat com.netflix.spinnaker.orca.q.handler.RunTaskHandler$handle$1$1.invoke(RunTaskHandler.kt:75)\n\tat com.netflix.spinnaker.orca.q.handler.AuthenticationAware$sam$java_util_concurrent_Callable$0.call(AuthenticationAware.kt)\n\tat com.netflix.spinnaker.security.AuthenticatedRequest.lambda$wrapCallableForPrincipal$0(AuthenticatedRequest.java:272)\n\tat com.netflix.spinnaker.orca.q.handler.AuthenticationAware$DefaultImpls.withAuth(AuthenticationAware.kt:51)\n\tat com.netflix.spinnaker.orca.q.handler.RunTaskHandler.withAuth(RunTaskHandler.kt:75)\n\tat com.netflix.spinnaker.orca.q.handler.RunTaskHandler$handle$1.invoke(RunTaskHandler.kt:104)\n\tat com.netflix.spinnaker.orca.q.handler.RunTaskHandler$handle$1.invoke(RunTaskHandler.kt:75)\n\tat com.netflix.spinnaker.orca.q.handler.RunTaskHandler$withTask$1.invoke(RunTaskHandler.kt:247)\n\tat com.netflix.spinnaker.orca.q.handler.RunTaskHandler$withTask$1.invoke(RunTaskHandler.kt:75)\n\tat com.netflix.spinnaker.orca.q.handler.OrcaMessageHandler$withTask$1.invoke(OrcaMessageHandler.kt:68)\n\tat com.netflix.spinnaker.orca.q.handler.OrcaMessageHandler$withTask$1.invoke(OrcaMessageHandler.kt:46)\n\tat com.netflix.spinnaker.orca.q.handler.OrcaMessageHandler$withStage$1.invoke(OrcaMessageHandler.kt:85)\n\tat com.netflix.spinnaker.orca.q.handler.OrcaMessageHandler$withStage$1.invoke(OrcaMessageHandler.kt:46)\n\tat com.netflix.spinnaker.orca.q.handler.OrcaMessageHandler$DefaultImpls.withExecution(OrcaMessageHandler.kt:95)\n\tat com.netflix.spinnaker.orca.q.handler.RunTaskHandler.withExecution(RunTaskHandler.kt:75)\n\tat com.netflix.spinnaker.orca.q.handler.OrcaMessageHandler$DefaultImpls.withStage(OrcaMessageHandler.kt:74)\n\tat com.netflix.spinnaker.orca.q.handler.RunTaskHandler.withStage(RunTaskHandler.kt:75)\n\tat com.netflix.spinnaker.orca.q.handler.OrcaMessageHandler$DefaultImpls.withTask(OrcaMessageHandler.kt:60)\n\tat com.netflix.spinnaker.orca.q.handler.RunTaskHandler.withTask(RunTaskHandler.kt:75)\n\tat com.netflix.spinnaker.orca.q.handler.RunTaskHandler.withTask(RunTaskHandler.kt:236)\n\tat com.netflix.spinnaker.orca.q.handler.RunTaskHandler.handle(RunTaskHandler.kt:101)\n\tat com.netflix.spinnaker.orca.q.handler.RunTaskHandler.handle(RunTaskHandler.kt:75)\n\tat com.netflix.spinnaker.q.MessageHandler$DefaultImpls.invoke(MessageHandler.kt:36)\n\tat com.netflix.spinnaker.orca.q.handler.OrcaMessageHandler$DefaultImpls.invoke(OrcaMessageHandler.kt)\n\tat com.netflix.spinnaker.orca.q.handler.RunTaskHandler.invoke(RunTaskHandler.kt:75)\n\tat com.netflix.spinnaker.orca.q.audit.ExecutionTrackingMessageHandlerPostProcessor$ExecutionTrackingMessageHandlerProxy.invoke(ExecutionTrackingMessageHandlerPostProcessor.kt:72)\n\tat com.netflix.spinnaker.q.QueueProcessor$callback$1$1.run(QueueProcessor.kt:90)\n\tat java.base/java.util.concurrent.ThreadPoolExecutor.runWorker(ThreadPoolExecutor.java:1128)\n\tat java.base/java.util.concurrent.ThreadPoolExecutor$Worker.run(ThreadPoolExecutor.java:628)\n\tat java.base/java.lang.Thread.run(Thread.java:834)\n"
              },
              "exceptionType": "RuntimeException",
              "operation": "launchGremlinAttack",
              "shouldRetry": false,
              "timestamp": 1620926704638
            }
          },
          "endTime": null,
          "id": "01F5KC59VXD6BY9PBRNTTQJVPV",
          "lastModified": null,
          "name": "Gremlin",
          "outputs": {},
          "parentStageId": null,
          "refId": "27",
          "requisiteStageRefIds": [],
          "scheduledTime": null,
          "startTime": 1620926703775,
          "startTimeExpiry": null,
          "status": "RUNNING",
          "syntheticStageOwner": null,
          "tasks": [
            {
              "endTime": null,
              "id": "1",
              "implementingClass": "com.netflix.spinnaker.orca.gremlin.tasks.LaunchGremlinAttackTask",
              "loopEnd": false,
              "loopStart": false,
              "name": "launchGremlinAttack",
              "stageEnd": false,
              "stageStart": true,
              "startTime": 1620926704078,
              "status": "RUNNING"
            },
            {
              "endTime": null,
              "id": "2",
              "implementingClass": "com.netflix.spinnaker.orca.gremlin.tasks.MonitorGremlinAttackTask",
              "loopEnd": false,
              "loopStart": false,
              "name": "monitorGremlinAttack",
              "stageEnd": true,
              "stageStart": false,
              "startTime": null,
              "status": "NOT_STARTED"
            }
          ],
          "type": "gremlin"
        },
        {
          "context": {
            "continuePipeline": false,
            "failPipeline": true
          },
          "endTime": null,
          "id": "01F5KC59VX8GY09S5X7RW10BWR",
          "lastModified": null,
          "name": "Jenkins",
          "outputs": {},
          "parentStageId": null,
          "refId": "28",
          "requisiteStageRefIds": [],
          "scheduledTime": null,
          "startTime": 1620926703791,
          "startTimeExpiry": null,
          "status": "RUNNING",
          "syntheticStageOwner": null,
          "tasks": [
            {
              "endTime": null,
              "id": "1",
              "implementingClass": "com.netflix.spinnaker.orca.igor.tasks.StartJenkinsJobTask",
              "loopEnd": false,
              "loopStart": false,
              "name": "startJenkinsJob",
              "stageEnd": false,
              "stageStart": true,
              "startTime": 1620926704300,
              "status": "RUNNING"
            },
            {
              "endTime": null,
              "id": "2",
              "implementingClass": "com.netflix.spinnaker.orca.igor.tasks.MonitorQueuedJenkinsJobTask",
              "loopEnd": false,
              "loopStart": false,
              "name": "waitForJenkinsJobStart",
              "stageEnd": false,
              "stageStart": false,
              "startTime": null,
              "status": "NOT_STARTED"
            },
            {
              "endTime": null,
              "id": "3",
              "implementingClass": "com.netflix.spinnaker.orca.igor.tasks.MonitorJenkinsJobTask",
              "loopEnd": false,
              "loopStart": false,
              "name": "monitorJenkinsJob",
              "stageEnd": false,
              "stageStart": false,
              "startTime": null,
              "status": "NOT_STARTED"
            },
            {
              "endTime": null,
              "id": "4",
              "implementingClass": "com.netflix.spinnaker.orca.igor.tasks.GetBuildPropertiesTask",
              "loopEnd": false,
              "loopStart": false,
              "name": "getBuildProperties",
              "stageEnd": false,
              "stageStart": false,
              "startTime": null,
              "status": "NOT_STARTED"
            },
            {
              "endTime": null,
              "id": "5",
              "implementingClass": "com.netflix.spinnaker.orca.igor.tasks.GetBuildArtifactsTask",
              "loopEnd": false,
              "loopStart": false,
              "name": "getBuildArtifacts",
              "stageEnd": true,
              "stageStart": false,
              "startTime": null,
              "status": "NOT_STARTED"
            }
          ],
          "type": "jenkins"
        },
        {
          "context": {
            "action": "suspend",
            "cloudProvider": "aws",
            "cluster": "test",
            "credentials": "staging",
            "processes": [],
            "regions": [
              "us-east-2"
            ],
            "target": "current_asg_dynamic"
          },
          "endTime": null,
          "id": "01F5KC5AFRWAY7V0E7H2YQ6N87",
          "lastModified": null,
          "name": "determineTargetServerGroup",
          "outputs": {},
          "parentStageId": "01F5KC59VXWZ12ZWT3J2F4FQ4V",
          "refId": "29<1",
          "requisiteStageRefIds": [],
          "scheduledTime": null,
          "startTime": 1620926704606,
          "startTimeExpiry": null,
          "status": "RUNNING",
          "syntheticStageOwner": "STAGE_BEFORE",
          "tasks": [
            {
              "endTime": null,
              "id": "1",
              "implementingClass": "com.netflix.spinnaker.orca.clouddriver.tasks.servergroup.support.DetermineTargetServerGroupTask",
              "loopEnd": false,
              "loopStart": false,
              "name": "determineTargetServerGroup",
              "stageEnd": true,
              "stageStart": true,
              "startTime": null,
              "status": "NOT_STARTED"
            }
          ],
          "type": "determineTargetServerGroup"
        },
        {
          "context": {
            "action": "suspend",
            "cloudProvider": "aws",
            "cluster": "test",
            "credentials": "staging",
            "processes": [],
            "region": "us-east-2",
            "target": "current_asg_dynamic",
            "targetLocation": {
              "type": "REGION",
              "value": "us-east-2"
            }
          },
          "endTime": null,
          "id": "01F5KC5AH42HXDTZS8YDQ0JAD7",
          "lastModified": null,
          "name": "modifyAwsScalingProcess",
          "outputs": {},
          "parentStageId": "01F5KC59VXWZ12ZWT3J2F4FQ4V",
          "refId": "29<2",
          "requisiteStageRefIds": [
            "29<1"
          ],
          "scheduledTime": null,
          "startTime": null,
          "startTimeExpiry": null,
          "status": "NOT_STARTED",
          "syntheticStageOwner": "STAGE_BEFORE",
          "tasks": [],
          "type": "modifyAwsScalingProcess"
        },
        {
          "context": {
            "action": "suspend",
            "cloudProvider": "aws",
            "cluster": "test",
            "credentials": "staging",
            "processes": [],
            "target": "current_asg_dynamic"
          },
          "endTime": null,
          "id": "01F5KC59VXWZ12ZWT3J2F4FQ4V",
          "lastModified": null,
          "name": "Modify Scaling Process",
          "outputs": {},
          "parentStageId": null,
          "refId": "29",
          "requisiteStageRefIds": [],
          "scheduledTime": null,
          "startTime": 1620926703815,
          "startTimeExpiry": null,
          "status": "RUNNING",
          "syntheticStageOwner": null,
          "tasks": [],
          "type": "modifyAwsScalingProcess"
        },
        {
          "context": {
            "account": "spinnaker",
            "app": "test",
            "cloudProvider": "kubernetes",
            "location": "staging",
            "manifestName": "deployment hostname",
            "mode": "static",
            "options": {
              "mergeStrategy": "strategic",
              "record": true
            },
            "patchBody": [
              {
                "apiVersion": "apps/v1",
                "kind": "Deployment",
                "metadata": {
                  "name": "hostname",
                  "namespace": "staging"
                },
                "spec": {
                  "replicas": "1",
                  "selector": {
                    "matchLabels": {
                      "app": "hostname",
                      "version": "v1"
                    }
                  },
                  "strategy": {
                    "rollingUpdate": {
                      "maxSurge": 1,
                      "maxUnavailable": 1
                    },
                    "type": "RollingUpdate"
                  },
                  "template": {
                    "metadata": {
                      "annotations": {
                        "prometheus.io/port": "9113",
                        "prometheus.io/scrape": "true"
                      },
                      "labels": {
                        "app": "hostname",
                        "version": "v1"
                      }
                    },
                    "spec": {
                      "containers": [
                        {
                          "image": "rstarmer/hostname:v1",
                          "imagePullPolicy": "Always",
                          "name": "hostname",
                          "resources": {},
                          "volumeMounts": [
                            {
                              "mountPath": "/etc/nginx/conf.d/nginx-status.conf",
                              "name": "nginx-status-conf",
                              "readOnly": true,
                              "subPath": "nginx.status.conf"
                            }
                          ]
                        },
                        {
                          "args": [
                            "-nginx.scrape-uri=http://localhost:8090/nginx_status"
                          ],
                          "image": "nginx/nginx-prometheus-exporter:0.3.0",
                          "imagePullPolicy": "Always",
                          "name": "nginx-exporter",
                          "ports": [
                            {
                              "containerPort": 9113,
                              "name": "nginx-ex-port",
                              "protocol": "TCP"
                            }
                          ]
                        }
                      ],
                      "restartPolicy": "Always",
                      "volumes": [
                        {
                          "configMap": {
                            "defaultMode": 420,
                            "name": "nginx-status-conf"
                          },
                          "name": "nginx-status-conf"
                        }
                      ]
                    }
                  }
                }
              }
            ],
            "source": "text"
          },
          "endTime": null,
          "id": "01F5KC59VXC778CNV0X6TKP9A6",
          "lastModified": null,
          "name": "Patch (Manifest)",
          "outputs": {},
          "parentStageId": null,
          "refId": "30",
          "requisiteStageRefIds": [],
          "scheduledTime": null,
          "startTime": 1620926703872,
          "startTimeExpiry": null,
          "status": "RUNNING",
          "syntheticStageOwner": null,
          "tasks": [
            {
              "endTime": null,
              "id": "1",
              "implementingClass": "com.netflix.spinnaker.orca.clouddriver.tasks.manifest.ResolveTargetManifestTask",
              "loopEnd": false,
              "loopStart": false,
              "name": "resolveTargetManifest",
              "stageEnd": false,
              "stageStart": true,
              "startTime": 1620926704220,
              "status": "RUNNING"
            },
            {
              "endTime": null,
              "id": "2",
              "implementingClass": "com.netflix.spinnaker.orca.clouddriver.tasks.manifest.ResolvePatchSourceManifestTask",
              "loopEnd": false,
              "loopStart": false,
              "name": "resolvePatchSourceManifest",
              "stageEnd": false,
              "stageStart": false,
              "startTime": null,
              "status": "NOT_STARTED"
            },
            {
              "endTime": null,
              "id": "3",
              "implementingClass": "com.netflix.spinnaker.orca.clouddriver.tasks.manifest.PatchManifestTask",
              "loopEnd": false,
              "loopStart": false,
              "name": "patchManifest",
              "stageEnd": false,
              "stageStart": false,
              "startTime": null,
              "status": "NOT_STARTED"
            },
            {
              "endTime": null,
              "id": "4",
              "implementingClass": "com.netflix.spinnaker.orca.clouddriver.tasks.MonitorKatoTask",
              "loopEnd": false,
              "loopStart": false,
              "name": "monitorPatch",
              "stageEnd": false,
              "stageStart": false,
              "startTime": null,
              "status": "NOT_STARTED"
            },
            {
              "endTime": null,
              "id": "5",
              "implementingClass": "com.netflix.spinnaker.orca.clouddriver.tasks.manifest.PromoteManifestKatoOutputsTask",
              "loopEnd": false,
              "loopStart": false,
              "name": "promoteOutputs",
              "stageEnd": false,
              "stageStart": false,
              "startTime": null,
              "status": "NOT_STARTED"
            },
            {
              "endTime": null,
              "id": "6",
              "implementingClass": "com.netflix.spinnaker.orca.clouddriver.tasks.manifest.WaitForManifestStableTask",
              "loopEnd": false,
              "loopStart": false,
              "name": "waitForManifestToStabilize",
              "stageEnd": false,
              "stageStart": false,
              "startTime": null,
              "status": "NOT_STARTED"
            },
            {
              "endTime": null,
              "id": "7",
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
          "type": "patchManifest"
        },
        {
          "context": {
            "application": "test",
            "failPipeline": true,
            "pipeline": "da91948b-b4a6-4483-88ef-e25bc69f83a9",
            "waitForCompletion": true
          },
          "endTime": null,
          "id": "01F5KC59VXCAGPGW4W0KPA3W18",
          "lastModified": null,
          "name": "Pipeline",
          "outputs": {},
          "parentStageId": null,
          "refId": "31",
          "requisiteStageRefIds": [],
          "scheduledTime": null,
          "startTime": 1620926703872,
          "startTimeExpiry": null,
          "status": "RUNNING",
          "syntheticStageOwner": null,
          "tasks": [
            {
              "endTime": null,
              "id": "1",
              "implementingClass": "com.netflix.spinnaker.orca.front50.tasks.StartPipelineTask",
              "loopEnd": false,
              "loopStart": false,
              "name": "startPipeline",
              "stageEnd": false,
              "stageStart": true,
              "startTime": 1620926704268,
              "status": "RUNNING"
            },
            {
              "endTime": null,
              "id": "2",
              "implementingClass": "com.netflix.spinnaker.orca.front50.tasks.MonitorPipelineTask",
              "loopEnd": false,
              "loopStart": false,
              "name": "monitorPipeline",
              "stageEnd": true,
              "stageStart": false,
              "startTime": null,
              "status": "NOT_STARTED"
            }
          ],
          "type": "pipeline"
        },
        {
          "context": {
            "action": "scale_up",
            "beforeStagePlanningFailed": true,
            "capacity": {},
            "cloudProvider": "aws",
            "cloudProviderType": "aws",
            "credentials": "staging",
            "exception": {
              "details": {
                "error": "Unexpected Task Failure",
                "errors": [
                  "Cannot invoke method singularType() on null object"
                ],
                "stackTrace": "java.lang.NullPointerException: Cannot invoke method singularType() on null object\n\tat org.codehaus.groovy.runtime.NullObject.invokeMethod(NullObject.java:91)\n\tat org.codehaus.groovy.runtime.callsite.PogoMetaClassSite.call(PogoMetaClassSite.java:43)\n\tat org.codehaus.groovy.runtime.callsite.CallSiteArray.defaultCall(CallSiteArray.java:47)\n\tat org.codehaus.groovy.runtime.callsite.NullCallSite.call(NullCallSite.java:34)\n\tat org.codehaus.groovy.runtime.callsite.CallSiteArray.defaultCall(CallSiteArray.java:47)\n\tat org.codehaus.groovy.runtime.callsite.AbstractCallSite.call(AbstractCallSite.java:115)\n\tat org.codehaus.groovy.runtime.callsite.AbstractCallSite.call(AbstractCallSite.java:119)\n\tat com.netflix.spinnaker.orca.clouddriver.pipeline.servergroup.support.TargetServerGroupLinearStageSupport.composeDynamicTargets(TargetServerGroupLinearStageSupport.groovy:176)\n\tat java.base/jdk.internal.reflect.NativeMethodAccessorImpl.invoke0(Native Method)\n\tat java.base/jdk.internal.reflect.NativeMethodAccessorImpl.invoke(NativeMethodAccessorImpl.java:62)\n\tat java.base/jdk.internal.reflect.DelegatingMethodAccessorImpl.invoke(DelegatingMethodAccessorImpl.java:43)\n\tat java.base/java.lang.reflect.Method.invoke(Method.java:566)\n\tat org.codehaus.groovy.runtime.callsite.PlainObjectMetaMethodSite.doInvoke(PlainObjectMetaMethodSite.java:43)\n\tat org.codehaus.groovy.runtime.callsite.PogoMetaMethodSite$PogoCachedMethodSiteNoUnwrapNoCoerce.invoke(PogoMetaMethodSite.java:190)\n\tat org.codehaus.groovy.runtime.callsite.PogoMetaMethodSite.callCurrent(PogoMetaMethodSite.java:58)\n\tat org.codehaus.groovy.runtime.callsite.CallSiteArray.defaultCallCurrent(CallSiteArray.java:51)\n\tat org.codehaus.groovy.runtime.callsite.PogoMetaMethodSite.callCurrent(PogoMetaMethodSite.java:63)\n\tat org.codehaus.groovy.runtime.callsite.AbstractCallSite.callCurrent(AbstractCallSite.java:184)\n\tat com.netflix.spinnaker.orca.clouddriver.pipeline.servergroup.support.TargetServerGroupLinearStageSupport.composeTargets(TargetServerGroupLinearStageSupport.groovy:144)\n\tat com.netflix.spinnaker.orca.clouddriver.pipeline.servergroup.support.TargetServerGroupLinearStageSupport$composeTargets.callCurrent(Unknown Source)\n\tat org.codehaus.groovy.runtime.callsite.CallSiteArray.defaultCallCurrent(CallSiteArray.java:51)\n\tat com.netflix.spinnaker.orca.clouddriver.pipeline.servergroup.support.TargetServerGroupLinearStageSupport$composeTargets.callCurrent(Unknown Source)\n\tat com.netflix.spinnaker.orca.clouddriver.pipeline.servergroup.support.TargetServerGroupLinearStageSupport.beforeStages(TargetServerGroupLinearStageSupport.groovy:110)\n\tat com.netflix.spinnaker.orca.q.StageDefinitionBuildersKt.buildBeforeStages(StageDefinitionBuilders.kt:103)\n\tat com.netflix.spinnaker.orca.q.handler.StartStageHandler.plan(StartStageHandler.kt:174)\n\tat com.netflix.spinnaker.orca.q.handler.StartStageHandler.access$plan(StartStageHandler.kt:61)\n\tat com.netflix.spinnaker.orca.q.handler.StartStageHandler$handle$1$1.invoke(StartStageHandler.kt:99)\n\tat com.netflix.spinnaker.orca.q.handler.StartStageHandler$handle$1$1.invoke(StartStageHandler.kt:61)\n\tat com.netflix.spinnaker.orca.q.handler.AuthenticationAware$sam$java_util_concurrent_Callable$0.call(AuthenticationAware.kt)\n\tat com.netflix.spinnaker.security.AuthenticatedRequest.lambda$wrapCallableForPrincipal$0(AuthenticatedRequest.java:272)\n\tat com.netflix.spinnaker.orca.q.handler.AuthenticationAware$DefaultImpls.withAuth(AuthenticationAware.kt:51)\n\tat com.netflix.spinnaker.orca.q.handler.StartStageHandler.withAuth(StartStageHandler.kt:61)\n\tat com.netflix.spinnaker.orca.q.handler.StartStageHandler$handle$1.invoke(StartStageHandler.kt:81)\n\tat com.netflix.spinnaker.orca.q.handler.StartStageHandler$handle$1.invoke(StartStageHandler.kt:61)\n\tat com.netflix.spinnaker.orca.q.handler.OrcaMessageHandler$withStage$1.invoke(OrcaMessageHandler.kt:85)\n\tat com.netflix.spinnaker.orca.q.handler.OrcaMessageHandler$withStage$1.invoke(OrcaMessageHandler.kt:46)\n\tat com.netflix.spinnaker.orca.q.handler.OrcaMessageHandler$DefaultImpls.withExecution(OrcaMessageHandler.kt:95)\n\tat com.netflix.spinnaker.orca.q.handler.StartStageHandler.withExecution(StartStageHandler.kt:61)\n\tat com.netflix.spinnaker.orca.q.handler.OrcaMessageHandler$DefaultImpls.withStage(OrcaMessageHandler.kt:74)\n\tat com.netflix.spinnaker.orca.q.handler.StartStageHandler.withStage(StartStageHandler.kt:61)\n\tat com.netflix.spinnaker.orca.q.handler.StartStageHandler.handle(StartStageHandler.kt:79)\n\tat com.netflix.spinnaker.orca.q.handler.StartStageHandler.handle(StartStageHandler.kt:61)\n\tat com.netflix.spinnaker.q.MessageHandler$DefaultImpls.invoke(MessageHandler.kt:36)\n\tat com.netflix.spinnaker.orca.q.handler.OrcaMessageHandler$DefaultImpls.invoke(OrcaMessageHandler.kt)\n\tat com.netflix.spinnaker.orca.q.handler.StartStageHandler.invoke(StartStageHandler.kt:61)\n\tat com.netflix.spinnaker.orca.q.audit.ExecutionTrackingMessageHandlerPostProcessor$ExecutionTrackingMessageHandlerProxy.invoke(ExecutionTrackingMessageHandlerPostProcessor.kt:72)\n\tat com.netflix.spinnaker.q.QueueProcessor$callback$1$1.run(QueueProcessor.kt:90)\n\tat java.base/java.util.concurrent.ThreadPoolExecutor.runWorker(ThreadPoolExecutor.java:1128)\n\tat java.base/java.util.concurrent.ThreadPoolExecutor$Worker.run(ThreadPoolExecutor.java:628)\n\tat java.base/java.lang.Thread.run(Thread.java:834)\n"
              },
              "exceptionType": "NullPointerException",
              "operation": "Resize Server Group",
              "shouldRetry": false,
              "timestamp": 1620926704112
            },
            "resizeType": "pct",
            "target": "current_asg_dynamic",
            "targetHealthyDeployPercentage": 100
          },
          "endTime": 1620926704426,
          "id": "01F5KC59VXJWHXYA30AFABEW9W",
          "lastModified": null,
          "name": "Resize Server Group",
          "outputs": {},
          "parentStageId": null,
          "refId": "32",
          "requisiteStageRefIds": [],
          "scheduledTime": null,
          "startTime": 1620926703885,
          "startTimeExpiry": null,
          "status": "TERMINAL",
          "syntheticStageOwner": null,
          "tasks": [],
          "type": "resizeServerGroup"
        },
        {
          "context": {
            "cloudProvider": "aws",
            "cloudProviderType": "aws",
            "credentials": "staging",
            "regions": [
              "us-east-2"
            ],
            "targetHealthyRollbackPercentage": 100
          },
          "endTime": null,
          "id": "01F5KC59VXNYZJ0640BVZXQ46N",
          "lastModified": null,
          "name": "Rollback Cluster",
          "outputs": {},
          "parentStageId": null,
          "refId": "33",
          "requisiteStageRefIds": [],
          "scheduledTime": null,
          "startTime": 1620926703883,
          "startTimeExpiry": null,
          "status": "RUNNING",
          "syntheticStageOwner": null,
          "tasks": [
            {
              "endTime": null,
              "id": "1",
              "implementingClass": "com.netflix.spinnaker.orca.clouddriver.tasks.cluster.DetermineRollbackCandidatesTask",
              "loopEnd": false,
              "loopStart": false,
              "name": "determineRollbackCandidates",
              "stageEnd": true,
              "stageStart": true,
              "startTime": 1620926704276,
              "status": "RUNNING"
            }
          ],
          "type": "rollbackCluster"
        },
        {
          "context": {
            "account": "spinnaker",
            "alias": "runJob",
            "application": "test",
            "cloudProvider": "kubernetes",
            "credentials": "spinnaker",
            "manifestArtifactId": "05ad020e-73a6-49f2-9988-2073831219e9",
            "source": "artifact"
          },
          "endTime": null,
          "id": "01F5KC59VX0JK21YEGDWX8310Z",
          "lastModified": null,
          "name": "Run Job (Manifest)",
          "outputs": {},
          "parentStageId": null,
          "refId": "34",
          "requisiteStageRefIds": [],
          "scheduledTime": null,
          "startTime": 1620926703889,
          "startTimeExpiry": null,
          "status": "RUNNING",
          "syntheticStageOwner": null,
          "tasks": [
            {
              "endTime": null,
              "id": "1",
              "implementingClass": "com.netflix.spinnaker.orca.clouddriver.tasks.job.RunJobTask",
              "loopEnd": false,
              "loopStart": false,
              "name": "runJob",
              "stageEnd": false,
              "stageStart": true,
              "startTime": 1620926704288,
              "status": "RUNNING"
            },
            {
              "endTime": null,
              "id": "2",
              "implementingClass": "com.netflix.spinnaker.orca.clouddriver.tasks.job.MonitorJobTask",
              "loopEnd": false,
              "loopStart": false,
              "name": "monitorDeploy",
              "stageEnd": false,
              "stageStart": false,
              "startTime": null,
              "status": "NOT_STARTED"
            },
            {
              "endTime": null,
              "id": "3",
              "implementingClass": "com.netflix.spinnaker.orca.clouddriver.tasks.manifest.PromoteManifestKatoOutputsTask",
              "loopEnd": false,
              "loopStart": false,
              "name": "promoteOutputs",
              "stageEnd": false,
              "stageStart": false,
              "startTime": null,
              "status": "NOT_STARTED"
            },
            {
              "endTime": null,
              "id": "4",
              "implementingClass": "com.netflix.spinnaker.orca.clouddriver.tasks.job.WaitOnJobCompletion",
              "loopEnd": false,
              "loopStart": false,
              "name": "waitOnJobCompletion",
              "stageEnd": true,
              "stageStart": false,
              "startTime": null,
              "status": "NOT_STARTED"
            }
          ],
          "type": "runJobManifest"
        },
        {
          "context": {
            "pipelinesArtifactId": "05ad020e-73a6-49f2-9988-2073831219e9"
          },
          "endTime": null,
          "id": "01F5KC59VXEB15WXN5VSW8H8H8",
          "lastModified": null,
          "name": "Save Pipelines",
          "outputs": {},
          "parentStageId": null,
          "refId": "35",
          "requisiteStageRefIds": [],
          "scheduledTime": null,
          "startTime": 1620926703891,
          "startTimeExpiry": null,
          "status": "RUNNING",
          "syntheticStageOwner": null,
          "tasks": [
            {
              "endTime": null,
              "id": "1",
              "implementingClass": "com.netflix.spinnaker.orca.clouddriver.tasks.pipeline.GetPipelinesFromArtifactTask",
              "loopEnd": false,
              "loopStart": false,
              "name": "getPipelinesFromArtifact",
              "stageEnd": false,
              "stageStart": true,
              "startTime": 1620926704288,
              "status": "RUNNING"
            },
            {
              "endTime": null,
              "id": "2",
              "implementingClass": "com.netflix.spinnaker.orca.clouddriver.tasks.pipeline.PreparePipelineToSaveTask",
              "loopEnd": false,
              "loopStart": true,
              "name": "preparePipelineToSaveTask",
              "stageEnd": false,
              "stageStart": false,
              "startTime": null,
              "status": "NOT_STARTED"
            },
            {
              "endTime": null,
              "id": "3",
              "implementingClass": "com.netflix.spinnaker.orca.front50.tasks.SavePipelineTask",
              "loopEnd": false,
              "loopStart": false,
              "name": "savePipeline",
              "stageEnd": false,
              "stageStart": false,
              "startTime": null,
              "status": "NOT_STARTED"
            },
            {
              "endTime": null,
              "id": "4",
              "implementingClass": "com.netflix.spinnaker.orca.front50.tasks.MonitorFront50Task",
              "loopEnd": false,
              "loopStart": false,
              "name": "waitForPipelineSave",
              "stageEnd": false,
              "stageStart": false,
              "startTime": null,
              "status": "NOT_STARTED"
            },
            {
              "endTime": null,
              "id": "5",
              "implementingClass": "com.netflix.spinnaker.orca.clouddriver.tasks.pipeline.CheckPipelineResultsTask",
              "loopEnd": false,
              "loopStart": false,
              "name": "checkPipelineResults",
              "stageEnd": false,
              "stageStart": false,
              "startTime": null,
              "status": "NOT_STARTED"
            },
            {
              "endTime": null,
              "id": "6",
              "implementingClass": "com.netflix.spinnaker.orca.clouddriver.tasks.pipeline.CheckForRemainingPipelinesTask",
              "loopEnd": true,
              "loopStart": false,
              "name": "checkForRemainingPipelines",
              "stageEnd": false,
              "stageStart": false,
              "startTime": null,
              "status": "NOT_STARTED"
            },
            {
              "endTime": null,
              "id": "7",
              "implementingClass": "com.netflix.spinnaker.orca.clouddriver.tasks.pipeline.SavePipelinesCompleteTask",
              "loopEnd": false,
              "loopStart": false,
              "name": "savePipelinesCompleteTask",
              "stageEnd": true,
              "stageStart": false,
              "startTime": null,
              "status": "NOT_STARTED"
            }
          ],
          "type": "savePipelinesFromArtifact"
        },
        {
          "context": {
            "allowScaleDownActive": false,
            "cloudProvider": "aws",
            "cloudProviderType": "aws",
            "cluster": "TEST",
            "credentials": "staging",
            "preferLargerOverNewer": "false",
            "regions": [
              "us-east-2"
            ],
            "remainingFullSizeServerGroups": 1
          },
          "endTime": null,
          "id": "01F5KC59VX4WM95WVQG3P8FPGK",
          "lastModified": null,
          "name": "Scale Down Cluster",
          "outputs": {},
          "parentStageId": null,
          "refId": "36",
          "requisiteStageRefIds": [],
          "scheduledTime": null,
          "startTime": 1620926703895,
          "startTimeExpiry": null,
          "status": "RUNNING",
          "syntheticStageOwner": null,
          "tasks": [
            {
              "endTime": null,
              "id": "1",
              "implementingClass": "com.netflix.spinnaker.orca.clouddriver.tasks.DetermineHealthProvidersTask",
              "loopEnd": false,
              "loopStart": false,
              "name": "determineHealthProviders",
              "stageEnd": false,
              "stageStart": true,
              "startTime": 1620926704294,
              "status": "RUNNING"
            },
            {
              "endTime": null,
              "id": "2",
              "implementingClass": "com.netflix.spinnaker.orca.clouddriver.tasks.cluster.ScaleDownClusterTask",
              "loopEnd": false,
              "loopStart": false,
              "name": "scaleDownCluster",
              "stageEnd": false,
              "stageStart": false,
              "startTime": null,
              "status": "NOT_STARTED"
            },
            {
              "endTime": null,
              "id": "3",
              "implementingClass": "com.netflix.spinnaker.orca.clouddriver.tasks.MonitorKatoTask",
              "loopEnd": false,
              "loopStart": false,
              "name": "monitorScaleDownCluster",
              "stageEnd": false,
              "stageStart": false,
              "startTime": null,
              "status": "NOT_STARTED"
            },
            {
              "endTime": null,
              "id": "4",
              "implementingClass": "com.netflix.spinnaker.orca.clouddriver.tasks.servergroup.ServerGroupCacheForceRefreshTask",
              "loopEnd": false,
              "loopStart": false,
              "name": "forceCacheRefresh",
              "stageEnd": false,
              "stageStart": false,
              "startTime": null,
              "status": "NOT_STARTED"
            },
            {
              "endTime": null,
              "id": "5",
              "implementingClass": "com.netflix.spinnaker.orca.clouddriver.tasks.cluster.WaitForScaleDownClusterTask",
              "loopEnd": false,
              "loopStart": false,
              "name": "waitForScaleDownCluster",
              "stageEnd": false,
              "stageStart": false,
              "startTime": null,
              "status": "NOT_STARTED"
            },
            {
              "endTime": null,
              "id": "6",
              "implementingClass": "com.netflix.spinnaker.orca.clouddriver.tasks.servergroup.ServerGroupCacheForceRefreshTask",
              "loopEnd": false,
              "loopStart": false,
              "name": "forceCacheRefresh",
              "stageEnd": true,
              "stageStart": false,
              "startTime": null,
              "status": "NOT_STARTED"
            }
          ],
          "type": "scaleDownCluster"
        },
        {
          "context": {
            "failPipeline": true,
            "user": "myUserName",
            "waitForCompletion": true
          },
          "endTime": null,
          "id": "01F5KC59VXM9SH65YQVYSPYQ07",
          "lastModified": null,
          "name": "Script",
          "outputs": {},
          "parentStageId": null,
          "refId": "37",
          "requisiteStageRefIds": [],
          "scheduledTime": null,
          "startTime": 1620926703903,
          "startTimeExpiry": null,
          "status": "RUNNING",
          "syntheticStageOwner": null,
          "tasks": [
            {
              "endTime": null,
              "id": "1",
              "implementingClass": "com.netflix.spinnaker.orca.igor.tasks.StartScriptTask",
              "loopEnd": false,
              "loopStart": false,
              "name": "startScript",
              "stageEnd": false,
              "stageStart": true,
              "startTime": 1620926704279,
              "status": "RUNNING"
            },
            {
              "endTime": null,
              "id": "2",
              "implementingClass": "com.netflix.spinnaker.orca.igor.tasks.MonitorQueuedJenkinsJobTask",
              "loopEnd": false,
              "loopStart": false,
              "name": "waitForScriptStart",
              "stageEnd": false,
              "stageStart": false,
              "startTime": null,
              "status": "NOT_STARTED"
            },
            {
              "endTime": null,
              "id": "3",
              "implementingClass": "com.netflix.spinnaker.orca.igor.tasks.MonitorJenkinsJobTask",
              "loopEnd": false,
              "loopStart": false,
              "name": "monitorScript",
              "stageEnd": false,
              "stageStart": false,
              "startTime": null,
              "status": "NOT_STARTED"
            },
            {
              "endTime": null,
              "id": "4",
              "implementingClass": "com.netflix.spinnaker.orca.igor.tasks.GetBuildPropertiesTask",
              "loopEnd": false,
              "loopStart": false,
              "name": "getBuildProperties",
              "stageEnd": true,
              "stageStart": false,
              "startTime": null,
              "status": "NOT_STARTED"
            }
          ],
          "type": "script"
        },
        {
          "context": {
            "allowDeleteActive": false,
            "cloudProvider": "aws",
            "cloudProviderType": "aws",
            "cluster": "TEST",
            "credentials": "staging",
            "regions": [
              "us-east-2"
            ],
            "retainLargerOverNewer": "false",
            "shrinkToSize": 1
          },
          "endTime": null,
          "id": "01F5KC59VX9V47GNGF65Z1TSG3",
          "lastModified": null,
          "name": "Shrink Cluster",
          "outputs": {},
          "parentStageId": null,
          "refId": "38",
          "requisiteStageRefIds": [],
          "scheduledTime": null,
          "startTime": 1620926704032,
          "startTimeExpiry": null,
          "status": "RUNNING",
          "syntheticStageOwner": null,
          "tasks": [
            {
              "endTime": null,
              "id": "1",
              "implementingClass": "com.netflix.spinnaker.orca.clouddriver.tasks.DetermineHealthProvidersTask",
              "loopEnd": false,
              "loopStart": false,
              "name": "determineHealthProviders",
              "stageEnd": false,
              "stageStart": true,
              "startTime": 1620926704384,
              "status": "RUNNING"
            },
            {
              "endTime": null,
              "id": "2",
              "implementingClass": "com.netflix.spinnaker.orca.clouddriver.tasks.cluster.ShrinkClusterTask",
              "loopEnd": false,
              "loopStart": false,
              "name": "shrinkCluster",
              "stageEnd": false,
              "stageStart": false,
              "startTime": null,
              "status": "NOT_STARTED"
            },
            {
              "endTime": null,
              "id": "3",
              "implementingClass": "com.netflix.spinnaker.orca.clouddriver.tasks.MonitorKatoTask",
              "loopEnd": false,
              "loopStart": false,
              "name": "monitorShrinkCluster",
              "stageEnd": false,
              "stageStart": false,
              "startTime": null,
              "status": "NOT_STARTED"
            },
            {
              "endTime": null,
              "id": "4",
              "implementingClass": "com.netflix.spinnaker.orca.clouddriver.tasks.servergroup.ServerGroupCacheForceRefreshTask",
              "loopEnd": false,
              "loopStart": false,
              "name": "forceCacheRefresh",
              "stageEnd": false,
              "stageStart": false,
              "startTime": null,
              "status": "NOT_STARTED"
            },
            {
              "endTime": null,
              "id": "5",
              "implementingClass": "com.netflix.spinnaker.orca.clouddriver.tasks.cluster.WaitForClusterShrinkTask",
              "loopEnd": false,
              "loopStart": false,
              "name": "waitForClusterShrink",
              "stageEnd": false,
              "stageStart": false,
              "startTime": null,
              "status": "NOT_STARTED"
            },
            {
              "endTime": null,
              "id": "6",
              "implementingClass": "com.netflix.spinnaker.orca.clouddriver.tasks.servergroup.ServerGroupCacheForceRefreshTask",
              "loopEnd": false,
              "loopStart": false,
              "name": "forceCacheRefresh",
              "stageEnd": true,
              "stageStart": false,
              "startTime": null,
              "status": "NOT_STARTED"
            }
          ],
          "type": "shrinkCluster"
        },
        {
          "context": {
            "cloudProvider": "aws",
            "cloudProviderType": "aws",
            "consideredStages": [],
            "exception": {
              "details": {
                "error": "Unexpected Task Failure",
                "errors": [
                  "Unable to determine source image(s)"
                ],
                "stackTrace": "java.lang.IllegalStateException: Unable to determine source image(s)\n\tat com.netflix.spinnaker.orca.clouddriver.tasks.image.ImageTagger.findImages(ImageTagger.java:80)\n\tat com.netflix.spinnaker.orca.clouddriver.tasks.providers.aws.AmazonImageTagger.getOperationContext(AmazonImageTagger.java:62)\n\tat com.netflix.spinnaker.orca.clouddriver.tasks.image.UpsertImageTagsTask.execute(UpsertImageTagsTask.java:65)\n\tat com.netflix.spinnaker.orca.q.handler.RunTaskHandler$handle$1$1$1.invoke(RunTaskHandler.kt:144)\n\tat com.netflix.spinnaker.orca.q.handler.RunTaskHandler$handle$1$1$1.invoke(RunTaskHandler.kt:75)\n\tat com.netflix.spinnaker.orca.q.handler.RunTaskHandler.withLoggingContext(RunTaskHandler.kt:419)\n\tat com.netflix.spinnaker.orca.q.handler.RunTaskHandler.access$withLoggingContext(RunTaskHandler.kt:75)\n\tat com.netflix.spinnaker.orca.q.handler.RunTaskHandler$handle$1$1.invoke(RunTaskHandler.kt:105)\n\tat com.netflix.spinnaker.orca.q.handler.RunTaskHandler$handle$1$1.invoke(RunTaskHandler.kt:75)\n\tat com.netflix.spinnaker.orca.q.handler.AuthenticationAware$sam$java_util_concurrent_Callable$0.call(AuthenticationAware.kt)\n\tat com.netflix.spinnaker.security.AuthenticatedRequest.lambda$wrapCallableForPrincipal$0(AuthenticatedRequest.java:272)\n\tat com.netflix.spinnaker.orca.q.handler.AuthenticationAware$DefaultImpls.withAuth(AuthenticationAware.kt:51)\n\tat com.netflix.spinnaker.orca.q.handler.RunTaskHandler.withAuth(RunTaskHandler.kt:75)\n\tat com.netflix.spinnaker.orca.q.handler.RunTaskHandler$handle$1.invoke(RunTaskHandler.kt:104)\n\tat com.netflix.spinnaker.orca.q.handler.RunTaskHandler$handle$1.invoke(RunTaskHandler.kt:75)\n\tat com.netflix.spinnaker.orca.q.handler.RunTaskHandler$withTask$1.invoke(RunTaskHandler.kt:247)\n\tat com.netflix.spinnaker.orca.q.handler.RunTaskHandler$withTask$1.invoke(RunTaskHandler.kt:75)\n\tat com.netflix.spinnaker.orca.q.handler.OrcaMessageHandler$withTask$1.invoke(OrcaMessageHandler.kt:68)\n\tat com.netflix.spinnaker.orca.q.handler.OrcaMessageHandler$withTask$1.invoke(OrcaMessageHandler.kt:46)\n\tat com.netflix.spinnaker.orca.q.handler.OrcaMessageHandler$withStage$1.invoke(OrcaMessageHandler.kt:85)\n\tat com.netflix.spinnaker.orca.q.handler.OrcaMessageHandler$withStage$1.invoke(OrcaMessageHandler.kt:46)\n\tat com.netflix.spinnaker.orca.q.handler.OrcaMessageHandler$DefaultImpls.withExecution(OrcaMessageHandler.kt:95)\n\tat com.netflix.spinnaker.orca.q.handler.RunTaskHandler.withExecution(RunTaskHandler.kt:75)\n\tat com.netflix.spinnaker.orca.q.handler.OrcaMessageHandler$DefaultImpls.withStage(OrcaMessageHandler.kt:74)\n\tat com.netflix.spinnaker.orca.q.handler.RunTaskHandler.withStage(RunTaskHandler.kt:75)\n\tat com.netflix.spinnaker.orca.q.handler.OrcaMessageHandler$DefaultImpls.withTask(OrcaMessageHandler.kt:60)\n\tat com.netflix.spinnaker.orca.q.handler.RunTaskHandler.withTask(RunTaskHandler.kt:75)\n\tat com.netflix.spinnaker.orca.q.handler.RunTaskHandler.withTask(RunTaskHandler.kt:236)\n\tat com.netflix.spinnaker.orca.q.handler.RunTaskHandler.handle(RunTaskHandler.kt:101)\n\tat com.netflix.spinnaker.orca.q.handler.RunTaskHandler.handle(RunTaskHandler.kt:75)\n\tat com.netflix.spinnaker.q.MessageHandler$DefaultImpls.invoke(MessageHandler.kt:36)\n\tat com.netflix.spinnaker.orca.q.handler.OrcaMessageHandler$DefaultImpls.invoke(OrcaMessageHandler.kt)\n\tat com.netflix.spinnaker.orca.q.handler.RunTaskHandler.invoke(RunTaskHandler.kt:75)\n\tat com.netflix.spinnaker.orca.q.audit.ExecutionTrackingMessageHandlerPostProcessor$ExecutionTrackingMessageHandlerProxy.invoke(ExecutionTrackingMessageHandlerPostProcessor.kt:72)\n\tat com.netflix.spinnaker.q.QueueProcessor$callback$1$1.run(QueueProcessor.kt:90)\n\tat java.base/java.util.concurrent.ThreadPoolExecutor.runWorker(ThreadPoolExecutor.java:1128)\n\tat java.base/java.util.concurrent.ThreadPoolExecutor$Worker.run(ThreadPoolExecutor.java:628)\n\tat java.base/java.lang.Thread.run(Thread.java:834)\n"
              },
              "exceptionType": "IllegalStateException",
              "operation": "upsertImageTags",
              "shouldRetry": false,
              "timestamp": 1620926705284
            },
            "tags": {
              "TEST": "TEST"
            }
          },
          "endTime": null,
          "id": "01F5KC59VX7DERMTWGYZA30B5X",
          "lastModified": null,
          "name": "Tag Image",
          "outputs": {},
          "parentStageId": null,
          "refId": "39",
          "requisiteStageRefIds": [],
          "scheduledTime": null,
          "startTime": 1620926703980,
          "startTimeExpiry": null,
          "status": "RUNNING",
          "syntheticStageOwner": null,
          "tasks": [
            {
              "endTime": null,
              "id": "1",
              "implementingClass": "com.netflix.spinnaker.orca.clouddriver.tasks.image.UpsertImageTagsTask",
              "loopEnd": false,
              "loopStart": false,
              "name": "upsertImageTags",
              "stageEnd": false,
              "stageStart": true,
              "startTime": 1620926704310,
              "status": "RUNNING"
            },
            {
              "endTime": null,
              "id": "2",
              "implementingClass": "com.netflix.spinnaker.orca.clouddriver.tasks.MonitorKatoTask",
              "loopEnd": false,
              "loopStart": false,
              "name": "monitorUpsert",
              "stageEnd": false,
              "stageStart": false,
              "startTime": null,
              "status": "NOT_STARTED"
            },
            {
              "endTime": null,
              "id": "3",
              "implementingClass": "com.netflix.spinnaker.orca.clouddriver.tasks.image.ImageForceCacheRefreshTask",
              "loopEnd": false,
              "loopStart": false,
              "name": "forceCacheRefresh",
              "stageEnd": false,
              "stageStart": false,
              "startTime": null,
              "status": "NOT_STARTED"
            },
            {
              "endTime": null,
              "id": "4",
              "implementingClass": "com.netflix.spinnaker.orca.clouddriver.tasks.image.WaitForUpsertedImageTagsTask",
              "loopEnd": false,
              "loopStart": false,
              "name": "waitForTaggedImage",
              "stageEnd": true,
              "stageStart": false,
              "startTime": null,
              "status": "NOT_STARTED"
            }
          ],
          "type": "upsertImageTags"
        },
        {
          "context": {
            "beforeStagePlanningFailed": true,
            "continuePipeline": false,
            "exception": {
              "details": {
                "error": "Unexpected Task Failure",
                "errors": [],
                "stackTrace": "java.lang.NullPointerException\n\tat com.netflix.spinnaker.orca.igor.pipeline.TravisStage.taskGraph(TravisStage.java:36)\n\tat com.netflix.spinnaker.orca.api.pipeline.graph.StageDefinitionBuilder.buildTaskGraph(StageDefinitionBuilder.java:48)\n\tat com.netflix.spinnaker.orca.q.StageDefinitionBuildersKt.buildTasks(StageDefinitionBuilders.kt:41)\n\tat com.netflix.spinnaker.orca.q.handler.StartStageHandler.plan(StartStageHandler.kt:173)\n\tat com.netflix.spinnaker.orca.q.handler.StartStageHandler.access$plan(StartStageHandler.kt:61)\n\tat com.netflix.spinnaker.orca.q.handler.StartStageHandler$handle$1$1.invoke(StartStageHandler.kt:99)\n\tat com.netflix.spinnaker.orca.q.handler.StartStageHandler$handle$1$1.invoke(StartStageHandler.kt:61)\n\tat com.netflix.spinnaker.orca.q.handler.AuthenticationAware$sam$java_util_concurrent_Callable$0.call(AuthenticationAware.kt)\n\tat com.netflix.spinnaker.security.AuthenticatedRequest.lambda$wrapCallableForPrincipal$0(AuthenticatedRequest.java:272)\n\tat com.netflix.spinnaker.orca.q.handler.AuthenticationAware$DefaultImpls.withAuth(AuthenticationAware.kt:51)\n\tat com.netflix.spinnaker.orca.q.handler.StartStageHandler.withAuth(StartStageHandler.kt:61)\n\tat com.netflix.spinnaker.orca.q.handler.StartStageHandler$handle$1.invoke(StartStageHandler.kt:81)\n\tat com.netflix.spinnaker.orca.q.handler.StartStageHandler$handle$1.invoke(StartStageHandler.kt:61)\n\tat com.netflix.spinnaker.orca.q.handler.OrcaMessageHandler$withStage$1.invoke(OrcaMessageHandler.kt:85)\n\tat com.netflix.spinnaker.orca.q.handler.OrcaMessageHandler$withStage$1.invoke(OrcaMessageHandler.kt:46)\n\tat com.netflix.spinnaker.orca.q.handler.OrcaMessageHandler$DefaultImpls.withExecution(OrcaMessageHandler.kt:95)\n\tat com.netflix.spinnaker.orca.q.handler.StartStageHandler.withExecution(StartStageHandler.kt:61)\n\tat com.netflix.spinnaker.orca.q.handler.OrcaMessageHandler$DefaultImpls.withStage(OrcaMessageHandler.kt:74)\n\tat com.netflix.spinnaker.orca.q.handler.StartStageHandler.withStage(StartStageHandler.kt:61)\n\tat com.netflix.spinnaker.orca.q.handler.StartStageHandler.handle(StartStageHandler.kt:79)\n\tat com.netflix.spinnaker.orca.q.handler.StartStageHandler.handle(StartStageHandler.kt:61)\n\tat com.netflix.spinnaker.q.MessageHandler$DefaultImpls.invoke(MessageHandler.kt:36)\n\tat com.netflix.spinnaker.orca.q.handler.OrcaMessageHandler$DefaultImpls.invoke(OrcaMessageHandler.kt)\n\tat com.netflix.spinnaker.orca.q.handler.StartStageHandler.invoke(StartStageHandler.kt:61)\n\tat com.netflix.spinnaker.orca.q.audit.ExecutionTrackingMessageHandlerPostProcessor$ExecutionTrackingMessageHandlerProxy.invoke(ExecutionTrackingMessageHandlerPostProcessor.kt:72)\n\tat com.netflix.spinnaker.q.QueueProcessor$callback$1$1.run(QueueProcessor.kt:90)\n\tat java.base/java.util.concurrent.ThreadPoolExecutor.runWorker(ThreadPoolExecutor.java:1128)\n\tat java.base/java.util.concurrent.ThreadPoolExecutor$Worker.run(ThreadPoolExecutor.java:628)\n\tat java.base/java.lang.Thread.run(Thread.java:834)\n"
              },
              "exceptionType": "NullPointerException",
              "operation": "Travis",
              "shouldRetry": false,
              "timestamp": 1620926704081
            },
            "failPipeline": true
          },
          "endTime": 1620926704398,
          "id": "01F5KC59VXPMHB9QXG535QFZJG",
          "lastModified": null,
          "name": "Travis",
          "outputs": {},
          "parentStageId": null,
          "refId": "40",
          "requisiteStageRefIds": [],
          "scheduledTime": null,
          "startTime": 1620926704031,
          "startTimeExpiry": null,
          "status": "TERMINAL",
          "syntheticStageOwner": null,
          "tasks": [],
          "type": "travis"
        },
        {
          "context": {
            "account": "spinnaker",
            "cloudProvider": "kubernetes",
            "location": "staging",
            "manifestName": "deployment hostname",
            "mode": "static",
            "numRevisionsBack": 1
          },
          "endTime": null,
          "id": "01F5KC59VX9TE0A2AJ6XMJ8F4X",
          "lastModified": null,
          "name": "Undo Rollout (Manifest)",
          "outputs": {},
          "parentStageId": null,
          "refId": "41",
          "requisiteStageRefIds": [],
          "scheduledTime": null,
          "startTime": 1620926703984,
          "startTimeExpiry": null,
          "status": "RUNNING",
          "syntheticStageOwner": null,
          "tasks": [
            {
              "endTime": null,
              "id": "1",
              "implementingClass": "com.netflix.spinnaker.orca.clouddriver.tasks.manifest.UndoRolloutManifestTask",
              "loopEnd": false,
              "loopStart": false,
              "name": "undoRolloutManifest",
              "stageEnd": false,
              "stageStart": true,
              "startTime": 1620926704314,
              "status": "RUNNING"
            },
            {
              "endTime": null,
              "id": "2",
              "implementingClass": "com.netflix.spinnaker.orca.clouddriver.tasks.MonitorKatoTask",
              "loopEnd": false,
              "loopStart": false,
              "name": "monitorUndoRollout",
              "stageEnd": false,
              "stageStart": false,
              "startTime": null,
              "status": "NOT_STARTED"
            },
            {
              "endTime": null,
              "id": "3",
              "implementingClass": "com.netflix.spinnaker.orca.clouddriver.tasks.manifest.WaitForManifestStableTask",
              "loopEnd": false,
              "loopStart": false,
              "name": "waitForManifestToStabilize",
              "stageEnd": true,
              "stageStart": false,
              "startTime": null,
              "status": "NOT_STARTED"
            }
          ],
          "type": "undoRolloutManifest"
        },
        {
          "context": {
            "waitTime": 30
          },
          "endTime": null,
          "id": "01F5KC59VXSZJG27YDEWDA3X4N",
          "lastModified": null,
          "name": "Wait",
          "outputs": {},
          "parentStageId": null,
          "refId": "42",
          "requisiteStageRefIds": [],
          "scheduledTime": null,
          "startTime": 1620926704152,
          "startTimeExpiry": null,
          "status": "RUNNING",
          "syntheticStageOwner": null,
          "tasks": [
            {
              "endTime": null,
              "id": "1",
              "implementingClass": "com.netflix.spinnaker.orca.pipeline.tasks.WaitTask",
              "loopEnd": false,
              "loopStart": false,
              "name": "wait",
              "stageEnd": true,
              "stageStart": true,
              "startTime": 1620926704453,
              "status": "RUNNING"
            }
          ],
          "type": "wait"
        },
        "01F5KC59VXHMA91KG8XYQ7RRZK",
        {
          "context": {
            "continuePipeline": false,
            "failPipeline": true
          },
          "endTime": null,
          "id": "01F5KC59VXKBS6NWPNNTG1T1EH",
          "lastModified": null,
          "name": "Wercker",
          "outputs": {},
          "parentStageId": null,
          "refId": "44",
          "requisiteStageRefIds": [],
          "scheduledTime": null,
          "startTime": 1620926704161,
          "startTimeExpiry": null,
          "status": "RUNNING",
          "syntheticStageOwner": null,
          "tasks": [
            {
              "endTime": null,
              "id": "1",
              "implementingClass": "com.netflix.spinnaker.orca.igor.tasks.StartJenkinsJobTask",
              "loopEnd": false,
              "loopStart": false,
              "name": "startWerckerJob",
              "stageEnd": false,
              "stageStart": true,
              "startTime": 1620926704452,
              "status": "RUNNING"
            },
            {
              "endTime": null,
              "id": "2",
              "implementingClass": "com.netflix.spinnaker.orca.igor.tasks.MonitorWerckerJobStartedTask",
              "loopEnd": false,
              "loopStart": false,
              "name": "waitForWerckerJobStart",
              "stageEnd": false,
              "stageStart": false,
              "startTime": null,
              "status": "NOT_STARTED"
            },
            {
              "endTime": null,
              "id": "3",
              "implementingClass": "com.netflix.spinnaker.orca.igor.tasks.MonitorJenkinsJobTask",
              "loopEnd": false,
              "loopStart": false,
              "name": "monitorWerckerJob",
              "stageEnd": false,
              "stageStart": false,
              "startTime": null,
              "status": "NOT_STARTED"
            },
            {
              "endTime": null,
              "id": "4",
              "implementingClass": "com.netflix.spinnaker.orca.igor.tasks.GetBuildPropertiesTask",
              "loopEnd": false,
              "loopStart": false,
              "name": "getBuildProperties",
              "stageEnd": false,
              "stageStart": false,
              "startTime": null,
              "status": "NOT_STARTED"
            },
            {
              "endTime": null,
              "id": "5",
              "implementingClass": "com.netflix.spinnaker.orca.igor.tasks.GetBuildArtifactsTask",
              "loopEnd": false,
              "loopStart": false,
              "name": "getBuildArtifacts",
              "stageEnd": true,
              "stageStart": false,
              "startTime": null,
              "status": "NOT_STARTED"
            }
          ],
          "type": "wercker"
        },
        {
          "context": {
            "amiSuffix": "20210513172504",
            "baseLabel": "release",
            "baseOs": "ubuntu",
            "cloudProviderType": "aws",
            "extendedAttributes": {},
            "name": "Bake in us-east-2",
            "package": "nginx vim",
            "rebake": true,
            "region": "us-east-2",
            "storeType": "ebs",
            "type": "bake",
            "user": "myUserName",
            "vmType": "hvm"
          },
          "endTime": null,
          "id": "01F5KC5AJECT88MA2PHYG6TT3G",
          "lastModified": null,
          "name": "Bake in us-east-2",
          "outputs": {},
          "parentStageId": "01F5KC59VXEMS65RNVKF5HJJ9S",
          "refId": "8<1",
          "requisiteStageRefIds": [],
          "scheduledTime": null,
          "startTime": 1620926704513,
          "startTimeExpiry": null,
          "status": "RUNNING",
          "syntheticStageOwner": "STAGE_BEFORE",
          "tasks": [
            {
              "endTime": null,
              "id": "1",
              "implementingClass": "com.netflix.spinnaker.orca.bakery.tasks.CreateBakeTask",
              "loopEnd": false,
              "loopStart": false,
              "name": "createBake",
              "stageEnd": false,
              "stageStart": true,
              "startTime": 1620926705585,
              "status": "RUNNING"
            },
            {
              "endTime": null,
              "id": "2",
              "implementingClass": "com.netflix.spinnaker.orca.bakery.tasks.MonitorBakeTask",
              "loopEnd": false,
              "loopStart": false,
              "name": "monitorBake",
              "stageEnd": false,
              "stageStart": false,
              "startTime": null,
              "status": "NOT_STARTED"
            },
            {
              "endTime": null,
              "id": "3",
              "implementingClass": "com.netflix.spinnaker.orca.bakery.tasks.CompletedBakeTask",
              "loopEnd": false,
              "loopStart": false,
              "name": "completedBake",
              "stageEnd": false,
              "stageStart": false,
              "startTime": null,
              "status": "NOT_STARTED"
            },
            {
              "endTime": null,
              "id": "4",
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
          "type": "bake"
        },
        {
          "context": {
            "amiSuffix": "20210513172504",
            "baseLabel": "release",
            "baseOs": "ubuntu",
            "cloudProviderType": "aws",
            "extendedAttributes": {},
            "package": "nginx vim",
            "rebake": true,
            "region": "us-east-2",
            "regions": [
              "us-east-2"
            ],
            "storeType": "ebs",
            "user": "myUserName",
            "vmType": "hvm"
          },
          "endTime": null,
          "id": "01F5KC59VXEMS65RNVKF5HJJ9S",
          "lastModified": null,
          "name": "Bake",
          "outputs": {},
          "parentStageId": null,
          "refId": "8",
          "requisiteStageRefIds": [],
          "scheduledTime": null,
          "startTime": 1620926704174,
          "startTimeExpiry": null,
          "status": "RUNNING",
          "syntheticStageOwner": null,
          "tasks": [
            {
              "endTime": null,
              "id": "1",
              "implementingClass": "com.netflix.spinnaker.orca.bakery.pipeline.BakeStage.CompleteParallelBakeTask",
              "loopEnd": false,
              "loopStart": false,
              "name": "completeParallel",
              "stageEnd": true,
              "stageStart": true,
              "startTime": null,
              "status": "NOT_STARTED"
            }
          ],
          "type": "bake"
        },
        {
          "context": {},
          "endTime": null,
          "id": "01F5KC59VX4RE5RZVJG239ZD42",
          "lastModified": null,
          "name": "AWS CodeBuild",
          "outputs": {},
          "parentStageId": null,
          "refId": "9",
          "requisiteStageRefIds": [],
          "scheduledTime": null,
          "startTime": 1620926704185,
          "startTimeExpiry": null,
          "status": "RUNNING",
          "syntheticStageOwner": null,
          "tasks": [
            {
              "endTime": null,
              "id": "1",
              "implementingClass": "com.netflix.spinnaker.orca.igor.tasks.StartAwsCodeBuildTask",
              "loopEnd": false,
              "loopStart": false,
              "name": "startAwsCodeBuildTask",
              "stageEnd": false,
              "stageStart": true,
              "startTime": 1620926704452,
              "status": "RUNNING"
            },
            {
              "endTime": null,
              "id": "2",
              "implementingClass": "com.netflix.spinnaker.orca.igor.tasks.MonitorAwsCodeBuildTask",
              "loopEnd": false,
              "loopStart": false,
              "name": "monitorAwsCodeBuildTask",
              "stageEnd": false,
              "stageStart": false,
              "startTime": null,
              "status": "NOT_STARTED"
            },
            {
              "endTime": null,
              "id": "3",
              "implementingClass": "com.netflix.spinnaker.orca.igor.tasks.GetAwsCodeBuildArtifactsTask",
              "loopEnd": false,
              "loopStart": false,
              "name": "getAwsCodeBuildArtifactsTask",
              "stageEnd": false,
              "stageStart": false,
              "startTime": null,
              "status": "NOT_STARTED"
            },
            {
              "endTime": null,
              "id": "4",
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
          "type": "awsCodeBuild"
        }
      ],
      "startTime": 1620926703525,
      "startTimeExpiry": null,
      "status": "TERMINAL",
      "systemNotifications": [],
      "templateVariables": null,
      "trigger": {
        "artifacts": [
          {
            "artifactAccount": "myUserName",
            "customKind": false,
            "location": null,
            "metadata": {
              "id": "d14e7e5b-247c-455d-8260-9e9b0a3ae936"
            },
            "name": "manifests/deploy-spinnaker.yaml",
            "provenance": null,
            "reference": "Https://api.github.com/repos/myUserName/hostname/contents/manifests/deploy-spinnaker.yaml",
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
                "id": "d14e7e5b-247c-455d-8260-9e9b0a3ae936"
              },
              "name": "manifests/deploy-spinnaker.yaml",
              "reference": "Https://api.github.com/repos/myUserName/hostname/contents/manifests/deploy-spinnaker.yaml",
              "type": "github/file",
              "version": "master"
            }
          ],
          "dryRun": false,
          "enabled": false,
          "eventId": "c1090782-f485-490e-a2d7-31763b3bd4d8",
          "executionId": "01F5KC59TRGWKCP31C4N51CDSB",
          "expectedArtifacts": [
            {
              "boundArtifact": {
                "artifactAccount": "myUserName",
                "customKind": false,
                "metadata": {
                  "id": "d14e7e5b-247c-455d-8260-9e9b0a3ae936"
                },
                "name": "manifests/deploy-spinnaker.yaml",
                "reference": "Https://api.github.com/repos/myUserName/hostname/contents/manifests/deploy-spinnaker.yaml",
                "type": "github/file",
                "version": "master"
              },
              "defaultArtifact": {
                "artifactAccount": "myUserName",
                "customKind": false,
                "metadata": {
                  "id": "d14e7e5b-247c-455d-8260-9e9b0a3ae936"
                },
                "name": "manifests/deploy-spinnaker.yaml",
                "reference": "Https://api.github.com/repos/myUserName/hostname/contents/manifests/deploy-spinnaker.yaml",
                "type": "github/file",
                "version": "master"
              },
              "id": "05ad020e-73a6-49f2-9988-2073831219e9",
              "matchArtifact": {
                "artifactAccount": "myUserName",
                "customKind": true,
                "metadata": {
                  "id": "f7a9b229-0a23-42ab-82de-9990d77084df"
                },
                "name": "manifests/deploy-spinnaker.yaml",
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
                  "id": "d14e7e5b-247c-455d-8260-9e9b0a3ae936"
                },
                "name": "manifests/deploy-spinnaker.yaml",
                "reference": "Https://api.github.com/repos/myUserName/hostname/contents/manifests/deploy-spinnaker.yaml",
                "type": "github/file",
                "version": "master"
              },
              "defaultArtifact": {
                "artifactAccount": "myUserName",
                "customKind": false,
                "metadata": {
                  "id": "d14e7e5b-247c-455d-8260-9e9b0a3ae936"
                },
                "name": "manifests/deploy-spinnaker.yaml",
                "reference": "Https://api.github.com/repos/myUserName/hostname/contents/manifests/deploy-spinnaker.yaml",
                "type": "github/file",
                "version": "master"
              },
              "id": "05ad020e-73a6-49f2-9988-2073831219e9",
              "matchArtifact": {
                "artifactAccount": "myUserName",
                "customKind": true,
                "metadata": {
                  "id": "f7a9b229-0a23-42ab-82de-9990d77084df"
                },
                "name": "manifests/deploy-spinnaker.yaml",
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
                "id": "d14e7e5b-247c-455d-8260-9e9b0a3ae936"
              },
              "name": "manifests/deploy-spinnaker.yaml",
              "provenance": null,
              "reference": "Https://api.github.com/repos/myUserName/hostname/contents/manifests/deploy-spinnaker.yaml",
              "type": "github/file",
              "uuid": null,
              "version": "master"
            },
            "defaultArtifact": {
              "artifactAccount": "myUserName",
              "customKind": false,
              "location": null,
              "metadata": {
                "id": "d14e7e5b-247c-455d-8260-9e9b0a3ae936"
              },
              "name": "manifests/deploy-spinnaker.yaml",
              "provenance": null,
              "reference": "Https://api.github.com/repos/myUserName/hostname/contents/manifests/deploy-spinnaker.yaml",
              "type": "github/file",
              "uuid": null,
              "version": "master"
            },
            "id": "05ad020e-73a6-49f2-9988-2073831219e9",
            "matchArtifact": {
              "artifactAccount": "myUserName",
              "customKind": true,
              "location": null,
              "metadata": {
                "id": "f7a9b229-0a23-42ab-82de-9990d77084df"
              },
              "name": "manifests/deploy-spinnaker.yaml",
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
        "statusUrlResolution": "getMethod"
      },
      "endTime": null,
      "id": "01F5KC59VXHMA91KG8XYQ7RRZK",
      "lastModified": null,
      "name": "Webhook",
      "outputs": {},
      "parentStageId": null,
      "refId": "43",
      "requisiteStageRefIds": [],
      "scheduledTime": null,
      "startTime": 1620926704157,
      "startTimeExpiry": null,
      "status": "RUNNING",
      "syntheticStageOwner": null,
      "tasks": [
        {
          "endTime": null,
          "id": "1",
          "implementingClass": "com.netflix.spinnaker.orca.webhook.tasks.CreateWebhookTask",
          "loopEnd": false,
          "loopStart": false,
          "name": "createWebhook",
          "stageEnd": true,
          "stageStart": true,
          "startTime": 1620926704632,
          "status": "RUNNING"
        }
      ],
      "type": "webhook"
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

| Key                                               | Type      | Description |
| ------------------------------------------------- | --------- | ----------- |
| `input.pipeline.application` | `string`  | The name of the Spinnaker application to which this pipeline belongs. |
| `input.pipeline.authentication.allowedAccounts[]` | `string`  |             |
| `input.pipeline.authentication.user`              | `string`  |             |
| `input.pipeline.buildTime`                        | `number`  |             |
| `input.pipeline.canceledBy`                       | ` `       |             |
| `input.pipeline.canceled`                         | `boolean` |             |
| `input.pipeline.cancellationReason`               | ` `       |             |
| `input.pipeline.description`                      | ` `       |             |
| `input.pipeline.endTime`                          | `number`  |             |
| `input.pipeline.id`                               | `string`  |             |
| `input.pipeline.keepWaitingPipelines`             | `boolean` |             |
| `input.pipeline.limitConcurrent`                  | `boolean` |             |
| `input.pipeline.name`                             | `string`  |             |
| `input.pipeline.origin`                           | `string`  |             |
| `input.pipeline.partition`                        | ` `       |             |
| `input.pipeline.paused`                           | ` `       |             |
| `input.pipeline.pipelineConfigId`                 | `string`  |             |
| `input.pipeline.source`                           | ` `       |             |
| `input.pipeline.spelEvaluator`                    | `string`  |             |
| `input.pipeline.startTimeExpiry`                  | ` `       |             |
| `input.pipeline.startTime`                        | `number`  |             |
| `input.pipeline.status`                           | `string`  |             |
| `input.pipeline.templateVariables`                | ` `       |             |
| `input.pipeline.type`                             | `string`  |             |

### input.pipeline.stages

| Key                                                                                                    | Type      | Description |
| ------------------------------------------------------------------------------------------------------ | --------- | ----------- |
| `input.pipeline.stages[].context.account`                                                              | `string`  |             |
| `input.pipeline.stages[].context.action`                                                               | `string`  |             |
| `input.pipeline.stages[].context.alias`                                                                | `string`  |             |
| `input.pipeline.stages[].context.allowDeleteActive`                                                    | `boolean` |             |
| `input.pipeline.stages[].context.allowScaleDownActive`                                                 | `boolean` |             |
| `input.pipeline.stages[].context.amiSuffix`                                                            | `string`  |             |
| `input.pipeline.stages[].context.analysisType`                                                         | `string`  |             |
| `input.pipeline.stages[].context.app`                                                                  | `string`  |             |
| `input.pipeline.stages[].context.application`                                                          | `string`  |             |
| `input.pipeline.stages[].context.artifacts[].customKind`                                               | `boolean` |             |
| `input.pipeline.stages[].context.artifacts[].location`                                                 | `string`  |             |
| `input.pipeline.stages[].context.artifacts[].metadata.account`                                         | `string`  |             |
| `input.pipeline.stages[].context.artifacts[].name`                                                     | `string`  |             |
| `input.pipeline.stages[].context.artifacts[].reference`                                                | `string`  |             |
| `input.pipeline.stages[].context.artifacts[].type`                                                     | `string`  |             |
| `input.pipeline.stages[].context.artifacts[].version`                                                  | `string`  |             |
| `input.pipeline.stages[].context.attempt`                                                              | `number`  |             |
| `input.pipeline.stages[].context.availabilityZones.us-east-2[]`                                        | `string`  |             |
| `input.pipeline.stages[].context.baseLabel`                                                            | `string`  |             |
| `input.pipeline.stages[].context.baseOs`                                                               | `string`  |             |
| `input.pipeline.stages[].context.beforeStagePlanningFailed`                                            | `boolean` |             |
| `input.pipeline.stages[].context.canaryConfig.metricsAccountName`                                      | `string`  |             |
| `input.pipeline.stages[].context.canaryConfig.scopes[].scopeName`                                      | `string`  |             |
| `input.pipeline.stages[].context.canaryConfig.storageAccountName`                                      | `string`  |             |
| `input.pipeline.stages[].context.capacity.desired`                                                     | `number`  |             |
| `input.pipeline.stages[].context.capacity.max`                                                         | `number`  |             |
| `input.pipeline.stages[].context.capacity.min`                                                         | `number`  |             |
| `input.pipeline.stages[].context.cloudProviderType`                                                    | `string`  |             |
| `input.pipeline.stages[].context.cloudProvider`                                                        | `string`  |             |
| `input.pipeline.stages[].context.cluster`                                                              | `string`  |             |
| `input.pipeline.stages[].context.clusters[].account`                                                   | `string`  |             |
| `input.pipeline.stages[].context.clusters[].application`                                               | `string`  |             |
| `input.pipeline.stages[].context.clusters[].availabilityZones.us-east-2[]`                             | `string`  |             |
| `input.pipeline.stages[].context.clusters[].capacity.desired`                                          | `number`  |             |
| `input.pipeline.stages[].context.clusters[].capacity.max`                                              | `number`  |             |
| `input.pipeline.stages[].context.clusters[].capacity.min`                                              | `number`  |             |
| `input.pipeline.stages[].context.clusters[].cloudProvider`                                             | `string`  |             |
| `input.pipeline.stages[].context.clusters[].cooldown`                                                  | `number`  |             |
| `input.pipeline.stages[].context.clusters[].copySourceCustomBlockDeviceMappings`                       | `boolean` |             |
| `input.pipeline.stages[].context.clusters[].ebsOptimized`                                              | `boolean` |             |
| `input.pipeline.stages[].context.clusters[].freeFormDetails`                                           | `string`  |             |
| `input.pipeline.stages[].context.clusters[].healthCheckGracePeriod`                                    | `number`  |             |
| `input.pipeline.stages[].context.clusters[].healthCheckType`                                           | `string`  |             |
| `input.pipeline.stages[].context.clusters[].iamRole`                                                   | `string`  |             |
| `input.pipeline.stages[].context.clusters[].instanceMonitoring`                                        | `boolean` |             |
| `input.pipeline.stages[].context.clusters[].instanceType`                                              | `string`  |             |
| `input.pipeline.stages[].context.clusters[].keyPair`                                                   | `string`  |             |
| `input.pipeline.stages[].context.clusters[].provider`                                                  | `string`  |             |
| `input.pipeline.stages[].context.clusters[].reason`                                                    | `string`  |             |
| `input.pipeline.stages[].context.clusters[].spotPrice`                                                 | `string`  |             |
| `input.pipeline.stages[].context.clusters[].stack`                                                     | `string`  |             |
| `input.pipeline.stages[].context.clusters[].strategy`                                                  | `string`  |             |
| `input.pipeline.stages[].context.clusters[].subnetType`                                                | `string`  |             |
| `input.pipeline.stages[].context.clusters[].targetHealthyDeployPercentage`                             | `number`  |             |
| `input.pipeline.stages[].context.clusters[].terminationPolicies[]`                                     | `string`  |             |
| `input.pipeline.stages[].context.clusters[].useAmiBlockDeviceMappings`                                 | `boolean` |             |
| `input.pipeline.stages[].context.consecutiveNotFound`                                                  | `number`  |             |
| `input.pipeline.stages[].context.continuePipeline`                                                     | `boolean` |             |
| `input.pipeline.stages[].context.cooldown`                                                             | `number`  |             |
| `input.pipeline.stages[].context.copySourceCustomBlockDeviceMappings`                                  | `boolean` |             |
| `input.pipeline.stages[].context.credentials`                                                          | `string`  |             |
| `input.pipeline.stages[].context.ebsOptimized`                                                         | `boolean` |             |
| `input.pipeline.stages[].context.entityRef.entityId`                                                   | `string`  |             |
| `input.pipeline.stages[].context.entityRef.entityType`                                                 | `string`  |             |
| `input.pipeline.stages[].context.exception.details.error`                                              | `string`  |             |
| `input.pipeline.stages[].context.exception.details.errors[]`                                           | `string`  |             |
| `input.pipeline.stages[].context.exception.details.kind`                                               | `string`  |             |
| `input.pipeline.stages[].context.exception.details.responseBody`                                       | `string`  |             |
| `input.pipeline.stages[].context.exception.details.stackTrace`                                         | `string`  |             |
| `input.pipeline.stages[].context.exception.details.status`                                             | `number`  |             |
| `input.pipeline.stages[].context.exception.details.url`                                                | `string`  |             |
| `input.pipeline.stages[].context.exception.exceptionType`                                              | `string`  |             |
| `input.pipeline.stages[].context.exception.operation`                                                  | `string`  |             |
| `input.pipeline.stages[].context.exception.shouldRetry`                                                | `boolean` |             |
| `input.pipeline.stages[].context.exception.timestamp`                                                  | `number`  |             |
| `input.pipeline.stages[].context.executionOptions.successful`                                          | `boolean` |             |
| `input.pipeline.stages[].context.expectedArtifacts[].defaultArtifact.customKind`                       | `boolean` |             |
| `input.pipeline.stages[].context.expectedArtifacts[].defaultArtifact.id`                               | `string`  |             |
| `input.pipeline.stages[].context.expectedArtifacts[].displayName`                                      | `string`  |             |
| `input.pipeline.stages[].context.expectedArtifacts[].id`                                               | `string`  |             |
| `input.pipeline.stages[].context.expectedArtifacts[].matchArtifact.artifactAccount`                    | `string`  |             |
| `input.pipeline.stages[].context.expectedArtifacts[].matchArtifact.customKind`                         | `boolean` |             |
| `input.pipeline.stages[].context.expectedArtifacts[].matchArtifact.id`                                 | `string`  |             |
| `input.pipeline.stages[].context.expectedArtifacts[].matchArtifact.name`                               | `string`  |             |
| `input.pipeline.stages[].context.expectedArtifacts[].matchArtifact.type`                               | `string`  |             |
| `input.pipeline.stages[].context.expectedArtifacts[].useDefaultArtifact`                               | `boolean` |             |
| `input.pipeline.stages[].context.expectedArtifacts[].usePriorArtifact`                                 | `boolean` |             |
| `input.pipeline.stages[].context.expressionEvaluationSummary.trigger.buildInfo.number[].description`   | `string`  |             |
| `input.pipeline.stages[].context.expressionEvaluationSummary.trigger.buildInfo.number[].exceptionType` | `string`  |             |
| `input.pipeline.stages[].context.expressionEvaluationSummary.trigger.buildInfo.number[].level`         | `string`  |             |
| `input.pipeline.stages[].context.expressionEvaluationSummary.trigger.buildInfo.number[].timestamp`     | `number`  |             |
| `input.pipeline.stages[].context.failOnFailedExpressions`                                              | `boolean` |             |
| `input.pipeline.stages[].context.failPipeline`                                                         | `boolean` |             |
| `input.pipeline.stages[].context.freeFormDetails`                                                      | `string`  |             |
| `input.pipeline.stages[].context.healthCheckGracePeriod`                                               | `number`  |             |
| `input.pipeline.stages[].context.healthCheckType`                                                      | `string`  |             |
| `input.pipeline.stages[].context.iamRole`                                                              | `string`  |             |
| `input.pipeline.stages[].context.inputArtifacts[].account`                                             | `string`  |             |
| `input.pipeline.stages[].context.inputArtifacts[].id`                                                  | `string`  |             |
| `input.pipeline.stages[].context.instanceMonitoring`                                                   | `boolean` |             |
| `input.pipeline.stages[].context.instanceType`                                                         | `string`  |             |
| `input.pipeline.stages[].context.interestingHealthProviderNames[]`                                     | `string`  |             |
| `input.pipeline.stages[].context.kato.last.task.id.id`                                                 | `string`  |             |
| `input.pipeline.stages[].context.kato.result.expected`                                                 | `boolean` |             |
| `input.pipeline.stages[].context.keyPair`                                                              | `string`  |             |
| `input.pipeline.stages[].context.lastException`                                                        | `string`  |             |
| `input.pipeline.stages[].context.location`                                                             | `string`  |             |
| `input.pipeline.stages[].context.manifestArtifactId`                                                   | `string`  |             |
| `input.pipeline.stages[].context.manifestName`                                                         | `string`  |             |
| `input.pipeline.stages[].context.mode`                                                                 | `string`  |             |
| `input.pipeline.stages[].context.name`                                                                 | `string`  |             |
| `input.pipeline.stages[].context.namespace`                                                            | `string`  |             |
| `input.pipeline.stages[].context.notification.type`                                                    | `string`  |             |
| `input.pipeline.stages[].context.numRevisionsBack`                                                     | `number`  |             |
| `input.pipeline.stages[].context.onlyEnabled`                                                          | `boolean` |             |
| `input.pipeline.stages[].context.options.mergeStrategy`                                                | `string`  |             |
| `input.pipeline.stages[].context.options.record`                                                       | `boolean` |             |
| `input.pipeline.stages[].context.outputName`                                                           | `string`  |             |
| `input.pipeline.stages[].context.package`                                                              | `string`  |             |
| `input.pipeline.stages[].context.patchBody[].apiVersion`                                               | `string`  |             |
| `input.pipeline.stages[].context.patchBody[].kind`                                                     | `string`  |             |
| `input.pipeline.stages[].context.patchBody[].metadata.name`                                            | `string`  |             |
| `input.pipeline.stages[].context.patchBody[].metadata.namespace`                                       | `string`  |             |
| `input.pipeline.stages[].context.patchBody[].spec.replicas`                                            | `string`  |             |
| `input.pipeline.stages[].context.patchBody[].spec.selector.matchLabels.app`                            | `string`  |             |
| `input.pipeline.stages[].context.patchBody[].spec.selector.matchLabels.version`                        | `string`  |             |
| `input.pipeline.stages[].context.patchBody[].spec.strategy.rollingUpdate.maxSurge`                     | `number`  |             |
| `input.pipeline.stages[].context.patchBody[].spec.strategy.rollingUpdate.maxUnavailable`               | `number`  |             |
| `input.pipeline.stages[].context.patchBody[].spec.strategy.type`                                       | `string`  |             |
| `input.pipeline.stages[].context.patchBody[].spec.template.metadata.annotations.prometheus.io/port`    | `string`  |             |
| `input.pipeline.stages[].context.patchBody[].spec.template.metadata.annotations.prometheus.io/scrape`  | `string`  |             |
| `input.pipeline.stages[].context.patchBody[].spec.template.metadata.labels.app`                        | `string`  |             |
| `input.pipeline.stages[].context.patchBody[].spec.template.metadata.labels.version`                    | `string`  |             |
| `input.pipeline.stages[].context.patchBody[].spec.template.spec.containers[].args[]`                   | `string`  |             |
| `input.pipeline.stages[].context.patchBody[].spec.template.spec.containers[].imagePullPolicy`          | `string`  |             |
| `input.pipeline.stages[].context.patchBody[].spec.template.spec.containers[].image`                    | `string`  |             |
| `input.pipeline.stages[].context.patchBody[].spec.template.spec.containers[].name`                     | `string`  |             |
| `input.pipeline.stages[].context.patchBody[].spec.template.spec.containers[].ports[].containerPort`    | `number`  |             |
| `input.pipeline.stages[].context.patchBody[].spec.template.spec.containers[].ports[].name`             | `string`  |             |
| `input.pipeline.stages[].context.patchBody[].spec.template.spec.containers[].ports[].protocol`         | `string`  |             |
| `input.pipeline.stages[].context.patchBody[].spec.template.spec.containers[].volumeMounts[].mountPath` | `string`  |             |
| `input.pipeline.stages[].context.patchBody[].spec.template.spec.containers[].volumeMounts[].name`      | `string`  |             |
| `input.pipeline.stages[].context.patchBody[].spec.template.spec.containers[].volumeMounts[].readOnly`  | `boolean` |             |
| `input.pipeline.stages[].context.patchBody[].spec.template.spec.containers[].volumeMounts[].subPath`   | `string`  |             |
| `input.pipeline.stages[].context.patchBody[].spec.template.spec.restartPolicy`                         | `string`  |             |
| `input.pipeline.stages[].context.patchBody[].spec.template.spec.volumes[].configMap.defaultMode`       | `number`  |             |
| `input.pipeline.stages[].context.patchBody[].spec.template.spec.volumes[].configMap.name`              | `string`  |             |
| `input.pipeline.stages[].context.patchBody[].spec.template.spec.volumes[].name`                        | `string`  |             |
| `input.pipeline.stages[].context.pipeline`                                                             | `string`  |             |
| `input.pipeline.stages[].context.pipelinesArtifactId`                                                  | `string`  |             |
| `input.pipeline.stages[].context.preferLargerOverNewer`                                                | `string`  |             |
| `input.pipeline.stages[].context.provider`                                                             | `string`  |             |
| `input.pipeline.stages[].context.reason`                                                               | `string`  |             |
| `input.pipeline.stages[].context.rebake`                                                               | `boolean` |             |
| `input.pipeline.stages[].context.region`                                                               | `string`  |             |
| `input.pipeline.stages[].context.regions[]`                                                            | `string`  |             |
| `input.pipeline.stages[].context.remainingEnabledServerGroups`                                         | `number`  |             |
| `input.pipeline.stages[].context.remainingFullSizeServerGroups`                                        | `number`  |             |
| `input.pipeline.stages[].context.resizeType`                                                           | `string`  |             |
| `input.pipeline.stages[].context.resolvedExpectedArtifacts[].boundArtifact.customKind`                 | `boolean` |             |
| `input.pipeline.stages[].context.resolvedExpectedArtifacts[].boundArtifact.location`                   | `string`  |             |
| `input.pipeline.stages[].context.resolvedExpectedArtifacts[].boundArtifact.metadata.account`           | `string`  |             |
| `input.pipeline.stages[].context.resolvedExpectedArtifacts[].boundArtifact.name`                       | `string`  |             |
| `input.pipeline.stages[].context.resolvedExpectedArtifacts[].boundArtifact.reference`                  | `string`  |             |
| `input.pipeline.stages[].context.resolvedExpectedArtifacts[].boundArtifact.type`                       | `string`  |             |
| `input.pipeline.stages[].context.resolvedExpectedArtifacts[].boundArtifact.version`                    | `string`  |             |
| `input.pipeline.stages[].context.resolvedExpectedArtifacts[].defaultArtifact.customKind`               | `boolean` |             |
| `input.pipeline.stages[].context.resolvedExpectedArtifacts[].defaultArtifact.metadata.id`              | `string`  |             |
| `input.pipeline.stages[].context.resolvedExpectedArtifacts[].id`                                       | `string`  |             |
| `input.pipeline.stages[].context.resolvedExpectedArtifacts[].matchArtifact.customKind`                 | `boolean` |             |
| `input.pipeline.stages[].context.resolvedExpectedArtifacts[].matchArtifact.metadata.id`                | `string`  |             |
| `input.pipeline.stages[].context.resolvedExpectedArtifacts[].useDefaultArtifact`                       | `boolean` |             |
| `input.pipeline.stages[].context.resolvedExpectedArtifacts[].usePriorArtifact`                         | `boolean` |             |
| `input.pipeline.stages[].context.retainLargerOverNewer`                                                | `string`  |             |
| `input.pipeline.stages[].context.selectionStrategy`                                                    | `string`  |             |
| `input.pipeline.stages[].context.shrinkToSize`                                                         | `number`  |             |
| `input.pipeline.stages[].context.source`                                                               | `string`  |             |
| `input.pipeline.stages[].context.spotPrice`                                                            | `string`  |             |
| `input.pipeline.stages[].context.stackArtifactAccount`                                                 | `string`  |             |
| `input.pipeline.stages[].context.stackArtifactId`                                                      | `string`  |             |
| `input.pipeline.stages[].context.stackName`                                                            | `string`  |             |
| `input.pipeline.stages[].context.stack`                                                                | `string`  |             |
| `input.pipeline.stages[].context.storeType`                                                            | `string`  |             |
| `input.pipeline.stages[].context.strategy`                                                             | `string`  |             |
| `input.pipeline.stages[].context.subnetType`                                                           | `string`  |             |
| `input.pipeline.stages[].context.tags.TEST`                                                            | `string`  |             |
| `input.pipeline.stages[].context.tags.test`                                                            | `string`  |             |
| `input.pipeline.stages[].context.tags[].name`                                                          | `string`  |             |
| `input.pipeline.stages[].context.tags[].namespace`                                                     | `string`  |             |
| `input.pipeline.stages[].context.tags[].value`                                                         | `string`  |             |
| `input.pipeline.stages[].context.targetCluster`                                                        | `string`  |             |
| `input.pipeline.stages[].context.targetHealthyDeployPercentage`                                        | `number`  |             |
| `input.pipeline.stages[].context.targetHealthyRollbackPercentage`                                      | `number`  |             |
| `input.pipeline.stages[].context.targetLocation.type`                                                  | `string`  |             |
| `input.pipeline.stages[].context.targetLocation.value`                                                 | `string`  |             |
| `input.pipeline.stages[].context.target`                                                               | `string`  |             |
| `input.pipeline.stages[].context.templateRenderer`                                                     | `string`  |             |
| `input.pipeline.stages[].context.terminationPolicies[]`                                                | `string`  |             |
| `input.pipeline.stages[].context.type`                                                                 | `string`  |             |
| `input.pipeline.stages[].context.useAmiBlockDeviceMappings`                                            | `boolean` |             |
| `input.pipeline.stages[].context.useSourceCapacity`                                                    | `boolean` |             |
| `input.pipeline.stages[].context.user`                                                                 | `string`  |             |
| `input.pipeline.stages[].context.variables[].key`                                                      | `string`  |             |
| `input.pipeline.stages[].context.variables[].sourceValue`                                              | `string`  |             |
| `input.pipeline.stages[].context.variables[].value`                                                    | `string`  |             |
| `input.pipeline.stages[].context.vmType`                                                               | `string`  |             |
| `input.pipeline.stages[].context.waitForCompletion`                                                    | `boolean` |             |
| `input.pipeline.stages[].context.waitTime`                                                             | `number`  |             |
| `input.pipeline.stages[].endTime`                                                                      | ` `       |             |
| `input.pipeline.stages[].endTime`                                                                      | `number`  |             |
| `input.pipeline.stages[].id`                                                                           | `string`  |             |
| `input.pipeline.stages[].lastModified`                                                                 | ` `       |             |
| `input.pipeline.stages[].name`                                                                         | `string`  |             |
| `input.pipeline.stages[].outputs.artifacts[].customKind`                                               | `boolean` |             |
| `input.pipeline.stages[].outputs.artifacts[].location`                                                 | `string`  |             |
| `input.pipeline.stages[].outputs.artifacts[].metadata.account`                                         | `string`  |             |
| `input.pipeline.stages[].outputs.artifacts[].name`                                                     | `string`  |             |
| `input.pipeline.stages[].outputs.artifacts[].reference`                                                | `string`  |             |
| `input.pipeline.stages[].outputs.artifacts[].type`                                                     | `string`  |             |
| `input.pipeline.stages[].outputs.artifacts[].version`                                                  | `string`  |             |
| `input.pipeline.stages[].outputs.resolvedExpectedArtifacts[].boundArtifact.customKind`                 | `boolean` |             |
| `input.pipeline.stages[].outputs.resolvedExpectedArtifacts[].boundArtifact.location`                   | `string`  |             |
| `input.pipeline.stages[].outputs.resolvedExpectedArtifacts[].boundArtifact.metadata.account`           | `string`  |             |
| `input.pipeline.stages[].outputs.resolvedExpectedArtifacts[].boundArtifact.name`                       | `string`  |             |
| `input.pipeline.stages[].outputs.resolvedExpectedArtifacts[].boundArtifact.reference`                  | `string`  |             |
| `input.pipeline.stages[].outputs.resolvedExpectedArtifacts[].boundArtifact.type`                       | `string`  |             |
| `input.pipeline.stages[].outputs.resolvedExpectedArtifacts[].boundArtifact.version`                    | `string`  |             |
| `input.pipeline.stages[].outputs.resolvedExpectedArtifacts[].defaultArtifact.customKind`               | `boolean` |             |
| `input.pipeline.stages[].outputs.resolvedExpectedArtifacts[].defaultArtifact.metadata.id`              | `string`  |             |
| `input.pipeline.stages[].outputs.resolvedExpectedArtifacts[].id`                                       | `string`  |             |
| `input.pipeline.stages[].outputs.resolvedExpectedArtifacts[].matchArtifact.customKind`                 | `boolean` |             |
| `input.pipeline.stages[].outputs.resolvedExpectedArtifacts[].matchArtifact.metadata.id`                | `string`  |             |
| `input.pipeline.stages[].outputs.resolvedExpectedArtifacts[].useDefaultArtifact`                       | `boolean` |             |
| `input.pipeline.stages[].outputs.resolvedExpectedArtifacts[].usePriorArtifact`                         | `boolean` |             |
| `input.pipeline.stages[].parentStageId`                                                                | ` `       |             |
| `input.pipeline.stages[].parentStageId`                                                                | `string`  |             |
| `input.pipeline.stages[].refId`                                                                        | `string`  |             |
| `input.pipeline.stages[].requisiteStageRefIds[]`                                                       | `string`  |             |
| `input.pipeline.stages[].scheduledTime`                                                                | ` `       |             |
| `input.pipeline.stages[].startTimeExpiry`                                                              | ` `       |             |
| `input.pipeline.stages[].startTime`                                                                    | ` `       |             |
| `input.pipeline.stages[].startTime`                                                                    | `number`  |             |
| `input.pipeline.stages[].status`                                                                       | `string`  |             |
| `input.pipeline.stages[].syntheticStageOwner`                                                          | ` `       |             |
| `input.pipeline.stages[].syntheticStageOwner`                                                          | `string`  |             |
| `input.pipeline.stages[].tasks[].endTime`                                                              | ` `       |             |
| `input.pipeline.stages[].tasks[].endTime`                                                              | `number`  |             |
| `input.pipeline.stages[].tasks[].id`                                                                   | `string`  |             |
| `input.pipeline.stages[].tasks[].implementingClass`                                                    | `string`  |             |
| `input.pipeline.stages[].tasks[].loopEnd`                                                              | `boolean` |             |
| `input.pipeline.stages[].tasks[].loopStart`                                                            | `boolean` |             |
| `input.pipeline.stages[].tasks[].name`                                                                 | `string`  |             |
| `input.pipeline.stages[].tasks[].stageEnd`                                                             | `boolean` |             |
| `input.pipeline.stages[].tasks[].stageStart`                                                           | `boolean` |             |
| `input.pipeline.stages[].tasks[].startTime`                                                            | ` `       |             |
| `input.pipeline.stages[].tasks[].startTime`                                                            | `number`  |             |
| `input.pipeline.stages[].tasks[].status`                                                               | `string`  |             |
| `input.pipeline.stages[].type`                                                                         | `string`  |             |
| `input.pipeline.stages[]`                                                                              | `string`  |             |

### input.pipeline.trigger

See [input.pipeline.trigger]({{< ref "input.pipeline.trigger.md" >}}) for more information.

### input.stage

| Key                                       | Type      | Description |
| ----------------------------------------- | --------- | ----------- |
| `input.stage.context.statusUrlResolution` | `string`  |             |
| `input.stage.endTime`                     | ` `       |             |
| `input.stage.id`                          | `string`  |             |
| `input.stage.lastModified`                | ` `       |             |
| `input.stage.name`                        | `string`  |             |
| `input.stage.parentStageId`               | ` `       |             |
| `input.stage.refId`                       | `string`  |             |
| `input.stage.scheduledTime`               | ` `       |             |
| `input.stage.startTimeExpiry`             | ` `       |             |
| `input.stage.startTime`                   | `number`  |             |
| `input.stage.status`                      | `string`  |             |
| `input.stage.syntheticStageOwner`         | ` `       |             |
| `input.stage.tasks[].endTime`             | ` `       |             |
| `input.stage.tasks[].id`                  | `string`  |             |
| `input.stage.tasks[].implementingClass`   | `string`  |             |
| `input.stage.tasks[].loopEnd`             | `boolean` |             |
| `input.stage.tasks[].loopStart`           | `boolean` |             |
| `input.stage.tasks[].name`                | `string`  |             |
| `input.stage.tasks[].stageEnd`            | `boolean` |             |
| `input.stage.tasks[].stageStart`          | `boolean` |             |
| `input.stage.tasks[].startTime`           | `number`  |             |
| `input.stage.tasks[].status`              | `string`  |             |
| `input.stage.type`                        | `string`  |             |

### input.user

This object provides information about the user performing the action. This can be used to restrict actions by role. See [input.user]({{< ref "input.user.md" >}}) for more information.