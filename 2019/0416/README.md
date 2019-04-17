# Velero Community Meeting - April 16, 2019

[Previous meeting notes](https://github.com/heptio/velero-community)

You can find the video recording of this meeting [on YouTube](https://youtu.be/35FIMxm2rGI)

Add your request, question or suggestion to [our issue list](https://github.com/heptio/velero-community/issues)

# Agenda
- ## What have we been working on?
    - [first v1.0.0 alpha](https://github.com/heptio/velero/releases/tag/v1.0.0-alpha.1)!
        - container image: `gcr.io/heptio-images/velero:v1.0.0-alpha.1`
    - [Steve] revisions to backup/restore phases
        - https://github.com/heptio/velero/issues/1371
    - [Nolan] wrapping up install command and reviewing the v0.11.0 Helm chart
    - [Carlisia] Plugin name collision and protobuf refactoring
- ## What's coming up?
    - remaining must-have items for v1.0: https://github.com/heptio/velero/issues?utf8=%E2%9C%93&q=is%3Aopen+label%3A%22P1+-+Important%22++milestone%3Av1.0.0
- ## How can you get involved?
    - Let us know how you use Velero! https://github.com/heptio/velero/issues/1327
    - Join us in slack (Kubernetes - [#velero](https://kubernetes.slack.com/messages/velero)) and help answer fellow users' questions!
    - Test out v1.0.0 alpha!
        - Plugins interfaces have changed - try them out! (See https://github.com/heptio/velero-plugin-example/)
        - Try the install command (See https://github.com/heptio/velero/pull/1376 for in-progress docs)
        - Try the updated Helm chart (https://github.com/helm/charts/pull/12031)
        - Backups made prior to v0.11.0 are not supported
            - Migration support coming in v0.11.1 (https://github.com/heptio/velero/pull/1360)

- ## Contributor shoutouts!
    - @amanw / James King - disable specific controllers via CLI flag
    - @ipochi - update docs for restic + RancherOS
    - @sseago - allow restore item actions to skip restoring an item
    - @fabito - add prometheus metrics for backup deletion
    - @faiq - add notice that current plugin examples are for master, not v0.11.0
    - @josephgorse - working on the v0.11.0 Helm chart rename
