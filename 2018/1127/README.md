# Heptio Ark 1.0 Discussion - 11/27/2018

You can find the video recording of this meeting [on YouTube](https://www.youtube.com/watch?v=Ml5lN4cV1Yk&list=PLvmPtYZtoXOFxnW32NRcS8857A4novNVs&index=4) 

Add your request, question or suggestion to [our issue list](https://github.com/heptio/velero-community/issues)

# Ark 1.0 / Roadmap discussion

## Agenda

- Team Intros
    - Steve Kriss
    - Andy Goldstein
    - Carlisia Pinto
    - Ross Kukulinski
    - Jennifer Rondeau
    - Nolan Brubaker
    - and Jorge Castro
- v0.11+
- 1.0
- 1.x
- Future

[All issues](https://docs.google.com/spreadsheets/d/1Y7eHB6-9a8VNWWvILYp748UEfSdjjEqSB5asbishTu0/edit#gid=0)

## Why 1.0?

We want to provide stability and compability for our users. Since our release in August 2017, we've made breaking changes, but with a 1.0 release we're making a commitment on future compatibility.

We're planning to get 1.0 out in Q1 2019. We may have a few point releases (v0.11, v0.12, etc) before then, likely starting in January.

Outstanding docs work is mostly decoupled from the code versions.

## 1.0 Features
- [Ark CLI, Server, & CRD Installation & upgrade mechanics #752](https://github.com/heptio/ark/issues/752)
    - [`ark install`, `ark upgrade` #52](https://github.com/heptio/ark/issues/52)
    - Support the Helm Chart - help maintain and take ownership of the Helm chart. Ensure it works with each new Ark version.
    - [Backup versioning #134](https://github.com/heptio/ark/issues/134)
    - [Policy on supported Kubernetes versions & features #596](https://github.com/heptio/ark/issues/596)
- Plugins
    - [Finalize naming](https://github.com/heptio/ark/issues/582)
    - [Finalize protobuf defintions & Go interfaces](https://github.com/heptio/ark/issues/602)
    - [Improve crash & error reporting](https://github.com/heptio/ark/issues/581)
    - [Name collision handling](https://github.com/heptio/ark/issues/583)
    - Q: How about lifecycle plugins? For example, post-backup hooks.
        - We've had discussions on this, but need to dig deeper.
        - For post-backup/restore hooks for now, users can write external components that watch the Backup/Restore objects and react to state changes.
    - Q: What about things like Kafka and ElasticSearch, which aren't file-based? These should be managed on the statefulset/deployment level, not necessarily individual pods.
        - We have some code for hooks on resources, but only pods are plumbed right now. Planned for calling to webhooks, but not implemented.
        - Maybe we could use annotations, too, as a way to exec into a pod or start a new pod to perform application-specific prep work. Needs further discussion.
- [Documentation overhaul #980](https://github.com/heptio/ark/issues/980)
- Finalize UI/UX for all commands
    - Ensure that flags and arguments are consistent.
    - Finalize how to specify inclusion/exclusion of resources, namespaces, etc.
    - Make sure each command has support for [VERB]/[NOUN] and [NOUN]/[VERB] ordering.
    - Possibly rework any commands that have been consistently confusing for users.
- Finalize API
    - CRDs
    - Public-facing Go packages
        - Dependencies clean up for plugin authors so they can ship smaller binaries. 
- [Multi-threaded backup & restore](https://github.com/heptio/ark/issues/487)
- Add CPU & memory requests/limits guidance
- [Backup data integrity](https://github.com/heptio/ark/issues/1072)
- [Additional backup metadata](https://github.com/heptio/ark/issues/396)
- Update Azure SDK to non-beta

## 1.x Features
- [Data-only restores](https://github.com/heptio/ark/issues/504)
- [Support restoring a PV into the same cluster](https://github.com/heptio/ark/issues/192)
- [Generic find/replace plugin for restores](https://github.com/heptio/ark/issues/474)
    - Could help with PVC resizing, changing storageclass, ...
- [Dry runs](https://github.com/heptio/ark/issues/448)
- [`ark debug` command](https://github.com/heptio/ark/issues/675)
- [Ability to keep backups from being garbage collected](https://github.com/heptio/ark/issues/251)
- Backup/restore progress [#20](https://github.com/heptio/ark/issues/20) [#21](https://github.com/heptio/ark/issues/21)
- [Backup ownership and sharing #726](https://github.com/heptio/ark/issues/726)

## Future Features
- [Replication](https://github.com/heptio/ark/issues/103)
- [Encryption at rest](https://github.com/heptio/ark/issues/434)
- [Support non-PVC volume snapshot/restore](https://github.com/heptio/ark/issues/408)
- [Git/other storage backend(s)](https://github.com/heptio/ark/issues/238)
- [Multi-tenancy](https://github.com/heptio/ark/issues/18)

## Questions from the Audience

*Michal Wieczorek*: Regarding v1.0 meeting: I won't be able to join online but I'd appreciate if you mention about any plans to extend metrics for ark (I don't see anything on google docs but my issues were created after the spreadsheet. 

- https://github.com/heptio/ark/issues/1059 - Post 1.x., may require more invasive changes, probably post 1.0 but not 2.0, inbetween somewhere. :D 
- https://github.com/heptio/ark/issues/1077 - Would be a good first issue for someone, we'll see what we can do.

*Ryan Anthony*: Backups across regions, currently using Azure. Where does this fall? 
Andy: Part of replication feature, there are cloud provider limitations, they don't let us take a snapshot and move it to another zone, you need to make a copy. We were hoping to do this in .10 but ended up splitting it into multiple epics. Phase 1 complete, it's extremely unlikely to make 1.0, but will come in 2019. 

*Justin Nauman*: This might be a place where we could shoehorn in a plugin, like a post-pod backup plugin hook, might be able to get the feature out-of-tree to prototype. 