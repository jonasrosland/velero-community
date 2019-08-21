# Velero Community Meeting - August 20, 2019

[Previous meeting notes](https://github.com/heptio/velero-community)

You can find the video recording of this meeting [on YouTube](https://youtu.be/WsLjG3DUvlk) 

Add your request, question or suggestion to [our issue list](https://github.com/heptio/velero-community/issues)

# Agenda
- ## What have we been working on?
    - v1.1-beta.x bug fixes - thanks for help from testers!
    - [steve] https://github.com/heptio/velero/issues/192 - clone PV when remapping namespace
    - [Nolan] https://github.com/heptio/velero/pull/1748 - Properly set namespace for invoking in-tree plugins
    - [Carlisia] #vmwarecodehouse + Article about Velero
- ## What's coming up?
    - v1.1 release - targeting Thursday
    - [v1.2 scope definition](https://github.com/heptio/velero#workspaces/velero-5c59c15e39d47b774b5864e3/board?milestones=v1.2%232019-10-31&filterLogic=any&repos=99143276&showPipelineDescriptions=false) in progress
        - continued work to bring restic integration to GA
        - CSI snapshot integration
        - move existing cloud provider plugins out of tree
        - R&D for encryption at rest
        - feature flags
    - we're moving to monthly community meetings! (1st Tuesdays)
- ## How can you get involved?
    - User survey closing soon! https://velero.io/survey
    - Join us in slack (Kubernetes - [#velero](https://kubernetes.slack.com/messages/velero)) and help answer fellow users' questions!

- ## Contributor shoutouts!
    - @betta1 - include object storage prefix in backup storage location map of config data
    - Nicolas Kowenski - documentation fix for helm install commands
    - @code-chris - docs fix for port-forwarding commands
    - Dylan Murray and Scott Seago - testing beta.1 and finding bugs!
- ## Community questions:
    - None this week


