---
title: Docker delegate environment variables
description: This topic describes the environment variables that are available for use with a Docker delegate. Some of these variables are included by default; you can specify others based on use case…
---


The following environment variables are available for use in the Docker delegate manifest. Some of these variables are included in the YAML by default; you can specify others based on use case.

### ACCOUNT_ID

The Harness account ID for the account with which this delegate registers.

```
- ACCOUNT_ID = XXXXXXxxxxxxxxxx
```

### DELEGATE_TOKEN

The Harness account token that is used to register the delegate.

```
- DELEGATE_TOKEN = d229ee88bf7bbxxxx6ea
```

### MANAGER_HOST_AND_PORT

The Harness SaaS manager URL. `https` indicates port 443.

```
- MANAGER_HOST_AND_PORT = https://app.harness.io
```

### WATCHER_STORAGE_URL

The URL location of the Watcher versions. For more information, go to [Delegate installation overview](/docs/platform/delegates/delegate-concepts/delegate-overview.md).

```
- WATCHER_STORAGE_URL = https://app.harness.io/public/prod/premium/watchers
```

### WATCHER_CHECK_LOCATION

The location of the delegate version that the Watcher references.

```yaml
- name: WATCHER_CHECK_LOCATION
  value: current.version
```

### REMOTE_WATCHER_URL_CDN

The CDN URL for Watcher builds.

```yaml
- name: REMOTE_WATCHER_URL_CDN
  value: https://app.harness.io/public/shared/watchers/builds
```

### DELEGATE_STORAGE_URL

The URL where published delegate JAR files are stored.

```yaml
- name: DELEGATE_STORAGE_URL
  value: https://app.harness.io
```

### DELEGATE_CHECK_LOCATION

The storage location that hosts the published delegate versions.

```yaml
- name: DELEGATE_CHECK_LOCATION
  value: delegateprod.txt
```

### DEPLOY_MODE

The mode of deployment, for example, Kubernetes or Docker.

```yaml
- name: DEPLOY_MODE
  value: DOCKER
```

### DELEGATE_NAME

The name of the delegate. This is the name that appears in Harness when the delegate is registered.

You can automate delegate creation by omitting the name and using a script to copy the delegate YAML file, giving a unique name to the `value` of the delegate name for each newly created delegate you want to register.

For more information, go to [Automate delegate installation](/docs/platform/delegates/install-delegates/automate-delegate-installation.md).

```yaml
- name: DELEGATE_NAME
  value: qa
```

### NEXT_GEN

Indicates whether the delegate registers in Harness NextGen (`true`) or FirstGen (`false`).

```yaml
- name: NEXT_GEN
  value: "true"
```

### DELEGATE_DESCRIPTION

The description that is given to the delegate in Harness Manager or YAML before the delegate registers. The description appears on the delegate details page in Harness Manager.

```yaml
- name: DELEGATE_DESCRIPTION
  value: ""
```

### DELEGATE_TYPE

The type of the delegate.

```yaml
- name: DELEGATE_TYPE
  value: "DOCKER"
```

### DELEGATE_TAGS

The tags that were added to the delegate in Harness Manager or YAML before delegate registration.

Harness generates tags based on the delegate name. You can add others. The tags appear on the delegate details page in Harness Manager.

For more information, go to [Tags reference](/docs/platform/references/tags-reference.md) and [Select delegates with tags](/docs/platform/delegates/manage-delegates/select-delegates-with-selectors.md).

```yaml
- name: DELEGATE_TAGS
  value: ""
```

### DELEGATE_TASK_LIMIT

The maximum number of tasks the delegate can perform at one time. Delegate operations are categorized as different types of tasks.

```yaml
- name: DELEGATE_TASK_LIMIT
  value: "50"
```

### DELEGATE_ORG_IDENTIFIER

The Harness organization [Identifier](/docs/platform/references/entity-identifier-reference.md) where the delegate registers.

This value is not specified for delegates at the account level.

```yaml
- name: DELEGATE_ORG_IDENTIFIER
  value: "engg"
```

### DELEGATE_PROJECT_IDENTIFIER

The Harness project [Identifier](/docs/platform/references/entity-identifier-reference.md) within which the delegate registers.

This value is not specified for delegates at the account or organization level.

```yaml
- name: DELEGATE_PROJECT_IDENTIFIER
  value: "myproject"
```

### PROXY_MANAGER

Indicates whether to use Harness Manager or a proxy. A value of `true` indicates an outbound proxy of traffic to Harness.

The default value is `true`.

```yaml
- PROXY_MANAGER = true
```

### INIT_SCRIPT

You can use this environment variable to run scripts on the delegate. For example, you can add a script to `INIT_SCRIPT` to install software on the delegate pod. The software is installed after you apply the delegate YAML.

A multiline script must follow the YAML spec for [literal scalar style](https://yaml.org/spec/1.2-old/spec.html#id2795688).

For more information, go to [Build custom delegate images with third-party tools](/docs/platform/delegates/install-delegates/build-custom-delegate-images-with-third-party-tools.md).

```yaml
- INIT_SCRIPT =  echo hello world!
```

### USE_CDN

Specifies the delegate use of a CDN for new versions.

```yaml
- name: USE_CDN
  value: "true"
```

### CDN_URL

The CDN URL for delegate versions.

```yaml
- name: CDN_URL
  value: https://app.harness.io
```

### VERSION_CHECK_DISABLED

By default, the delegate always checks for new versions (using the Watcher).

```yaml
- name: VERSION_CHECK_DISABLED
  value: "false"
```

### See also

[Delegate environment variables](/docs/platform/delegates/delegate-reference/delegate-environment-variables.md)
