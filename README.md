# argo-test

- The root application manifest uses 2 sources:
  - env/<env>/application.yaml (for apps)
  - stack/overlay/<env>/application.yaml (for infra)
- These 3 manifests create 3 total Argo Apps:
  - Root
  - App
  - Infra
-  The App/Infra application manifests use their own directory as the source path. These directory paths also contain a kustomization.yaml.
  - The App's kustomization points to the app-base directory who's kustomization file applies the K8s ens-user application manifests.
  - The Infra's kustomization points to the stack/base directory who's kustomization file applies infra K8s manifests (Grafana)
