### Helm Chart for the [Flink Operator](https://github.com/lyft/flinkk8soperator) from Lyft.

##### Configuration

The following table lists the configurable parameters of the chart and their default values.

| Parameter                              | Description                                                  | Default                  |
| -------------------------------------- | ------------------------------------------------------------ | ------------------------ |
| `operatorImageName`                    | The name of the operator image                               | `lyft/flinkk8soperator`  |
| `operatorVersion`                      | The version of the operator to install                       | `0.3.0`                  |
| `imagePullPolicy`                      | Docker image pull policy                                     | `IfNotPresent`           |
| `flinkJobNamespace`                    | K8s namespace where Flink jobs are to be deployed.           | `default`                |
| `namespacesToWatch`                    | Comma separated list of namespaces that the operator is configured to watch. Empty string by default, which indicates all namespaces will be watched. | ""                       |
| `rbac.create`                          | Whether to create required roles and bindings                | `true`                   |
| `resourcesRequests.memory`             | Requested memory for the operator deployment                 | 1G                       |
| `resourcesRequests.cpu`                | Requested CPU for the operator deployment                    | 0.5                      |
| `resourcesLimits.memory`               | Memory limits for the operator deployment                    | 1G                       |
| `resourcesLimits.cpu`                  | CPU limits for the operator deployment                       | 2                        |
| **Name-related configs**               | **See below for further explanation**                        |                          |
| `serviceAccounts.flink.create`         | Create Flink operator ServiceAccount name using fully qualified app name | `true`                   |
| `serviceAccounts.flink.name`           | ServiceAccount name for the Flink operator                   | `default` if not created |
| `serviceAccounts.flinkoperator.create` | Create Flink job ServiceAccount name using release name      | `true`                   |
| `serviceAccounts.flinkoperator.name`   | ServiceAccount name for the Flink jobs                       | `default` if not created |

Specify each parameter using the `--set key=value[,key=value]` argument to `helm install`.

