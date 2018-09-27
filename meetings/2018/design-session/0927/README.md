# Ark Design Sessions: Backup & Volume Snapshot Locations

## Topic: Backup & Volume Snapshot Locations

# September 27, 9AM PT / 10AM MT / 12pm ET

Add your request or suggestion to our issue list: https://github.com/heptio/ark-community/issues

todo: link to video

## Intros

* [Steve Kriss](https://github.com/skriss)
* [Andy Goldstein](https://github.com/ncdc)
* [Nolan Brubaker](https://github.com/nrb)
* [Carlisia Pinto](https://github.com/carlisia)
* [Ross Kukulinski](https://github.com/rosskukulinski)
* [Wayne Witzel III](https://github.com/wwitzel3)
* [Jorge Castro](https://github.com/castrojo)

## Announcements

Thanks to our community contributors:

* @twforeman for the memory leak bug report
* @sachinar and @bashofmann for reporting issue causing restic restores not to work (#834)
* @james-powis for the PR to discard service account tokens from non-default service accounts on restore (#843)

Ark Office Hours in two weeks! 10/09

## Topic

* [Steve] demo of Backup Locations
* [Steve] talk about reorg of object storage
* Volume Snapshot Locations
  * [Nolan] overview of the feature
  * [Nolan] show API changes (slide deck and/or go code)
  * discuss Portworx as an example of how this is valuable (local vs. cloud snaps)
  * relation to replication
* tricky parts (e.g. copies across regions, knowing where to restore)
  * Snapshot copies can be slow because they require the source snapshot to be finished, and the copy itself can take time. We don't want this to block the backup/restore queue
  * hypothesis is that any cross-region copying should be done as part of replication, and backup/restore operations require that snapshots be directly restorable to the target region
  * if we're restoring into a different place than where we backed up from, how do we know which AZs the volumes should be created in?  Currently, we always create them in the same AZ that the source volumes existed in
* Also in 0.10: plugin rewrite. todo: add the two issues

### Q&A

## Heptio Ark Community

### [Ark on Kubernetes Slack](https://kubernetes.slack.com/messages/C6VCGP4MT)
### [Github](https://github.com/heptio/ark)
### [Ark Zenhub Project](https://github.com/heptio/ark#boards?repos=99143276)
### [Google Groups](https://groups.google.com/forum/#!forum/heptio-ark)
### [Ark Youtube Playlist](https://www.youtube.com/watch?v=5WTx8su8t_8&list=PLvmPtYZtoXOFxnW32NRcS8857A4novNVs)
### [Ark on Twitter](https://twitter.com/heptioark)
