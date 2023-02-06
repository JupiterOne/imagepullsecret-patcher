# imagepullsecret-patcher Helm Chart

# Config

| Config Path                    | Meaning                                               | Default                            |
| ------------------------------ | ----------------------------------------------------- | ---------------------------------- |
| replicaCount                   | Number of pods to run                                 | 1                                  |
| image.repository               | Image to use                                          | jupiterone/imagepullsecret-patcher |
| image.tag                      | Image tag to use                                      | <latest_version>                   |
| image.pullPolicy               | Image pull policy                                     | `IfNotPresent`                     |
| image.pullSecrets              | Secret needed to pull from `image.repository`         | `[]`                               |
| managedSecretName              | Name of the secret to populate through all namespaces | `"CHANGE_ME"`                      |
| env.CONFIG_FORCE               | Overwrite secrets when they don't match               | `true`                             |
| env.CONFIG_DEBUG               | Show debug logs                                       | `false`                            |
| env.CONFIG_MANAGEDONLY         | Only modify secrets that were created by this tool    | `false`                            |
| env.CONFIG_RUNONCE             | Only run once, and then terminate                     | `false`                            |
| env.CONFIG_SERVICEACCOUNTS     | Which services accounts should be patched             | `default`                          |
| env.CONFIG_ALLSERVICEACCOUNT   | Update all service accounts                           | `false`                            |
| env.CONFIG_EXCLUDED_NAMESPACES | Comma-separated list of namespaces to ignore          | `""`                               |
| env.CONFIG_LOOP_DURATION       | How often to query the namespaces                     | `10s`                              |
