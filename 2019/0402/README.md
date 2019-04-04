# Velero Community Meeting - April 2, 2019

You can find the video recording of this meeting [on YouTube](https://www.youtube.com/watch?v=nc48ocI-6go) 

Add your request, question or suggestion to [our issue list](https://github.com/heptio/velero-community/issues)

Agenda
- what have we been working on?
    - steve: quick big-picture recap
    - nrb: Adding an `install` command for simple use cases.
        - Still need to test with Azure
        - Also fleshing out the `install` package for programmatic access
        - Will also start getting more involved in the Helm chart once the command work is mostly done.
    - carlisia & steve: plugins work
        - Changes to the interface and smaller dependency foot print
        - Spruced up examples
        - Velero will now hault if there's a mismatch between the plugin and Velero versions
        - Velero now checks and doesn't allow duplicate plugin names 
        - BlockStore is now VolumeSnapshotter
        - Error improvements: stack traces so we know error location from within the plugin
        - Restore plugin interface now adds original, unmodified item
        - Velero passes metadata to plugins (wip)
        - Enable/disable plugins (wip)
- what's coming up?
    - v1.0 - May timeframe
        - [ZenHub board](https://app.zenhub.com/workspaces/velero-5c59c15e39d47b774b5864e3/boards?repos=99143276)
        - closing out the in-flight items from above, plus as many UX and stability bugs as we can get to
        - steve: rationalizing phases & warning/error reporting
            - https://github.com/heptio/velero/issues/286

- Update from Red Hat - @dymurray
    - Submitted PRs upstream around plugin development updates
    - Submitting PRs to Restic to decrease downtime restoring PVs
    - Primarily focused on OCP specific backup/restore functions
        - https://github.com/fusor/ocp-velero-plugin
- how can you get involved?
    - we need help with v1.0 pre-release testing!
    - if you're interested in...
        - Azure
            - help test AZ disks support: https://github.com/heptio/velero/pull/1298 
            - support for German cloud: https://github.com/heptio/velero/issues/287
            - support using storage account keys in addition to service principal: https://github.com/heptio/velero/issues/1165
            - support certificates for service principals: https://github.com/heptio/velero/issues/1289
        - GCE/GKE:
            - support cross-project snapshot restores: https://github.com/heptio/velero/issues/1268
        - restic: 
            - don't error on empty volumes: https://github.com/heptio/velero/issues/1266
            - bug fix: first backup in a namespace fails: https://github.com/heptio/velero/issues/1078
        - debuggability / supportability:
            - create `velero debug` command: https://github.com/heptio/velero/issues/675 
            - improve instructions to user when something goes wrong: https://github.com/heptio/velero/issues/305
        - metrics:
            - add last successful backup timestamp metric: https://github.com/heptio/velero/issues/1136
            - add gauge metrics for number of backups/restores that exist: https://github.com/heptio/velero/issues/1077
        - general:
            - handle long restore names gracefully: https://github.com/heptio/velero/issues/1021
            - support not-equal operator in label selectors: https://github.com/heptio/velero/issues/1218
            - join us in slack (Kubernetes - #velero) and help answer fellow users' questions!
- Contributor shoutouts!
    - @mwieczorek - pass original item to restore item action plugins
    - @asaf-erlich - don't keep every file open during restore tarball extraction
    - @tsturzl - AWS - use AZ in volume ID during snapshot restore
    - @pei0804 - compile regexp only once
    - @mstump - AWS - set Encrypted field when restoring snapshot to avoid IAM issues
    - @fabito - gracefully handle failed API groups from discovery
- let us know how you use Velero! https://github.com/heptio/velero/issues/1327
- Community questions:
    - Can we do multiple backups at once?
        - Currently brainstorming on options for this, including a pod or job per backup.
            - Something we want to tackle soon after 1.0
    - What about CSI?
        - The team hasn't been directly engaged, but we're going to be.
            - Long term, we'll likely want to support both Velero and CSI plugins, and even longer term, just CSI.
