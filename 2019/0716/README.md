# Velero Community Meeting - July 16, 2019

[Previous meeting notes](https://github.com/heptio/velero-community)

You can find the video recording of this meeting [on YouTube](https://www.youtube.com/watch?v=KQpinNZhFTI) 

Add your request, question or suggestion to [our issue list](https://github.com/heptio/velero-community/issues)

# Agenda
- ## What have we been working on?
    - [Tom] Velero User Survey
        - Launching soon!
    - [Tom] Velero CNCF Webinar
        - https://www.cncf.io/event/cncf-webinar-series-kubernetes-backup-and-migration-strategies-using-project-velero/
    - [Steve] plugin to remap storage classes on restore - demo
    - [Nolan] Our CSI support proposal is up! Please give us your feedback.
        - https://github.com/heptio/velero/pull/1661
    - [Steve] design proposal for running each backup/restore in its own worker pod - please provide feedback! (https://github.com/heptio/velero/pull/1653)
    - [Carlisia] Restic stuff:
        - 1) Adding the pod volume backup to object storage, have it synched, and use that as the backup source for pod volumes (as opposed to doing backups using the annotation on the pod): https://github.com/heptio/velero/issues/1169
        - 2) "add restic stale lock checking": https://github.com/heptio/velero/issues/1511
- ## What's coming up?
    - v1.1 release ~end of summer
- ## How can you get involved?
    - Let us know how you use Velero! https://github.com/heptio/velero/issues/1327
    - Good first issues: https://github.com/heptio/velero/labels/Good%20first%20issue
    - Other help wanted: https://github.com/heptio/velero/labels/Help%20wanted
    - Join us in slack (Kubernetes - [#velero](https://kubernetes.slack.com/messages/velero)) and help answer fellow users' questions!

- ## Contributor shoutouts!
    - @ThoTischner - better documenting requirements for using Velero + restic on OpenShift
    - @Prajyot-Parab - adding support for ppc64le
    - @jwmatthews - bug fix in `velero version` command
    - @tlkamp - add pod annotations flag to `velero install`

- ## Community questions:
    - None this week
