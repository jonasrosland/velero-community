# Velero Community Meeting - June 4, 2019

[Previous meeting notes](https://github.com/heptio/velero-community)

You can find the video recording of this meeting [on YouTube](https://youtu.be/0xTz-G-486c)

Add your request, question or suggestion to [our issue list](https://github.com/heptio/velero-community/issues)

# Agenda
- ## What have we been working on?
    - v1.1+ planning
        - prototype of integration with CSI snapshot API
            - Why? Support more volume providers "for free", hopefully improving the overall experience
            - Current goal is to test the waters, make sure we're compatible, and inform the future design
            - Intending to track the CSI snapshotting feature's state, so we'll start in alpha.
            - The plugins are hosted at https://github.com/heptio/velero-csi-plugin, and there's a design doc at https://github.com/heptio/velero-csi-plugin/blob/master/doc/design.md
        - restic improvements
            - https://hackmd.io/K7A0tw4sRPCLX_2psJLYmw
        - testing improvements
            - goal is to make tests more helpful and less of a maintenance burden for developers
            - start by focusing on unit tests in `pkg/backup`, `pkg/restore`
            - focus more on testing public interface/behavior, less on testing implementation details
            - first PR: https://github.com/heptio/velero/pull/1532
            - plan to look at KinD-based integration tests next

- ## What's coming up?

- ## How can you get involved?
    - Let us know how you use Velero! https://github.com/heptio/velero/issues/1327
    - Join us in slack (Kubernetes - [#velero](https://kubernetes.slack.com/messages/velero)) and help answer fellow users' questions!
    - Let us know what features you're interested in seeing in Velero 1.1+!

- ## Community questions:
