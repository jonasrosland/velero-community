# Velero Community Meeting - May 7, 2019

[Previous meeting notes](https://github.com/heptio/velero-community)

You can find the video recording of this meeting [on YouTube](https://youtu.be/WlhRJLwe_Qk)

Add your request, question or suggestion to [our issue list](https://github.com/heptio/velero-community/issues)

# Agenda
- ## What have we been working on?
    - v1.0.0-beta.1 is out!
        - https://github.com/heptio/velero/releases/tag/v1.0.0-beta.1
        - Add PartiallyFailed phase for restores (#1389, @skriss)
        - Add PartiallyFailed phase for backups, log + continue on errors during backup process (#1386, @skriss)
        - Switch from restic stats to restic snapshots for checking restic repository existence (#1416, @skriss)
        - Disallow bucket names starting with '-' (#1407, @nrb)
        - Shorten label values when they're longer than 63 characters (#1392, @anshulc)
        - Fail backup if it already exists in object storage. (#1390, @ncdc,carlisia)
        - Install command: Use latest image tag if no version information is provided at build time (#1439, @nrb)
        - GCP: add optional 'project' config to volume snapshot location for if snapshots are in a different project than the IAM account (#1405, @skriss)
        - Azure: restore disks with zone information if it exists (#1298, @sylr)
        - Replace config/ with examples/ in release tarball (#1406, @skriss)
    - restic integration will be "beta" as of v1.0.
    - stabilizing and updating of the Helm chart
        - CI/CD fixes
        - CRD fixes
        - Azure secret changes (using a secrets file instead of environment variables)
- ## What's coming up?
    - v1.0.0 GA release - May 21
        - Upgrade process -- https://heptio.github.io/velero/v1.0.0-beta.1/upgrade-to-1.0
    - Post-1.0 planning
        - CSI snapshot integration
        - bringing restic integration to GA
        - much more
- ## How can you get involved?
    - Let us know how you use Velero! https://github.com/heptio/velero/issues/1327
    - Join us in slack (Kubernetes - [#velero](https://kubernetes.slack.com/messages/velero)) and help answer fellow users' questions!
    - Let us know what features you're interested in seeing in Velero 1.1+!

- ## Contributor shoutouts!
    - @sylr - add support for Azure AZ disks
    - @fabito - add validation to `velero backup download` command

- ## Community questions:
    - None during meeting. See you in a couple of weeks!
