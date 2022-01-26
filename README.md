# Helmfile v0.143.0 reggression report

Simple example to reproduce reggression introduced in v0.143.0. It seems to be related to https://github.com/roboll/helmfile/pull/2026.

1. Installing [Helmfile v0.143.0](https://github.com/roboll/helmfile/releases/tag/v0.143.0)

1. The following commands succeeeds with no panic

    ```bash
    helmfile \
      --namespace dev1 \
      -l app=php,partial=false \
      template

    helmfile \
      --namespace dev1 \
      -l app=php,partial=true \
      template
    ```

1. But, this one never succeed and always get panic:

    ```bash
    helmfile \
      --namespace dev1 \
      -l app=ingress \
      template
    ```
